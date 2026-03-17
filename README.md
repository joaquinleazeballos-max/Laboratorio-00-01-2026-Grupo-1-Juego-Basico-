# Laboratorio-00-01-2026-Grupo-1-Juego-Basico-
#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

// Clase que representa el juego de lanzar moneda
class JuegoMoneda {

private:
    int resultadoMoneda;
    char opcionJugador;

public:

    // Constructor
    JuegoMoneda() {
        srand(time(0));
    }

    // MÃ©todo para lanzar la moneda
    void lanzarMoneda() {
        resultadoMoneda = rand() % 2;

        if (resultadoMoneda == 0) {
            cout << "Resultado: CARA\n";
        }
        else {
            cout << "Resultado: CRUZ\n";
        }
    }

    // MÃ©todo para preguntar si desea volver a jugar
    bool continuarJuego() {
        cout << "\n¿Deseas lanzar la moneda otra vez? (s/n): ";
        cin >> opcionJugador;

        if (opcionJugador == 's' || opcionJugador == 'S') {
            return true;
        }

        return false;
    }

    // MÃ©todo principal del juego
    void iniciarJuego() {

        bool seguir = true;

        while (seguir) {

            cout << "\nPresiona ENTER para lanzar la moneda...";
            cin.ignore();
            cin.get();

            lanzarMoneda();

            seguir = continuarJuego();
        }

        cout << "\nGracias por jugar.\n";
    }
};

int main() {

    // CreaciÃ³n del objeto del juego
    JuegoMoneda juego;

    // Inicio del juego
    juego.iniciarJuego();

    return 0;
}
