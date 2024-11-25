@startuml 
class Tablero { 
- intentos : List<Intento> 
- codigoSecreto CodigoSecreto 
- maxIntentos : int
}

class CodigoSecreto { 
- colores : List<Color> 
 }

class Intento { 
- codigo : Codigo 
- fichas : Ficha

}

class Codigo { 
- colores : List<Color>
 }

class Color {
}

class Jugador { 
- nombre : string
- puntos : int
}

class Juego { 
- creador : Jugador 
- adivinador : Jugador
- tablero : Tablero
}

Class Ficha{
    +tamano: bool
    +color: List<Color>

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
Intento "1" --> "1" Ficha
 
@enduml
