# Examen Parcial - sergiofernandez1-hue

**Usuario GitHub:** sergiofernandez1-hue
**Fecha:** 4 de noviembre de 2025
**Retos tenidos en cuenta:** Reto 002

---

## Instrucciones

A continuación encontrarás fragmentos de código extraídos de tus entregas. Cada fragmento contiene una o más situaciones relacionadas con los conceptos vistos en clase.

Para cada pregunta debes:
1) Identificar a qué se refiere la observación
2) Explicar si es o no un error y por qué
3) Proponer la corrección

Nota: Responde 5 de las 10 preguntas (en función a lo indicado en el examen).


---

## Pregunta 1

Archivo: `Batalla Extendida.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/a15cf8e4fdd5b0802206f86a21acbc3c90357a6a/entregas/sergio.fernandez/reto-002/Batalla%20Extendida.java) (Reto 002)

```java
class batallaExtendida {
    public static void main(String[] args) {
        // ...
    }
}
```

¿Qué observas en este código?

---

## Pregunta 2

Archivo: `Batalla Extendida.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/a15cf8e4fdd5b0802206f86a21acbc3c90357a6a/entregas/sergio.fernandez/reto-002/Batalla%20Extendida.java) (Reto 002)

```java
switch (ataqueElegidoGuerrero){
  case 1 -> { /* ... */ }
  case 2 -> { /* ... */ }
  case 3 -> { /* ... */ }
}
if (vidaVampiro <= 0){
    vampiroVivo = false;
}
```

¿Qué observas en este código?

#### En este código podemos ver el uso de switch, en este caso tiene el objetivo de, en función del ataque elegido (1, 2 o 3), ejecutar la parte del código relacionada con dicho ataque relacionada con el daño que hace y la probabilidad que tiene de acertar. 

#### Tras atacar se comprueba si el enemigo ha sido abatido o no, para ello se usa un if y las variables vidaVampiro y vampiroVivo. En este caso si la vida del enemigo llega a 0 o menos el if se encargará de que la variable vampiroVivo pase a ser falsa.

---

## Pregunta 3

Archivo: `Batalla Extendida.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/a15cf8e4fdd5b0802206f86a21acbc3c90357a6a/entregas/sergio.fernandez/reto-002/Batalla%20Extendida.java) (Reto 002)

```java
eleccionAtaqueVampiro = Math.random();
if (eleccionAtaqueVampiro <= PROBABILIDAD_ELECCION_ATAQUE_1){
    // ...
} else if (eleccionAtaqueVampiro >= PROBABILIDAD_ELECCION_ATAQUE_1 && eleccionAtaqueVampiro <= PROBABILIDAD_ELECCION_ATAQUE_2){
    // ...
} else {
    // ...
}
```

¿Qué observas en este código?

#### Este código tiene la función de elegir que ataque realizará el vampiro, el cual tiene a elegir entre tres ataques distintos, cada uno con un daño y probabilidad de acertar distintos. Para ello se usan las constantes PROBABILIDAD_ELECCION_ATAQUE_1 y PROBABILIDAD_ELECCION_ATAQUE_2. El código se divide en 4 partes:

#### - En primer lugar se calcula un número aleatorio entre 0 y 1, que es asignado a la variable eleccionAtaqueVampiro.

#### - En segundo lugar se comprueba si eleccionAtaqueVampiro ha sido menor que PROBABILIDAD_ELECCION_ATAQUE_1, en ese caso ese será el ataque elegido.

#### - En caso de que no haya sido menor que PROBABILIDAD_ELECCION_ATAQUE_1 se comprueba si ha sido menor que PROBABILIDAD_ELECCION_ATAQUE_2 y mayor que PROBABILIDAD_ELECCION_ATAQUE_1, si ha sido asi el segundo ataque será elegido.

#### - En caso de que ninguno de estos casos se dé se elige el tercer ataque.

#### Una forma más limpia de escribir este código sería la siguiente:

```java
eleccionAtaqueVampiro = Math.random();
if (eleccionAtaqueVampiro <= PROBABILIDAD_ELECCION_ATAQUE_1){
    // ...
} else if (eleccionAtaqueVampiro <= PROBABILIDAD_ELECCION_ATAQUE_2){
    // ...
} else {
    // ...
}
```
#### En ella eliminamos que, en el else if, se compruebe que el número haya sido mayor que PROBABILIDAD_ELECCION_ATAQUE_1, ya que en el primer if comprobamos si es menor, y si no es así el número debe ser mayor, sin necesidad de comprobarlo.


---

## Pregunta 4

Archivo: `batalla.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/a15cf8e4fdd5b0802206f86a21acbc3c90357a6a/entregas/sergio.fernandez/reto-002/batalla.java) (Reto 002)

```java
if (caballeroVivo == true){ /* ... */ }
// ...
if (vampiroVivo == true){ /* ... */ }
```

¿Qué observas en este código?

#### En este código observamos que cuando le toca el turno a un personaje, primero vemos si sige vivo o no, y si es así se ejecuta el código relacionado con su turno. 

#### Podemos mejorar este código del siguiente modo:

```java
if (caballeroVivo){ /* ... */ }
// ...
if (vampiroVivo){ /* ... */ }
```

#### En esta corrección eliminamos que se compruebe si caballeroVivo o vampiroVivo son verdaderas, ya que al ser variables booleanas no es necesario comprobarlo.

---

## Pregunta 5

Archivo: `batalla.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/a15cf8e4fdd5b0802206f86a21acbc3c90357a6a/entregas/sergio.fernandez/reto-002/batalla.java) (Reto 002)

```java
System.out.println("Turno del guerrero, con " + vidaGuerrero + " puntos de vida");
// ... lógica de turno y fin de lazo
if (vidaGuerrero <= 0 || vidaVampiro <= 0) {
    algunMuerto = true;
}
```

¿Qué observas en este código?

#### En este código se comprueba si la vida de alguno de los dos personajes ha llegado a 0 o menos que 0, en cuyo caso la variable algunMuerto pasa a ser verdadera, lo que hace que se termine la batalla.

#### Este código se puede escribir de formal más clara de la siguiente forma:

```java
System.out.println("Turno del guerrero, con " + vidaGuerrero + " puntos de vida");
// ... lógica de turno y fin de lazo
if (!guerreroVivo || !vampiroVivo) {
    algunMuerto = true;
}
```

#### En esta corrección usamos las variables guerreroVivo y vampiroVivo negadas para comprobar si hay algun muerto, ya que si por ejemplo el guerrero muere guerreroVivo pasaría a ser falso, al negarla sería verdadera lo que ejecutaría el código dentro del if.

---

## Pregunta 6

Archivo: `batalla.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/a15cf8e4fdd5b0802206f86a21acbc3c90357a6a/entregas/sergio.fernandez/reto-002/batalla.java) (Reto 002)

```java
if (caballeroVivo == true){
    System.out.println("Turno del guerrero, con " + vidaGuerrero + " puntos de vida");
    probabilidadGolpe = Math.random();
    if (probabilidadGolpe >= PORCENTAJE_EXITO_GUERRERO){
        vidaVampiro = vidaVampiro - DAÑO_ESPADA;
```

¿Qué observas en este código?

#### Este código tiene el objetivo de que, en caso de que el guerrero continúe vivo, comience su turno. Al comienzo del turno se muestra en pantalla con un print que así es además de cuanta vida le queda. Cuando el guerrero ataca debemos calcular si acierta o no, para ello usamos la variable probabilidadGolpe, que será un número aleatorio entre 0 y 1; y la constante PORCENTAJE_EXITO_GUERRERO, que tendrá un valor fijo. En caso de que el número aleatorio haya sido mayor que PORCENTAJE_EXITO_GUERRERO se le restara a la vida del vampiro el daño del ataque del guerrero.

#### Sin embargo las variables en este código no tienen un nombre que describa perfectamente su función. La corrección a este problema sería la siguiente:

```java
if (caballeroVivo == true){
    System.out.println("Turno del guerrero, con " + vidaGuerrero + " puntos de vida");
    intentoAtaque = Math.random();
    if (intentoAtaque >= PORCENTAJE_EXITO_ATAQUE_GUERRERO){
        vidaVampiro = vidaVampiro - DAÑO_ESPADA;
```

#### Con estos cambios ahora las variables describen perfectamente su función.

---

## Pregunta 7

Archivo: `batalla.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/a15cf8e4fdd5b0802206f86a21acbc3c90357a6a/entregas/sergio.fernandez/reto-002/batalla.java) (Reto 002)

```java
if (vidaVampiro <=0){
    vampiroVivo = false;
    System.out.println("El vampiro ha muerto");
}
} else {
    System.out.println("El vampiro ha conseguido esquivar el ataque");
}
```

¿Qué observas en este código?

---

## Pregunta 8

Archivo: `Batalla Extendida.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/a15cf8e4fdd5b0802206f86a21acbc3c90357a6a/entregas/sergio.fernandez/reto-002/Batalla%20Extendida.java) (Reto 002)

```java
while (ataqueElegidoGuerrero != 1 && ataqueElegidoGuerrero != 2 && ataqueElegidoGuerrero != 3){
    System.out.println("Elige el ataque: \n [1] Ataque cuchillo \n [2] Ataque espada \n [3] Ataque hacha");
    ataqueElegidoGuerrero = scanner.nextInt();
    if(ataqueElegidoGuerrero != 1 && ataqueElegidoGuerrero != 2 && ataqueElegidoGuerrero != 3){
        System.out.println("El guerrero no conoce ese ataque");
    }
}
```

¿Qué observas en este código?

---

## Pregunta 9

Archivo: `Batalla Extendida.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/a15cf8e4fdd5b0802206f86a21acbc3c90357a6a/entregas/sergio.fernandez/reto-002/Batalla%20Extendida.java) (Reto 002)

```java
eleccionAtaqueVampiro = Math.random();
if (eleccionAtaqueVampiro <= PROBABILIDAD_ELECCION_ATAQUE_1){
    System.out.println("El vampiro trata de atacar al guerrero con sus garras");
    probabilidadGolpe = Math.random();
    if (probabilidadGolpe <= PORCENTAJE_EXITO_VAMPIRO_ATAQUE_1){
        vidaGuerrero = vidaGuerrero - DAÑO_MORDIDA1;
        System.out.println("El vampiro ha herido al guerrero con -" + DAÑO_MORDIDA1 + " puntos de vida");
    }else{
        System.out.println("El guerrero ha conseguido esquivar el ataque");
    }

}else if (eleccionAtaqueVampiro >= PROBABILIDAD_ELECCION_ATAQUE_1 && eleccionAtaqueVampiro <= PROBABILIDAD_ELECCION_ATAQUE_2){
```

¿Qué observas en este código?

---

## Pregunta 10

Archivo: `Batalla Extendida.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/a15cf8e4fdd5b0802206f86a21acbc3c90357a6a/entregas/sergio.fernandez/reto-002/Batalla%20Extendida.java) (Reto 002)

```java
switch (ataqueElegidoGuerrero){

    case 1 -> {
        probabilidadGolpe = Math.random();
        if (probabilidadGolpe <= PORCENTAJE_EXITO_GUERRERO_CUCHILLO){
            vidaVampiro = vidaVampiro - DAÑO_CUCHILLO;
            System.out.println("El guerrero ha herido al vampiro con -" + DAÑO_CUCHILLO + " puntos de vida");
        }else{
            System.out.println("El vampiro ha conseguido esquivar el ataque");
        }
    }
```

¿Qué observas en este código?


