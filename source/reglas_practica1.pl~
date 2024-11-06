% Tablero inicial vacio

tablero([[_,_,_],[_,_,_],[_,_,_]]).

% Tachar una casilla (Fila, Columna) con el símbolo del Jugador (x o o)

tachar(Jugador,Fila,Columna,Tablero,TableroActualizado):-
    reemplazar_elemento(Fila, Columna, Jugador, Tablero, TableroActualizado).

% Función para actualizar un elemento en una matriz
reemplazar_elemento(Fila, Columna, Valor, Tablero, TableroActualizado) :-
    nth1(Fila, Tablero, FilaTablero, RestoFilas),
    reemplazar_en_lista(Columna, Valor, FilaTablero, NuevaFila),
    nth1(Fila, TableroActualizado, NuevaFila, RestoFilas).

% Función para actualizar un elemento en una lista
reemplazar_en_lista(1, Valor, [_|Resto], [Valor|Resto]).
reemplazar_en_lista(Pos, Valor, [Cabeza|Resto], [Cabeza|NuevoResto]) :-
    Pos > 1,
    Pos1 is Pos - 1,
    reemplazar_en_lista(Pos1, Valor, Resto, NuevoResto).

% Consultar casillas libres del tablero 

consultar_libres(Tablero):-
    buscar_libres(Tablero,1).

buscar_libres([],_).
buscar_libres([Fila|Resto],Numfila):-
    buscar_libres_fila(Fila,Numfila,1),
    Numfila1 is Numfila+1,
    buscar_libres(Resto,Numfila1).

buscar_libres_fila([],_,_).
buscar_libres_fila([Casilla|Resto],Fila,Columna):-
    (var(Casilla) -> format("Posición libre: (~w, ~w)~n", [Fila, Columna]) ; true),
    Columna1 is Columna+1,
    buscar_libres_fila(Resto,Fila,Columna1).

% Vamos a verificar si algun jugador ha ganado
ganador(Tablero, Jugador):-
    fila_ganadora(Tablero,Jugador);
    columna_ganadora(Tablero,Jugador);
    diagonal_ganadora(Tablero,Jugador).

% Comprobamos si hay fila ganadora 

fila_ganadora([Fila|_],Jugador):- all_equal(Fila,Jugador).
fila_ganadora([_|Resto],Jugador):- fila_ganadora(Resto,Jugador).

% Verificar si alguna columna es ganadora
columna_ganadora([[A,_,_], [B,_,_], [C,_,_]], Jugador) :- all_equal([A,B,C], Jugador).  % Primera columna
columna_ganadora([[_,A,_], [_,B,_], [_,C,_]], Jugador) :- all_equal([A,B,C], Jugador).  % Segunda columna
columna_ganadora([[_,_,A], [_,_,B], [_,_,C]], Jugador) :- all_equal([A,B,C], Jugador).  % Tercera columna

% Verificar si una diagonal es ganadora
diagonal_ganadora([[A,_,_], [_,B,_], [_,_,C]], Jugador) :- all_equal([A,B,C], Jugador).  % Diagonal principal
diagonal_ganadora([[_,_,A], [_,B,_], [C,_,_]], Jugador) :- all_equal([A,B,C], Jugador).  % Diagonal secundaria

% Verificamos si todos los elementos son iguales 
all_equal([X,X,X],X).

% Imprimir el tablero actual
imprimir_tablero([]).
imprimir_tablero([Fila|Resto]):-
    writeln(Fila),
    imprimir_tablero(Resto).

% Nueva regla para jugar y visualizar el tablero en cada paso
jugar(Jugador, Fila, Columna, Tablero, TableroActualizado) :-
    tachar(Jugador, Fila, Columna, Tablero, TableroActualizado),
    imprimir_tablero(TableroActualizado).