# Novo-processo-de-valida-o-DIO
Vamos começar criando o projeto DesafioControleFluxo e as classes Contador e ParametrosInvalidosException.

Aqui está a estrutura básica do projeto:

Crie uma pasta chamada DesafioControleFluxo.
Dentro dessa pasta, crie outra pasta chamada src para armazenar o código-fonte.
Dentro da pasta src, crie o pacote desafiocontrolefluxo.
Dentro do pacote desafiocontrolefluxo, crie os arquivos Contador.java e ParametrosInvalidosException.java.
Vamos começar criando a classe ParametrosInvalidosException:
package desafiocontrolefluxo;

public class ParametrosInvalidosException extends Exception {
    public ParametrosInvalidosException(String message) {
        super(message);
    }
}
Agora, vamos implementar a classe Contador:
package desafiocontrolefluxo;

public class Contador {
    public static void main(String[] args) {
        try {
            if (args.length != 2) {
                throw new IllegalArgumentException("Número inválido de argumentos. Forneça dois números inteiros.");
            }

            int numeroInicial = Integer.parseInt(args[0]);
            int numeroFinal = Integer.parseInt(args[1]);

            if (numeroInicial >= numeroFinal) {
                throw new ParametrosInvalidosException("O segundo parâmetro deve ser maior que o primeiro.");
            }

            for (int i = numeroInicial; i <= numeroFinal; i++) {
                System.out.println("Imprimindo o número " + i);
            }
        } catch (NumberFormatException e) {
            System.out.println("Os argumentos devem ser números inteiros.");
        } catch (ParametrosInvalidosException e) {
            System.out.println(e.getMessage());
        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }
    }
}
Com isso, temos a estrutura básica do projeto pronto. Agora, podemos executar a classe Contador passando os parâmetros via terminal para testar o comportamento do sistema. Por exemplo:
java desafiocontrolefluxo.Contador 12 30
Com isso, ele deve imprimir os números de 12 a 30 no console. Se tentarmos passar o segundo parâmetro menor que o primeiro, deverá ser lançada a exceção ParametrosInvalidosException.
