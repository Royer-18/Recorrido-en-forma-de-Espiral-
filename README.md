package ejer6recorridoenespiral;
import java.util.Scanner;

public class Ejer6RecorridoenEspiral {

    public static void main(String[] args) {
        // TODO code application logic here
        
         Scanner teclado = new Scanner(System.in);
        System.out.println("Ingrese la cantidad de filas: ");
        int filas = teclado.nextInt();
        System.out.println("Ingrese la cantidad de columnas: ");
        int columnas = teclado.nextInt();
        int matriz[][] = new int[filas][columnas];
        System.out.println("Ingrese los elementos: ");
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                matriz[i][j] = teclado.nextInt();
            }
        }
        // Mostrar matriz
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                System.out.print("[" + matriz[i][j] + "]");
            }
            System.out.println("");
        }
        // Recorrido en espiral
        int izquierda = 0;
        int derecha = columnas - 1;
        int arriba = 0;
        int abajo = filas - 1;
        while (izquierda <= derecha && arriba <= abajo) {
            // Recorre la fila superior de izquierda a derecha
            for (int i = izquierda; i <= derecha; i++) {
                System.out.print(matriz[arriba][i] + " ");
            }
            arriba++;
            // Recorre la columna derecha de arriba a abajo
            for (int i = arriba; i <= abajo; i++) {
                System.out.print(matriz[i][derecha] + " ");
            }
            derecha--;
            // Recorre la fila inferior de derecha a izquierda
            if (arriba <= abajo) {
                for (int i = derecha; i >= izquierda; i--) {
                    System.out.print(matriz[abajo][i] + " ");
                }
                abajo--;
            }
            // Recorre la columna izquierda de abajo a arriba
            if (izquierda <= derecha) {
                for (int i = abajo; i >= arriba; i--) {
                    System.out.print(matriz[i][izquierda] + " ");
                }
                izquierda++;
            }
        }    
    }
}
