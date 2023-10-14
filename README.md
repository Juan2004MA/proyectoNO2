# proyectoNO2
bienvenidos a nuestro proyecto 

# Bienvenidos a nuestro proyecto 2 de Algoritmos
### José Miguel Marroquín Aquino (7690-23-16393)
### Juan José Marroquín Aquino (7690-23-16390)
```c++
        #include <iostream>
        #include <vector>
        #include <string>

        using namespace std;

        struct Producto {
            string nombre;
            string codigo;
            float precio;
            string proveedor;
            int existencias;
            char estado;
            float descuento;
        }; 


        void agregarProducto(vector<Producto>& inventario) {
            Producto nuevoProducto;
            cout << "Ingrese el producto que quiera crear : ";
            cin >> nuevoProducto.nombre;
            cout << "Ingrese el precio que desea ponerle: ";
        cin >> nuevoProducto.precio;
        cout << "ingrese el codigo que desea ponerle:";
        cin >> nuevoProducto.codigo;
            inventario.push_back(nuevoProducto);
        }


        void buscarProducto(const vector<Producto>& inventario) {
            
            string nombreBuscado;
            cout << "ingrese el producto que quiera buscar: ";
            cin >> nombreBuscado;

            for (const auto& producto : inventario) {
                if (producto.nombre == nombreBuscado) {
                    cout << "resultados de su busqueda:" << endl;
                    cout << "Nombre: " << producto.nombre << endl;
                    cout << "Precio: " << producto.precio << endl;
                    cout << "codigo: " << producto.codigo << endl;
                return;
                }
            }
            
            cout << "lo siento, producto no encontrado." << endl;
        }


        void modificarProducto(vector<Producto>& inventario) {
            
            string nombreModificado;
            cout << "¿que producto desea modificar?: ";
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

            cout << "lo siento:( no se encontró el producto: " << endl;
        }


        int main() {
            vector<Producto> inventario;
            vector<Producto> otroArreglo;  
            int opcion;
            do {
                cout << "1. Agregar Producto" << endl;
                cout << "2. Buscar Producto" << endl;
                cout << "3. Modificar Producto" << endl;
                cout << "4. Salir" << endl;
                cout << "Ingrese su opción: ";
                cin >> opcion;

                switch(opcion) {
                    case 1:
                        agregarProducto(inventario);
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
            } while(opcion != 4);

            return 0;
        }
  



  
[link del video de nuestro proyeco, funcionamiento y explicacion de nuestro código](https://youtu.be/w9U3jg1CCBc?feature=shared)
