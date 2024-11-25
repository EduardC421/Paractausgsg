@startuml 
class Tablero { 
- List intentos 
- CodigoSecreto codigoSecreto 
- int maxIntentos = 10 
}

class CodigoSecreto { 
- List colores 
 }

class Intento { 
- Codigo codigo 
- int fichasNegras 
- int fichasBlancas 

}

class Codigo { 
- List colores
 }

class Color {
}

class Jugador { 
- String nombre 
- int puntos 
}

class Juego { 
- Jugador creador 
- Jugador adivinador 
- Tablero tablero 
}

Class Ficha{
    +tamano: bool
    +color: array[string]

}

Juego "1" *-- "1" Tablero 
Tablero "1" --> "1" CodigoSecreto 
Tablero "1" --> "*" Intento 
Intento "1" --> "1" Codigo 
CodigoSecreto "1" --> "*" Color 
Codigo "1" --> "*" Color 
Juego "1" --> "2" Jugador 
Codigo "1" --> "*" Color 
@enduml
