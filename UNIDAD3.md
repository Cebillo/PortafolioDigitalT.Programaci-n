# Unidad 3

### 1. Modularidad

La modularidad es la práctica de dividir un programa grande en partes más pequeñas llamadas funciones o módulos, cada una encargada de resolver una tarea específica. Esto ayuda a que el código sea más fácil de leer, de corregir y de reutilizar, en lugar de tener todo el programa escrito de corrido en una sola parte.

Cuando se llama a una función y se le pasan datos, existen dos formas principales de hacerlo:

- **Paso por valor:** se envía una copia del dato. Si la función modifica ese valor dentro de sí misma, el cambio no afecta a la variable original que está fuera de la función.
- **Paso por referencia:** en vez de enviar una copia, se envía la dirección de memoria de la variable (en C esto se hace con punteros). Así, cualquier cambio que se haga dentro de la función sí afecta a la variable original.

Esta diferencia es importante porque, dependiendo de lo que se necesite hacer, hay que elegir bien qué tipo de paso de parámetro usar. Si solo se necesita leer un dato, basta con pasarlo por valor. Pero si la función tiene que modificar el valor original (por ejemplo, para intercambiar dos números), se necesita el paso por referencia.

**Ejemplo en C:**

```c
#include <stdio.h>

// Función que recibe el parámetro por valor
void duplicarPorValor(int numero) {
    numero = numero * 2;
    printf("Dentro de la funcion (por valor): %d\n", numero);
}

// Función que recibe el parámetro por referencia (usando un puntero)
void duplicarPorReferencia(int *numero) {
    *numero = *numero * 2;
    printf("Dentro de la funcion (por referencia): %d\n", *numero);
}

int main() {
    int a = 5;
    int b = 5;

    duplicarPorValor(a);
    printf("Despues de la llamada por valor, a sigue siendo: %d\n", a);

    duplicarPorReferencia(&b);
    printf("Despues de la llamada por referencia, b cambio a: %d\n", b);

    return 0;
}
```

**Salida esperada:**

```
Dentro de la funcion (por valor): 10
Despues de la llamada por valor, a sigue siendo: 5
Dentro de la funcion (por referencia): 10
Despues de la llamada por referencia, b cambio a: 10
```

Como se ve en el ejemplo, `a` no cambia porque solo se envió una copia. En cambio, `b` sí cambia porque la función recibió la dirección de memoria de la variable y trabajó directamente sobre ella.

---

### 2. Arreglos

Un arreglo (o array) es una estructura que permite guardar varios datos del mismo tipo bajo un solo nombre, ubicados en posiciones consecutivas de memoria y accesibles mediante índices. Son útiles cuando se necesita manejar muchos valores relacionados sin tener que crear una variable distinta para cada uno.

Existen varios tipos de arreglos según su número de dimensiones:

- **Unidimensional (vector):** una sola fila de datos, se accede con un solo índice.
- **Bidimensional (matriz):** filas y columnas, se accede con dos índices.
- **Multidimensional:** tres o más dimensiones, útil para representar datos más complejos (por ejemplo, información organizada por categoría, fila y columna al mismo tiempo).

**Ejemplo de arreglo unidimensional:**

```c
#include <stdio.h>

int main() {
    int notas[5] = {8, 7, 9, 6, 10};
    int suma = 0;

    for (int i = 0; i < 5; i++) {
        suma += notas[i];
    }

    printf("Promedio de notas: %.2f\n", suma / 5.0);

    return 0;
}
```

**Ejemplo de arreglo bidimensional (matriz):**

```c
#include <stdio.h>

int main() {
    int matriz[2][3] = {
        {1, 2, 3},
        {4, 5, 6}
    };

    for (int fila = 0; fila < 2; fila++) {
        for (int col = 0; col < 3; col++) {
            printf("%d ", matriz[fila][col]);
        }
        printf("\n");
    }

    return 0;
}
```

**Ejemplo de arreglo multidimensional (tridimensional):**

```c
#include <stdio.h>

int main() {
    // Representa, por ejemplo, 2 bodegas, cada una con 2 estantes y 2 productos por estante
    int inventario[2][2][2] = {
        { {5, 3}, {8, 2} },
        { {6, 1}, {4, 7} }
    };

    for (int bodega = 0; bodega < 2; bodega++) {
        printf("Bodega %d:\n", bodega + 1);
        for (int estante = 0; estante < 2; estante++) {
            for (int producto = 0; producto < 2; producto++) {
                printf("  Estante %d, Producto %d: %d unidades\n",
                       estante + 1, producto + 1, inventario[bodega][estante][producto]);
            }
        }
    }

    return 0;
}
```

---

### 3. Principales dificultades y reflexión crítica

Al principio me costó entender bien la diferencia entre paso por valor y paso por referencia, sobre todo porque en C hay que usar punteros y al inicio no tenía muy claro cuándo poner el `*` o el `&`. Tuve que hacer varias pruebas cambiando el código para ver realmente qué pasaba con las variables antes y después de llamar a la función, y ahí fue cuando entendí la diferencia de verdad, no solo de memoria.

Con los arreglos, la parte que más se me complicó fue el manejo de índices en las matrices y en el arreglo tridimensional, porque es fácil perderse contando filas, columnas y niveles, y terminar con un error de índice fuera de rango. Me ayudó bastante dibujar en papel cómo se organiza la memoria antes de escribir el código.

---
## Aprendizaje de la Unidad
Esta unidad me hizo ver por qué es importante organizar el código en funciones y no escribir todo junto: cuando algo falla, es mucho más fácil revisar una función pequeña que buscar el error en un programa entero.

## Conclusiones generales

Con estas tres unidades pude ir avanzando desde las estructuras básicas de un programa (condicionales y repetitivas) hasta temas más de organización del código, como la modularidad y el manejo de arreglos. Creo que lo más valioso fue entender que programar no es solo hacer que el código funcione, sino organizarlo de una forma que otra persona (o yo mismo más adelante) pueda entenderlo sin problema. La práctica constante con ejemplos y errores fue lo que más me ayudó a fijar los conceptos.

---
---

## Declaración de uso de la IA generativa
Se hizo uso de la IA como apoyo para realizar una parte del codgio en github y para comprobar si el portafolio estaba bien estructurado.

[📘Carátula](CARÁTULA.md)
