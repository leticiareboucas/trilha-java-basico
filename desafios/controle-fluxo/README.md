import java.util.Scanner;

// Exceção personalizada
class ParametrosInvalidosException extends Exception {
    public ParametrosInvalidosException() {
        super("O segundo parâmetro deve ser maior que o primeiro.");
    }
}

public class Contador {
    public static void main(String[] args) {
        Scanner terminal = new Scanner(System.in);
        System.out.println("Digite o primeiro parâmetro");
        int parametroUm = terminal.nextInt(); // Use nextInt para ler um valor inteiro
        System.out.println("Digite o segundo parâmetro");
        int parametroDois = terminal.nextInt(); // Use nextInt para ler um valor inteiro

        try {
            contar(parametroUm, parametroDois);
        } catch (ParametrosInvalidosException exception) { // Capture a exceção personalizada
            System.out.println(exception.getMessage()); // Imprima a mensagem da exceção
        }
    }

    static void contar(int parametroUm, int parametroDois) throws ParametrosInvalidosException {
        if (parametroUm >= parametroDois) {
            throw new ParametrosInvalidosException(); // Lança a exceção se o primeiro parâmetro não for menor que o segundo
        }

        for (int i = parametroUm; i <= parametroDois; i++) {
            System.out.println(i);
        }
    }
}
