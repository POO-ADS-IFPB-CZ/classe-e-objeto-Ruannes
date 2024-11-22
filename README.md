## Questão1

**Atributos:**                                      
* Marca;                                            
* Potência;                                         
* Tipo(Led, fluorescente, incandescente);           
* Voltagem;
* Preço;
* Disponibilidade;
* Garantia.

**Métodos:**
* Exibir informações;                                            
* Alterar preço;                                         
* Atualizar estoque.

## Questão7

Nome da classe com espaços; não pode ter espaço pro nome  
Não possui expecificador de acesso; não é obrigatório mas é bom ter   
Atributos sem encapsulamento; não segue o senso comum da p.o.o  
Não tem os getters e setters;

## Questão 8

Retorno de true e false em um método que declara retornar int;  
O método menor tenta retornar um valor em um método void;  
Os campos (num1 e num2) e os métodos (maior e menor) não têm especificadores de acesso (public, private, ou protected);  
Não há um construtor ou métodos setter para inicializar os campos.  

## Questão 14  

Ele serve pra proteger os dados de uma classe, deixando a modificação ser feita só por meio de métodos específicos, como os getters e setters. Isso acontece quando declara os atributos como privados (private) e tem métodos públicos (public) pra acessar ou fazer alteração controlada.

Ex sem encapsulamento:
public class Conta {
    public double saldo;
    public String nome;
}
Conta conta = new Conta();
conta.saldo = -1000;

Desse jeito ele vai deixar valores inconsistentes como o saldo negativo.

Ex com encapsulamento:  

public class Conta {  
    private double saldo;  
    private String nome;  
  
    public Conta(String nome, double saldoInicial) {  
        this.nome = nome;  
        if (saldoInicial >= 0) {  
            this.saldo = saldoInicial;  
        } else {  
            this.saldo = 0; // Valor padrão se inválido  
        }  
    }  
  
    public double getSaldo() {  
        return saldo;  
    }  
  
    public void deposita(double valor) {  
        if (valor > 0) {  
            saldo += valor;  
        }  
    }  
  
    public boolean retira(double valor) {  
        if (valor > 0 && valor <= saldo) {  
            saldo -= valor;  
            return true;  
        }  
        return false;  
    }  
}  
Conta conta = new Conta("João", 1000);  
conta.deposita(500); // Saldo agora é 1500  
conta.retira(2000);  // Operação negada (retorna false)  
System.out.println(conta.getSaldo()); // Saldo é 1500  
  
Assim com as validações nos métodos deposita e retira, a classe impede que valores inválidos ou inconsistentes sejam atribuídos pro saldo e só esses métodos conseguem alterar o valor do saldo e assegurando a lógica. Assim sendo, o encapsulamento vai garantir sistemas seguros e robustos.


