# Biblioteca_PPR
Trabajo práctico _ Paradigma de programación

package test;
import java.sql.Connection;
import javax.swing.JOptionPane;


public class Prestamo {
    private int nroPrestamo;
    private Date fechaSolicitud;
    private Date fechaCancelacion;
    private EstadoPrestamo estado;
    private Date fechaAnulacion;
    private Empleado entrego;
    private DetallePrestamo detallePrestamo;
    private ReclamoLibro reclamo;

    public Prestamo(int nroPrestamo, Date fechaSolicitud, EstadoPrestamo estado) {
        this.nroPrestamo = nroPrestamo;
        this.fechaSolicitud = fechaSolicitud;
        this.estado = estado;
        
    }
    
    public void anular(Date fechaAnulacion) {
        this.fechaAnulacion = fechaAnulacion;
        this.estado = EstadoPrestamo.ANULADO; 
    }
    
     public void cancelar() {
        this.estado = EstadoPrestamo.CANCELADO;  
    }
}


public class DetallePrestamo {
    private Date fechaDevolucionReal;
    private EstadoDetallePrestamo estado;
    private Ejemplar ejemplar;
    private Date fechaCancelacion;

    public DetallePrestamo(Date fechaDevolucionReal, EstadoDetallePrestamo estado, Ejemplar ejemplar, Date fechaCancelacion) {
        this.fechaDevolucionReal = fechaDevolucionReal;
        this.estado = estado;
        this.ejemplar = ejemplar;
        this.fechaCancelacion = fechaCancelacion;
    }

}

public class EstadoPrestamo {
    private String nombre;
    private String descripcion;

    public EstadoPrestamo(String nombre, String descripcion) {
        this.nombre = nombre;
        this.descripcion = descripcion;
    }

}

public class EstadoDetallePrestamo {
    private String nombre;
    private String descripcion;

    public EstadoDetallePrestamo(String nombre, String descripcion) {
        this.nombre = nombre;
        this.descripcion = descripcion;
    }
}


public class Ejemplar {
    private int nroEjemplar;
    private Date fechaCompra;
    private Date fechaBaja;
    private boolean estado;
    private Prestamo prestamo;
    private DetallePedido detallePedido;

    public Ejemplar(int nroEjemplar, Date fechaCompra, Date fechaBaja, boolean estado, Prestamo prestamo, DetallePedido detallePedido) {
        this.nroEjemplar = nroEjemplar;
        this.fechaCompra = fechaCompra;
        this.fechaBaja = fechaBaja;
        this.estado = estado;
        this.prestamo = prestamo;
        this.detallePedido = detallePedido;
    }

}


public class Libro {
    private String titulo;
    private int anioEdicion;
    private int numeroEdicion;
    private int cantidadHojas;
    private Genero genero; 
    private Autor autor;
    private Editorial editorial;

    public Libro(String titulo, int anioEdicion, int numeroEdicion, int cantidadHojas,
                 Genero genero, Autor autor, Editorial editorial
    private boolean disponible;
    private ArrayList<Prestamo> prestamos;
        this.titulo = titulo;
        this.anioEdicion = anioEdicion;
        this.numeroEdicion = numeroEdicion;
        this.cantidadHojas = cantidadHojas;
        this.genero = genero;
        this.autor = autor;
        this.editorial = editorial;
    }

    public Genero getGenero() {
        return genero;
    }

    public void setGenero(Genero genero) {
        this.genero = genero;
    }

    public Autor getAutor() {
        return autor;
    }

    public void setAutor(Autor autor) {
        this.autor = autor;
    }
    
     public Editorial getEditorial() {
        return editorial;
    }

public class Genero {
    private String nombre;
    private String descripcion;

    public Genero(String nombre, String descripcion) {
        this.nombre = nombre;
        this.descripcion = descripcion;
    }

}

public class Autor {
    private String nombre;

    public Autor(String nombre) {
        this.nombre = nombre;
    }

}

public class Editorial {
    private String nombre;
    private String descripcion;

    public Editorial(String nombre, String descripcion) {
        this.nombre = nombre;
        this.descripcion = descripcion;
    }

}

public class LibroBiblioteca {
    private int codigoLibro;
    private List<Ejemplar> ejemplares;
    private String sector;
    private String estante;
    private Date fechaBaja;
    private String resumen;

    public LibroBiblioteca(int codigoLibro, List<Ejemplar> ejemplares, String sector, String estante, Date fechaBaja, String resumen) {
        this.codigoLibro = codigoLibro;
        this.ejemplares = ejemplares;
        this.sector = sector;
        this.estante = estante;
        this.fechaBaja = fechaBaja;
        this.resumen = resumen;
    }

}


public class Asociacion {
    private String fechaAlta;
    private String fechaBaja;
    private String motivoBaja;
    private Empleado empleado;

    public Asociacion(String fechaAlta, String fechaBaja, String motivoBaja, Empleado empleado) {
        this.fechaAlta = fechaAlta;
        this.fechaBaja = fechaBaja;
        this.motivoBaja = motivoBaja;
        this.empleado = empleado;
    }

}

public class Estudiante {
    private int nroEstudiante;
    private int telefono;
    private String email;
    private Asociacion asociaciones;
    private Prestamo prestamos;
    private boolean habilitado;

    public Estudiante(int nroEstudiante, int telefono, String email,
                      Asociacion asociaciones, Prestamo prestamos, boolean habilitado) {
        this.nroEstudiante = nroEstudiante;
        this.telefono = telefono;
        this.email = email;
        this.asociaciones = asociaciones;
        this.prestamos = prestamos;
        this.habilitado = habilitado;
    }
}

public class Pedido {
    private int nroPedido;
    private Date fechaPedido;
    private Date fechaRecepcion;
    private EstadoPedido estadoPedido;
    private DetallePedido detallePedido;
    private Empleado empleadoQueGenera;

    public Pedido(int nroPedido, Date fechaPedido, Date fechaRecepcion, EstadoPedido estadoPedido, DetallePedido detallePedido, Empleado empleadoQueGenera) {
        this.nroPedido = nroPedido;
        this.fechaPedido = fechaPedido;
        this.fechaRecepcion = fechaRecepcion;
        this.estadoPedido = estadoPedido;
        this.detallePedido = detallePedido;
        this.empleadoQueGenera = empleadoQueGenera;
    }
}

public class DetallePedido {
    private int cantidad;
    private Libro libro;
    private double precioCompra;

    public DetallePedido(int cantidad, Libro libro, double precioCompra) {
        this.cantidad = cantidad;
        this.libro = libro;
        this.precioCompra = precioCompra;
    }

}

public class Persona {
    private String nombre;
    private String apellido;
    private TipoDocumento tipoDoc;
    private int nroDocumento;
    private String nroUsuario;
    private String contrasena;

    public Persona(String nombre, String apellido, TipoDocumento tipoDoc, int nroDocumento, String nroUsuario, String contrasena) {
        this.nombre = nombre;
        this.apellido = apellido;
        this.tipoDoc = tipoDoc;
        this.nroDocumento = nroDocumento;
        this.nroUsuario = nroUsuario;
        this.contrasena = contrasena;
    }

}

public class TipoDocumento {
    private String nombre;
    private String descripcion;

    public TipoDocumento(String nombre, String descripcion) {
        this.nombre = nombre;
        this.descripcion = descripcion;
    }


}

public class Empleado {
    private String legajo;

    public Empleado(String legajo) {
        this.legajo = legajo;
    }

}


public class Proveedor {
    private int cuit;
    private String razonSocial;
    private int telefono;
    private Pedido pedido;
    private Date fechaBaja;
    private String motivoBaja;

    public Proveedor(int cuit, String razonSocial, int telefono, Pedido pedido, Date fechaBaja, String motivoBaja) {
        this.cuit = cuit;
        this.razonSocial = razonSocial;
        this.telefono = telefono;
        this.pedido = pedido;
        this.fechaBaja = fechaBaja;
        this.motivoBaja = motivoBaja;
    }

}

public class Catalogo {
    private int numero;
    private Date fecha;
    private String descripcion;
    private Date fechaVigenteDesde;
    private Date fechaVigenteHasta;
    private Proveedor proveedor;
    private List<Libro> libros;

    public Catalogo(int numero, Date fecha, String descripcion, Date fechaVigenteDesde, Date fechaVigenteHasta, Proveedor proveedor, List<Libro> libros) {
        this.numero = numero;
        this.fecha = fecha;
        this.descripcion = descripcion;
        this.fechaVigenteDesde = fechaVigenteDesde;
        this.fechaVigenteHasta = fechaVigenteHasta;
        this.proveedor = proveedor;
        this.libros = libros;
    }

}

public class LibroCatalogo {
    private Libro libro;
    private double precio;

    public LibroCatalogo(Libro libro, double precio) {
        this.libro = libro;
        this.precio = precio;
    }

}


public class Biblioteca {
    private ArrayList<Libro> librosDisponibles = new ArrayList<>();

    public void prestarLibro(Libro libro, Estudiante estudiante) {
        if (librosDisponibles.contains(libro)) {
            librosDisponibles.remove(libro);
            estudiante.prestarLibro(libro);
            System.out.println("Libro prestado a " + estudiante.getNombre());
        } else {
            System.out.println("El libro no está disponible para préstamo.");
        }
    }

    public void devolverLibro(Libro libro, Estudiante estudiante) {
        librosDisponibles.add(libro);
        estudiante.devolverLibro(libro);
        System.out.println("Libro devuelto correctamente.");
    }
}

public class ReclamoLibro {
    private int numero;
    private Date fecha;
    private String descripcion;
    private List<DetallePrestamo> ejemplaresReclamados;

    public ReclamoLibro(int numero, Date fecha, String descripcion, List<DetallePrestamo> ejemplaresReclamados) {
        this.numero = numero;
        this.fecha = fecha;
        this.descripcion = descripcion;
        this.ejemplaresReclamados = ejemplaresReclamados;
    }

}
