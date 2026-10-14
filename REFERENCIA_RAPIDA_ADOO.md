# Referencia Rápida - Análisis y Diseño Orientado a Objetos

## Acrónimos y Conceptos Clave

### GRASP (9 Patrones)
1. **EI** - Experto en Información: Quien tiene la información → responsabilidad
2. **C** - Creador: Quien contiene/usa → crear instancias
3. **CO** - Controlador: Representante sistema/caso uso → manejar eventos
4. **BAC** - Bajo Acoplamiento: Minimizar dependencias
5. **AC** - Alta Cohesión: Responsabilidades relacionadas
6. **P** - Polimorfismo: Usar tipos para variaciones
7. **I** - Indirección: Intermediario para desacoplar
8. **FP** - Fabricación Pura: Clase auxiliar artificial
9. **VP** - Variaciones Protegidas: Interfaces estables en puntos variables

### SOLID
- **S** - Single Responsibility Principle (SRP)
- **O** - Open/Closed Principle (OCP)
- **L** - Liskov Substitution Principle (LSP)
- **I** - Interface Segregation Principle (ISP)
- **D** - Dependency Inversion Principle (DIP)

### Otros Principios
- **YAGNI** - You Aren't Gonna Need It (no lo vas a necesitar)
- **DRY** - Don't Repeat Yourself (no te repitas)
- **KISS** - Keep It Simple, Stupid (mantén simple)
- **LSP** - Liskov Substitution Principle
- **OCP** - Open/Closed Principle
- **IoC** - Inversion of Control (Principio Hollywood)
- **DIP** - Dependency Inversion Principle
- **LSP** - Ley de Demeter (Law of Demeter)

---

## Enfoques de Clasificación

| Enfoque | Características | Limitación |
|---------|-----------------|-----------|
| **Categorización Clásica** | Propiedades necesarias y suficientes | Excepciones naturales |
| **Agrupación Conceptual** | Conceptos difusos, probabilísticos | Menos riguroso |
| **Teoría de Prototipos** | Parecidos de familia, semejanzas | Flexible para dominios complejos |

---

## Relaciones entre Clases

### Colaboración
```
┌─ Composición/Agregación (tiene un)
│  ├─ Composición: Fuerte (comparten ciclo de vida)
│  └─ Agregación: Débil (independientes)
│
├─ Asociación (usa los servicios de)
│  └─ Cliente/Servidor permanentes
│
└─ Dependencia (uso)
   └─ Más débil que composición

Jerarquía
└─ Herencia (es un)
   └─ Transmisión de miembros públicos y privados
```

### Características de Relación
- **Visibilidad**: Privada vs Pública
- **Temporalidad**: Breve vs Indefinida
- **Versatilidad**: Intercambiable vs Fija

---

## Guía de Asignación de Responsabilidades (GRASP)

```
¿Quién debería...?

├─ ...tener esta responsabilidad?
│  └─ → Experto en Información (quien tiene datos)
│
├─ ...crear nuevas instancias?
│  └─ → Creador (quien contiene/usa/registra)
│
├─ ...manejar eventos del sistema?
│  └─ → Controlador (representante de sistema/caso uso)
│
├─ ...minimizar dependencias?
│  └─ → Bajo Acoplamiento (depender de abstracciones)
│
├─ ...mantener responsabilidades enfocadas?
│  └─ → Alta Cohesión (relacionadas entre sí)
│
├─ ...manejar comportamientos variables?
│  └─ → Polimorfismo (tipos en que varía)
│
├─ ...reducir acoplamiento con intermediario?
│  └─ → Indirección (clase intermediaria)
│
├─ ...apoyar cohesión y acoplamiento sin conceptos dominio?
│  └─ → Fabricación Pura (clase auxiliar artificial)
│
└─ ...proteger de variaciones futuras?
   └─ → Variaciones Protegidas (interfaces estables)
```

---

## Checklist de Código Limpio

### Formato
- [ ] Líneas de código separadas en bloques lógicos
- [ ] Atributos al principio de la clase
- [ ] Funciones que se llaman entre sí están cerca
- [ ] Líneas entre 40-120 caracteres
- [ ] Sangría consistente

### Nombrado
- [ ] Nombres revelan intención
- [ ] Pronunciables
- [ ] Del dominio del problema
- [ ] Consistencia: una palabra por concepto
- [ ] CamelCase
- [ ] Sin notación Húngara
- [ ] Sin nombres de una letra (excepto i, j, k en bucles)
- [ ] Sin acrónimos

### Estándares
- [ ] Equipo usa estándar único
- [ ] Convenciones consistentes
- [ ] Código como documento vivo

---

## Checklist de Diseño de Métodos

### Interfaz
- [ ] Suficiente: Exactamente necesarios
- [ ] Completa: Todas las operaciones
- [ ] Primitiva: No redundantes

### Cohesión
- [ ] Hace una sola cosa
- [ ] Todas las líneas enfocadas en ese propósito
- [ ] Reutilizable en otros contextos

### Respuesta
- [ ] Comportamiento como espera el cliente
- [ ] Minimiza sorpresas
- [ ] Consistencia con otros métodos

---

## Checklist de Diseño de Clases

### Responsabilidad
- [ ] ¿Un único motivo de cambio?
- [ ] ¿Si hay múltiples razones, separar?
- [ ] ¿Responsabilidades relacionadas?

### Cohesión
- [ ] ¿Métodos y atributos relacionados?
- [ ] ¿Baja cohesión → separar?
- [ ] ¿Cada método contribuye al propósito?

### Acoplamiento
- [ ] ¿Depende de abstracciones o concretos?
- [ ] ¿Conoce solo lo necesario?
- [ ] ¿Cambia en otros lugares si cambio?

### Violaciones Comunes
- [ ] ¿Clases grandes? → Dividir
- [ ] ¿Clases perezosas? → Eliminar o fusionar
- [ ] ¿Solo getters/setters? → Agregar comportamiento
- [ ] ¿Cambios en muchos lugares? → Acoplamiento alto
- [ ] ¿Atributos nunca usados? → Responsabilidades múltiples

---

## Checklist de Herencia

### ¿Usar Herencia?
- [ ] ¿Pasa test ISA? (¿es un?)
- [ ] ¿Especialización de características?
- [ ] ¿LSP será respetado?
- [ ] ¿No cambiarán tipos en ejecución?

### ¿Usar Composición en su lugar?
- [ ] ¿El tipo puede cambiar en ejecución?
- [ ] ¿Necesitas solo algunas operaciones?
- [ ] ¿Violaría LSP?

### Reglas
- [ ] Precondiciones más débiles en subclases
- [ ] Postcondiciones más fuertes en subclases
- [ ] Sin instanceof/RTTI
- [ ] Subclases realmente sustituibles

---

## Principios de Diseño de Paquetes

### Cohesión (Las 3 primeras)
| Principio | Significado | Beneficio |
|-----------|------------|----------|
| **REP** | Release/Reuse equivalence | Paquetes liberados reutilizables |
| **CCP** | Common Closure | Cambios afectan pocos paquetes |
| **CRP** | Common Reuse | Clases usadas juntas, empaquetadas juntas |

### Acoplamiento (Las 3 últimas)
- **ADP** - Acyclic Dependencies: Sin ciclos
- **SDP** - Stable Dependencies: Depender de estables
- **SAP** - Stable Abstractions: Lo abstracto es estable

---

## Cuándo Aplicar Cada Principio

### SIEMPRE
- SRP - Única Responsabilidad
- Alta Cohesión
- Bajo Acoplamiento
- Código Limpio (formato, nombrado)

### CUANDO SEA NECESARIO (no especulativo)
- Polimorfismo - cuando hay variación real
- Variaciones Protegidas - cuando hay cambio probable
- OCP - cuando hay cambios frecuentes
- DIP - cuando hay acoplamiento alto

### NUNCA (Anti-patrones)
- Código duplicado (DRY)
- Funcionalidad innecesaria (YAGNI)
- Complejidad innecesaria (KISS)
- Violación de LSP en herencia
- Clases god (múltiples responsabilidades)

---

## Decisiones de Diseño Comunes

### "¿Qué clase debería hacer X?"
1. ¿Quién tiene la información? → **Experto**
2. ¿Quién contiene/usa? → **Creador**
3. ¿Si hay bajo acoplamiento? → **Indirección**
4. ¿Si no existe en dominio? → **Fabricación Pura**

### "¿Herencia o Composición?"
1. ¿Pasa ISA? NO → **Composición**
2. ¿Cambio dinámico? SÍ → **Composición**
3. ¿LSP se respeta? NO → **Composición**
4. Si todas las condiciones se cumplen → **Herencia**

### "¿Cuándo refactorizar?"
1. Cambio divergente → SRP
2. Cirugía a escopetazos → Bajo Acoplamiento
3. Métodos largos → Cohesión de Métodos
4. Duplicación → DRY
5. Clases grandes → Dividir responsabilidades

---

## Proceso de Análisis y Diseño

```
1. ANÁLISIS
   ├─ Entender dominio del problema
   ├─ Aplicar enfoques de clasificación
   ├─ Identificar clases candidatas
   ├─ Definir relaciones (ISA, tiene un, usa)
   └─ Documentar responsabilidades

2. DISEÑO
   ├─ Aplicar GRASP para asignaciones
   ├─ Asegurar alta cohesión
   ├─ Minimizar acoplamiento
   ├─ Escribir código limpio
   ├─ Considerar herencia vs composición
   └─ Organizar en paquetes

3. IMPLEMENTACIÓN
   ├─ Seguir estándares de equipo
   ├─ Aplicar principios SOLID
   ├─ Escribir tests
   └─ Refactorizar iterativamente

4. EVOLUCIÓN
   ├─ Monitorear cambios
   ├─ Aplicar refactorización
   └─ Mantener principios
```

---

## Máximas a Recordar

> "Una línea de código se escribe una vez y se lee cientos de veces"
> — Cox

> "No te repitas"
> — DRY Principle

> "No lo vas a necesitar"
> — YAGNI

> "Mantén simple"
> — KISS

> "Una clase, una responsabilidad"
> — SRP

> "Abierto a extensión, cerrado a modificación"
> — OCP

> "Los subtipos deben ser sustituibles por sus supertipos"
> — LSP

> "Depende de abstracciones, no de concretos"
> — DIP

---

## Referencias Cruzadas Rápidas

**Si tienes problema con...**
- Métodos largos → Cohesión de Métodos
- Clases grandes → Única Responsabilidad
- Muchas dependencias → Bajo Acoplamiento, Inyección
- Condicionales complejos → Polimorfismo
- Reutilización difícil → Alta Cohesión, Bajo Acoplamiento
- Cambios en cascada → Inversión de Dependencias
- Código repetido → DRY
- Complejidad innecesaria → YAGNI, KISS
- Interfaz confusa → Nombrado, Interfaz Suficiente/Completa
- Jerarquías rotas → LSP, Herencia vs Composición

---

**Documento de Referencia Rápida**
*Para consulta rápida durante diseño e implementación*
