# taller visual estudio code.
punto 1.1
import java.util.Scanner;

public class CalculadoraM {
    public static void main(String[] args) {
        char operacion = leerOperacion();
        double num1 = leerNumero("ingresa el primer numero");
        double num2 = leerNumero("ingresa el segundo numero");

        if (operacion == '/' && num2 == 0) {
            System.out.println("No se puede dividir entre 0.");
        } else {
            double resultado = calcular(num1, num2, operacion);
            mostrarResultado(resultado);
        }
    }

    public static double leerNumero(String mensaje) {
        Scanner scanner = new Scanner(System.in);
        double numero;
        while (true) {
            System.out.print(mensaje);
            String entrada = scanner.nextLine();
            if (esNumeroValido(entrada)) {
                numero = Double.parseDouble(entrada);
                return numero;
            } else {
            }
        }
    }

    public static boolean esNumeroValido(String entrada) {
        return entrada.matches("-?\\d+(\\.\\d+)?");
    }

    public static char leerOperacion() {
        Scanner scanner = new Scanner(System.in);
        char operacion;
        while (true) {
            System.out.print("Introduce la operación (+, -, *, /): ");
            String entrada = scanner.nextLine();
            if (entrada.length() == 1 && "+-*/".indexOf(entrada.charAt(0)) != -1) {
                operacion = entrada.charAt(0);
                return operacion;
            } else {
                System.out.println("Operación no válida. Por favor, introduce una operación válida.");
            }
        }
    }

    public static double calcular(double a, double b, char op) {
        if (op == '+') {
            return a + b;
        } else if (op == '-') {
            return a - b;
        } else if (op == '*') {
            return a * b;
        } else if (op == '/') {
            return a / b;
        } else {
            return 0;
        }
    }

    public static void mostrarResultado(double resultado) {
        System.out.println("El resultado de la operación es: " + resultado);
    }
}
