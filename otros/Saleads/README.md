# 📌 Saleads - Sistema de Drafts

Documentación completa sobre el sistema de **Drafts** (borradores de leads) en Saleads.

## 📚 Documentos Incluidos

### 1. [[1. Draft en Saleads|📖 Definición de Draft]]
**¿Qué es un Draft?**
- Definición y concepto
- Cuándo un lead es DRAFT
- Ciclo de vida del lead
- Estados del lead en el sistema
- Impacto en reportes

### 2. [[2. Draft API y Componentes|🔧 API y Componentes]]
**Implementación técnica**
- Tipos de datos (DTOs)
- Endpoints REST detallados
- Componentes React
- Hooks (useDraft)
- Validaciones
- Flujo en UI

### 3. [[3. Ejemplo Práctico - Draft Workflow|🎬 Flujo Completo]]
**Caso de uso real paso a paso**
- Crear un draft
- Editar información
- Validar datos
- Confirmar y activar
- Cambios en BD
- Impacto en dashboard

### 4. [[4. Arquitectura de Draft|🏗️ Arquitectura]]
**Estructura de capas**
- Diagrama de arquitectura
- Flujo de datos detallado
- Ciclo de estados
- Endpoints mapeados
- Autenticación/Autorización
- Manejo de errores
- Estrategia de caché

### 5. [[5. Resumen y Checklist|✅ Resumen y Checklist]]
**Guía rápida y checklist**
- Resumen ejecutivo
- Casos de uso
- API endpoints principales
- Estructura de datos
- Validaciones
- Checklist de implementación

---

## 🎯 Quick Reference

### ¿Qué es un DRAFT?
```
🟡 DRAFT = Lead incompleto o sin validar
         = No está en pipeline activo
         = Requiere completitud 100% para confirmar
         = No cuenta en reportes
```

### Estados del Lead
```
DRAFT 🟡 → ACTIVO 🟢 → CALIFICADO 🔵 → OPORTUNIDAD → GANADO ✅
  ↓ (opcional)
  └─────────────────── PERDIDO ❌ ──────────────┘
```

### Campos Obligatorios
```
✓ Nombre
✓ Email
✓ Empresa

❌ = Draft (falta información)
✅ = Activo (completo, listo)
```

### Validaciones Automáticas
```
Email:    Formato válido + NO duplicado
Teléfono: Formato de país correcto
Empresa:  No vacío
Duplicado: Busca en BD si existe similar
```

---

## 🔧 Endpoints Clave

| Método | Endpoint | Acción |
|--------|----------|--------|
| **POST** | `/api/drafts` | Crear draft |
| **GET** | `/api/drafts` | Listar drafts |
| **PUT** | `/api/drafts/{id}` | Editar draft |
| **POST** | `/api/drafts/{id}/confirm` | Confirmar y activar |
| **DELETE** | `/api/drafts/{id}` | Descartar |

---

## 🏗️ Arquitectura

```
┌──────────────┐
│ UI Component │ (React)
└──────┬───────┘
       │
┌──────▼───────┐
│ useDraft Hook│ (State Management)
└──────┬───────┘
       │
┌──────▼───────┐
│ Service      │ (Business Logic)
└──────┬───────┘
       │
┌──────▼───────┐
│ API Client   │ (HTTP)
└──────┬───────┘
       │
┌──────▼───────┐
│ Backend API  │ (Express)
└──────┬───────┘
       │
┌──────▼───────┐
│ Database     │ (MongoDB)
└──────────────┘
```

---

## 📊 Flujo Principal

```
1. USUARIO ACCEDE A DRAFTS
   ├─ Ve lista de leads incompletos
   ├─ Muestra completitud de cada uno
   └─ Opciones: Editar, Confirmar, Descartar

2. USUARIO EDITA DRAFT
   ├─ Llena campos faltantes
   ├─ Validación en tiempo real
   ├─ Calcula completitud automáticamente
   └─ Guarda cambios (PUT)

3. USUARIO CONFIRMA DRAFT
   ├─ Modal de confirmación
   ├─ Verifica completitud = 100%
   ├─ Asigna vendedor
   ├─ Selecciona fuente
   └─ Confirma (POST /confirm)

4. LEAD ACTIVADO
   ├─ Estado: DRAFT → ACTIVO
   ├─ Entra al pipeline
   ├─ Aparece en reportes
   └─ Se asigna a vendedor
```

---

## 💾 Estructura de Datos

```typescript
{
  id: "DRAFT-2025-001",
  estado: "draft",
  datos: {
    nombre: "Carlos López",      ✓ Requerido
    email: "carlos@empresa.com", ✓ Requerido
    empresa: "TechCorp",         ✓ Requerido
    telefono: "+34 912345678",   - Opcional
    cargo: "Director TI",        - Opcional
    vendedorAsignado: "USR-456", - Al confirmar
    fuente: "LinkedIn"           - Al confirmar
  },
  completitud: 60,               // 0-100%
  createdAt: "2025-01-20T10:30:00Z",
  updatedAt: "2025-01-20T11:15:00Z"
}
```

---

## ✅ Validaciones

### Lado Cliente (Tiempo Real)
- ✓ Email: formato válido
- ✓ Teléfono: formato internacional
- ✓ Campos obligatorios: no vacíos
- ✓ Completitud: se actualiza dinámicamente

### Lado Servidor
- ✓ Token válido (autenticación)
- ✓ Todos los campos validados
- ✓ Búsqueda de duplicados
- ✓ Verificación de permisos
- ✓ Cálculo de completitud

---

## 🔐 Permisos

| Rol | Ver | Editar | Confirmar |
|-----|-----|--------|-----------|
| **Creador** | ✅ | ✅ | ✅ |
| **Admin** | ✅ | ✅ | ✅ |
| **Vendedor** | ✅ | ❌ | ❌ |
| **Otros** | ❌ | ❌ | ❌ |

---

## 📈 Impacto en Sistema

### Drafts NO afectan:
- Pipeline total de leads
- Estadísticas de vendedores
- Tasas de conversión
- Reportes de leads activos

### Drafts SÍ afectan:
- Cantidad "En Revisión"
- Tasa de confirmación
- Tiempo en estado draft

---

## 🚀 Próximos Pasos

1. **Leer la definición**: Empieza por [[1. Draft en Saleads]]
2. **Entender la API**: Revisa [[2. Draft API y Componentes]]
3. **Ver ejemplo real**: Estudia [[3. Ejemplo Práctico - Draft Workflow]]
4. **Arquitectura**: Comprende [[4. Arquitectura de Draft]]
5. **Implementar**: Usa [[5. Resumen y Checklist]]

---

## ❓ Preguntas Frecuentes

**P: ¿Qué es un DRAFT?**
R: Un lead incompleto que no está en el pipeline activo.

**P: ¿Cuándo se confirma un DRAFT?**
R: Cuando tiene completitud del 100% (todos campos requeridos).

**P: ¿Qué pasa al confirmar?**
R: El DRAFT se convierte en ACTIVO y entra al pipeline de ventas.

**P: ¿Se ve en reportes?**
R: No, solo cuando está ACTIVO.

**P: ¿Quién puede confirmar?**
R: El creador o un administrador.

**P: ¿Se puede descartar un DRAFT?**
R: Sí, sin ningún impacto en el sistema.

---

## 📞 Contacto/Soporte

Para preguntas o clarificaciones:
- Revisar documentación completa
- Consultar ejemplos prácticos
- Contactar con team

---

**Última actualización**: 2025-01-20
**Versión**: 1.0
**Estado**: ✅ Completo
