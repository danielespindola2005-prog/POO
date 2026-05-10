### Main Accion
```java
public class Accion {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // Declaramos una referencia a una acción del hotel
        AccionHotel accion;

        // Tomar una reserva
        accion = new ReservarHabitacion("Habitación 101 ", "Juan Pérez");
        accion.ejecutarAccion();

        // Procesar un pago
        accion = new ProcesarPago("Tarjeta de crédito", 5000);
        accion.ejecutarAccion();
    }
}

```
### Clase Accion Hotel
```java
public abstract class AccionHotel{
    abstract void ejecutarAccion();
}
```
### Clase Procesar Pago
```java
public class ProcesarPago extends AccionHotel{
    private String formaPago;
    private int precio;

    public ProcesarPago() {
    }

    public ProcesarPago(String formaPago, int precio) {
        this.formaPago = formaPago;
        this.precio = precio;
    }

    public String getFormaPago() {
        return formaPago;
    }

    public void setFormaPago(String formaPago) {
        this.formaPago = formaPago;
    }

    public int getPrecio() {
        return precio;
    }

    public void setPrecio(int precio) {
        this.precio = precio;
    }

    @Override
    void ejecutarAccion() {
    System.out.println(""+formaPago+ ""+ precio); 
    }  
}

```
### Clase Reservar Habitacion
```java

public class ReservarHabitacion extends AccionHotel{
    private String habitacion;
    private String nombre;

    public ReservarHabitacion() {
    }
    
    public ReservarHabitacion(String habitacion, String nombre) {
    this.habitacion= habitacion;
    this.nombre = nombre;
    }

    public String getHabitacion() {
        return habitacion;
    }

    public void setHabitacion(String habitacion) {
        this.habitacion = habitacion;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    @Override
    void ejecutarAccion() {
    System.out.println(""+ habitacion+"" +nombre);
    }
    
    
}

```