### Main
```java
public class Main {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        Circulo miCirculo= new Circulo(5);
        
        Triangulo miTriangulo = new Triangulo(3,4,5);
        
        Circulo Circulo= miCirculo;
        Triangulo Triangulo= miTriangulo;
    
    System.out.println("Area de circulo "+ Circulo.AreaCalculo());
    System.out.println("Area del Triangulo "+ Triangulo.AreaCalculo());
    }
    
}


```
### Interface Figura
```java
public interface Figura {
double AreaCalculo();
}
```
### Clase Circulo
```java
public class Circulo implements Figura{
private double radio;

    public Circulo(double radio) {
        this.radio = radio;
    }

    @Override
    public double AreaCalculo() {
   return Math.PI * radio * radio;
    }
    }


```
### Clase Triangulo
```java
public class Triangulo implements Figura{
    private double l1;
    private double l2;
    private double l3;

    public Triangulo(double l1, double l2, double l3) {
        this.l1 = l1;
        this.l2 = l2;
        this.l3 = l3;
    }

    @Override
    public double AreaCalculo() {
        return (l1+l2+l3) /2;
    
    }
}

```