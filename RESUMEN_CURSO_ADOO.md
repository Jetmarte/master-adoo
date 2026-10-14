# Análisis y Diseño Orientado a Objetos - Resumen Comprensivo

## Tabla de Contenidos

1. [Introducción](#introducción)
2. [Conceptos Fundamentales](#conceptos-fundamentales)
3. [Análisis de Clases](#análisis-de-clases)
4. [Relaciones entre Clases](#relaciones-entre-clases)
5. [Principios GRASP](#principios-grasp)
6. [Código Limpio](#código-limpio)
7. [Diseño de Métodos](#diseño-de-métodos)
8. [Diseño de Clases](#diseño-de-clases)
9. [Diseño de Herencia](#diseño-de-herencia)
10. [Diseño de Dependencias](#diseño-de-dependencias)
11. [Diseño de Paquetes](#diseño-de-paquetes)
12. [Conclusión](#conclusión)

---

## Introducción

El Análisis y Diseño Orientado a Objetos (ADOO) es una metodología fundamental en la ingeniería de software que permite crear sistemas escalables, mantenibles y flexibles. Este curso integra dos aspectos clave:

- **Análisis**: Comprender el problema del negocio y modelar clases que lo representen
- **Diseño**: Implementar soluciones de software que sean robustas y mantenibles

### Diferencia Clave: Dominio vs. Solución

- **Dominio del Problema**: Describe la realidad del negocio en el mundo real, sin pensar en software
- **Solución del Problema**: Describe cómo implementaremos el software para resolver el problema
- **Lógica de Negocio**: Las reglas y procesos que gobiernan las entidades del dominio
- **Modelo del Dominio**: La representación conceptual de las entidades y sus relaciones

---

## Conceptos Fundamentales

### 1. Enfoques de Clasificación

Existen tres teorías sobre cómo categorizar entidades para crear clases:

#### Categorización Clásica
- Todas las entidades que comparten un conjunto de propiedades comunes forman una categoría
- Las propiedades son necesarias y suficientes
- **Limitación**: Categorías naturales suelen tener excepciones (ej: pingüinos que no vuelan)

#### Agrupación Conceptual
- Las clases se generan a partir de descripciones conceptuales
- Se clasifican entidades según conceptos difusos (no lógicos)
- Más flexible que la categorización clásica
- **Ejemplo**: Concepto de "canción de amor"

#### Teoría de Prototipos
- Una clase está representada por un objeto prototípico
- Un objeto es miembro de la clase si se asemeja significativamente al prototipo
- Aplicación: Parecidos de familia (Wittgenstein)
- **Ventaja**: Diseño más flexible para dominios complejos

### 2. Modelo del Dominio vs. Lógica de Negocio

| Aspecto | Modelo del Dominio | Lógica de Negocio |
|--------|-------------------|-------------------|
| **Naturaleza** | Estático (estructura) | Dinámico (comportamiento) |
| **Pregunta clave** | ¿Qué entidades existen? | ¿Qué reglas rigen? |
| **Ejemplo** | Clases: Cuenta, Cliente | No permitir sobregiros |

---

## Análisis de Clases

### Estrategias de Identificación

#### 1. Descripción Normal (Método de Abbott)
- Escribir descripción del problema
- Subrayar sustantivos (candidatos a clases)
- Subrayar verbos (candidatos a responsabilidades)
- **Limitación**: No escala bien para problemas complejos

#### 2. Análisis Clásico
Fuentes de clases:
- **Cosas**: Objetos físicos (coches, sensores)
- **Conceptos**: Ideas abstractas (préstamo, reunión, intersección)
- **Eventos**: Cosas que ocurren (aterrizaje, solicitud)
- **Personas**: Usuarios con diferentes roles (profesor, cliente)
- **Organizaciones**: Colecciones formales (empresas, departamentos)
- **Lugares Físicos**: Espacios importantes (oficinas, zonas)
- **Dispositivos**: Componentes con los que interactúa
- **Sistemas Externos**: Sistemas con los que se integra

#### 3. Análisis del Dominio
- Análisis del comportamiento
- Análisis de casos de uso

---

## Relaciones entre Clases

### Tipos de Relaciones

#### 1. Relación de Composición/Agregación
**Patrón**: "tiene un"

**Composición** (fuerte):
- El todo y la parte comparten ciclo de vida
- Si el todo desaparece, la parte también
- Ejemplo: Persona y cabeza
- Características: Visibilidad privada, temporalidad no momentánea

**Agregación** (débil):
- El todo contiene la parte, pero pueden existir independientemente
- La parte puede ser compartida por múltiples todos
- Ejemplo: Persona y familia
- El destruir el compuesto no destruye los componentes

#### 2. Relación de Asociación
**Patrón**: "usa los servicios de"
- Cliente colabora con servidor determinado
- Durabilidad indefinida
- Características: Visibilidad pública, temporalidad no momentánea, versatilidad reducida

#### 3. Relación de Dependencia (Uso)
- Cuando un objeto envía mensajes a otro
- La clase que envía depende de la que recibe
- Más débil que composición/agregación

#### 4. Relación de Herencia
**Patrón**: "es un"
- Transmisión de vista pública (métodos) y privada (atributos)
- **Regla ISA**: ¿Es un elemento del nodo hijo un elemento del nodo padre?
- **Generalización/Especialización**: Características específicas de un subconjunto

### Características de Relaciones

- **Visibilidad**: Privada (solo la clase) o pública (accesible desde afuera)
- **Temporalidad**: Breve o indefinida (cuánto dura la colaboración)
- **Versatilidad**: Intercambiabilidad de objetos en la colaboración

---

## Principios GRASP

GRASP (General Responsibility Assignment Software Patterns) son 9 pautas propuestas por Craig Larman para asignar responsabilidades en diseño orientado a objetos.

### 1. Experto en Información (Information Expert)

**Problema**: ¿Cuál es el principio general de asignación de responsabilidades?

**Solución**: Asignar la responsabilidad al experto en la información: la clase que tiene la información necesaria para cumplirla.

**Beneficios**:
- Mantiene encapsulación de información
- Bajo acoplamiento
- Distribuye comportamiento de manera cohesionada

**Nota**: Evitar que una clase contenga todo el código (clases god)

### 2. Creador (Creator)

**Problema**: ¿Quién debería ser responsable de crear instancias?

**Solución**: Asignar a clase B la responsabilidad de crear instancias de clase A si:
- B contiene/agrega objetos de A
- B registra instancias de A
- B usa estrechamente A
- B tiene datos de inicialización para A

**Beneficios**:
- Bajo acoplamiento
- Encapsulación
- Reutilización

### 3. Controlador (Controller)

**Problema**: ¿Quién maneja los eventos del sistema?

**Solución**: Asignar a una clase que:
- Represente el sistema/dispositivo en general, O
- Represente un caso de uso (<UseCaseName>Controller)

**Implicaciones**:
- No es un objeto de interfaz de usuario
- Recibe eventos y delega trabajo a otros
- Coordina actividad sin hacer todo el trabajo

### 4. Bajo Acoplamiento (Low Coupling)

**Problema**: ¿Cómo apoyar bajo acoplamiento y bajo impacto del cambio?

**Definición**: Medida de la fuerza con que un elemento está conectado a otros.

**Formas de acoplamiento directo**:
- Atributos que referencian otra clase
- Métodos que referencian otra clase
- Herencia de otra clase

**Solución**: Asignar responsabilidades para mantener acoplamiento bajo.

**Beneficios**:
- No se ve afectado por cambios en otros componentes
- Fácil de entender aisladamente
- Conveniente para reutilizar

**Nota**: Moderación - no todo acoplamiento es malo. El acoplamiento a elementos estables y generalizados es aceptable (ej: librerías estándar).

### 5. Alta Cohesión (High Cohesion)

**Problema**: ¿Cómo mantener la complejidad manejable?

**Definición**: Medida de qué tan fuerte están relacionadas las responsabilidades de un elemento.

**Niveles de cohesión**:
- **Muy baja**: Una clase responsable de muchas cosas en áreas diferentes
- **Baja**: Una clase con una responsabilidad compleja en un área
- **Moderada**: Responsabilidades ligeras en pocas áreas lógicamente relacionadas
- **Alta**: Responsabilidades moderadas en un área, colabora con otros objetos

**Solución**: Asignar responsabilidades para mantener cohesión alta.

**Beneficios**:
- Mayor claridad y comprensión
- Simplifica mantenimiento y mejoras
- Compatible con bajo acoplamiento
- Soporta mayor reutilización

### 6. Polimorfismo (Polymorphism)

**Problema**: ¿Cómo manejar alternativas basadas en tipo? ¿Cómo crear componentes conectables?

**Solución**: Asignar responsabilidad del comportamiento usando operaciones polimórficas a los tipos donde el comportamiento varía.

**Corolario**: No preguntes por el tipo de un objeto ni uses lógica condicional para variaciones basadas en tipo.

**Beneficios**:
- Nuevas variaciones son fáciles de agregar
- Nuevas implementaciones sin afectar clientes

**Contraindicación**: YAGNI - no diseñar polimorfismo especulativamente

### 7. Indirección (Indirection)

**Solución**: Introducir un intermediario para reducir acoplamiento entre clases o lograr mayor flexibilidad.

**Ejemplo**: Un ServicioMensajeria que delega el envío a WhatsAppAPI o EmailAPI.

### 8. Fabricación Pura / Invención Pura (Pure Fabrication)

**Problema**: Asignación de responsabilidades solo a clases del dominio causa bajo acoplamiento, baja cohesión o bajo potencial de reutilización.

**Solución**: Crear una clase artificial que no representa un concepto del dominio, pero que ayuda a lograr:
- Alta cohesión
- Bajo acoplamiento
- Reutilización

**Ejemplos**:
- RepositorioUsuarios (para persistencia)
- FormateadorIntervalos (para presentaciones diferentes)
- CadenaCaracteresPoética (para responsabilidades específicas)

### 9. Variaciones Protegidas (Protected Variations)

**Problema**: ¿Cómo diseñar sistemas para que variaciones e inestabilidades no tengan impacto indeseable en otros elementos?

**Solución**: Identificar puntos de variación o inestabilidad previstos y asignar responsabilidades para crear interfaces estables alrededor de estos.

**Mecanismos nucleares**:
- Encapsulación de datos
- Polimorfismo
- Indirección
- Estándares
- Diseño dirigido por datos (lectura de configuración externa)

**Contraindicación**: Moderación - no sobre-diseñar para puntos de evolución especulativos

---

## Código Limpio

### 1. Respetar Estándares de Código Limpio

**Justificación**: Cada equipo debe adoptar y seguir un estándar unificado basado en convenciones de la industria.

**Aspectos clave**:
- Ubicación de declaración de variables de instancia
- Nombrado de clases, métodos y variables
- Colocación de llaves y sintaxis
- Consistencia entre todos los miembros del equipo

**Principio**: El código mismo debe ser el documento vivo de estas convenciones.

### 2. Formato de Código Limpio

#### Organización Lógica
- **Separación de bloques**: Línea en blanco entre grupos lógicos
- **Atributos al principio**: Fáciles de identificar
- **Proximidad de funciones**: Las que se llaman entre sí deben estar cerca
- **Agrupación**: Funciones similares juntas

#### Proximidad de Variables
- Declara variables lo más cerca posible de su primer uso
- Ayuda a entender propósito y alcance

#### Longitud de Línea
- Ideal: ~40 caracteres
- Máximo recomendado: 80-120 caracteres
- Espacio en blanco: Asociar elementos relacionados, separar no relacionados, enfatizar precedencia

#### Jerarquía y Sangría
- Usar sangría consistentemente
- Refleja la estructura del código
- Nunca romper la sangría por líneas cortas

### 3. Nombrado de Código Limpio

#### Principios Generales
- **Revelar intención**: El nombre debe explicar por qué existe, qué hace
- **Pronunciables**: Permitir conversación
- **Del dominio**: Usar palabras conocidas en el negocio
- **Consistencia**: Una palabra para un concepto
- **CamelCase**: Mayúsculas en cambios de palabra

#### Convenciones por Tipo

**Paquetes**:
- Sustantivos, minúsculas
- Ej: models.customers

**Clases**:
- Sustantivos, mayúsculas
- Ej: Controller, Usuario

**Métodos**:
- Verbos o frase con verbo, minúsculas
- get/set para accesadores
- is para booleanos

#### Violaciones Comunes a Evitar
- Nombres que requieren comentario (d, mpd, lista1)
- Nombres de una letra (excepto i, j, k en bucles muy locales)
- Acrónimos no internacionales (BHPS → BehaviourHumanPredictionSystem)
- Notación Húngara (iAge, m_iAge)
- Palabras vacías (Object, Class, Data, Inform)
- Nombres en serie (player1, player2)
- Nombres desinformativos (customerList si no es lista)
- Nombres polisémicos en mismo contexto

#### Máxima
> "Una línea de código se escribe una vez y se lee cientos de veces" - Cox

---

## Diseño de Métodos

### 1. Interfaz Suficiente, Completa y Primitiva

#### Interfaz Suficiente
- Expone exactamente los métodos necesarios
- Ni más ni menos
- Si falta algo: obliga a cliente a hacer trabajo adicional
- Si sobra algo: ofrece operaciones redundantes

#### Interfaz Completa
- Ofrece todas las operaciones necesarias para manipular la abstracción
- Si falta un método importante: clientes deben hacer "trucos" o violar encapsulación
- Cubre todos los aspectos de la abstracción

**Pero cuidado**: No agregar todas las operaciones previsibles (ej: esPalíndromo en String)

#### Interfaz Primitiva
- Métodos independientes y no redundantes
- Ningún método implementable en términos de otros
- Evita sobrecarga innecesaria

**Relación**: YAGNI está en oposición a "interfaz suficiente, completa y primitiva"

### 2. Principio de Menor Compromiso (Mínima Sorpresa)
- Métodos deben comportarse como espera el usuario
- Minimizar sorpresas
- Consistencia en nomenclatura y comportamiento

### 3. Cohesión de Métodos

**Definición**: Grado en que todas las instrucciones de un método están enfocadas en una sola tarea.

**Problema**: Métodos que hacen múltiples secciones con diferentes objetivos
- Producen acoplamiento temporal
- Imposibilitan reutilización

**Niveles**:
- **Alta**: Hace una sola cosa bien definida
- **Baja**: Hace muchas cosas no relacionadas

**Solución**: Convertir en varias funciones pequeñas que hagan una sola cosa

**Beneficios**:
- Métodos más cortos y claros
- Única responsabilidad
- Facilita mantenimiento y pruebas unitarias

---

## Diseño de Clases

### 1. Interfaz de Clases

Los tres principios (suficiente, completa, primitiva) se aplican también a clases:
- **Suficiente**: Mínimo de métodos para usar la clase
- **Completa**: Todos los métodos necesarios
- **Primitiva**: Métodos básicos no redundantes

### 2. Principio de Única Responsabilidad (SRP)

**Definición (Robert Martin)**: Una clase debería tener un único motivo de cambio.

**Inspiración**: Concepto de cohesión (DeMarco, Page-Jones)

**Responsabilidad**: Una razón de cambio
- Si puedes pensar en más de un motivo para cambiar una clase, tiene múltiples responsabilidades

**Justificación**:
- Si una clase tiene múltiples responsabilidades, pueden acoplarse
- Cambios de una pueden perjudicar otras
- Produce diseños frágiles

**Ejemplos de violación**:
- Clase Board responsable de fichas Y presentación
- Entidad que se guarda a sí misma en base de datos

**Solución**:
- Separar funcionalidad en clases distintas
- Cada clase maneja una única responsabilidad
- Colaboran según sea necesario

**Nota**: YAGNI aplica - solo separar si el cambio ocurre realmente

### 3. Código Sucio en Clases

#### Clases Grandes
- Hacen demasiadas cosas
- Baja cohesión
- Difíciles de entender y mantener

#### Clases Perezosas
- Muy poco código o responsabilidad
- No justifican su existencia
- Mezclar en otra clase o crear solución diferente

#### Obsesión por Tipos Primitivos
- Usar int, String para todo en lugar de objetos de dominio
- Perder semántica del negocio
- Hacer if/switch sobre tipos

#### Grupos de Datos
- Variables que viajan juntas pero no están encapsuladas
- Crear clase para agruparlas

#### Clases de Datos
- Solo get/set, sin comportamiento
- Violación de OOP
- Mover comportamiento a clases que usan estos datos

#### Librería Incompleta
- Clase que wrapper una librería pero no cubre completamente
- Genera código sucio en clientes

#### Cirugía a Escopetazos
- Un cambio requiere modificar muchas clases
- Señal de bajo acoplamiento
- Agrupar cambios relacionados

#### Cambios Divergentes
- Una clase tiene múltiples razones para cambiar
- Violación de SRP
- Separar responsabilidades

#### Atributos Temporales
- Algunos atributos solo usados en ciertos contextos
- Otros nunca usados
- Indicador de múltiples responsabilidades

---

## Diseño de Herencia

### 1. Principio de Sustitución de Liskov (LSP)

**Definición (Barbara Liskov)**: Si para cada objeto o1 de tipo S hay un objeto o2 de tipo T tal que para todo programa P definido en términos de T, el comportamiento de P no cambia cuando o1 sustituye a o2, entonces S es subtipo de T.

**Implicación**:
- Tipos derivados totalmente sustituibles por sus tipos base
- Funciones que usan tipos base pueden reutilizarse con tipos derivados

**Regla**:
- Redefinir un método reemplazando precondición por una más débil
- Y postcondición por una más fuerte

**Violaciones**:
- Usar instanceof o RTTI para seleccionar función basada en tipo
- Ejemplo: Square hereda de Rectangle pero redefine setAncho/setAlto (viola expectativas del cliente)

### 2. Herencia vs. Composición

| Aspecto | Herencia (es un) | Composición (tiene un) |
|--------|-----------------|----------------------|
| **Patrón** | ISA | Tiene un |
| **Ciclo de vida** | Compartido | Independiente (agregación) |
| **Cambio dinámico** | No soporta | Soporta |
| **Problema** | LSP, cambio dinámico | Más código |

**Regla de Cambio**: No usar herencia si el objeto compuesto puede cambiar en tiempo de ejecución.

**Reglas de Polimorfismo**: Herencia apropiada si entidad tipo general puede enlazarse a objetos tipo especializado.

**Solución** (si se rechaza herencia):
1. **Delegación**: El todo delega a la parte
2. **Interfaces**: Si se necesita polimorfismo, heredar de interfaces

### 3. Otros Patrones de Herencia

#### Herencia Rechazada
- Clase derivada no usa métodos/atributos heredados
- Señal de mala jerarquía
- Reconsiderar relación

#### Clases Alternativas con Interfaces Diferentes
- Misma responsabilidad pero interfaces distintas
- Crear interface común

#### Jerarquías Paralelas de Herencia
- Cuando añades subclase A, también debes añadir subclase B
- Acoplamiento fuerte entre jerarquías
- Separar jerarquías o refactorizar

#### Método Plantilla (Template Method)
- Clase base define estructura del algoritmo
- Clases derivadas implementan pasos específicos
- Define "esqueleto" en clase base

#### Técnica del Doble Despacho
- Resolver método basado en dos tipos de objetos
- Evitar lógica condicional compleja

#### Principio de Separación de Interfaces (ISP)
- No forzar a clientes depender de interfaces que no usan
- Interfaces específicas por cliente, no interfaces genéricas grandes

---

## Diseño de Dependencias

### 1. Inapropiada Intimidad

**Problema**: Una clase depende demasiado de implementación interna de otra.

**Solución**: Reducir dependencias, usar interfaces públicas.

### 2. Leyes de Demeter (Law of Demeter)

**Sinónimo**: "No hables con extraños"

**Regla**: Enviar mensajes únicamente a:
- `this` (el objeto mismo)
- Parámetros de método
- Atributos del objeto
- Variables locales del método

**Prohibición**: No enviar a objetos indirectos obtenidos como resultado de mensaje a conocimiento directo.

**Beneficio**: Reducir acoplamiento, implementar bajo acoplamiento

### 3. Inversión de Control (IoC)

**Sinónimo**: Principio Hollywood: "No me llames, ya te llamaremos"

**Definición**: Framework llama a código del usuario, no al revés.

**Diferencia**:
- **Librería**: Conjunto de funciones, cliente controla flujo
- **Framework**: Encarna diseño abstracto, cliente inserta comportamiento en puntos predefinidos

**Variaciones**:
- Patrón Método Plantilla
- Inyección de Dependencias
- Eventos con auditores
- Configuración con datos externos

### 4. Inyección de Dependencias

**Concepto**: No es solo IoC, es un estilo específico de IoC donde dependencias se "inyectan" en un objeto.

### 5. Principio de Inversión de Dependencias (DIP)

**Regla**:
- Clases de alto nivel no deben depender de clases de bajo nivel
- Ambas deben depender de abstracciones
- Las abstracciones no deben depender de detalles
- Los detalles deben depender de abstracciones

**Beneficio**: Flexibilidad, bajo acoplamiento, facilita cambios

### 6. Principio Abierto/Cerrado (OCP)

**Definición (Bertrand Meyer)**: Entidades de software deben estar abiertas a extensión pero cerradas a modificación.

**Paradoja**: Parece contradictorio - ¿cómo extender sin modificar?

**Solución**: Usar OOP para crear abstracciones que son fijas pero representan comportamientos ilimitados.
- Abstracciones: clases base abstractas (fijas)
- Comportamientos variables: clases derivadas

**Implementación**:
- No preguntar por tipo de objeto polimórfico
- No usar atributos públicos
- No usar variables globales

**Nota**: No es posible 100% de cierre, debe ser estrategia selectiva basada en probabilidad de cambio.

---

## Diseño de Paquetes

### Definición

Un paquete es una pieza de software reusable y testeable que:
- Provee conjunto de funcionalidades específicas
- Está formado por grupo de clases
- Genera archivo jar, dll, etc.

### Convenciones de Nombres

- **Paquetes**: Sustantivos, minúsculas
- **Clases**: Sustantivos, mayúsculas
- **Métodos**: Verbos, minúsculas
- **Booleanos**: Prefijo `is`

### Principios de Cohesión de Paquetes

#### REP: The Release/Reuse Equivalency Principle
- Un paquete reusable debe ser liberado (release)
- Solo paquetes liberados a través de sistema de tracking pueden reutilizarse efectivamente
- Vienen en "caja negra" (jar, dll)
- Desarrolladores deciden cuándo integrar versiones nuevas

**Herramientas**:
- Java: Maven
- .NET: NuGet
- Ruby: RubyGems/Bundler
- Python: PIP/PyPI
- PHP: Packagist/Composer
- Node.js: NPM

**Criterios para usar paquete externo**:
- Documentación completa, acertada y actualizada
- Mantenimiento: bugs corregidos, mejoras consideradas
- Confiabilidad: no cambios repentinos, mantiene versiones previas

#### CCP: The Common Closure Principle
- Clases que cambian juntas empaquetadas juntas
- Un cambio en un paquete afecta clases dentro
- Objetivo: Minimizar impacto de cambios
- Si clases tienen alto acoplamiento, empaquetarlas juntas
- Beneficio: Al cambiar, afecta pocos paquetes

#### CRP: The Common Reuse Principle
- Clases usadas juntas empaquetadas juntas
- Si reusas una clase, reusas todas
- Análogo a SRP: paquete con múltiples responsabilidades debe partirse
- Beneficio: Evitar dependencias innecesarias

---

## Principios Generales de Diseño

### 1. YAGNI (You Aren't Gonna Need It)

**Definición**: No implementes funcionalidad hasta que realmente sea necesaria.

**Justificación**:
- Características innecesarias son inconvenientes
- Tiempo para agregar, probar, mantener
- Conduce a hinchazón de código
- Restricciones en futuro

**Violaciones**:
- Funcionalidad "por si acaso"
- Difícil de definir completamente sin requisito real
- Puede no funcionar correctamente cuando se necesite
- Desconocida por programadores que podrían usarla
- Restringe qué se puede hacer después

**Nota**: Usar con refactorización continua, TDD, integración continua

### 2. DRY (Don't Repeat Yourself)

**Definición (Hunt & Thomas)**: Cada pieza de conocimiento debe tener representación única, inequívoca y autoritativa dentro del sistema.

**Objetivo**: Reducir repetición de información, facilitar mantenimiento.

**Consecuencia**: Modificación de elemento individual no requiere cambios en elementos lógicamente no relacionados (similar a 1FN en BD).

**Aplicable a**: Programación, esquemas BD, planes de prueba, sistema de construcción, documentación

**Violaciones**:
- Código repetido idéntico
- Código semánticamente repetido con diferentes nombres/orden
- Bloques que podrían sustituirse por llamadas a otros métodos

**Nota**: DRY no significa que nunca haya código parecido - si responden a cosas diferentes, está bien

### 3. KISS (Keep It Simple, Stupid)

**Definición**: Mantener diseño y código lo más simple posible.

**Beneficio**: Menos complejidad, más mantenible, más comprensible.

---

## Relaciones entre Tópicos

### Jerarquía de Principios

```
Código Limpio (Base)
├── Nombrado (Fundamental)
├── Formato (Presentación)
├── Comentarios (Claridad)
└── Descomposición Funcional

Diseño de Métodos
├── Interfaz Suficiente/Completa/Primitiva
├── Cohesión de Métodos
└── Mínima Sorpresa

Diseño de Clases
├── Única Responsabilidad (SRP)
├── Alta Cohesión (GRASP)
├── Bajo Acoplamiento (GRASP)
└── Principio de Experto (GRASP)

Relaciones entre Clases
├── Composición/Agregación
├── Asociación
├── Dependencia
└── Herencia (ISA)

Principios GRASP
├── Asignación de Responsabilidades (Experto, Creador, Controlador)
├── Manejo de Complejidad (Alta Cohesión, Bajo Acoplamiento)
├── Variabilidad (Polimorfismo, Variaciones Protegidas)
└── Apoyo Arquitectónico (Indirección, Fabricación Pura)

Diseño de Herencia
├── Principio de Sustitución (LSP)
├── Herencia vs. Composición
└── Patrones (Template Method, Doble Despacho)

Diseño de Dependencias
├── Leyes de Demeter (Bajo Acoplamiento)
├── Inversión de Control (Framework)
├── Inversión de Dependencias (DIP)
└── Principio Abierto/Cerrado (OCP)

Diseño de Paquetes
├── Cohesión (REP, CCP, CRP)
└── Acoplamiento
```

### Cómo se Conectan

1. **Análisis** identifica clases usando enfoques de clasificación
2. **Relaciones** conectan clases (composición, herencia, asociación)
3. **GRASP** guía asignación de responsabilidades
4. **Código Limpio** asegura calidad del código
5. **Diseño de Métodos** define cómo operan responsabilidades
6. **Diseño de Clases** refina responsabilidades
7. **Diseño de Herencia** organiza jerarquías
8. **Diseño de Dependencias** gestiona acoplamientos
9. **Diseño de Paquetes** organiza en componentes reusables

---

## Patrones Aplicados

### Patrones de Asignación de Responsabilidades

| Patrón | Responsabilidad | Objetivo |
|--------|-----------------|----------|
| Experto | A quien tiene información | Encapsulación, cohesión |
| Creador | A quien contiene/usa | Bajo acoplamiento |
| Controlador | A representante de sistema/caso de uso | Separación de UI |
| Polimorfismo | A tipos donde varía comportamiento | Evitar condicionales |
| Fabricación Pura | A clase auxiliar artificial | Cohesión, acoplamiento |
| Indirección | A intermediario | Desacoplamiento |
| Variaciones Protegidas | A punto de variación | Estabilidad, extensibilidad |

### Patrones de Comportamiento

- **Método Plantilla**: Estructura en base, detalles en derivadas
- **Doble Despacho**: Resolver basado en dos tipos

---

## Conclusión

### Síntesis del Curso

El Análisis y Diseño Orientado a Objetos es un proceso integrado que combina:

1. **Análisis Riguroso**: Entender el dominio del problema, identificar clases y relaciones
2. **Principios Sólidos**: Aplicar GRASP y SOLID para guiar decisiones de diseño
3. **Código de Calidad**: Mantener estándares de código limpio
4. **Arquitectura Mantenible**: Diseñar clases, métodos, herencia y paquetes pensando en cambio

### Principios Clave a Recordar

1. **Responsabilidad Única**: Una clase, un motivo de cambio
2. **Alta Cohesión**: Métodos y clases enfocadas en su propósito
3. **Bajo Acoplamiento**: Dependencias mínimas, máxima independencia
4. **Flexibilidad**: Diseñar para cambios reales, no especulativos (YAGNI)
5. **No Repetir**: Conocimiento único y autoritativo (DRY)
6. **Simplicidad**: Lo más simple que funciona (KISS)
7. **Sustituibilidad**: Subtipos intercambiables (LSP)
8. **Extensibilidad**: Abierto a extensión, cerrado a modificación (OCP)

### Matices Importantes

- **Moderación**: No sobre-diseñar. Los principios son guías, no reglas rígidas
- **Contexto**: Las decisiones dependen del dominio y probabilidad de cambio real
- **Evolución**: El diseño mejora iterativamente; usa refactorización continua
- **Equipo**: La consistencia en un equipo es más importante que la perfección individual
- **Herramientas**: Las herramientas modernas (IDEs, refactorización) facilitan la aplicación de estos principios

### Pregunta Final para Reflexión

Al diseñar cualquier sistema, pregúntate:
> ¿Cuál es la responsabilidad única de esta clase? ¿Quién tiene la información para cumplirla? ¿Cómo minimizar dependencias mientras mantengo cohesión?

Responder estas preguntas correctamente es el corazón del buen diseño orientado a objetos.

---

**Fin del Resumen Comprensivo**

Este documento integra toda la teoría de Análisis y Diseño Orientado a Objetos, desde identificación de clases hasta arquitectura de paquetes, proporcionando una visión holística del proceso de diseño de software de calidad.
