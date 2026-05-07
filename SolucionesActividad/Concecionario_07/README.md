## Clase Concecionario (main)
...java
public class Concesionaria {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        Scanner lector = new Scanner(System.in);

    Persona cli1= new Persona("jose","gomez", "123");
    Persona vend1= new Persona("vic", "gom", "456");
     //creamos los vehiculos (aplicando polimorfismo) para aprovehcar el polimorfimo pero para usar los metodo de auto hay que castear
     Vehiculo auto = new automovil(2, "goolf", "Auto", 30000, "AAD345");
     Vehiculo moto = new motocicleta("123", "CovilBike", "Moto", 5000, "ACD12");
     
        System.out.println("que vehiculo quieres comprar: ");
        boolean fin = false;

            System.out.println("1-auto");
            System.out.println("2-moto");
            System.out.println("0-finalizar");
            System.out.print("ingrese un opcion: ");
            int op = lector.nextInt();
            
            switch (op) {
                case 0:
                    fin = true;
                    break;
                case 1:
                  Venta v1 = new Venta(cli1, vend1, auto);
                  v1.mostrarVenta();
                    break;
                case 2:
                    Venta v2 = new Venta(cli1, vend1, moto);
                    v2.mostrarVenta();
                    break;                
                default:
                    System.out.println("Opcion no valida");
            }
        }
    }

...

## Clase Persona
..java
public  class Persona {
    private String nombre;
    private String apellido;
    private String dni;

    public Persona() {
    }
    
    public Persona(String nombre, String apellido, String dni) {
        this.nombre = nombre;
        this.apellido = apellido;
        this.dni = dni;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public String getApellido() {
        return apellido;
    }

    public void setApellido(String apellido) {
        this.apellido = apellido;
    }

    public String getDni() {
        return dni;
    }

    public void setDni(String dni) {
        this.dni = dni;
    }}
...

## Clase Vehículo
...java
public abstract class Vehiculo {
    protected String modelo;
    protected String marca;
    protected double precio;
    protected String patente;

    public Vehiculo() {
    }

    public Vehiculo(String modelo, String marca, double precio, String patente) {
        this.modelo = modelo;
        this.marca = marca;
        this.precio = precio;
        this.patente = patente;
    }

    public String getModelo() {
        return modelo;
    }

    public void setModelo(String modelo) {
        this.modelo = modelo;
    }

    public String getMarca() {
        return marca;
    }

    public void setMarca(String marca) {
        this.marca = marca;
    }

    public double getPrecio() {
        return precio;
    }

    public void setPrecio(double precio) {
        this.precio = precio;
    }

    public String getPatente() {
        return patente;
    }

    public void setPatente(String patente) {
        this.patente = patente;
    }
    
    public abstract String mostrarInfo();
}

...

## Clase Automovil
...java
public class automovil extends Vehiculo {
    private float puertas;

    public automovil() {
    }

    public automovil(float puertas) {
        this.puertas = puertas;
    }

    public automovil(float puertas, String modelo, String marca, double precio, String patente) {
        super(modelo, marca, precio, patente);
        this.puertas = puertas;
    }

    public float getPuertas() {
        return puertas;
    }

    public void setPuertas(float puertas) {
        this.puertas = puertas;
    }

    @Override
    public String mostrarInfo() {
        return "Auto: " + marca + " - Patente: " + patente + " cantidad de Puertas: "+puertas;
    }
}

...

## Clase motocicleta
...java
public class motocicleta extends Vehiculo {
   private String cilindrada;

    public motocicleta() {
    }

    public motocicleta(String cilindrada) {
        this.cilindrada = cilindrada;
    }

    public motocicleta(String cilindrada, String modelo, String marca, double precio, String patente) {
        super(modelo, marca, precio, patente);
        this.cilindrada = cilindrada;
    }

    public String getCilindrada() {
        return cilindrada;
    }

    public void setCilindrada(String cilindrada) {
        this.cilindrada = cilindrada;
    }
   

    public String mostrarInfo() {
        return "Moto: " + marca + " - Cilindrada: " + cilindrada;
    }
}

...

## Clase Venta

'''java
public class Venta {
private Persona cliente;
    private Persona vendedor;
    private Vehiculo vehiculo;
    private Date fecha;

    public Venta(Persona cliente, Persona vendedor, Vehiculo vehiculo) {
        this.cliente = cliente;
        this.vendedor = vendedor;
        this.vehiculo = vehiculo;
        this.fecha = new Date();
    }

    public void mostrarVenta() {
        System.out.println("\n--- VENTA ---");
        System.out.println("Cliente: " + cliente.getNombre());
        System.out.println("Vendedor: " + vendedor.getNombre());
        System.out.println("Vehiculo: " + vehiculo.mostrarInfo());
        System.out.println("Precio: $" + vehiculo.getPrecio());
        System.out.println("Fecha: " + fecha);
    }
}
'''
