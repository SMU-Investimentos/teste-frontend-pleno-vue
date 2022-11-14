## Avaliação nível pleno para VueJS


### Objetivo
O objetivo deste exercício é avaliar se o desenvolvedor tem conhecimento dos padrões de desenvolvimento Web, no que diz respeito a construção de layout, componentização, comunicação assíncrona e gerenciamento de estado.

### Requerimentos
- NodeJS v14+
- npm

### Setup
- Iniciar um projeto executando `npm init vue@3` no terminal.
- Escolha as seguintes opções:
    - Typescript
    - Vue Router
    - ESlint
- Instalar a biblioteca `vuex` para gerenciamento de estado.
    - https://vuex.vuejs.org/guide/

### Descrição do projeto
Construir uma **boleta** (interface capaz de enviar ordens de compra e venda de uma determinada ação) e um **livro de ofertas** (uma lista das ordens de compra e venda de uma determinada ação). Neste exercício será feita uma versão simplificada da interface de um homebroker.

**Boleta**

![boleta](https://user-images.githubusercontent.com/59885322/201717761-7d636c5a-1595-402c-9d94-8fd5583b21e4.png)

- Campo **Ativo** representa o nome da empresa, e deve ser um valor fixo `SMU1`.
- Campo **Quantidade** representa quantas ações o investidor deseja comprar ou vender.
- Campo **Assinatura Eletronica** representa a senha para validação de segurança.

- O Botão de **compra** deve exibir o **valor do melhor preço de venda** (ou seja, o menor preço)
- O Botão de **venda** deve exibir o **valor do melhor preço de compra** (ou seja, o menor preço)

Regras:
- Ativo: valor fixo.
- Quantidade: inteiro positivo
- Assinatura eletrônica: Apenas números, tamanho exato de 8 caracteres.
- Os botões devem ficar desabilitados enquanto as regras não forem satisfeitas.

**Livro de Ofertas**
