# Practica1-inteligencia-artificial

# Tic-Tac-Toe en Prolog

Este repositorio contiene una implementación del juego clásico de Tic-Tac-Toe (Tres en Raya) en el lenguaje de programación Prolog. El juego permite a dos jugadores alternar turnos para marcar casillas en un tablero de 3x3 y determinar un ganador cuando tres casillas seguidas son ocupadas por el mismo jugador.

## Funcionalidades

- **Tablero Inicial Vacío**: Crea un tablero vacío al inicio del juego.
  ```prolog
  tablero([[_,_,_],[_,_,_],[_,_,_]]).
  ```

- **Tachar Casilla**: Marca una casilla en el tablero con el símbolo del jugador actual (`x` o `o`).
  ```prolog
  tachar(Jugador, Fila, Columna, Tablero, TableroActualizado).
  ```

- **Consulta de Casillas Libres**: Muestra todas las posiciones libres del tablero, permitiendo al jugador ver las casillas disponibles.
  ```prolog
  consultar_libres(Tablero).
  ```

- **Verificar Ganador**: Determina si algún jugador ha ganado el juego revisando filas, columnas o diagonales.
  ```prolog
  ganador(Tablero, Jugador).
  ```

- **Imprimir el Tablero**: Muestra el estado actual del tablero en la consola.
  ```prolog
  imprimir_tablero(Tablero).
  ```

- **Jugar un Turno**: Realiza una jugada para el jugador actual, actualiza el tablero e imprime el tablero en cada turno.
  ```prolog
  jugar(Jugador, Fila, Columna, Tablero, TableroActualizado).
  ```

## Ejemplo de Uso

1. **Iniciar un tablero vacío**:
   ```prolog
   tablero([[_,_,_],[_,_,_],[_,_,_]]).
   ```

2. **Realizar una jugada**:
   - Llama a `jugar/5` para que un jugador marque una casilla:
     ```prolog
     jugar(x, 1, 1, [[_,_,_],[_,_,_],[_,_,_]], TableroActualizado).
     ```
   - Esto marcará la posición `(1,1)` con `x` y actualizará el tablero.

3. **Verificar casillas libres**:
   ```prolog
   consultar_libres(TableroActualizado).
   ```

4. **Comprobar si hay un ganador**:
   ```prolog
   ganador(TableroActualizado, x).
   ```

## Reglas y Estructura del Código

- **Funciones principales**:
  - `tablero/1`: Define el tablero vacío.
  - `tachar/5`: Marca una posición específica para el jugador.
  - `consultar_libres/1`: Busca y muestra las posiciones libres del tablero.
  - `ganador/2`: Comprueba si un jugador ha ganado.
  - `imprimir_tablero/1`: Imprime el estado actual del tablero.
  - `jugar/5`: Permite realizar una jugada, actualizando y mostrando el tablero en cada paso.

- **Verificación de Ganador**:
  - `fila_ganadora/2`: Verifica si alguna fila contiene el mismo símbolo.
  - `columna_ganadora/2`: Verifica si alguna columna contiene el mismo símbolo.
  - `diagonal_ganadora/2`: Verifica si alguna diagonal contiene el mismo símbolo.

## Requisitos

Para ejecutar este código, necesitas un entorno que soporte Prolog, como SWI-Prolog.

## Ejecución

1. Abre SWI-Prolog.
2. Carga el archivo en Prolog:
   ```prolog
   [TicTacToe-Prolog].
   ```
3. Inicia el juego con un tablero vacío y usa las reglas disponibles para jugar.

## Contribuciones

Las contribuciones son bienvenidas. Puedes abrir issues para reportar bugs o sugerir mejoras, y pull requests para aportar al código.

## Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.
