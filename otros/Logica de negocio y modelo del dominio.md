Muy buena pregunta 👌 porque suele haber confusión entre **lógica de negocio** y **modelo del dominio**, ya que ambos están en el corazón de un sistema orientado a objetos.

---

# 📌 Diferencia entre **Lógica de Negocio** y **Modelo del Dominio**

## 🔹 Modelo del Dominio

- **Definición:**  
    Es la **representación conceptual del negocio** en términos de clases, atributos, relaciones y reglas fundamentales.
    
- **Propósito:**  
    Captura **qué es el negocio** y **cómo se estructura** (conceptos, entidades, asociaciones).
    
- **En qué se centra:**  
    En el **lenguaje ubicuo** (conceptos entendidos tanto por devs como por expertos del negocio).
    
- **Ejemplo:**  
    En un sistema bancario:
    
    - Entidades: `Cliente`, `Cuenta`, `Transacción`.
        
    - Relaciones: un `Cliente` puede tener varias `Cuentas`, una `Cuenta` puede tener varias `Transacciones`.
        

👉 Es más **estático y conceptual**. Define el "mapa" del negocio.

---

## 🔹 Lógica de Negocio

- **Definición:**  
    Es el **conjunto de reglas, procesos y operaciones** que rigen cómo funcionan las entidades del modelo dentro del sistema.
    
- **Propósito:**  
    Captura **qué hace el negocio** y **cómo se comporta**.
    
- **En qué se centra:**  
    En los **procesos y reglas dinámicas** que manipulan el modelo del dominio.
    
- **Ejemplo (en el mismo sistema bancario):**
    
    - Regla: una `Cuenta` no puede quedar con saldo negativo si es de tipo _Ahorro_.
        
    - Proceso: cuando se realiza una `Transacción` de débito, se valida el saldo.
        
    - Lógica: aplicar una comisión si una transferencia supera cierto monto.
        

👉 Es más **dinámico y funcional**. Define el "comportamiento" del negocio.

---

## ⚖️ Comparación directa

|Aspecto|Modelo del Dominio|Lógica de Negocio|
|---|---|---|
|**Qué es**|Representación conceptual de entidades y relaciones.|Reglas y procesos que manipulan esas entidades.|
|**Naturaleza**|Estático (estructura, conceptos).|Dinámico (comportamientos, validaciones, operaciones).|
|**Ejemplo bancario**|`Cuenta`, `Cliente`, `Transacción`.|No permitir sobregiros, aplicar comisiones.|
|**Pregunta clave**|¿Qué entidades existen en el negocio?|¿Qué reglas gobiernan a esas entidades?|

---

## ✅ Ejemplo en código (Java simplificado)

### Modelo del dominio:

```java
public class Cuenta {
    private String numero;
    private double saldo;

    public Cuenta(String numero, double saldoInicial) {
        this.numero = numero;
        this.saldo = saldoInicial;
    }

    public String getNumero() { return numero; }
    public double getSaldo() { return saldo; }
}
```

### Lógica de negocio:

```java
public class ServicioCuenta {

    public void debitar(Cuenta cuenta, double monto) {
        if (cuenta.getSaldo() - monto < 0) {
            throw new IllegalArgumentException("Saldo insuficiente");
        }
        // Aplica el débito
        // (en un modelo real, Cuenta debería encapsular esto)
    }

    public void transferir(Cuenta origen, Cuenta destino, double monto) {
        debitar(origen, monto);
        // acreditar en destino...
    }
}
```

- **`Cuenta`** → parte del **modelo del dominio** (qué es una cuenta).
    
- **`ServicioCuenta`** → contiene la **lógica de negocio** (cómo se usa la cuenta bajo reglas del banco).
    

---

👉 Una forma sencilla de recordarlo:

- **Modelo del dominio = sustantivos** del negocio.
    
- **Lógica de negocio = verbos** que actúan sobre esos sustantivos.
    

---

