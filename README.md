import java.util.Random;
import java.util.Scanner;
public class LOTOFACIL_EM_JAVA {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        int tipo;
        do {
            Menu();
            tipo = scanner.nextInt();
            scanner.nextLine();
            switch (tipo) {
                case 1: caso0ate100(scanner, random);
                    break;
                case 2: casoLetra(scanner);
                    break;
                case 3: casoParImpar(scanner);
                    break;
                case 0: System.out.println("Saindo do jogo...");
                    break;
                default: System.out.println("Opção inválida. Por favor, escolha uma opção válida.");
            }
        } while (tipo != 0);
        scanner.close();
    }
    public static void Menu() {
        System.out.println("Menu da LOTOFÁCIL");
        System.out.println("Escolha uma opção abaixo para apostar: ");
        System.out.println("1 - 0 a 100");
        System.out.println("2 - A à Z");
        System.out.println("3 - Par ou ímpar");
        System.out.println("0 - Sair");
        System.out.print("OPÇÃO: ");
    }
    public static void caso0ate100(Scanner scanner, Random random) {
        System.out.print("Digite um número de 0 a 100: ");
        int numero = scanner.nextInt();

        if (!(numero >= 0 && numero <= 100)) {
            System.out.println("Aposta inválida.");
            return;
        }

        int numerorandom = random.nextInt(101);

        if (numero == numerorandom) {
            System.out.println("Você ganhou R$ 1.000,00 reais.");
        } else {
            System.out.println("Que pena! O número sorteado foi: " + numerorandom + ".");
        }
    }
    public static void casoLetra(Scanner scanner) {
        System.out.print("Digite uma letra de A à Z: ");
        char letraApostada = scanner.next().toUpperCase().charAt(0);

        if (!Character.isLetter(letraApostada)) {
            System.out.println("Aposta inválida.");
            return;
        }

        char letraPremiada = 'E';

        if (letraApostada == letraPremiada) {
            System.out.println("Você ganhou R$ 500,00 reais.");
        } else {
            System.out.println("Que pena! A letra sorteada foi : " + letraPremiada + ".");
        }
    }
    public static void casoParImpar(Scanner scanner) {
        System.out.print("Digite um número inteiro: ");
        int numero = scanner.nextInt();

        if (numero % 2 == 0) {
            System.out.println("Você ganhou R$ 100,00 reais.");
        } else {
            System.out.println("Que pena! O número digitado é ímpar e a premiação foi para números pares.");
        }
    }
}
