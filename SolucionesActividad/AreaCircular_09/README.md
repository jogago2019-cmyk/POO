## Clase (main)
```java
    public static void main(String[] args) {
        
        CirculoImple miCirculo = new CirculoImple(5);
        
        Triangulo miTriangulo = new Triangulo(3,4,5);
        
        Figura figura1 = miCirculo;
        Figura figura2 = miTriangulo;
        
         System.out.println("Area del circulo : "+figura1.calcularArea());
        System.out.println("Area del triangulo : "+figura2.calcularArea());
        
    }
```

## Interface Figura
```java
public interface Figura{
   double calcularArea();
}
```

## Clase Triangulo
```java
public class Triangulo implements Figura{
  private double base;
    private double altura;
    private double lado;

    public Triangulo(double base, double altura, double lado) {
        this.base = base;
        this.altura = altura;
        this.lado = lado;
    }

    @Override
    public double calcularArea() {
        return (base * altura) / 2;
    }
   
```

## Clase Circulo

```java
public class CirculoImple implements Figura{
private double  radio;

    public CirculoImple(double radio) {
        this.radio = radio;
    }

    public CirculoImple() {
    }

    @Override
    public double calcularArea() {
     return Math.PI * radio * radio;
    }

 
}

```
