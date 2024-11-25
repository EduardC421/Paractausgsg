@startuml 
class Tablero { 
- intentos : List<Intento> 
- CodigoSecreto codigoSecreto 
- int maxIntentos = 10 
}

class CodigoSecreto { 
- List colores 
 }

class Intento { 
- Codigo codigo 
- fichas : Ficha

}

class Codigo { 
- colores : List<Color>
 }

class Color {
}

class Jugador { 
- String nombre 
- int puntos 
}

class Juego { 
- creador : Jugador 
- adivinador : Jugador
- tablero : Tablero
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
Juego "1" *-- "2" Jugador 
Juego "1" *-- "*" Ficha
Ficha "1" --> "1" Color
 
@enduml

