package Main;
import java.util.ArrayList;
import java.util.Scanner;

public class ProjetoEtapa1 {
    public static void main(String[] args) {
        ArrayList<String> listaLivros = new ArrayList<>();
        ArrayList<String> listAuthor = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        int opcao;

        do {
            System.out.println("\n** Sistema de Lista de Livros **");
            System.out.println("1. Adicionar Livro");
            System.out.println("2. Remover Livro");
            System.out.println("3. Buscar Livro");
            System.out.println("4. Exibir lista de Livros");
            System.out.println("5. Limpar lista de Livros");
            System.out.println("6. Sair");
            System.out.print("Escolha uma opção: ");
            opcao = scanner.nextInt();
            scanner.nextLine();

            switch (opcao) {
                case 1:

                    System.out.print("\nDigite o nome do Livro para adicionar: ");
                    String livro = scanner.nextLine();
                    System.out.print("Digite o nome do Autor: ");
                    String autor = scanner.nextLine();

                    if (listaLivros.contains(livro)) {
                        System.out.println("Livro já existe na lista.");
                    } else {
                        listaLivros.add(livro);
                        listAuthor.add(autor);

                        System.out.println("--------------------------------------");
                        System.out.println("Livro e autor adicionados com sucesso!");
                        System.out.println("--------------------------------------");
                    }
                    break;

                case 2:
                    System.out.print("\nDigite o nome do Livro para remover: ");
                    String itemRemover = scanner.nextLine();
                    int index = listaLivros.indexOf(itemRemover);
                    if (index != -1) {
                        listaLivros.remove(index);
                        listAuthor.remove(index);

                        System.out.println("------------------------------");
                        System.out.println("Livro removido com sucesso!");
                        System.out.println("------------------------------");
                    } else {
                        System.out.println("------------------------------");
                        System.out.println("Livro não encontrado.");
                        System.out.println("------------------------------");
                    }
                    break;

                case 3:
                    System.out.print("\nDigite o nome do livro para buscar: ");
                    String livroBusca = scanner.nextLine();
                    int iBusca = listaLivros.indexOf(livroBusca);
                    //Procura  posição da String
                    if (iBusca != -1) {
                        System.out.println("------------------------------");
                        System.out.println("Livro encontrado:");
                        System.out.println("- " + listaLivros.get(iBusca) + " (Autor: " + listAuthor.get(iBusca) + ")");
                        //retorna o elemento que está naquela posição.
                        System.out.println("------------------------------");
                    } else {
                        System.out.println("------------------------------");
                        System.out.println("Livro não encontrado.");
                        System.out.println("------------------------------");
                    }
                    break;

                case 4:
                    if (listaLivros.isEmpty()) {//verifica se essa lista está vazia, retorna o boleano true ou false
                        System.out.println("------------------------------");
                        System.out.println("A lista de livros está vazia.");
                        System.out.println("------------------------------");
                    } else {
                        System.out.println("------------------------------");
                        System.out.println("Lista de Livros:");
                        for (int i = 0; i < listaLivros.size(); i++) {
                            // retorna o número de elementos da lista.
                            System.out.println("- " + listaLivros.get(i) + " (Autor: " + listAuthor.get(i) + ")");
                        }
                        System.out.println("------------------------------");
                    }
                    break;

                case 5:
                    listaLivros.clear();
                    listAuthor.clear();
                    System.out.println("------------------------------");
                    System.out.println("Lista de Livros limpa com sucesso!");
                    System.out.println("------------------------------");
                    break;

                case 6:
                    System.out.print("*********************************");
                    System.out.print("\nObrigado por usar nosso sistema!!!");
                    System.out.println("\nAté mais!!");
                    System.out.println("*********************************");
                    break;

                default:
                    System.out.println("--------------------------------");
                    System.out.println("Opção inválida. Tente novamente.");
                    System.out.println("--------------------------------");
            }

        } while (opcao != 6);

        scanner.close();
    }
}
