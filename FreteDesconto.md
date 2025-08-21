package App;

import java.util.Scanner;

public class FreteDesconto {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Entrada de dados
        System.out.print("Informe a distância percorrida (km): ");
        double distancia = sc.nextDouble();

        System.out.print("Informe o valor por km (R$): ");
        double valorKm = sc.nextDouble();

        sc.nextLine(); // limpar buffer
        System.out.print("Informe o tipo de cliente (COMUM, FIDELIDADE, VIP): ");
        String tipoCliente = sc.nextLine().toUpperCase();

        // Cálculo do valor bruto
        double valorBruto = distancia * valorKm;
        double desconto = 0.0;

        // Estrutura de decisão
        if (tipoCliente.equals("FIDELIDADE")) {
            desconto = 0.10; // 10%
        } else if (tipoCliente.equals("VIP")) {
            desconto = 0.20; // 20%
        }

        double valorFinal = valorBruto - (valorBruto * desconto);

        // Saída formatada
        System.out.println("\n=== RESUMO DO FRETE ===");
        System.out.printf("Distância: %.2f km%n", distancia);
        System.out.printf("Valor por km: R$ %.2f%n", valorKm);
        System.out.printf("Cliente: %s%n", tipoCliente);
        System.out.printf("Valor bruto: R$ %.2f%n", valorBruto);
        System.out.printf("Desconto aplicado: %.0f%%%n", desconto * 100);
        System.out.printf("Valor final: R$ %.2f%n", valorFinal);

        sc.close();
    }
}
