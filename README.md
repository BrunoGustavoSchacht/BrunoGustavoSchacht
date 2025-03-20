public class Compra {
    private String status;
    private String enderecoEntrega;
    private String produto;
    private int qnt;
    private double precoUnitario;

    // Construtor vazio
    public Compra() {}

    // Construtor com todos os atributos
    public Compra(String produto, double precoUnitario, int qnt, String enderecoEntrega, String status) {
        this.produto = produto;
        this.precoUnitario = precoUnitario;
        this.qnt = qnt;
        this.enderecoEntrega = enderecoEntrega;
        this.status = status;
    }

    // Métodos getters e setters
    public String getStatus() {
        return status;
    }

    public void setStatus(String status) {
        this.status = status;
    }

    public String getEnderecoEntrega() {
        return enderecoEntrega;
    }

    public void setEnderecoEntrega(String enderecoEntrega) {
        this.enderecoEntrega = enderecoEntrega;
    }

    public String getProduto() {
        return produto;
    }

    public void setProduto(String produto) {
        this.produto = produto;
    }

    public int getQnt() {
        return qnt;
    }

    public void setQnt(int qnt) {
        this.qnt = qnt;
    }

    public double getPrecoUnitario() {
        return precoUnitario;
    }

    public void setPrecoUnitario(double precoUnitario) {
        this.precoUnitario = precoUnitario;
    }

    // Método para calcular o valor total da compra
    public double valorTotal() {
        return qnt * precoUnitario;
    }
}

//-------------------------------------------------------------------------------------------------------------------------------
import java.util.ArrayList;
import java.util.List;

public class ExemploCompra {
    private static List<Compra> compras = new ArrayList<>();

    public static void main(String[] args) {
        Compra compra = new Compra();
        compra.setProduto("Camiseta XPTO");
        compra.setPrecoUnitario(140.0);
        compra.setQnt(2);
        compra.setEnderecoEntrega("Rua Getúlio Vargas");
        compra.setStatus("Pedido realizado");

        compras.add(compra);

        Compra compra2 = new Compra("Tenis", 300.0, 1, "Caixa Postal 27 89140 970", "Pagamento confirmado");
        compras.add(compra2);

        for (int i = 0; i < compras.size(); i++) {
            Compra c = compras.get(i);

            System.out.println("Compra: " + c.getProduto() + " a " + c.getPrecoUnitario() + 
            "/unidade, totalizando: " + c.valorTotal() + ".");
        }
        System.out.println("Comprimento do ArrayList 'compras':  " + compras.size());
    }
}
