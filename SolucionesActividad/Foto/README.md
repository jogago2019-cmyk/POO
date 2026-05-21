## Clase Foto (main)
```java
public class Foto {
  private String archivo;
  private double espacioMB;
  
  public Foto(String archivo,double espacioMB){
  this.archivo=archivo;
  this.espacioMB=espacioMB;
  
  }

    public String getArchivo() {
        return archivo;
    }

    public void setArchivo(String archivo) {
        this.archivo = archivo;
    }

    public double getEspacioMB() {
        return espacioMB;
    }

    public void setEspacioMB(double espacioMB) {
        this.espacioMB = espacioMB;
    }

}

```
## clase Album
```java
 public class Album {
    private String titulo;
    private ArrayList<Foto> ListaFotos = new ArrayList<>();
    
    public Album(String titulo){
    this.titulo = titulo;
    }
    
    public String getTitulo() {
        return titulo;
    }

    
    public void añadirFoto(Foto fot){
    ListaFotos.add(fot);
    
    }
    
    public void verGaleria(){
        System.out.println("el Album es: "+ this.titulo);
        for (int i = 0; i < ListaFotos.size(); i++) {
            System.out.println("el nombre del archivo es: "+ListaFotos.get(i).getArchivo()+"el espacio"+ListaFotos.get(i).getEspacioMB());
            
        }
    
    }
}

```

## clase Fotografia
```java
public class Fotografia {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
     
        Album verano = new Album("Viaje 2026");
        
        verano.añadirFoto(new Foto("playa.jpg", 4.5));
        verano.añadirFoto(new Foto("familia.png", 3.2));
        verano.añadirFoto(new Foto("atardecer.jpg", 5.1));

        System.out.println("--- Galería del Álbum ---");
        verano.verGaleria();
    }
  
    }
    

```