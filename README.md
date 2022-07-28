# Controle-de-estoque-de-mercadoria-codigo-em-Java

Considere o problema abaixo:

Faça um programa para controlar o estoque de mercadorias de uma empresa. Inicialmente, o programa deverá preencher dois vetores com dez posições cada, onde o primeiro corresponde ao código do produto e o segundo ao total desse produto em estoque. Logo após, o programa deverá ler o código de um produto comprado por um cliente juntamente com a quantidade. O programa deverá verificar:

se o código do produto solicitado existe. Se existir, tentar atender ao pedido; caso contrário, exibir mensagem “Código inexistente”;
cada pedido feito por um cliente só pode ser atendido integralmente. Caso isso não seja possível, mostrar a mensagem “Não temos estoque suficiente desta mercadoria”. Se puder atende-lo, mostrar a mensagem “Pedido atendido!”;
efetuar a atualização do estoque (subtrair de seu valor a quantidade) somente se o pedido for atendido integralmente;
no final do programa, escrever os códigos dos produtos com seus respectivos estoques já atualizados.
Complete o programa abaixo, arrastando e soltando os trechos de código nos espaços em branco, de forma que o problema acima seja corretamente implementado.

public class GerenciaEstoque {
	public static void main(String[] args) {
		int[] codigos = new int[10];
		[int[] estoque = new int[10];]
		
		// Leitura
		for(int cont = 0; cont < codigos.length; cont++) {
			System.out.printf("-------------------------- PRODUTO %02d --------------------------\n", cont+1);
			System.out.print("Codigo: ");
			[codigos[cont] = Integer.parseInt(System.console().readLine());]
			System.out.print("Quant. em estoque: ");
			[estoque[cont] = Integer.parseInt(System.console().readLine());]
		}
		
		System.out.println("\n----------------------------- COMPRA -----------------------------");
		System.out.print("Codigo do produto: ");
		[int codProd = Integer.parseInt(System.console().readLine());]
		System.out.print("Quantidade comprada: ");
		[int quant = Integer.parseInt(System.console().readLine());]
		
		// Processamento e Saída
		boolean achou = false;
		for(int cont = 0; cont < codigos.length; cont++) {
			if([codigos[cont] == codProd]) {
				[achou = true;]
				if([quant <= estoque[cont]]) {
					System.out.println("\nPedido atendido!");
					[estoque[cont] ‑= quant;]
				} else {
					System.out.println("\nNao temos estoque suficiente desta mercadoria.");
				}
			}
		}
		
		if(!achou)
			System.out.println("\nCodigo inexistente!");
		
		System.out.println();
		for(int cont = 0; cont < codigos.length; cont++) {
			System.out.printf("-------------------------- PRODUTO %02d --------------------------\n", cont+1);
			System.out.printf("Codigo: %d\n", codigos[cont]);
			System.out.printf("Quant. em estoque: %d\n", estoque[cont]);
		}
	}
}
