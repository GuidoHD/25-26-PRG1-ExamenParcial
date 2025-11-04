# Examen Parcial - GuidoHD

**Usuario GitHub:** GuidoHD
**Fecha:** 4 de noviembre de 2025
**Retos tenidos en cuenta:** Reto 003

---

## Instrucciones

A continuación encontrarás fragmentos de código extraídos de tus entregas. Cada fragmento contiene una o más situaciones relacionadas con los conceptos vistos en clase.

Para cada pregunta debes:
1) Identificar a qué se refiere la observación
2) Explicar si es o no un error y por qué
3) Proponer la corrección

Nota: Responde 5 de las 9 preguntas (en función a lo indicado en el examen).


---

## Pregunta 1

Archivo: `UnEdificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/1ce0c911d2fddb8930e1a76dea5c498a875b9fe8/entregas/marcos.huidobro/UnEdificio.java) (Reto 003)

```java
final String TEJADO = "               __/\\__\n" +
                      "  |    |    |  |####|  |    |    |  \n" +
                      "====================================";
```

¿Qué observas en este código?



ERROR: he utilizado "\n" para hacer el salto de línea.
En clase hemos utilizado println(); siendo "ln" el salto de línea.

CORRECCIÓN: 

final String PUNTA_TEJADO = "               __/\\__";
final String MEDIO_TEJADO = "  |    |    |  |####|  |    |    |  ";
final String BASE_TEJADO = "====================================";

final String TEJADO = PUNTA_TEJADO + MEDIO_TEJADO + BASE_TEJADO;





---

## Pregunta 2

Archivo: `UnEdificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/1ce0c911d2fddb8930e1a76dea5c498a875b9fe8/entregas/marcos.huidobro/UnEdificio.java) (Reto 003)

```java
for (int dia = 1; dia <= DIAS; dia++) {
    for (int hora = 0; hora < HORAS_POR_DIA; hora++) {
        // ...
    }
}
```

ERROR:
He utilizado "dia++" para añadir 1 a la variable "dia".
He fallado en lo mismo con la variable "hora".
Lo que tendría que haber utilizado sería la expresión "a = a + 1"


CORRECCIÓN:

for (int dia = 1; dia <= DIAS; dia = dia + 1) {
    for (int hora = 0; hora < HORAS_POR_DIA; hora = hora + 1) {
        // ...
    }
}




¿Qué observas en este código?

---

## Pregunta 3

Archivo: `UnEdificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/1ce0c911d2fddb8930e1a76dea5c498a875b9fe8/entregas/marcos.huidobro/UnEdificio.java) (Reto 003)

```java
String fila = ":";
int lado = HABITACIONES / 2;
// ...
fila += ESPACIO_CENTRAL + ":";
```

¿Qué observas en este código?

---

## Pregunta 4

Archivo: `UnEdificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/1ce0c911d2fddb8930e1a76dea5c498a875b9fe8/entregas/marcos.huidobro/UnEdificio.java) (Reto 003)

```java
boolean persiana_abierta = Math.random() < PROBABILIDAD_PERSIANA_ABIERTA;
boolean luz_encendida = Math.random() < PROBABILIDAD_LUZ_ENCENDIDA;
if (persiana_abierta) {
    fila += PERSIANA_ABIERTA;
} else {
    fila += (luz_encendida ? LUZ_ENCENDIDA : LUZ_APAGADA);
}
```

¿Qué observas en este código?

ERROR:
He escrito las variables en formato snake case (aaa_aaa) en vez de en camel case (aaaAaa) como hemos estado viendo en clase.

CORRECCIÓN:

boolean persianaAbierta = Math.random() < PROBABILIDAD_PERSIANA_ABIERTA;
boolean luzEncendida = Math.random() < PROBABILIDAD_LUZ_ENCENDIDA;
if (persianaAbierta) {
    fila += PERSIANA_ABIERTA;
} else {
    fila += (luzEncendida ? LUZ_ENCENDIDA : LUZ_APAGADA);
}





---

## Pregunta 5

Archivo: `UnEdificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/1ce0c911d2fddb8930e1a76dea5c498a875b9fe8/entregas/marcos.huidobro/UnEdificio.java) (Reto 003)

```java
System.out.println("Día " + dia + " - " + (hora < 10 ? "0" + hora : hora) + ":00h\n");
```

¿Qué observas en este código?

---

## Pregunta 6

Archivo: `UnEdificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/1ce0c911d2fddb8930e1a76dea5c498a875b9fe8/entregas/marcos.huidobro/UnEdificio.java) (Reto 003)

```java
for (int numero_planta = PLANTAS; numero_planta >= 1; numero_planta--) {
    String fila = ":";
    int lado = HABITACIONES / 2;
```

¿Qué observas en este código?

---

## Pregunta 7

Archivo: `UnEdificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/1ce0c911d2fddb8930e1a76dea5c498a875b9fe8/entregas/marcos.huidobro/UnEdificio.java) (Reto 003)

```java
for (int i = 0; i < lado; i++) {
    boolean persiana_abierta = Math.random() < PROBABILIDAD_PERSIANA_ABIERTA;
    boolean luz_encendida = Math.random() < PROBABILIDAD_LUZ_ENCENDIDA;
```

¿Qué observas en este código?

ERRORES:
Al igual que antes he utilizado snake_case erróneamente y además he escrito i++ de nuevo en vez de i = i + 1.
Pero el error a comentar es que en vez de llamar a la variable "i", la debería poner un nombre acorde al contexto en el programa.

CORRECCIÓN:

for (int cantidadHabitacionesVistas = 0; cantidadHabitacionesVistas < lado; cantidadHabitacionesVistas = cantidadHabitacionesVistas + 1) {
    boolean persianaAbierta = Math.random() < PROBABILIDAD_PERSIANA_ABIERTA;
    boolean luzEncendida = Math.random() < PROBABILIDAD_LUZ_ENCENDIDA;

Estos cambios ayudan a que el código se entienda mejor sin necesidar de usar un (prohibidísimo) comentario.


---

## Pregunta 8

Archivo: `UnEdificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/1ce0c911d2fddb8930e1a76dea5c498a875b9fe8/entregas/marcos.huidobro/UnEdificio.java) (Reto 003)

```java
final String TEJADO = "               __/\\__\n" + "  |    |    |  |####|  |    |    |  \n" + "====================================";

final String SUELO = "------------------------------------\n" + "     ==========================\n" + "   ==============================\n" + " ==================================\n";
```

¿Qué observas en este código?

---

## Pregunta 9

Archivo: `UnEdificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/1ce0c911d2fddb8930e1a76dea5c498a875b9fe8/entregas/marcos.huidobro/UnEdificio.java) (Reto 003)

```java
if (i < lado - 1) fila += ":";
```

¿Qué observas en este código?


ERRORES:

Al igual que antes he utilizado "+=" y además he escrito i de nuevo en vez de darle un nombre acorde a la variable.
También voy a añadir corchetes para que sea más "bonito".

CORRECIÓN:
if (cantidadHabitacionesVistas < lado - 1){
fila = fila + ":";
}








