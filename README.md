
#resolucion de ejercicio propio.

# AlgoCultivos

Una empresa agropecuaria desea desarrollar un sistema para evaluar la eficiencia de parcelas de cultivo. Esta eficiencia depende de los cultivos sembrados y del método de riego utilizado. El sistema debe permitir evaluar la productividad global de una parcela y ser fácilmente extensible para incorporar nuevos factores en el futuro, como fertilizantes, clima, tipo de suelo, etc.

## Descripción general

Una **Parcela** tiene una lista de **Cultivos** y un **Método de Riego**.

Cada **Cultivo** tiene un nombre y una productividad base (un valor entre 0 y 100).

El **Método de Riego** puede aumentar o disminuir la productividad base de cada cultivo.

La eficiencia de una parcela se calcula como el **promedio** de las productividades ajustadas de sus cultivos.

El método de riego debe poder cambiarse dinámicamente, sin acoplar la clase `Parcela` a una implementación concreta.

## Métodos de riego

Se desea representar los métodos de riego de manera que puedan ser fácilmente intercambiables. Se definen como estrategias que modifican la productividad de un cultivo.

### Riego por Goteo

- Aumenta la productividad en un 10%.

### Riego por Inundación

- Disminuye la productividad en un 20%.

### Riego Natural (lluvia)

- No modifica la productividad.

> El sistema debe permitir agregar nuevos tipos de riego en el futuro sin modificar la lógica de `Parcela`.

## Futuras extensiones

En versiones futuras se podrían incluir:
- Fertilización (afecta la productividad base).
- Clima (puede afectar de forma variable según la estación).
- Compatibilidad entre cultivos en una misma parcela.

## Casos de uso

### Caso 1

Una parcela con:
- Cultivo: “Soja”, productividad base 80.
- Cultivo: “Maíz”, productividad base 90.
- Riego por Goteo.

La eficiencia debe ser:  
`((80 * 1.1) + (90 * 1.1)) / 2 = (88 + 99) / 2 = 93.5`

### Caso 2

Misma parcela, pero se cambia el método a **Riego por Inundación**.

La eficiencia debe ser:  
`((80 * 0.8) + (90 * 0.8)) / 2 = (64 + 72) / 2 = 68.0`

## Se pide

- Realizar un **diagrama de clases** completo que represente el modelo propuesto.
- Realizar **diagramas de secuencia** para los dos casos de uso indicados (calculando eficiencia antes y después de cambiar el riego).
- El diseño debe contemplar el principio de **abierto/cerrado** y aplicar un **patrón de diseño apropiado** (como Strategy).

