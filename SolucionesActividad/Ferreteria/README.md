# Ferreteria 23/4/2026

## Clase Ferreteria (main)
```java
   /public class Ferreteria {
    public static void main(String[] args) {
        Herramienta h1 = new Herramienta("Stanley", "Grande", 101, "Martillo de Galpón", 1500.50);

        InsumoElectrico i1 = new InsumoElectrico(220.0, true, 202, "Lámpara LED 10W", 450.0);

        Herraje her1 = new Herraje("Acero Inoxidable", "50mm x 50mm", 303, "Bisagra Reforzada", 890.0);

        System.out.println("--- Inventario de Ferretería Cargado ---");
        System.out.println("Producto: " + h1.getNombre() + " | Marca: " + h1.getMarca());
        System.out.println("Producto: " + i1.getNombre() + " | Voltaje: " + i1.getVoltaje() + "v");
        System.out.println("Producto: " + her1.getNombre() + " | Material: " + her1.getMaterial());
    }
}
```
## clase Herraje
```java
class Herraje extends Producto{
   private String dimensiones;
   private String material;

    public Herraje(String dimensiones, String material) {
        this.dimensiones = dimensiones;
        this.material = material;
    }

    public Herraje(String dimensiones, String material, int codigo, String nombre, double precio) {
        super(codigo, nombre, precio);
        this.dimensiones = dimensiones;
        this.material = material;
    }

    public String getDimensiones() {
        return dimensiones;
    }

    public void setDimensiones(String dimensiones) {
        this.dimensiones = dimensiones;
    }

    public String getMaterial() {
        return material;
    }

    public void setMaterial(String material) {
        this.material = material;
    }

    public int getCodigo() {
        return codigo;
    }

    public void setCodigo(int codigo) {
        this.codigo = codigo;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public double getPrecio() {
        return precio;
    }

    public void setPrecio(double precio) {
        this.precio = precio;
    }
   
}
```

## Clase Herramiente
```java
class Herramienta extends Producto{

    private String Marca;
    private String tamaño;

    public Herramienta(String Marca, String tamaño) {
        this.Marca = Marca;
        this.tamaño = tamaño;
    }

    public Herramienta(String Marca, String tamaño, int codigo, String nombre, double precio) {
        super(codigo, nombre, precio);
        this.Marca = Marca;
        this.tamaño = tamaño;
    }

    public String getMarca() {
        return Marca;
    }

    public void setMarca(String Marca) {
        this.Marca = Marca;
    }

    public String getTamaño() {
        return tamaño;
    }

    public void setTamaño(String tamaño) {
        this.tamaño = tamaño;
    }

    public int getCodigo() {
        return codigo;
    }

    public void setCodigo(int codigo) {
        this.codigo = codigo;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public double getPrecio() {
        return precio;
    }

    public void setPrecio(double precio) {
        this.precio = precio;
    }
}
```
### Clase InsumoEletrico
```java
class InsumoElectrico extends Producto{
    private double voltaje;
    private boolean esCertificado;

    public InsumoElectrico(double voltaje, boolean esCertificado, int codigo, String nombre, double precio) {
        super(codigo, nombre, precio);
        this.voltaje = voltaje;
        this.esCertificado = esCertificado;
    }

    public double getVoltaje() {
        return voltaje;
    }

    public void setVoltaje(double voltaje) {
        this.voltaje = voltaje;
    }

    public boolean isEsCertificado() {
        return esCertificado;
    }

    public void setEsCertificado(boolean esCertificado) {
        this.esCertificado = esCertificado;
    }

    public int getCodigo() {
        return codigo;
    }

    public void setCodigo(int codigo) {
        this.codigo = codigo;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public double getPrecio() {
        return precio;
    }

    public void setPrecio(double precio) {
        this.precio = precio;
    } 
}
```
## Clase Producto
```java
public abstract class Producto {
    protected int codigo;
    protected String nombre;
    protected double precio;

    public Producto() {
    }

    public Producto(int codigo, String nombre, double precio) {
        this.codigo = codigo;
        this.nombre = nombre;
        this.precio = precio;
    }

    
    public int getCodigo() {
        return codigo;
    }

    public void setCodigo(int codigo) {
        this.codigo = codigo;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public double getPrecio() {
        return precio;
    }

    public void setPrecio(double precio) {
        this.precio = precio;
    }
}
```