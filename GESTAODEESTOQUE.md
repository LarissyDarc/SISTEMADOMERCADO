package App;

import java.util.Scanner;

public class ControleEstoque {

	public static void main(String[] args) {
		
		Scanner entrada = new Scanner(System.in);
				
		// 1. Declaraçao de Variaveis 
		
		String nomeProduto = "Feijão preto 1kg";
		int quantidadeEstoque = 22;
		double precoProduto = 9.99;
		long codigoDeBarra = 7958230480156L;
		var categoria = "Alimento";
		boolean disponivel = true;
		
		// 2. Exibir informações iniciais 
		
		System.out.println("=== Informações do Produto ===");
		System.out.println("Nome: " + nomeProduto);
		System.out.println("Qualidade em estoque: " + quantidadeEstoque);
		System.out.println("Preço: R$ " + precoProduto);
		System.out.println("Codigo de barra: " + codigoDeBarra);
		System.out.println("Categoria: " + categoria);
		System.out.println("Disponível para Vendas: " + (disponivel ? "Sim " : "Não "));
		
		// 3. Simulacao de venda
		
		System.out.println("Digita a quantidade vendida: ");
		int quantidadeVendida = entrada.nextInt();
		quantidadeEstoque -= quantidadeVendida;
		System.out.println("Estoque após a venda: 	" + quantidadeEstoque);
		
		// 4. Simulaçao de reposiçao
		
		System.out.println("Digita a quantidade de repousição: ");
		int quantidadeRepousicao = entrada.nextInt();
		quantidadeEstoque += quantidadeRepousicao;
		System.out.println("Estoque apos a venda: " + quantidadeEstoque);
		
		entrada.close();
		
	}
}
