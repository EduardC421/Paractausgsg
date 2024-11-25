@startuml
class Tablero {
    - List<Intento> intentos
    - CodigoSecreto codigoSecreto
    - int maxIntentos = 10
    + bool verificarIntento(Codigo intento)
}

class CodigoSecreto {
    - List<Color> colores
    + bool esCorrecto(Codigo codigo)
    + int contarColoresCorrectos(Codigo codigo)
    + int contarColoresDesordenados(Codigo codigo)
}

class Intento {
    - Codigo codigo
    - int fichasNegras
    - int fichasBlancas
    + calcularFeedback(CodigoSecreto codigoSecreto)
}

class Codigo {
    - List<Color> colores
}

enum Color {
    ROJO, AZUL, VERDE, AMARILLO, NARANJA, MORADO
}

class Jugador {
    - String nombre
    - int puntos
    + realizarIntento(Codigo codigo)
}

class Partida {
    - Jugador creador
    - Jugador adivinador
    - Tablero tablero
    + iniciar()
    + determinarGanador()
}

Partida "1" --> "1" Tablero
Tablero "1" --> "1" CodigoSecreto
Tablero "1" --> "*" Intento
Intento "1" --> "1" Codigo
CodigoSecreto "1" --> "*" Color
Codigo "1" --> "*" Color
Partida "1" --> "2" Jugador
@enduml
