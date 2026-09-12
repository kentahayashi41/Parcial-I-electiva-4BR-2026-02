Sistema Gestor de Ventas e Inventario (Mini-POS)
Información del estudiante

Nombre completo: [Carlos_Cabarcas_Jimenez]

Módulo: Unidad 1 — Fundamentos de C# (.NET 8)

Proyecto: Reto Final de Unidad 1

Descripción del proyecto

El Sistema Gestor de Ventas e Inventario (Mini-POS) es una aplicación de consola desarrollada en C# con .NET 8.

El sistema permite a una tienda llevar un control básico de sus productos, inventario y ventas. La información se almacena temporalmente en memoria utilizando colecciones List<T>.

El programa cuenta con un menú interactivo que permanece activo hasta que el usuario selecciona la opción de salir.

Funcionalidades

El sistema cuenta con las siguientes opciones:

1. Registrar nuevo producto

Permite registrar productos ingresando:

Nombre del producto.
Precio unitario.
Stock inicial.

El sistema valida que:

El nombre no esté vacío.
El precio sea mayor que cero.
El stock sea mayor o igual a cero.
No existan dos productos con el mismo nombre.
2. Consultar inventario

Permite visualizar todos los productos registrados mostrando:

ID del producto.
Nombre.
Precio.
Stock disponible.

Cuando un producto tiene menos de 5 unidades, se muestra una alerta:

[ALERTA: BAJO STOCK]

3. Registrar una venta

Permite seleccionar un producto y especificar la cantidad que desea comprar el cliente.

El sistema verifica que exista suficiente stock antes de realizar la venta.

También permite aplicar un descuento del 10% para clientes frecuentes.

El cálculo de la venta utiliza:

Subtotal = Precio × Cantidad

Descuento = Subtotal × 10%

IVA = (Subtotal - Descuento) × 19%

Total a pagar = Subtotal - Descuento + IVA


Después de completar la venta:

Se descuenta la cantidad vendida del inventario.
Se registran las unidades vendidas.
Se actualiza el total de dinero en caja.
Se incrementa el número de ventas.
Se muestra un ticket de venta.
4. Reporte de caja y estadísticas

Permite consultar:

Total de ventas realizadas.
Total acumulado en caja.
Promedio de dinero por venta.
Producto con mayor cantidad de unidades vendidas.
5. Salir

Permite finalizar el programa de manera limpia.

Tecnologías utilizadas
Lenguaje: C#
Framework: .NET 8
Tipo de aplicación: Consola
Editor: Visual Studio Code
Control de versiones: Git y GitHub
Conceptos de la Unidad 1 utilizados

El proyecto fue desarrollado utilizando únicamente conceptos correspondientes a los fundamentos de C# vistos en la Unidad 1.

Se utilizaron:

Variables.
Tipos de datos int.
Tipos de datos decimal.
Tipos de datos string.
Tipos de datos bool.
Colecciones List<T>.
Estructuras if / else.
Estructura switch.
Ciclo for.
Ciclo while.
Ciclo do-while.
Métodos static.
int.TryParse.
decimal.TryParse.
Parámetros out.
Interpolación y formato de cadenas.
Validación de datos.

No se utilizan clases personalizadas para representar productos o ventas, bases de datos ni ORMs.

Estructura del proyecto
GestorVentasUnidad1/
│
├── Program.cs
├── README.md
├── .gitignore
└── GestorVentasUnidad1.csproj


Las carpetas bin/ y obj/ son generadas automáticamente por .NET y están excluidas mediante .gitignore.

Almacenamiento de información

El proyecto no utiliza una base de datos.

La información se almacena temporalmente en memoria utilizando listas:

static List<string> nombres = new List<string>();
static List<decimal> precios = new List<decimal>();
static List<int> stocks = new List<int>();
static List<int> unidadesVendidas = new List<int>();


Por este motivo, la información se reinicia cuando se cierra el programa.

Métodos principales

El programa contiene los métodos solicitados en el reto:

static int LeerEntero(string mensaje, int min, int max)


Permite leer y validar números enteros utilizando int.TryParse.

static decimal LeerDecimal(string mensaje, decimal min)


Permite leer y validar valores decimales utilizando decimal.TryParse.

static decimal CalcularFactura(
    decimal precio,
    int cantidad,
    bool tieneDescuento,
    out decimal montoIva,
    out decimal montoDescuento)


Realiza el cálculo del subtotal, descuento, IVA y total de la venta.

static void ImprimirEncabezado(string titulo)


Se utiliza para mostrar encabezados de manera organizada en la consola.

También se utilizan métodos adicionales para separar las diferentes funcionalidades del programa:

RegistrarProducto()
ConsultarInventario()
RegistrarVenta()
LeerDescuento()
MostrarReporte()

Requisitos para ejecutar el proyecto

Para ejecutar el programa se necesita tener instalado:

.NET 8 SDK.
Visual Studio Code, Visual Studio u otro editor compatible con C#.

Para comprobar que .NET está instalado, ejecutar:

dotnet --version

Crear el proyecto

Si se desea crear el proyecto desde cero, utilizar:

dotnet new console -n GestorVentasUnidad1


Después entrar en la carpeta:

cd GestorVentasUnidad1

Ejecutar el programa

Para ejecutar el proyecto:

dotnet run

Ejemplo del menú principal
====================================================
       SISTEMA GESTOR DE VENTAS E INVENTARIO
====================================================
1. Registrar nuevo producto en inventario
2. Consultar inventario completo
3. Registrar una venta
4. Ver reporte de caja y estadísticas diarias
5. Salir
====================================================
Seleccione una opción (1-5):

Ejemplo de inventario
====================================================
       INVENTARIO COMPLETO
====================================================
ID    PRODUCTO                       PRECIO        STOCK
---------------------------------------------------------
1.    Café Colombiano                $18.000,00       10
2.    Pan Tajado Integral             $6.500,00        3
      [ALERTA: BAJO STOCK]

Ejemplo de ticket de venta
====================================================
       TICKET DE VENTA
====================================================
Producto:    Café Colombiano (x2)
Subtotal:    $36.000,00
Descuento:  -$3.600,00
IVA (19%):  +$6.156,00
----------------------------------------------------
TOTAL:       $38.556,00
====================================================
[OK] Venta efectuada con éxito.
Stock actualizado: 8 unidades.

Ejemplo de validación

Si el usuario ingresa una opción incorrecta:

Seleccione una opción (1-5): abc

[ERROR] Entrada no válida. Debe ingresar un número entero.


Si selecciona una opción fuera del rango:

Seleccione una opción (1-5): 9

[ERROR] Ingrese un valor entre 1 y 5.


Si intenta vender más productos de los disponibles:

Ingrese la cantidad a comprar: 15

[ERROR] Stock insuficiente. Solo quedan 10 unidades.

Autor

Nombre: [Carlos Cabarcas Jimenez]

Proyecto académico — Reto Final de Unidad 1

Fundamentos de C# (.NET 8)
