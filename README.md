## PROYECTO 2
### BIENVENIDOS A NUESTRO PROYECTO
#### Juan José Marroquin Aquino / 7690-23-16390
#### José Miguel Marroquín Aquino / 7690-23-16393

```c++


#include <iostream>
#include <vector>
#include <string>
#include <fstream>

using namespace std;

struct Producto {
    string nombre;
    string codigo;
    float precio;
};

void agregarProducto(ofstream& es, vector<Producto>& inventario) {
    Producto nuevoProducto;
    cout << "Ingrese el nombre del producto: ";
    cin >> nuevoProducto.nombre;
    cout << "Ingrese el código del producto: ";
    cin >> nuevoProducto.codigo;
    cout << "Ingrese el precio del producto: ";
    cin >> nuevoProducto.precio;

    inventario.push_back(nuevoProducto);

    
    if (es.is_open()) {
        es << nuevoProducto.nombre << " " << nuevoProducto.codigo << " " << nuevoProducto.precio << "\n";
        es.close(); 
    } else {
        cerr << "Error al abrir el archivo." << endl;
    }
}

void buscarProducto(const 
vector<Producto>& inventario) {
   string nombreBuscado;
  cout << "Ingrese el producto que desea buscar: ";
    cin >> nombreBuscado;

    for (const auto& producto : inventario) {
        if (producto.nombre == nombreBuscado) {
            cout << "Resultado de la búsqueda:" << endl;
            cout << "Nombre: " << producto.nombre << endl;
            cout << "Código: " << producto.codigo << endl;
            cout << "Precio: " << producto.precio << endl;
            return;
        }
    }

    cout << "Lo siento, producto no encontrado." << endl;
}

void modificarProducto(vector<Producto>& inventario) {
    string nombreModificado;
    cout << "¿Qué producto desea modificar?: ";
    cin >> nombreModificado;

    for (auto& producto : inventario) {
        if (producto.nombre == nombreModificado) {
            cout << "Ingrese el nuevo nombre del producto: ";
            cin >> producto.nombre;
            cout << "Ingrese el nuevo precio del producto: ";
            cin >> producto.precio;
            cout << "Producto modificado exitosamente." << endl;
            return;
        }
    }

    cout << "Lo siento, no se encontró el producto." << endl;
}

int main() {
    vector<Producto> inventario;
    int opcion;
    ofstream es("productos2.txt", ios::app); 

    do {
        cout << "1. Agregar Producto" << endl;
        cout << "2. Buscar Producto" << endl;
        cout << "3. Modificar Producto" << endl;
        cout << "4. Salir" << endl;
        cout << "Ingrese su opción: ";
        cin >> opcion;

        switch (opcion) {
            case 1:
                agregarProducto(es, inventario);
                break;
            case 2:
                buscarProducto(inventario);
                break;
            case 3:
                modificarProducto(inventario);
                break;
            case 4:
                cout << "Saliendo..." << endl;
                break;
            default:
                cout << "Opción no válida. Intente de nuevo." << endl;
        }
    } while (opcion != 4);

    return 0;
}
```
[link del video de nuestro proyeco, funcionamiento y explicacion de nuestro código](https://youtu.be/w9U3jg1CCBc?feature=shared)
