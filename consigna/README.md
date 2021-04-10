# Trabajo Práctico del Taller de Programación Avanzada

## Introducción
Durante el taller desarrollaremos un juego de mesa multijugador, respetando las reglas del [Kingdomino](https://www.boardgamegeek.com/boardgame/204583/kingdomino). A lo largo de las clases del taller se les proveerá de herramientas para poder realizarlo en Java, con las buenas prácticas que irán adquiriendo.


### Metodología de trabajo

La realización del juego, tendrá tres etapas con sus respectivas entregas:

| Fecha | Contenido de la entrega                                                                                        |
|-------|----------------------------------------------------------------------------------------------------------------|
| 15/05 | Diagrama de clases del modelo del juego, implementado y testeado (código)                                      |
| 12/06 | Posibilidad de interactuar con los elementos del juego en tiempo real en un entorno simulado, de forma gráfica |
| 10/07 | Capacidad de ser jugado a través de cliente-servidor                                                           |


> Se espera que las prácticas de programación sean buenas, y adecuadas al conocimiento adquirido en la materia.
> Esto incluye evitar el código aglomerado, tener una buena interacción de clases, no duplicar funcionalidades, tener el código indentado y prolijo, entre otras.

---

## Mecánica del juego

El objetivo de cada jugador, es expandir los territorios donde reina de tal manera que consiga los más valiosos.

> En Kingdomino, sos un lord buscando nuevas tierras hacia las cuales expandir tu reino. Debés explorar todas las tierras, incluyendo campos de trigo, lagos y montañas, para localizar los mejores lotes mientras competís contra otros lores para adquirirlas primero.

* El juego utiliza un mazo de dominó especificado en su propia sección.
* Una partida debe contar con 4 jugadores, y dar la posibilidad de poder jugar solo 2 o 3 jugadores con reglas modificadas.
* Una partida debe contar con múltiples rondas, que finalizará cuando no haya más dominós en el mazo y se hayan colocado los últimos dominós en los terrenos correspondientes.
* Cuando finaliza la última ronda, el jugador con más puntos gana la partida. En caso de empate, el jugador con el territorio más extenso gana. En caso de empate nuevamente, los jugadores involucrados comparten la victoria

## Reglas del juego

Si bien estas son las [reglas oficiales en castellano](http://devir.cl/_manuales/blueorange/kingdomino-esp.pdf), también se puede ver una explicación de las reglas del juego [en este video de "La Ficha"](https://www.youtube.com/watch?v=Mr3sXI2vQJY).

Para facilitar el desarrollo, vamos a modificar las reglas de juego para 2 y 3 jugadores.
El juego se juega con todas las fichas de dominó, pero solo se eligen 2 o 3 (según la cantidad de jugadores) por ronda, el resto se descarta


## Mazo de dominós

El juego original presenta un mazo estandar de 48 fichas bien definidas. Recomendamos utilizar este mismo mazo o uno de equivalentes caracteristicas


## Requisitos

1. Como usuario quiero ingresar al juego eligiendo un nombre, para poder jugar contra otros jugadores en una sala
2. Como usuario quiero seleccionar una sala de las existentes, para poder ingresar y jugar con los participantes (*1)
3. Como usuario quiero crear nuevas salas para que ingresen otros jugadores (*2)
4. Como usuario quiero poder ver los jugares que ingresan a mi sala, antes de iniciar la partida
5. Como usuario quiero poder salir de una sala, incluso si en la misma el juego se encuentra en ejecución (rendirse) (si solo un jugador queda en la sala, este gana la partida). Las reglas del juego se modifican por las de los jugadores restantes
6. Como usuario quiero poder identificar cada jugador y poder ver su tablero (no necesariamente todo el tiempo) y su puntaje parcial
7. Como usuario quiero ver con claridad quien fue el ganador del juego y el estado final de los tableros

## Requisitos extras
Se debe cumplir con al menos uno de estos

### Base de datos
1. En vez de ingresar con un nombre, se debe ingresar con un nombre de usuario y una clave, o poder crear uno (modificando el punto 1)
2. Como usuario quiero poder elegir un jugador (incluso a mi mismo) para ver sus estadísticas (cantidad de: victorias, derrotas, partidas jugadas, dominós jugados, puntaje máximo, etc)

### Configuración
1. El creador de la sala debe poder elegir entre una variedad de mazos, y estilos visuales distintos antes de comenzar la partida.
2. Se deben poder crear mazos nuevos (que esten guardados en un archivo y puedan ser accedidos por el programa). Todos los mazos deben contar con 48 fichas de dominó y con distintos tipos de terrenos y coronas. Recordar que el número que llevan debería ser inferior si la ficha no es tan valiosa, o superior si lo es

### Variantes o reglas opcionales
1. El creador de la sala debe poder elegir una o más variantes antes de comenzar la partida.
2. Se deben implementar las variates o reglas opcionales del juego en el programa para ser utilizadas cuando sean elegidas. "El gran duelo" solo puede ser elegida en salas de 2 jugadores o no se debe poder elegir o activar al comenzar la partida si hay más de 2 jugadores

### Bots
1. El creador de la sala debe poder agregar uno o más bots si lo desea para que jueguen la partida reemplazando un lugar de un jugador.
2. Los bots no deberan jugar de forma aleatoria, sino tener algún tipo de estrategia y que tengan chances reales de ganar

Notas:
> (*1) Una sala puede estar activa para que ingresen jugadores mientras un juego no esté activo en la misma. Aún así, debe aparecer en la lista de juegos como que el juego ya inició y la cantidad de jugadores en juego

> (*2) La partida podrá ser iniciada por el creador de la sala, o cuando todos los jugadores estén listos, o cualquier otra condición que consideren
