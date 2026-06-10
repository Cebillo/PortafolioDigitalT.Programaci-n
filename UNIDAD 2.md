# 📘 Unidad 2 

> **Portafolio de Aprendizaje** · Fundamentos de Programación  
> Autor: *(Tu nombre aquí)*  
> Fecha: Junio 2026

---

## 📑 Tabla de Contenidos

1. [Estructuras Condicionales](#1-estructuras-condicionales)
   - [Tipos de estructuras condicionales](#11-tipos-de-estructuras-condicionales)
   - [Diagrama de flujo](#12-diagrama-de-flujo--condicional)
   - [Pseudocódigo](#13-pseudocódigo--condicional)
2. [Estructuras Repetitivas](#2-estructuras-repetitivas)
   - [Tipos de estructuras repetitivas](#21-tipos-de-estructuras-repetitivas)
   - [Diagrama de flujo](#22-diagrama-de-flujo--repetitiva)
   - [Pseudocódigo](#23-pseudocódigo--repetitiva)
3. [Ejercicio Integrador](#3-ejercicio-integrador)
   - [Planteamiento del problema](#31-planteamiento-del-problema)
   - [Análisis del problema](#32-análisis-del-problema)
   - [Diseño del algoritmo](#33-diseño-del-algoritmo--diagrama-de-flujo)
   - [Codificación](#34-codificación--código-fuente)
   - [Validación](#35-validación--prueba-de-escritorio)
4. [Reflexión Crítica](#4-principales-dificultades-y-reflexión-crítica)

---

## 1. Estructuras Condicionales

Las **estructuras condicionales** permiten que un programa tome decisiones y ejecute distintos bloques de código según si una condición es verdadera o falsa.

---

### 1.1 Tipos de Estructuras Condicionales

#### 🔹 1. Condicional Simple (`if`)

Ejecuta un bloque de instrucciones **solo si** la condición es verdadera. Si la condición es falsa, no hace nada.

```
Si (condición) entonces
    [instrucciones]
Fin Si
```

#### 🔹 2. Condicional Doble (`if - else`)

Evalúa una condición y ejecuta un bloque si es **verdadera**, y otro bloque diferente si es **falsa**. Siempre se ejecuta exactamente uno de los dos bloques.

```
Si (condición) entonces
    [instrucciones si verdadero]
Si no
    [instrucciones si falso]
Fin Si
---

#### 🔹 3. Condicional Múltiple (`if - else if - else`)

Permite evaluar **varias condiciones** en cadena. Se comprueba cada condición en orden; cuando una es verdadera, se ejecuta su bloque y se omiten las demás.

```
Si (condición 1) entonces
    [instrucciones 1]
Si no, si (condición 2) entonces
    [instrucciones 2]
Si no, si (condición 3) entonces
    [instrucciones 3]
Si no
    [instrucciones por defecto]
Fin Si
```

---

#### 🔹 4. Selección por Casos (`switch - case`)

Compara una variable con múltiples valores posibles (**casos**) y ejecuta el bloque correspondiente al valor que coincida. Es una alternativa más clara al `if-else if` cuando se compara la misma variable con valores discretos.

```
Según (variable) hacer
    Caso valor1: [instrucciones]
    Caso valor2: [instrucciones]
    Caso valor3: [instrucciones]
    Por defecto:  [instrucciones]
Fin Según
```

---

### 1.2 Diagrama de Flujo – Condicional

A continuación se presentan los diagramas de flujo para las dos estructuras condicionales más utilizadas:

#### Condicional Simple (`if`)

```
       ┌─────────┐
       │  INICIO │
       └────┬────┘
            │
     ┌──────▼──────┐
     │  Condición  │──── NO ────┐
     └──────┬──────┘            │
           SÍ                   │
            │                   │
    ┌───────▼────────┐          │
    │  Instrucciones │          │
    └───────┬────────┘          │
            │◄───────────────────┘
       ┌────▼────┐
       │   FIN   │
       └─────────┘
```

#### Condicional Doble (`if - else`)

```
            ┌─────────┐
            │  INICIO │
            └────┬────┘
                 │
         ┌───────▼───────┐
    ┌────┤   Condición   ├────┐
   SÍ    └───────────────┘   NO
    │                         │
┌───▼──────────┐     ┌────────▼─────┐
│ Instruc. "V" │     │ Instruc. "F" │
└───┬──────────┘     └────────┬─────┘
    │                         │
    └──────────┬──────────────┘
               │
          ┌────▼────┐
          │   FIN   │
          └─────────┘
```

> 💡 **Simbología usada:**
> - **Óvalo**: Inicio / Fin del algoritmo
> - **Rombo** (`◇`): Condición o decisión (sí/no, verdadero/falso)
> - **Rectángulo**: Instrucción o proceso
> - **Flechas**: Flujo de ejecución

---

### 1.3 Pseudocódigo – Condicional

#### Ejemplo: Determinar si un número es positivo, negativo o cero

```
ALGORITMO ClasificarNumero
    INICIO
        Leer numero

        SI numero > 0 ENTONCES
            Escribir "El número es POSITIVO"
        SINO SI numero < 0 ENTONCES
            Escribir "El número es NEGATIVO"
        SINO
            Escribir "El número es CERO"
        FIN SI

    FIN
FIN ALGORITMO
```

---

## 2. Estructuras Repetitivas

Las **estructuras repetitivas** (también llamadas *bucles* o *ciclos*) permiten ejecutar un conjunto de instrucciones **varias veces** mientras se cumpla una condición. Evitan la repetición manual de código y permiten procesar colecciones de datos.

---

### 2.1 Tipos de Estructuras Repetitivas

#### 🔄 1. Bucle `while` (Mientras)

Repite un bloque de instrucciones **mientras** la condición sea verdadera. La condición se evalúa **antes** de ejecutar el bloque, por lo que si la condición es falsa desde el inicio, el bloque nunca se ejecuta.

- **Tipo:** Bucle con condición de entrada (precondicional)
- **Uso:** Cuando no se sabe de antemano cuántas veces se repetirá

```
Mientras (condición) hacer
    [instrucciones]
Fin Mientras
```

---

#### 🔄 2. Bucle `do - while` (Hacer - Mientras)

Ejecuta el bloque de instrucciones **al menos una vez** y luego repite **mientras** la condición sea verdadera. La condición se evalúa **después** de ejecutar el bloque.

- **Tipo:** Bucle con condición de salida (postcondicional)
- **Uso:** Cuando se necesita garantizar al menos una ejecución (ej. menús)

```
Hacer
    [instrucciones]
Mientras (condición)
```

---

#### 🔄 3. Bucle `for` (Para)

Repite un bloque un número **determinado** de veces, controlado por un contador con valor inicial, condición de parada e incremento.

- **Tipo:** Bucle con contador (número de repeticiones conocido)
- **Uso:** Cuando se conoce de antemano cuántas iteraciones se necesitan

```
Para i = valorInicial hasta valorFinal con paso N hacer
    [instrucciones]
Fin Para
```

---

#### Comparativa de los tres tipos

| Característica      | `while`          | `do-while`        | `for`              |
|---------------------|-----------------|-------------------|--------------------|
| Evaluación condición | Antes del bloque | Después del bloque | Antes del bloque   |
| Ejecuciones mínimas | 0               | 1                 | 0                  |
| Contador explícito  | Manual           | Manual            | Incorporado        |
| Iteraciones conocidas | No necesario  | No necesario      | Sí (generalmente) |

---

### 2.2 Diagrama de Flujo – Repetitiva

#### Bucle `while` (condición al inicio)

```
       ┌─────────┐
       │  INICIO │
       └────┬────┘
            │
     ┌──────▼──────┐
┌────┤  Condición  ├──── NO ──► FIN
│    └─────────────┘
SÍ
│
│   ┌────────────────┐
└──►│  Instrucciones │
    └────────┬───────┘
             │
             └────────────────┘ (vuelve a la condición)
```

#### Bucle `do-while` (condición al final)

```
       ┌─────────┐
       │  INICIO │
       └────┬────┘
            │
   ┌────────▼────────┐
   │  Instrucciones  │◄────────┐
   └────────┬────────┘         │
            │                  │
     ┌──────▼──────┐           │
     │  Condición  │───SÍ──────┘
     └──────┬──────┘
           NO
            │
       ┌────▼────┐
       │   FIN   │
       └─────────┘
```

#### Bucle `for` (con contador)

```
       ┌─────────┐
       │  INICIO │
       └────┬────┘
            │
   ┌────────▼────────┐
   │  i = valorInicial│
   └────────┬────────┘
            │
     ┌──────▼──────┐
┌────┤  i <= límite ├──── NO ──► FIN
│    └─────────────┘
SÍ
│
│   ┌────────────────┐
└──►│  Instrucciones │
    └────────┬───────┘
             │
    ┌────────▼────────┐
    │    i = i + paso  │
    └────────┬────────┘
             └──────────────────┘ (vuelve a la condición)
```

---

### 2.3 Pseudocódigo – Repetitiva

#### Ejemplo con `while`: Leer números hasta ingresar 0

```
ALGORITMO LeerHastaCero
    INICIO
        Leer numero

        MIENTRAS numero ≠ 0 HACER
            Escribir "Número ingresado: ", numero
            Leer numero
        FIN MIENTRAS

        Escribir "Fin del programa"
    FIN
FIN ALGORITMO
```

#### Ejemplo con `for`: Mostrar la tabla de multiplicar de un número

```
ALGORITMO TablaMultiplicar
    INICIO
        Leer n

        PARA i = 1 HASTA 10 CON PASO 1 HACER
            Escribir n, " x ", i, " = ", n * i
        FIN PARA
    FIN
FIN ALGORITMO
```

---

## 3. Ejercicio Integrador

### 3.1 Planteamiento del Problema

> **Enunciado:**
> Desarrollar un programa que permita ingresar las calificaciones de **N estudiantes**. Para cada estudiante, el programa debe leer su nombre y su nota (de 0 a 10), determinar si **aprobó o reprobó** (aprueba con nota ≥ 7), y al final mostrar:
> - El promedio general del grupo
> - La nota más alta obtenida
> - El número de estudiantes aprobados y reprobados

---

### 3.2 Análisis del Problema

#### Entradas (datos que recibe el programa)
| Variable | Tipo | Descripción |
|----------|------|-------------|
| `n` | Entero | Cantidad de estudiantes |
| `nombre` | Cadena | Nombre del estudiante |
| `nota` | Real | Calificación del estudiante (0.0 – 10.0) |

#### Salidas (resultados que produce el programa)
| Variable | Tipo | Descripción |
|----------|------|-------------|
| `promedio` | Real | Promedio general del grupo |
| `notaMaxima` | Real | Calificación más alta del grupo |
| `aprobados` | Entero | Cantidad de estudiantes que aprobaron |
| `reprobados` | Entero | Cantidad de estudiantes que reprobaron |

#### Variables auxiliares
| Variable | Tipo | Descripción |
|----------|------|-------------|
| `suma` | Real | Acumulador de notas para calcular el promedio |
| `i` | Entero | Contador del bucle |

#### Condiciones y restricciones
- La nota debe estar en el rango `[0, 10]`
- Un estudiante **aprueba** si su nota es `>= 7`
- La cantidad de estudiantes `n` debe ser `> 0`

---

### 3.3 Diseño del Algoritmo – Diagrama de Flujo

```
                    ┌──────────────────┐
                    │      INICIO      │
                    └────────┬─────────┘
                             │
                    ┌────────▼─────────┐
                    │  Leer n          |
                    └────────┬─────────┘
                             │
                    ┌────────▼──────────────────────┐
                    │ suma=0, aprobados=0,          |
                    │ reprobados=0, notaMaxima=0,   |
                    │ i=1                           |
                    └────────┬──────────────────────┘
                             │
                    ┌────────▼─────────┐
               ┌────┤     i <= n       ├──── NO ────────────┐
               SÍ   └──────────────────┘                     │
               │                                             |
     ┌─────────▼──────────┐                                  │
     │ Leer nombre, nota  │                                  │
     └─────────┬──────────┘                                  │
               │                                             |
     ┌─────────▼──────────┐                                  │ 
     │ suma = suma + nota |                                  |
     └─────────┬──────────┘                                  │
               │                                             |
     ┌─────────▼──────────┐                                  │
     │  nota > notaMaxima │──SÍ──► notaMaxima = nota         │
     └─────────┬──────────┘                                  │
               │                                             |
     ┌─────────▼──────────┐                                  │
┌────┤     nota >= 7       ├──── NO ────┐                    │ 
SÍ   └────────────────────┘             │                    | 
│                                       │                    │
▼                                       ▼                    │
aprobados++                       reprobados++               │
│                                       │                    │
└──────────────┬────────────────────────┘                    │
               │                                             |
     ┌─────────▼──────────┐                                  │
     │     i = i + 1      │                                  │
     └─────────┬──────────┘                                  │
               └──────────────────────────┘ (vuelve)         │
                    ┌────────▼──────────────────────┐◄───────┘
                    │ promedio = suma / n           |
                    └────────┬──────────────────────┘
                             │
                    ┌────────▼──────────────────────┐
                    │ Mostrar promedio, notaMaxima,  │
                    │ aprobados, reprobados          │
                    └────────┬──────────────────────┘
                             │
                    ┌────────▼─────────┐
                    │       FIN        │
                    └──────────────────┘
```

---

### 3.4 Codificación – Código Fuente

> **Lenguaje:** Python 3

```python
# ============================================================
# Programa: Calificaciones de Estudiantes
# Descripción: Lee notas de N estudiantes, determina si
#              aprobaron o reprobaron y muestra estadísticas.
# Autor: (Tu nombre)
# Fecha: Junio 2026
# ============================================================

def main():
    # --- Entrada de datos ---
    n = int(input("Ingrese el número de estudiantes: "))

    # --- Inicialización de variables ---
    suma = 0
    aprobados = 0
    reprobados = 0
    nota_maxima = 0

    # --- Estructura repetitiva: FOR ---
    for i in range(1, n + 1):
        print(f"\n--- Estudiante {i} ---")
        nombre = input("Nombre del estudiante: ")
        nota = float(input(f"Nota de {nombre} (0-10): "))

        # Validación del rango de la nota
        while nota < 0 or nota > 10:
            print("⚠ Error: La nota debe estar entre 0 y 10.")
            nota = float(input(f"Ingrese nuevamente la nota de {nombre}: "))

        # Acumulamos la suma para el promedio
        suma += nota

        # Actualizamos la nota máxima
        if nota > nota_maxima:
            nota_maxima = nota

        # --- Estructura condicional: IF-ELSE ---
        if nota >= 7:
            print(f"✅ {nombre} APROBÓ con nota {nota:.1f}")
            aprobados += 1
        else:
            print(f"❌ {nombre} REPROBÓ con nota {nota:.1f}")
            reprobados += 1

    # --- Cálculo del promedio ---
    promedio = suma / n

    # --- Resultados finales ---
    print("\n" + "=" * 45)
    print("         📊 RESULTADOS FINALES")
    print("=" * 45)
    print(f"  Total de estudiantes : {n}")
    print(f"  Promedio del grupo   : {promedio:.2f}")
    print(f"  Nota mas alta        : {nota_maxima:.1f}")
    print(f"  Estudiantes aprobados: {aprobados}")
    print(f"  Estudiantes reprobados: {reprobados}")
    print("=" * 45)

# Punto de entrada del programa
if __name__ == "__main__":
    main()
```

---

### 3.5 Validación – Prueba de Escritorio

Se ejecuta el programa con **3 estudiantes** como caso de prueba para verificar que los resultados sean correctos.

#### Datos de entrada de la prueba

| # | Nombre  | Nota | ¿Aprueba? |
|---|---------|------|-----------|
| 1 | Ana     | 8.5  | ✅ Sí     |
| 2 | Carlos  | 5.0  | ❌ No     |
| 3 | Lucía   | 7.0  | ✅ Sí     |

#### Seguimiento paso a paso de las variables

| Iteración | nombre  | nota | suma  | nota_maxima | aprobados | reprobados |
|-----------|---------|------|-------|-------------|-----------|------------|
| Inicio    | –       | –    | 0     | 0           | 0         | 0          |
| i = 1     | Ana     | 8.5  | 8.5   | 8.5         | 1         | 0          |
| i = 2     | Carlos  | 5.0  | 13.5  | 8.5         | 1         | 1          |
| i = 3     | Lucía   | 7.0  | 20.5  | 8.5         | 2         | 1          |

#### Cálculo del promedio

```
promedio = suma / n = 20.5 / 3 = 6.83
```

#### Salida esperada en consola

```
--- Estudiante 1 ---
Nombre del estudiante: Ana
Nota de Ana (0-10): 8.5
✅ Ana APROBÓ con nota 8.5

--- Estudiante 2 ---
Nombre del estudiante: Carlos
Nota de Carlos (0-10): 5.0
❌ Carlos REPROBÓ con nota 5.0

--- Estudiante 3 ---
Nombre del estudiante: Lucía
Nota de Lucía (0-10): 7.0
✅ Lucía APROBÓ con nota 7.0

=============================================
         📊 RESULTADOS FINALES
=============================================
  Total de estudiantes : 3
  Promedio del grupo   : 6.83
  Nota más alta        : 8.5
  Estudiantes aprobados: 2
  Estudiantes reprobados: 1
=============================================
```

#### ✔ Verificación de correctitud

| Resultado esperado       | Valor calculado | ¿Correcto? |
|--------------------------|-----------------|------------|
| Promedio = 6.83          | 6.83            | ✅         |
| Nota máxima = 8.5        | 8.5             | ✅         |
| Aprobados = 2            | 2               | ✅         |
| Reprobados = 1           | 1               | ✅         |

---

## 4. Principales Dificultades y Reflexión Crítica

### 🚧 Dificultades encontradas

#### 1. Comprensión de las condiciones en los bucles
Al inicio resultó confuso entender la diferencia entre un bucle `while` (que puede no ejecutarse nunca) y un `do-while` (que siempre se ejecuta al menos una vez). Elegir el tipo incorrecto puede generar errores lógicos difíciles de detectar.

### 💡 Reflexión Crítica

El estudio de las estructuras condicionales y repetitivas marcó un punto de inflexión en mi comprensión de la programación. Antes de esta unidad, los programas que podía escribir eran secuenciales y limitados; ahora comprendo que la lógica real de cualquier sistema está construida sobre decisiones y repeticiones.

**Lo más valioso** fue aprender que el diseño del algoritmo tanto en pseudocódigo como en diagrama de flujo debe hacerse **antes** de escribir código. Cuando se salta este paso y se va directamente a programar, el código tiende a ser desordenado y lleno de errores difíciles de corregir.

**El mayor aprendizaje** fue que los errores lógicos son más peligrosos que los errores de sintaxis: el programa puede ejecutarse sin mensajes de error pero producir resultados completamente incorrectos. La prueba de escritorio es una herramienta esencial para detectar estos errores antes de la ejecución.


> *"Un algoritmo bien diseñado es la mitad del problema resuelto."*

---

## 📚 Referencias

- Joyanes Aguilar, L. (2008). *Fundamentos de Programación: Algoritmos, Estructura de Datos y Objetos* (4.ª ed.). McGraw-Hill.
- Cormen, T. H., et al. (2009). *Introduction to Algorithms* (3.ª ed.). MIT Press.
- Python Software Foundation. (2024). *Python 3 Documentation*. https://docs.python.org/3/

---

*📁 Portafolio académico — Unidad 2 | Fundamentos de Programación*
