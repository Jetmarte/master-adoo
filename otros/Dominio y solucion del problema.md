En **Análisis y Diseño Orientado a Objetos (ADOO)**, estos dos conceptos son **clave** y suelen confundirse, así que vamos paso a paso y con ejemplos claros.

---

## 🔹 Dominio del problema

El **dominio del problema** describe **qué es el problema en el mundo real**, **sin pensar todavía en software ni en código**.

👉 Se enfoca en:

- El **negocio o contexto real**
    
- Las **reglas del negocio**
    
- Los **conceptos reales** que existen
    
- El **lenguaje del usuario o del experto del dominio**
    

💡 Pregunta clave:

> **¿Qué está pasando en la realidad y qué se quiere lograr?**

### Ejemplo

Sistema para una **biblioteca**:

Dominio del problema:

- Libros
    
- Usuarios
    
- Préstamos
    
- Devoluciones
    
- Multas
    
- Reglas:
    
    - Un usuario puede prestar máximo 3 libros
        
    - Un préstamo dura 7 días
        

🚫 Aquí **NO** hablamos de:

- Bases de datos
    
- Clases
    
- APIs
    
- Frameworks
    

---

## 🔹 Solución del problema

La **solución del problema** describe **cómo vamos a resolver ese problema usando software**.

👉 Se enfoca en:

- Diseño del sistema
    
- Arquitectura
    
- Clases
    
- Métodos
    
- Patrones
    
- Tecnologías
    

💡 Pregunta clave:

> **¿Cómo vamos a construir el sistema para resolver el problema?**

### Ejemplo

Solución del problema para la biblioteca:

- Clases: `Libro`, `Usuario`, `Prestamo`
    
- Métodos: `prestarLibro()`, `devolverLibro()`
    
- Base de datos para almacenar libros y préstamos
    
- API REST para gestionar operaciones
    

---

## 🔹 Diferencias clave

|Dominio del problema|Solución del problema|
|---|---|
|Mundo real|Mundo del software|
|Qué se necesita|Cómo se implementa|
|Reglas del negocio|Diseño técnico|
|Lenguaje del usuario|Lenguaje del programador|
|Independiente de tecnología|Dependiente de tecnología|

---

## 🔹 En ADOO, ¿por qué es importante separarlos?

Porque:

- Evita **mezclar requisitos con código**
    
- Permite entender bien el problema antes de programar
    
- Facilita cambios (el negocio cambia más que el código)
    
- Mejora el diseño orientado a objetos
    

👉 En ADOO primero se **analiza el dominio**  
👉 Luego se **diseña la solución**

---

## 🔹 Frase para memorizar (muy usada en exámenes)

> **El dominio del problema describe la realidad que se quiere modelar, mientras que la solución del problema describe el software que se construye para resolverla.**

