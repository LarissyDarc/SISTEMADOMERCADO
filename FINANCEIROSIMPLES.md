package App;

import java.util.Scanner;

public class Financeiro {

	public static void main(String[] args) {
		
		Scanner entrada = new Scanner(System.in);
		
		// ===== Entrada de Dados =====
		
		System.out.printf("Digite o nome do produto: ");
		String nomeProduto = entrada.nextLine();
		
		System.out.printf("Digite o preço da compra: ");
		double precoCompra = entrada.nextDouble();
		
		System.out.printf("Digita o preço da venda: ");
		double precoVenda = entrada.nextDouble();
		
		System.out.printf("Digita a quantidade da vendida: ");
		int quantidadeVendida = entrada.nextInt();
		
		// ==== Calculos ====
		
		double receitaTotal = precoVenda * quantidadeVendida;
		double custoTotal = precoCompra * quantidadeVendida;
		double lucroBruto = receitaTotal - custoTotal;
		double imposto = receitaTotal * 0.09;
		double lucroLiquido = lucroBruto - imposto;
		
		// ==== Saida formada ====
		
		System.out.println("==== RELATÓRIO FINANCEIRO ");
		System.out.printf("Produto: %s%n ", nomeProduto);
		System.out.printf("Receita total: R$ %.2f%n", receitaTotal);
        System.out.printf("Custo total: R$ %.2f%n", custoTotal);
        System.out.printf("Lucro bruto: R$ %.2f%n", lucroBruto);
        System.out.printf("Imposto (8%%): R$ %.2f%n", imposto);
        System.out.printf("Lucro líquido: R$ %.2f%n", lucroLiquido);

        // Mensagem personalizada
        if (lucroLiquido > 0) {
            System.out.printf("\n✅ O produto \"%s\" gerou lucro líquido de R$ %.2f.%n", nomeProduto, lucroLiquido);
        } else if (lucroLiquido == 0) {
            System.out.printf("\n⚠️ O produto \"%s\" ficou no ponto de equilíbrio, sem lucro nem prejuízo.%n", nomeProduto);
        } else {
            System.out.printf("\n❌ O produto \"%s\" gerou prejuízo líquido de R$ %.2f.%n", nomeProduto, Math.abs(lucroLiquido));
        }

        entrada.close();
	}

}
