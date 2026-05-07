## Clase Hotel (main)
```java
    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
      // Declaramos una referencia a una acción del hotel
        AccionHotel accion;

        // Tomar una reserva
        accion = new ReservaHabitacion("Habitación 101", "Juan Pérez");
        accion.ejecutarAccion();

        // Procesar un pago
        accion = new Pago("Tarjeta de crédito", 5000);
        accion.ejecutarAccion();
    }
    
```
## clase AccionHotel
```java
  public  abstract class AccionHotel {
    
    abstract void ejecutarAccion();   
}
  
```

## clase Pago
```java
public class Pago extends AccionHotel {
   private String metodoPago;
   private int importe;

    public Pago(String metodoPago, int importe) {
        this.metodoPago = metodoPago;
        this.importe = importe;
    }

    @Override
    void ejecutarAccion() {
        System.out.println("informacion de pago");
        System.out.println("metodo pago: "+ metodoPago + " importe: "+ importe); 
    }

    public String getMetodoPago() {
        return metodoPago;
    }

    public void setMetodoPago(String metodoPago) {
        this.metodoPago = metodoPago;
    }

    public int getImporte() {
        return importe;
    }

    public void setImporte(int importe) {
        this.importe = importe;
    }
   
}

```

## Clase ReservaHabitacion 
```java
public class ReservaHabitacion extends AccionHotel{
    private String NombreHab;
    private String nombreCliente;

    public ReservaHabitacion(String NombreHab, String nombreCliente) {
        this.NombreHab = NombreHab;
        this.nombreCliente = nombreCliente;
    }

    @Override
    void ejecutarAccion() {
        System.out.println("informacion de hotel");
        System.out.println("nombre habitacion: "+ NombreHab + " Cliente: "+ nombreCliente); 
    }

    public String getNombreHab() {
        return NombreHab;
    }

    public void setNombreHab(String NombreHab) {
        this.NombreHab = NombreHab;
    }

    public String getNombreCliente() {
        return nombreCliente;
    }

    public void setNombreCliente(String nombreCliente) {
        this.nombreCliente = nombreCliente;
    }
    
    
}

```