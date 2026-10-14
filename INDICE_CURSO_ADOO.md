# Índice del Curso - Análisis y Diseño Orientado a Objetos

## Documentos del Curso

Este índice sirve como punto de entrada para navegar todos los materiales del curso de Análisis y Diseño Orientado a Objetos (ADOO).

### 1. Documentos de Resumen

#### [RESUMEN_CURSO_ADOO.md](RESUMEN_CURSO_ADOO.md)
**Resumen Comprensivo del Curso**
- Documento principal con todo el contenido del curso
- 843 líneas, ~29 KB
- Estructura: Introducción → Conceptos → Análisis → Relaciones → GRASP → Diseño → Conclusión
- **Uso**: Lectura completa del curso, referencia en profundidad

#### [REFERENCIA_RAPIDA_ADOO.md](REFERENCIA_RAPIDA_ADOO.md)
**Referencia Rápida para Consulta**
- Checklists y tablas de referencia rápida
- 288 líneas, ~9 KB
- **Uso**: Consulta durante implementación, tomar decisiones rápidas

---

## Estructura del Curso Completo

### SECCIÓN 1: FUNDAMENTOS

#### Tema 1: Conceptos Preliminares
- Dominio del Problema vs. Solución del Problema
- Modelo del Dominio vs. Lógica de Negocio
- **Archivos relacionados en bóveda**:
  - `Escuela_IT/otros/Dominio y solucion del problema.md`
  - `Escuela_IT/otros/Logica de negocio y modelo del dominio.md`

#### Tema 2: Enfoques de Clasificación
1. **Categorización Clásica**
   - Propiedades necesarias y suficientes
   - Excepciones naturales
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/1. Enfoques de clasificacion/1. Categorizacion clasica.md`

2. **Agrupación Conceptual**
   - Conceptos difusos
   - Clasificación probabilística
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/1. Enfoques de clasificacion/2. Agrupacion conceptual.md`

3. **Teoría de Prototipos**
   - Parecidos de familia
   - Prototipos representativos
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/1. Enfoques de clasificacion/3. Teoria de prototipos.md`

---

### SECCIÓN 2: ANÁLISIS DE CLASES

#### Tema 3: Identificación de Clases

##### Estrategias
1. Descripción Normal (Método Abbott)
2. Análisis Clásico
3. Análisis del Dominio
4. Análisis del Comportamiento
5. Análisis de Casos de Uso

**Archivos**:
- `Escuela_IT/Analisis/Identificar clases/4. Estratejias de clasificacion/1. Descripcion Normal.md`
- `Escuela_IT/Analisis/Identificar clases/4. Estratejias de clasificacion/2. Analisis clasico.md`
- `Escuela_IT/Analisis/Identificar clases/4. Estratejias de clasificacion/3. Analisis del dominio.md`
- `Escuela_IT/Analisis/Identificar clases/4. Estratejias de clasificacion/4. Analisis del comportamiento.md`
- `Escuela_IT/Analisis/Identificar clases/4. Estratejias de clasificacion/5. Analisis de casos de uso.md`

---

### SECCIÓN 3: RELACIONES ENTRE CLASES

#### Tema 4: Tipos de Relaciones

1. **Composición/Agregación** ("tiene un")
   - Composición fuerte (ciclo de vida compartido)
   - Agregación débil (independientes)
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/3. Relacion entre clases/3. Relacion de composicion - agregacion.md`

2. **Asociación** ("usa servicios de")
   - Cliente/Servidor
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/3. Relacion entre clases/4. Relacion de asociacion.md`

3. **Dependencia** ("usa")
   - Forma débil de relación
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/3. Relacion entre clases/5. Relacion de dependencia (uso).md`

4. **Herencia** ("es un")
   - Transmisión de miembros
   - Regla ISA
   - Generalización/Especialización
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/3. Relacion entre clases/7. Relacion de herencia.md`

#### Características de Relaciones
- Visibilidad
- Temporalidad
- Versatilidad
- **Archivo**: `Escuela_IT/Analisis/Identificar clases/3. Relacion entre clases/2. Caracteristicas de la relacion entre clases.md`

---

### SECCIÓN 4: PRINCIPIOS GRASP

#### Tema 5: Patrones GRASP (9 principios)

Directrices para asignar responsabilidades en el diseño orientado a objetos.

**Archivo principal**: `Escuela_IT/Analisis/Identificar clases/2. Clases de analisis/GRASP/1. GRASP.md`

#### Los 9 Principios GRASP

1. **Experto en Información**
   - Asignar a quien tiene la información
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/2. Clases de analisis/GRASP/2. Experto en la informacion.md`

2. **Creador**
   - Asignar creación a quien contiene/usa
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/2. Clases de analisis/GRASP/7. Creador.md`

3. **Controlador**
   - Manejar eventos del sistema
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/2. Clases de analisis/GRASP/6. Controlador.md`

4. **Bajo Acoplamiento**
   - Minimizar dependencias
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/2. Clases de analisis/GRASP/4. Bajo Acoplamiento.md`

5. **Alta Cohesión**
   - Responsabilidades relacionadas
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/2. Clases de analisis/GRASP/3. Alta cohesion.md`

6. **Polimorfismo**
   - Usar tipos para manejar variaciones
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/2. Clases de analisis/GRASP/9. Polimorfismo.md`

7. **Indirección**
   - Intermediario para desacoplar
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/2. Clases de analisis/GRASP/8. Indireccion.md`

8. **Fabricación Pura / Invención Pura**
   - Clases auxiliares artificiales
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/2. Clases de analisis/GRASP/5. Invension Pura.md`

9. **Variaciones Protegidas**
   - Interfaces estables en puntos variables
   - **Archivo**: `Escuela_IT/Analisis/Identificar clases/2. Clases de analisis/GRASP/10. Variaciones Protegidas.md`

---

### SECCIÓN 5: CÓDIGO LIMPIO

#### Tema 6: Fundamentos de Código Limpio

1. **Respetar Estándares**
   - Convenciones del equipo
   - **Archivo**: `Escuela_IT/Diseño/1. Codigo limpio/1. Respetar estandares de codigo limpio.md`

2. **Formato de Código**
   - Organización lógica
   - Sangría y espaciado
   - **Archivo**: `Escuela_IT/Diseño/2. Diseño general/1. Formato de codigo limpio.md`

3. **Nombrado**
   - Nombres que revelan intención
   - Convenciones por tipo
   - **Archivo**: `Escuela_IT/Diseño/2. Diseño general/3. Nombrado del codigo limpio.md`

4. **Comentarios**
   - Cuándo usar comentarios
   - **Archivo**: `Escuela_IT/Diseño/2. Diseño general/2. Comentarios de codigo limpio.md`

5. **Descomposición Funcional**
   - Separación de responsabilidades
   - **Archivo**: `Escuela_IT/Diseño/2. Diseño general/4. Descomposicion funcional.md`

---

### SECCIÓN 6: PRINCIPIOS GENERALES DE DISEÑO

#### Tema 7: Principios Ágiles y Pragmáticos

1. **YAGNI** (You Aren't Gonna Need It)
   - No implementar funcionalidad innecesaria
   - **Archivo**: `Escuela_IT/Diseño/2. Diseño general/6. Principio no vas ha necesitarlo YAGNI.md`

2. **DRY** (Don't Repeat Yourself)
   - No duplicar lógica
   - **Archivo**: `Escuela_IT/Diseño/2. Diseño general/7. Principio No te repitas DRY.md`

3. **KISS** (Keep It Simple, Stupid)
   - Mantener simple
   - **Archivo**: `Escuela_IT/Diseño/2. Diseño general/8. Principio KISS.md`

4. **Código Muerto**
   - Eliminar código no usado
   - **Archivo**: `Escuela_IT/Diseño/2. Diseño general/5. Anti patron Codigo Muerto.md`

---

### SECCIÓN 7: DISEÑO DE MÉTODOS

#### Tema 8: Principios de Métodos

1. **Interfaz Suficiente, Completa y Primitiva**
   - Diseño de interfaces de métodos
   - **Archivo**: `Escuela_IT/Diseño/3. Diseño de Metodos/1. Interfaz suficiente completa y primitiva.md`

2. **Principio de Menor Compromiso**
   - Mínima sorpresa
   - **Archivo**: `Escuela_IT/Diseño/3. Diseño de Metodos/2. Principio del menor compromiso o Minima sorpresa.md`

3. **Cohesión de Métodos**
   - Métodos con una única responsabilidad
   - **Archivo**: `Escuela_IT/Diseño/3. Diseño de Metodos/3. Cohesion de metodos.md`

4. **Alternativas con Interfaces Diferentes**
   - Normalizar interfaces
   - **Archivo**: `Escuela_IT/Diseño/3. Diseño de Metodos/4. Codigo sucio por clases alternativas con interfaces diferentes.md`

5. **Listas de Parámetros Largas**
   - Reducir parámetros
   - **Archivo**: `Escuela_IT/Diseño/3. Diseño de Metodos/5. Codigo sucio por listas de parametros largas.md`

6. **Métodos Largos**
   - Métodos cortos y enfocados
   - **Archivo**: `Escuela_IT/Diseño/3. Diseño de Metodos/6. Cogido sucio por metodos largos.md`

7. **Envidia de Características**
   - Usar métodos propios vs ajenos
   - **Archivo**: `Escuela_IT/Diseño/3. Diseño de Metodos/7. Codigo sucio por envidia de caracteristicas.md`

8. **Diseño por Contrato**
   - Precondiciones y postcondiciones
   - **Archivo**: `Escuela_IT/Diseño/3. Diseño de Metodos/8. Diseño por contrato.md`

---

### SECCIÓN 8: DISEÑO DE CLASES

#### Tema 9: Principios de Clases

1. **Única Responsabilidad** (SRP - SOLID)
   - Una clase, un motivo de cambio
   - **Archivo**: `Escuela_IT/Diseño/4. Diseño de clases/10. Principio de unica responsabilidad.md`

2. **Código Sucio en Clases**
   - Clases grandes
   - Clases perezosas
   - Obsesión por tipos primitivos
   - Grupos de datos
   - Clases de datos
   - Librería incompleta
   - Cirugía a escopetazos
   - Cambios divergentes
   - Atributos temporales
   - **Archivos**:
     - `Escuela_IT/Diseño/4. Diseño de clases/1. Codigo sucio por clases grandes.md`
     - `Escuela_IT/Diseño/4. Diseño de clases/2. Codigo sucio por clases perezosas.md`
     - `Escuela_IT/Diseño/4. Diseño de clases/3. Codigo sucio por obsecion de tipos primitivos.md`
     - `Escuela_IT/Diseño/4. Diseño de clases/4. Codigo sucio por grupos de datos.md`
     - `Escuela_IT/Diseño/4. Diseño de clases/5. Codigo sucio por clases de datos.md`
     - `Escuela_IT/Diseño/4. Diseño de clases/6. Codigo sucio por libreria incompleta.md`
     - `Escuela_IT/Diseño/4. Diseño de clases/7. Codigo sucio por cirugia a escopetazos.md`
     - `Escuela_IT/Diseño/4. Diseño de clases/8. Codigo sucio por Cambios Divergentes.md`
     - `Escuela_IT/Diseño/4. Diseño de clases/9. Codigo sucio por atributos temporales.md`

---

### SECCIÓN 9: DISEÑO DE HERENCIA

#### Tema 10: Principios de Herencia

1. **Principio de Sustitución de Liskov** (LSP - SOLID)
   - Subtipos sustituibles por tipos base
   - Precondiciones más débiles, postcondiciones más fuertes
   - **Archivo**: `Escuela_IT/Diseño/5. Diseño de herencia/1. Principio de sustitucion de LISCOV.md`

2. **Herencia vs. Composición**
   - Cuándo usar cada una
   - Delegación e interfaces
   - **Archivo**: `Escuela_IT/Diseño/5. Diseño de herencia/2. Relacion de herencia vs composicion.md`

3. **Clases Alternativas con Interfaces Diferentes**
   - Normalizar interfaces polimórficas
   - **Archivo**: `Escuela_IT/Diseño/5. Diseño de herencia/3. Codigo sucio por claes alternativas con interfaces diferentes.md`

4. **Herencia Rechazada**
   - Clases que no usan herencia
   - **Archivo**: `Escuela_IT/Diseño/5. Diseño de herencia/4. Codigo sucio por herencia rechazada.md`

5. **Jerarquías Paralelas de Herencia**
   - Acoplamiento en jerarquías
   - **Archivo**: `Escuela_IT/Diseño/5. Diseño de herencia/5. Codigo sucio por jerarquias paralelas de herencia.md`

6. **Método Plantilla** (Template Method Pattern)
   - Estructura en base, detalles en derivadas
   - **Archivo**: `Escuela_IT/Diseño/5. Diseño de herencia/6. Patron metodo plantilla.md`

7. **Técnica del Doble Despacho**
   - Resolver basado en dos tipos
   - **Archivo**: `Escuela_IT/Diseño/5. Diseño de herencia/7. Tecnica del doble despacho.md`

8. **Principio de Separación de Interfaces** (ISP - SOLID)
   - Interfaces específicas, no genéricas
   - **Archivo**: `Escuela_IT/Diseño/5. Diseño de herencia/8. Principio de separacion de interfaces.md`

---

### SECCIÓN 10: DISEÑO DE DEPENDENCIAS

#### Tema 11: Gestión de Dependencias

1. **Inapropiada Intimidad**
   - Reducir dependencias de implementación
   - **Archivo**: `Escuela_IT/Diseño/6. Diseño de dependencias/1. Inapropiada intimidad.md`

2. **Leyes de Demeter**
   - No hables con extraños
   - **Archivo**: `Escuela_IT/Diseño/6. Diseño de dependencias/2. Leyes de Demeter.md`

3. **Inversión de Control** (IoC)
   - Framework vs. Librería
   - Principio Hollywood
   - **Archivo**: `Escuela_IT/Diseño/6. Diseño de dependencias/3. Inversion de control.md`

4. **Inyección de Dependencias**
   - Estilo específico de IoC
   - **Archivo**: `Escuela_IT/Diseño/6. Diseño de dependencias/4. Inyeccion de dependencias.md`

5. **Principio de Inversión de Dependencias** (DIP - SOLID)
   - Depender de abstracciones
   - **Archivo**: `Escuela_IT/Diseño/6. Diseño de dependencias/5. Principio de inversion de dependencias.md`

6. **Principio Abierto/Cerrado** (OCP - SOLID)
   - Abierto a extensión, cerrado a modificación
   - **Archivo**: `Escuela_IT/Diseño/6. Diseño de dependencias/6. Principio abierto - cerrado.md`

7. **Resumen de Métricas**
   - Métricas de diseño
   - **Archivo**: `Escuela_IT/Diseño/6. Diseño de dependencias/7 Resumen de metricas.md`

---

### SECCIÓN 11: DISEÑO DE PAQUETES

#### Tema 12: Arquitectura de Componentes

1. **Principios de Paquetes**
   - REP, CCP, CRP, ADP, SDP, SAP
   - **Archivo**: `Escuela_IT/Diseño/7. Diseño de paquetes/1. Principios.md`

2. **Cohesión de Paquetes**
   - Release/Reuse equivalence
   - Common closure
   - Common reuse
   - **Archivo**: `Escuela_IT/Diseño/7. Diseño de paquetes/2. Cohesion de paquetes.md`

3. **Acoplamiento de Paquetes**
   - Dependencias cíclicas
   - Estabilidad
   - **Archivo**: `Escuela_IT/Diseño/7. Diseño de paquetes/3. Acoplamiento de paquetes.md`

4. **Principios OO en Paquetes**
   - Aplicación de SOLID a paquetes
   - **Archivo**: `Escuela_IT/Diseño/7. Diseño de paquetes/4. Principios OO.md`

---

## Prácticas y Ejercicios

Los ejercicios prácticos se encuentran en:

### Guión Práctico 1-20
Archivos en: `Escuela_IT/Guion practico/1-20/`

Conceptos cubiertos:
1. Mal formateado
2. Mal comentado
3. Mal nombrado
4. Descomposición funcional
5. Clases grandes
6. Clases perezosas
7. Cambios divergentes
8. Obsesión por tipos primitivos
9. Principio de Mínima Sorpresa
10. Código muerto
11. YAGNI
12. DRY
13. KISS
14. Diseño por contrato
15. Cirugía a escopetazos
16. Inapropiada intimidad
17. Relaciones entre clases
18. Reusabilidad por Herencia
19. Principio de Sustitución de Liskov
20. Colisión de nombres

### Guión Práctico 21-40
Archivos en: `Escuela_IT/Guion practico/21-40/`

Conceptos cubiertos:
21. Controlador por caso de uso
22. Clases alternativas con interfaces diferentes
23. Herencia rechazada
24. Cohesión de métodos
25. Polimorfismo
26. Ampliando funcionalidad
27. Ampliando funcionalidad 2
28. Jerarquías de Herencia Paralelas
29. Creador
30. Leyes de Demeter
31. Principio de Única Responsabilidad
32. Técnica de doble despacho
33. Principio de Inversión de Dependencias
34. Principio de Inversión de Dependencias
35. Principio de Separación de Interfaces
36. Alto acoplamiento
37. Técnica del doble despacho
38. Atributos temporales
39. Código repetido
40. Principio Abierto/Cerrado

---

## Cómo Usar Este Material

### Para Aprendizaje Inicial
1. Lee la [Introducción](RESUMEN_CURSO_ADOO.md#introducción)
2. Estudia [Conceptos Fundamentales](RESUMEN_CURSO_ADOO.md#conceptos-fundamentales)
3. Avanza por secciones en orden: Análisis → Relaciones → GRASP → Diseño

### Para Referencia Rápida
- Usa [REFERENCIA_RAPIDA_ADOO.md](REFERENCIA_RAPIDA_ADOO.md)
- Consulta checklists según tu necesidad
- Navega tablas de decisión

### Para Profundizar
- Accede a archivos individuales de la bóveda
- Lee ejemplos de código
- Practica con los ejercicios 1-40

### Para Tomar Decisiones de Diseño
1. Consulta el flujo de decisión en [Decisiones de Diseño Comunes](REFERENCIA_RAPIDA_ADOO.md#decisiones-de-diseño-comunes)
2. Verifica el principio relacionado en GRASP o SOLID
3. Consulta "Si tienes problema con..." en [Referencias Cruzadas](REFERENCIA_RAPIDA_ADOO.md#referencias-cruzadas-rápidas)

---

## Relaciones Principales entre Temas

```
Enfoques de Clasificación
    ↓
Identificación de Clases
    ↓
Relaciones entre Clases + GRASP
    ↓
Código Limpio (Base para todo)
    ↓
Diseño de Métodos
    ↓
Diseño de Clases (SRP)
    ↓
Diseño de Herencia (LSP)
    ↓
Diseño de Dependencias (DIP, OCP)
    ↓
Diseño de Paquetes (Arquitectura)
```

---

## Resumen de Acrónimos por Tipo

### Patrones GRASP (9)
EI, C, CO, BAC, AC, P, I, FP, VP

### Principios SOLID (5)
S (SRP), O (OCP), L (LSP), I (ISP), D (DIP)

### Principios Pragmáticos (3)
YAGNI, DRY, KISS

### Otros Importantes
IoC, LSP, OCP, ISP, DIP, SRP, REP, CCP, CRP

---

## Progreso de Aprendizaje

Recomendado:
- Semana 1: Secciones 1-2 (Fundamentos)
- Semana 2: Secciones 3-4 (Análisis y Relaciones)
- Semana 3: Sección 5 (GRASP)
- Semana 4: Secciones 6-7 (Principios y Métodos)
- Semana 5: Secciones 8-9 (Clases y Herencia)
- Semana 6: Secciones 10-11 (Dependencias y Paquetes)
- Semana 7-8: Prácticas y proyectos integradores

---

**Última actualización**: Febrero 24, 2026
**Versión**: 1.0 - Completo
**Estado**: Listo para usar
