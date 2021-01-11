//TareaT2
package es.studium.TareaT2;

public class TareaT2 {
    public static void main(String[] args) {
        
        /* Antonio y Beatriz se hacen cliente del banco */
        Cliente antonio = new Cliente("123456789Z", "Antonio Alonso", "Av. Pueblo Saharaui, s/n");
        Cliente beatriz = new Cliente("987654321A", "Beatriz Benítez", "Calle Sol, 4");

        /* Por defecto, todas las cuentas nuevas tienen 100€ */
        Cuenta cuentaAntonio = new Cuenta(48151, 100, antonio);
        Cuenta cuentaBeatriz = new Cuenta(62342, 100, beatriz);

        /* Antonio y Beatriz consultan el saldo */
        System.out.println("La cuenta de " + cuentaAntonio.getCliente().getNombre() + " tiene "
                        + cuentaAntonio.getSaldo() + " euros.");
        System.out.println("La cuenta de " + cuentaBeatriz.getCliente().getNombre() + " tiene "
                        + cuentaBeatriz.getSaldo() + " euros.");

        /* Beatriz transfiere 50€ a Antonio */
        cuentaBeatriz.setSaldo(cuentaBeatriz.getSaldo() - 50);
        cuentaAntonio.setSaldo(cuentaAntonio.getSaldo() + 50);

        /* Antonio y Beatriz vuelven a consultar para comprobar que todo ha ido bien */
        System.out.println("La cuenta de " + cuentaAntonio.getCliente().getNombre() + " tiene "
                        + cuentaAntonio.getSaldo() + " euros.");
        System.out.println("La cuenta de " + cuentaBeatriz.getCliente().getNombre() + " tiene "
                        + cuentaBeatriz.getSaldo() + " euros.");

        /* Antonio gana 100€ en una rifa y hace un ingreso en su cuenta */
        cuentaAntonio.setSaldo(cuentaAntonio.getSaldo() + 100);

        /* Beatriz tiene que pagar 30€ a hacienda y retira el dinero */
        cuentaBeatriz.setSaldo(cuentaBeatriz.getSaldo() - 30);

        /* Antonio transfiere 50€ a Beatriz */
        cuentaAntonio.setSaldo(cuentaAntonio.getSaldo() - 50);
        cuentaBeatriz.setSaldo(cuentaBeatriz.getSaldo() + 50);

        System.out.println("La cuenta de " + cuentaAntonio.getCliente().getNombre() + " tiene "
                        + cuentaAntonio.getSaldo() + " euros.");
        System.out.println("La cuenta de " + cuentaBeatriz.getCliente().getNombre() + " tiene "
                        + cuentaBeatriz.getSaldo() + " euros.");
        
	}
    
}
    

class Cliente {
    // Constructor por defecto
    Cliente() {
        
    }
    
    // Constructor por parametros
    Cliente(String id, String nombre, String direccion) {
        
        this.id = id;
        this.nombre = nombre;
        this.direccion = direccion;
        
    }
    
    // Getters
    String getId() { return id; }
    String getNombre() { return nombre; }
    String getDireccion() { return direccion; }
    
    // Setters
    void setId(String x) { id = x; }
    void setNombre(String x) { nombre = x; }
    void setDireccion(String x) { direccion = x; }
    
    
    // Definicion de variables
    private String id, nombre, direccion;
    
}


class Cuenta {
    
    // Constructor por defecto
    Cuenta() {
        
    }
    
    // Constructor por parametros
    Cuenta(int numCuenta, int saldo, Cliente c) {
        
        this.numCuenta = numCuenta;
        this.saldo = saldo;
        cliente = c;
        
    }
    
    // Getters
    int getNumCuenta() { return numCuenta; }
    int getSaldo() { return saldo; }
    Cliente getCliente() { return cliente; }
    
    // Setters
    void setNumCuenta(int x) { numCuenta = x; }
    void setSaldo(int x) { saldo = x; }
    void setCliente(Cliente x) { cliente = x; }
    
    // Definicion de variables
    private int numCuenta, saldo;
    Cliente cliente;
    
}
