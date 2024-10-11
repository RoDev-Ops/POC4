Rodrigo Mello 10409316

## POC - Fetch API com JavaScript

Esta Prova de Conceito (POC) demonstra o uso do método assíncrono fetch para buscar dados de uma API pública e exibi-los em uma página HTML. A API utilizada é a <a href="https://dummyjson.com/products">dummyjson/products</a>, que retorna uma lista de produtos com várias informações associadas.

### Como funciona o código
#### Estrutura básica HTML
O código tem uma estrutura básica de HTML, contendo:

- Um título \<h1\> chamado "Lista de Produtos".
- Uma lista não-ordenada \<ul\> com o id="products-list" para inserir os produtos dinamicamente.
- Um script JavaScript incorporado dentro da tag \<script\>.

#### Função fetchProducts

    async function fetchProducts() {
        const response = await fetch('https://dummyjson.com/products');
        const data = await response.json();
        const productList = document.getElementById('products-list');
        
        data.products.forEach(product => {
            const listItem = document.createElement('li');
            listItem.textContent = `${product.title} - $${product.price}`;
            productList.appendChild(listItem);
        });
    }

#### O que é a função fetch
A função fetch é uma função do JavaScript usada para realizar requisições HTTP. Ela permite que você busque recursos de servidores, como dados de uma API, arquivos JSON, imagens, entre outros. 

#### Como funciona o fetch
A função fetch realiza uma requisição HTTP e retorna uma Promise, que é uma forma de lidar com operações assíncronas no JavaScript.

#### O que é await
O await é uma palavra-chave usada em JavaScript para lidar com operações assíncronas. Ele só pode ser usado dentro de funções declaradas com async e serve para "esperar" até que a Promise seja resolvida antes de continuar a execução do código.

#### Como funciona o await
Quando você usa await antes de uma chamada de função que retorna uma Promise, ele "pausa" a execução do código até que a Promise seja resolvida. Isso faz com que o código pareça síncrono, mas continue sendo assíncrono por baixo dos panos, permitindo que você lide com operações de rede sem bloquear a execução do restante da aplicação.


Resultado:
<br/>
![alt text](image.png)
