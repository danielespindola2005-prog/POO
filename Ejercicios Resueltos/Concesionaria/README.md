## Concesionaria 

### Main ConcesionariaPOO
```java
 public static void main(String[] args) {
        Persona vendedor = new Persona("Juan Pérez", "33444555") {};
        Persona comprador = new Persona("Ana García", "40111222") {};

        // Creamos los vehículos (Aplicando Polimorfismo)
        Vehiculo auto1 = new Auto("Toyota", "Corolla", 33000000, 4);
        Vehiculo moto1 = new Moto("Honda", "CB500F", 5400000, 500);

        // Registramos la venta de un Auto
        Venta factura1 = new Venta(vendedor, comprador, auto1);

        System.out.println("--- Procesando Venta de Concesionaria ---");
        factura1.imprimirFactura();        
        System.out.println("\n------------------------------------------");
        
        // Registramos la venta de una Moto usando el mismo proceso
        Venta factura2 = new Venta(vendedor, comprador, moto1);
        
        System.out.println("--- Procesando venta de Concesionaria ---");
        factura2.imprimirFactura();
        System.out.println("\n-------------------------------------------------");
    }
```
### Clase Auto
``` java
public class Auto extends Vehiculo{
    private int cantPuertas;

    public Auto() {
    }

    public Auto(int cantPuertas) {
        this.cantPuertas = cantPuertas;
    }

    public Auto( String marca, String modelo, int precio, int cantPertas) {
        super(precio, marca, modelo);
        this.cantPuertas = cantPuertas;
    }
    
    
    public int getCantPuertas() {
        return cantPuertas;
    }

    public void setCantPuertas(int cantPuertas) {
        this.cantPuertas = cantPuertas;
    }   
}
```
### Clase Moto 
```java
public class Moto extends Vehiculo{
    private int cilindrada;

    public Moto(int cilindrada) {
        this.cilindrada = cilindrada;
    }

    public Moto( String marca, String modelo, int precio, int cilindrada) {
        super(precio, marca, modelo);
        this.cilindrada = cilindrada;
    }
       

    public int getCilindrada() {
        return cilindrada;
    }

    public void setCilindrada(int cilindrada) {
        this.cilindrada = cilindrada;
    }

    public String getMarca() {
        return marca;
    }

    public void setMarca(String marca) {
        this.marca = marca;
    }

    public String getModelo() {
        return modelo;
    }

    public void setModelo(String modelo) {
        this.modelo = modelo;
    }

    public int getPrecio() {
        return precio;
    }

    public void setPrecio(int precio) {
        this.precio = precio;
    }
}
```
### Clase Persona
```java
public class Persona {
    private String nombre;
    private String dni;

    public Persona() {
    }
    
    public Persona(String nombre, String dni) {
    this.nombre = nombre;
    this.dni= dni;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public String getDni() {
        return dni;
    }

    public void setDni(String dni) {
        this.dni = dni;
    }
}
```
### Clase Vehiculo 
```java
public abstract class Vehiculo {
    protected String marca="";
    protected String modelo="";
    protected int precio;

    public Vehiculo() {
    }

    public Vehiculo(int precio, String marca, String modelo) {
        this.precio = precio;
        this.marca=marca;
        this.modelo = modelo;
    }

    public String getMarca() {
        return marca;
    }

    public void setMarca(String marca) {
        this.marca = marca;
    }

    public String getModelo() {
        return modelo;
    }

    public void setModelo(String modelo) {
        this.modelo = modelo;
    }

    public int getPrecio() {
        return precio;
    }

    public void setPrecio(int precio) {
        this.precio = precio;
    }   
}
```
### Clase Venta
```java
public class Venta {

private Persona vendedor;
private Persona comprador;
private Vehiculo vehiculo;

    public Venta() {
    }

    public Venta(Persona vendedor, Persona comprador, Vehiculo vehiculo ) {
        this.vendedor = vendedor;
        this.comprador = comprador;
        this.vehiculo= vehiculo;
    }

    public Persona getVendedor() {
        return vendedor;
    }

    public void setVendedor(Persona vendedor) {
        this.vendedor = vendedor;
    }

    public Persona getComprador() {
        return comprador;
    }

    public void setComprador(Persona comprador) {
        this.comprador = comprador;
    }

    public Vehiculo getVehiculo() {
        return vehiculo;
    }

    public void setVehiculo(Vehiculo vehiculo) {
        this.vehiculo = vehiculo;
    }
    
        void imprimirFactura(){
            System.out.println(" Venta ");
        System.out.println("Vendedor "+ vendedor.getNombre());
        System.out.println("Comprador "+comprador.getNombre());
        System.out.println("Vehiculo "+vehiculo.getMarca());
        System.out.println(vehiculo.getModelo()+vehiculo.getPrecio());
        }

}
```