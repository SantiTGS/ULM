```mermaid
classDiagram
    class Auto {
        - string placa
        - string modelo
        - bool disponible
        + Auto(string p, string m)
        + ~Auto()
        + string getPlaca()
        + string getModelo()
        + bool estaDisponible()
        + void rentar()
        + void devolver()
    }

    class Cliente {
        - int id
        - string nombre
        + Cliente(int i, string n)
        + ~Cliente()
        + int getId()
        + string getNombre()
    }

    class Contrato {
        - Cliente* cliente
        - Auto* autoRentado
        - int dias
        + Contrato(Cliente* c, Auto* a, int d)
        + ~Contrato()
    }

    class AgenciaRenta {
        - string nombre
        - vector~Auto*~ autos
        - vector~Cliente*~ clientes
        + AgenciaRenta(string n)
        + ~AgenciaRenta()
        + void agregarAuto(Auto* autoPtr)
        + void agregarCliente(Cliente* clientePtr)
        + void mostrarInfo()
    }

    AgenciaRenta  o--  Auto 
    AgenciaRenta  o--  Cliente
    Contrato  o--  Cliente
    Contrato  o--  Auto
