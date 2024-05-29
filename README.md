# **Criando um App Gerenciador de Estoque com Programação Orientada a Objetos em Ruby**

## **Introdução**
Neste artigo, vamos desenvolver um aplicativo gerenciador de estoque utilizando os princípios da Programação Orientada a Objetos (POO) com Ruby. A POO é um paradigma de programação que utiliza conceitos como classes, objetos, herança, encapsulamento e polimorfismo para criar software mais robusto e escalável.

## **1. Princípios da POO**

### **1.1. Classes e Objetos**
Classes são os "moldes" para os objetos, definindo atributos e métodos. Objetos são instâncias de classes, contendo dados e comportamentos específicos.

### **1.2. Herança**
Herança permite que uma classe herde características de outra, promovendo reuso de código e organização.

### **1.3. Encapsulamento**
Encapsulamento protege o estado interno do objeto e expõe apenas métodos selecionados para interação.

### **1.4. Polimorfismo**
Polimorfismo permite que objetos de diferentes classes sejam tratados como instâncias de uma classe pai comum.

## **2. Estrutura do Projeto**

### **2.1. Classe Produto**
```ruby
class Produto
  attr_accessor :nome, :quantidade

  def initialize(nome, quantidade)
    @nome = nome
    @quantidade = quantidade
  end

  def to_s
    "Produto: #{@nome}, Quantidade: #{@quantidade}"
  end
end
```

### **2.2. Classe Estoque**
```ruby
class Estoque
  def initialize
    @produtos = []
  end

  def adicionar_produto(produto)
    @produtos << produto
  end

  def remover_produto(nome)
    @produtos.reject! { |produto| produto.nome == nome }
  end

  def listar_produtos
    @produtos.each { |produto| puts produto }
  end
end
```

### **2.3. Classe Venda**
```ruby
class Venda
  def initialize(estoque)
    @estoque = estoque
  end

  def vender(nome, quantidade)
    produto = @estoque.produtos.find { |p| p.nome == nome }
    produto.quantidade -= quantidade if produto
  end
end
```

## **3. Implementação e Uso**

### **3.1. Criando Produtos e Estoque**
```ruby
estoque = Estoque.new
estoque.adicionar_produto(Produto.new('Teclado', 50))
estoque.adicionar_produto(Produto.new('Mouse', 150))
```

### **3.2. Realizando Vendas**
```ruby
venda = Venda.new(estoque)
venda.vender('Teclado', 1)
```

### **3.3. Listando Produtos**
```ruby
estoque.listar_produtos
```

## **4. Conclusão**
Ao aplicar os princípios da POO, criamos um app gerenciador de estoque em Ruby que é fácil de entender, manter e expandir. Este projeto serve como uma excelente prática para quem deseja aprofundar-se em Ruby e na POO, além de ser um ótimo exemplo para adicionar ao seu portfólio.

Espero que este artigo tenha sido útil e que qualquer um que precisar, se sinta inspirado a desenvolver suas próprias aplicações utilizando a Programação Orientada a Objetos em Ruby.
