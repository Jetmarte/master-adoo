# Mapas Conceptuales - Análisis y Diseño Orientado a Objetos

Visualizaciones de las relaciones entre conceptos del curso.

---

## 1. Flujo General de ADOO

```
┌─────────────────────────────────────────────────────────┐
│     ANÁLISIS Y DISEÑO ORIENTADO A OBJETOS (ADOO)       │
└─────────────────────────────────────────────────────────┘
              ↓              ↓              ↓
        ┌──────────┐   ┌──────────┐   ┌──────────┐
        │ ANÁLISIS │   │ DISEÑO   │   │ CÓDIGO   │
        │ DEL      │   │ DE LA    │   │ LIMPIO   │
        │ DOMINIO  │   │ SOLUCIÓN │   │          │
        └──────────┘   └──────────┘   └──────────┘
             ↓              ↓              ↓
    • Clases         • Responsabilidades  • Formato
    • Relaciones     • Patrones (GRASP)   • Nombres
    • Conceptos      • Principios (SOLID) • Estructura
    • Entidades      • Patrones (GoF)     • Estándares
```

---

## 2. Jerarquía de Conceptos ADOO

```
ADOO (Análisis y Diseño OO)
│
├─ ANÁLISIS
│  ├─ Enfoques de Clasificación
│  │  ├─ Categorización Clásica
│  │  ├─ Agrupación Conceptual
│  │  └─ Teoría de Prototipos
│  │
│  ├─ Identificación de Clases
│  │  ├─ Descripción Normal (Abbott)
│  │  ├─ Análisis Clásico
│  │  ├─ Análisis del Dominio
│  │  ├─ Análisis del Comportamiento
│  │  └─ Análisis de Casos de Uso
│  │
│  └─ Relaciones entre Clases
│     ├─ Composición/Agregación
│     ├─ Asociación
│     ├─ Dependencia
│     └─ Herencia (ISA)
│
├─ PRINCIPIOS GRASP (9)
│  ├─ Asignación de Responsabilidades
│  │  ├─ Experto en Información
│  │  ├─ Creador
│  │  └─ Controlador
│  │
│  ├─ Gestión de Complejidad
│  │  ├─ Alta Cohesión
│  │  └─ Bajo Acoplamiento
│  │
│  ├─ Manejo de Variabilidad
│  │  ├─ Polimorfismo
│  │  └─ Variaciones Protegidas
│  │
│  └─ Apoyo Arquitectónico
│     ├─ Indirección
│     └─ Fabricación Pura
│
├─ CÓDIGO LIMPIO
│  ├─ Formato
│  │  ├─ Organización Lógica
│  │  ├─ Sangría y Espaciado
│  │  └─ Longitud de Línea
│  │
│  ├─ Nombrado
│  │  ├─ Nombres Descriptivos
│  │  ├─ Convenciones
│  │  └─ Evitar Antipatrones
│  │
│  └─ Estructura
│     ├─ Comentarios
│     └─ Descomposición Funcional
│
├─ DISEÑO
│  ├─ Diseño de Métodos
│  │  ├─ Interfaz (Suficiente, Completa, Primitiva)
│  │  ├─ Cohesión de Métodos
│  │  ├─ Mínima Sorpresa
│  │  └─ Diseño por Contrato
│  │
│  ├─ Diseño de Clases
│  │  ├─ Única Responsabilidad (SRP)
│  │  ├─ Código Sucio (Bad Smells)
│  │  │  ├─ Clases Grandes
│  │  │  ├─ Clases Perezosas
│  │  │  ├─ Obsesión Tipos Primitivos
│  │  │  ├─ Grupos de Datos
│  │  │  ├─ Clases de Datos
│  │  │  ├─ Librería Incompleta
│  │  │  ├─ Cirugía a Escopetazos
│  │  │  ├─ Cambios Divergentes
│  │  │  └─ Atributos Temporales
│  │  │
│  │  └─ Separación de Responsabilidades
│  │
│  ├─ Diseño de Herencia
│  │  ├─ Principio de Sustitución (LSP)
│  │  ├─ Herencia vs. Composición
│  │  ├─ Patrones de Herencia
│  │  │  ├─ Método Plantilla
│  │  │  └─ Doble Despacho
│  │  │
│  │  └─ Principios Relacionados
│  │     └─ Separación de Interfaces (ISP)
│  │
│  ├─ Diseño de Dependencias
│  │  ├─ Bajo Acoplamiento
│  │  ├─ Leyes de Demeter
│  │  ├─ Inversión de Control (IoC)
│  │  ├─ Inyección de Dependencias
│  │  ├─ Inversión de Dependencias (DIP)
│  │  └─ Principio Abierto/Cerrado (OCP)
│  │
│  └─ Diseño de Paquetes
│     ├─ Cohesión de Paquetes
│     │  ├─ Release/Reuse Equivalence (REP)
│     │  ├─ Common Closure (CCP)
│     │  └─ Common Reuse (CRP)
│     │
│     └─ Acoplamiento de Paquetes
│        ├─ Acyclic Dependencies (ADP)
│        ├─ Stable Dependencies (SDP)
│        └─ Stable Abstractions (SAP)
│
└─ PRINCIPIOS PRAGMÁTICOS
   ├─ YAGNI (You Aren't Gonna Need It)
   ├─ DRY (Don't Repeat Yourself)
   └─ KISS (Keep It Simple, Stupid)
```

---

## 3. Principios GRASP Interconectados

```
                      GRASP
                        │
        ┌───────────────┼───────────────┐
        │               │               │
    ┌─ASIGNACIÓN      ┌─COMPLEJIDAD    ┌─VARIABILIDAD
    │                 │                 │
    ├─Experto         ├─Alta Cohesión   ├─Polimorfismo
    ├─Creador         └─Bajo Acoplamiento│
    └─Controlador                      └─Variaciones
                                           Protegidas
        │ (Requisitos mínimos)
        └─ Indirección + Fabricación Pura
           (Soporte arquitectónico)


INTERDEPENDENCIAS:
└─ Experto + Bajo Acoplamiento → Bajo Acoplamiento al asignar
└─ Bajo Acoplamiento + Alta Cohesión → Clases enfocadas
└─ Creador + Bajo Acoplamiento → Crear quién está cerca
└─ Controlador + Indirección → UI delega a controlador
└─ Polimorfismo + Variaciones Protegidas → Flexibilidad
```

---

## 4. Relaciones entre Clases

```
RELACIONES (del todo) vs (de parte)

Composición/Agregación (TIENE UN)
│
├─ COMPOSICIÓN (Fuerte)
│  └─ Ciclo de vida compartido
│     └─ Ejemplo: Persona ←→ Cabeza
│
└─ AGREGACIÓN (Débil)
   └─ Ciclo de vida independiente
      └─ Ejemplo: Persona ←→ Familia

Asociación (SERVICIO)
│
└─ Cliente mantiene relación permanente con Servidor
   └─ Ejemplo: Profesor ←→ Aula

Dependencia (USO)
│
└─ Una clase usa servicios de otra
   └─ Forma débil de relación

Herencia (ES UN)
│
├─ Relación conceptual
├─ Transmisión de miembros
└─ Generalización ↔ Especialización
   └─ Regla ISA: ¿... es un ...?
```

---

## 5. Decisiones de Diseño Clave

```
┌─ ¿A quién asignar responsabilidad X?
│
├─ ¿Quién tiene la información?
│  └─ EXPERTO en Información
│
├─ ¿Quién crea objetos Y?
│  └─ CREADOR (quien contiene/usa)
│
├─ ¿Qué clase maneja eventos?
│  └─ CONTROLADOR (de caso uso)
│
├─ ¿Cómo evitar dependencias?
│  └─ BAJO ACOPLAMIENTO
│
├─ ¿Cómo mantener enfoque?
│  └─ ALTA COHESIÓN
│
├─ ¿Cómo manejar variaciones?
│  ├─ POLIMORFISMO (tipos varían)
│  └─ VARIACIONES PROTEGIDAS (puntos estables)
│
└─ ¿Cómo no existe en dominio?
   └─ FABRICACIÓN PURA (clase auxiliar)
```

---

## 6. Principios SOLID Aplicados a ADOO

```
SOLID (Principios de Diseño OO)

S - Single Responsibility Principle (SRP)
    │
    └─ Una clase, un motivo de cambio
       └─ Relación: GRASP Alta Cohesión
       └─ Implementación: Separar responsabilidades

O - Open/Closed Principle (OCP)
    │
    └─ Abierto a extensión, cerrado a modificación
       └─ Relación: GRASP Polimorfismo + Variaciones Protegidas
       └─ Implementación: Usar abstracciones

L - Liskov Substitution Principle (LSP)
    │
    └─ Subtipos sustituibles por tipos base
       └─ Relación: Diseño de Herencia
       └─ Implementación: Respetando contratos

I - Interface Segregation Principle (ISP)
    │
    └─ Interfaces específicas, no genéricas
       └─ Relación: GRASP Bajo Acoplamiento
       └─ Implementación: Dividir interfaces grandes

D - Dependency Inversion Principle (DIP)
    │
    └─ Depender de abstracciones
       └─ Relación: GRASP Bajo Acoplamiento + Variaciones
       └─ Implementación: Inyección de Dependencias
```

---

## 7. Flujo de Decisión: ¿Herencia o Composición?

```
        ¿Es un? (ISA)
        /         \
       SÍ          NO
      /              \
     └─ ¿Respeta LSP? → Composición
            /  \
          SÍ    NO
         /        \
        └─ ¿Cambio dinámico?
              /  \
            NO   SÍ
           /       \
       Herencia  Composición

REGLAS:
┌─ Composición si: Cambio dinámico, LSP viola, no pasa ISA
├─ Herencia si: ISA, LSP respeta, ciclo vida compartido
└─ Interfaces si: Se necesita polimorfismo pero composición
```

---

## 8. Mapa de Dependencias entre Principios

```
YAGNI (Base)
  │ (Implementar solo lo necesario)
  ├─ DRY (No duplicar lo necesario)
  │
  ├─ KISS (Mantener simple lo necesario)
  │
  └─ Código Limpio (Escribir bien lo necesario)
       │
       ├─ GRASP (Asignar responsabilidades bien)
       │
       ├─ Diseño de Métodos (Métodos simples y cohesivos)
       │
       ├─ Diseño de Clases (Clases con SRP)
       │
       ├─ Diseño de Herencia (LSP, Composición)
       │
       ├─ Diseño de Dependencias (DIP, OCP)
       │
       └─ Diseño de Paquetes (Arquitectura)
```

---

## 9. Ciclo de Mejora Continua

```
CÓDIGO INICIAL (Menos que Ideal)
        ↓
   DETECTAR PROBLEMAS
   • Código duplicado → DRY
   • Métodos largos → Cohesión
   • Clases grandes → SRP
   • Alto acoplamiento → Bajo Acoplamiento
   • Múltiples cambios → Variaciones Protegidas
        ↓
   APLICAR PRINCIPIOS
   • Refactorización
   • Reorganizar responsabilidades
   • Introducir abstracciones
   • Separar interfaces
        ↓
   CÓDIGO MEJORADO (Más limpio, mantenible)
        ↓
   MONITOREAR CAMBIOS (Nuevos requisitos)
        ↓
   ¿Más cambios necesarios?
        │
        ├─ SÍ → Repetir ciclo
        │
        └─ NO → Mantener y evolucionar
```

---

## 10. Matriz de Decisión: Bad Smells y Soluciones

```
┌─ BAD SMELL           │ CAUSA              │ SOLUCIÓN
├────────────────────┼────────────────────┼─────────────────────
│ Clases Grandes     │ Múltiples responsab│ SRP, Extraer clases
│ Clases Perezosas   │ No justifican exist│ Eliminar o fusionar
│ Tipos Primitivos   │ Sin objetos dominio │ Crear clases de dom.
│ Grupos de Datos    │ Variables relacion. │ Crear clase para grup
│ Clases de Datos    │ Solo get/set        │ Agregar comportamient
│ Métodos Largos     │ Múltiples tareas    │ Extraer métodos
│ Cambios Divergent. │ Múltiples motivos   │ Separar SRP
│ Cirugía Escopetazo │ Cambios en cascada  │ Bajo Acoplamiento
│ Atributos Temporal │ Solo en algunas ... │ Múltiples responsab
│ Duplicación Código │ Copiar/pegar        │ DRY, extraer método
│ Herencia Rechazada │ No usa heredado     │ Usar Composición
│ Jerarq. Paralelas  │ Cambios acoplados   │ Refactorizar
└─────────────────────┴────────────────────┴──────────────────────
```

---

## 11. Proceso Iterativo de Análisis y Diseño

```
ITERACIÓN 1: Fundamentos
├─ Enfoques de Clasificación
├─ Identificación de Clases
└─ Relaciones Básicas

ITERACIÓN 2: Patrones
├─ Principios GRASP
├─ Asignación de Responsabilidades
└─ Primeras Jerarquías

ITERACIÓN 3: Refinamiento
├─ Código Limpio
├─ Diseño de Métodos
└─ Separación de Responsabilidades (SRP)

ITERACIÓN 4: Arquitectura
├─ Diseño de Herencia Completo
├─ Inversión de Control
├─ Inyección de Dependencias
└─ Paquetes

ITERACIÓN 5: Optimización
├─ Refactorización
├─ Patrones (Template Method, Factory, etc.)
└─ Métricas de Calidad
```

---

## 12. Conceptos Clave por Nivel

```
NIVEL 1: Básico
├─ Clases y Objetos
├─ Atributos y Métodos
├─ Encapsulación
└─ Relaciones Simples (Composición)

NIVEL 2: Intermedio
├─ Herencia (ISA)
├─ Polimorfismo
├─ Asociación y Dependencia
└─ Responsabilidades

NIVEL 3: Avanzado
├─ GRASP (9 patrones)
├─ SOLID (5 principios)
├─ Inversión de Control
└─ Arquitectura de Paquetes

NIVEL 4: Experto
├─ Patrones de Diseño (GoF)
├─ Análisis de Dominio
├─ Domain-Driven Design
└─ Arquitectura Empresarial
```

---

## 13. Síntesis Visual: De Problema a Solución

```
PROBLEMA REAL
    │
    │ (ANÁLISIS)
    ↓
DOMINIO DEL PROBLEMA
    ├─ Entidades
    ├─ Relaciones
    └─ Reglas de Negocio
    │
    │ (GRASP + SOLID)
    ↓
MODELO DE CLASES (DISEÑO)
    ├─ Responsabilidades
    ├─ Dependencias
    └─ Jerarquías
    │
    │ (CÓDIGO LIMPIO)
    ↓
CÓDIGO IMPLEMENTADO
    ├─ Métodos
    ├─ Formato
    └─ Estándares
    │
    │ (REFACTORIZACIÓN CONTINUA)
    ↓
SOLUCIÓN MANTENIBLE Y FLEXIBLE
```

---

## 14. Acrónimos: Mapa Visual

```
GRASP (Asignación de Responsabilidades)
├─ EI = Experto en Información
├─ C = Creador
├─ CO = Controlador
├─ BAC = Bajo Acoplamiento
├─ AC = Alta Cohesión
├─ P = Polimorfismo
├─ I = Indirección
├─ FP = Fabricación Pura
└─ VP = Variaciones Protegidas

SOLID (Principios de Diseño)
├─ S = Single Responsibility
├─ O = Open/Closed
├─ L = Liskov Substitution
├─ I = Interface Segregation
└─ D = Dependency Inversion

PRAGMÁTICOS (Sentido Común)
├─ YAGNI = You Aren't Gonna Need It
├─ DRY = Don't Repeat Yourself
├─ KISS = Keep It Simple Stupid
└─ LSP = Law of Demeter (No hables con extraños)

PAQUETES
├─ REP = Release/Reuse Equivalence
├─ CCP = Common Closure
├─ CRP = Common Reuse
├─ ADP = Acyclic Dependencies
├─ SDP = Stable Dependencies
└─ SAP = Stable Abstractions
```

---

## 15. Flujo de Preguntas para Diseñar

```
¿CÓMO DISEÑO ESTO?

1. ¿Cuál es el problema? (ANÁLISIS)
   ├─ ¿Cuál es el dominio?
   ├─ ¿Cuáles son las entidades?
   └─ ¿Cuáles son las reglas?

2. ¿Cuáles son las clases? (IDENTIFICACIÓN)
   ├─ ¿Sustantivos en la descripción?
   └─ ¿Conceptos del dominio?

3. ¿Cómo se relacionan? (RELACIONES)
   ├─ ¿ISA (Herencia)?
   ├─ ¿Tiene un (Composición)?
   └─ ¿Usa servicios de (Asociación)?

4. ¿Quién hace qué? (GRASP)
   ├─ ¿Quién tiene la información?
   ├─ ¿Quién crea esto?
   ├─ ¿Cómo evitar dependencias?
   └─ ¿Cómo manejar cambios?

5. ¿Es código limpio? (CÓDIGO)
   ├─ ¿Se entiende fácilmente?
   ├─ ¿Respeta convenciones?
   └─ ¿Está bien formateado?

6. ¿Respeta SOLID? (VERIFICACIÓN)
   ├─ ¿Una responsabilidad? (S)
   ├─ ¿Abierto a extensión? (O)
   ├─ ¿Sustituible? (L)
   ├─ ¿Interfaz específica? (I)
   └─ ¿Depende de abstracciones? (D)

7. ¿Es simple? (PRAGMATISMO)
   ├─ ¿Necesario ahora? (YAGNI)
   ├─ ¿Única representación? (DRY)
   └─ ¿Lo más simple? (KISS)
```

---

**Fin de Mapas Conceptuales**

Estos diagramas ayudan a visualizar las relaciones entre conceptos del curso y servir como referencia rápida visual.
