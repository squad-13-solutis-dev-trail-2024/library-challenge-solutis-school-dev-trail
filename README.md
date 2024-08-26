# Desafio – Livraria Virtual - Solutis School Dev Trail

## 1. Introdução

Este projeto consiste em implementar um sistema de gerenciamento de uma livraria virtual, explorando os conceitos de
composição, herança e polimorfismo. O sistema deve seguir o diagrama de classes UML mostrado abaixo, onde os
construtores e os métodos de acesso (getters e setters) foram omitidos.

## 2. Descrição do Sistema

O sistema deverá ser baseado em um menu, entrada de dados via console, com as seguintes opções:

- **a) Cadastrar livro:** esta opção permite ao usuário cadastrar um livro.
- **b) Realizar uma venda:** esta opção permite ao usuário realizar a venda de um ou mais livros.
- **c) Listar livros:** o sistema deverá listar todos os livros cadastrados, sejam eles eletrônicos ou impressos.
- **d) Listar vendas:** o sistema deverá listar todas as vendas realizadas.
- **e) Sair do programa:** encerra a execução do programa.

## 3. Descrição das Classes

### 3.1 Livro

A classe abstrata Livro possui 4 atributos:

- **titulo:** título do livro.
- **autores:** nome do autor ou dos autores do livro.
- **editora:** nome da editora do livro.
- **preco:** preço do livro.

Método obrigatório:

- **String toString():** devolve uma representação textual dos atributos de um livro.

### 3.2 Impresso

A classe Impresso representa um livro impresso e possui 2 atributos:

- **frete:** frete cobrado para entrega do livro.
- **estoque:** número de exemplares do livro em estoque.

Métodos obrigatórios:

- **void atualizarEstoque():** subtrai 1 do valor do atributo estoque.
- **String toString():** devolve uma representação textual de todos os atributos de um livro impresso.

### 3.3 Eletronico

A classe Eletronico representa um livro eletrônico e possui 1 atributo:

- **tamanho:** representa o tamanho do arquivo eletrônico do livro em KB.

Método obrigatório:

- **String toString():** devolve uma representação textual de todos os atributos de um livro eletrônico.

### 3.4 Venda

A classe Venda possui 5 atributos:

- **livros:** um vetor de referências a objetos do tipo Livro, representando os livros associados a uma venda.
- **numVendas:** atributo estático que representa a quantidade de vendas realizadas.
- **numero:** valor sequencial com início em 1 e é incrementado a cada venda.
- **cliente:** nome do cliente que comprou o(s) livro(s).
- **valor:** valor total da venda.

Métodos obrigatórios:

- **addLivro(l: Livro, index: int):** adiciona o livro l na posição index do array livros.
- **listarLivros():** lista todos os livros da venda.

### 3.5 LivrariaVirtual

A classe LivrariaVirtual possui 9 atributos:

- **MAX_IMPRESSOS:** constante que representa o número máximo de livros impressos que podem ser cadastrados.
- **MAX_ELETRONICOS:** constante que representa o número máximo de livros eletrônicos que podem ser cadastrados.
- **MAX_VENDAS:** constante que representa o número máximo de vendas que podem ser cadastradas.
- **impressos:** vetor de referências a objetos da classe Impresso, representando os livros impressos cadastrados.
- **eletronicos:** vetor de referências a objetos da classe Eletronico, representando os livros eletrônicos cadastrados.
- **vendas:** vetor de referências a objetos da classe Venda, representando as vendas realizadas.
- **numImpressos:** número de livros impressos cadastrados.
- **numEletronicos:** número de livros eletrônicos cadastrados.
- **numVendas:** número de vendas realizadas.

Métodos obrigatórios:

- **cadastrarLivro():** permite ao usuário cadastrar um livro (impresso, eletrônico ou ambos).
- **realizarVenda():** permite ao usuário realizar uma venda, solicitando o nome do cliente e a quantidade de livros que
  ele deseja comprar.
- **listarLivrosImpressos():** exibe os dados de todos os livros impressos cadastrados.
- **listarLivrosEletronicos():** exibe os dados de todos os livros eletrônicos cadastrados.
- **listarLivros():** exibe os dados de todos os livros cadastrados.
- **listarVendas():** exibe os dados de todas as vendas realizadas.
- **main(args: String[]):** instancia um objeto da classe LivrariaVirtual, exibe o menu de opções e invoca os métodos
  apropriados.

## 4. Distribuição de Tarefas

1. **Aldemir Carlos** - Desenvolveu a classe `LivrariaVirtual` e seus métodos `main()`, `listarLivrosEletronicos()`, `listarLivros()`, `listarVendas()` e getters.
2. **Gabriel de Abreu** - Desenvolveu a classe `LivrariaVirtual` e seus métodos `cadastrarLivro()`, `realizarVenda()`, e `listarLivrosImpressos()` e getters.
3. **Kauê Alexandre** - Desenvolveu a classe `Venda` e seus métodos `addLivro()`, `listarLivros()`, `toString()`, `equals()` e `hashCode()`. Além dos construtores, getters e setters.
4. **Pedro Emanoel** - Desenvolveu a classe `Livro` e seu método `toString()`, `equals()` e `hashCode()`. Além dos construtores, getters e setters.
5. **Suerdo Flaubert** - Desenvolveu a classe `Eletronico` e seu método `toString()`, `equals()` e `hashCode()`. Além dos construtores, getters e setters.
6. **Pedro Messias** - Desenvolveu a classe `Impresso` e seus métodos `atualizarEstoque()`, `toString()`, `equals()` e `hashCode()`. Além dos construtores, getters e setters.
7. **Vinícius Andrade** - Desenvolveu a classe `EntradaDeDados` e seus métodos para leitura de entrada de dados e suas validações pertinentes: `lerTipoLivroVenda()`, `lerTipoLivroCadastro()` ,
`lerTitulo()`, `lerAutores()`, `lerEditora()`, `lerPreco()`, `lerFrete()`, `lerEstoque()`, `lerTamanhoArquivoEmKB()`, `lerLivroID()`, `lerQuantidadeExemplares()` e `lerCliente()`

## 5. Observação

Todos os membros participaram do code-review. 
Foi utilizado a Ferramenta IntelliJ IDEA Ultimate 2024.2.0.2 juntamente com o plugin 'Code With Me' para codificação em grupo na mesma IDE.

## 6. Ferramentas

- **IDE:** IntelliJ IDEA Ultimate 2024.2.0.2
- **JDK:** OpenJDK 21
- **Ferramenta de Colaboração:** Plugin 'Code With Me' para codificação em grupo
- **Sistema de Controle de Versão:** Git
- **Ferramenta de Build:** Maven