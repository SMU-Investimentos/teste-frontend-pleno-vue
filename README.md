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

![livro-de-ofertas](https://user-images.githubusercontent.com/59885322/201721568-3cb025e8-4805-4183-98cc-a18c39fa6ce4.png)

- **Qtd** representa a quantidade (informada na boleta na hora de enviar.)
- **Preço** representa o preço da ordem em questão. (Informada na boleta na hora de enviar.)
- As barras de compra e venda tem seu tamanho decidido da seguinte forma:
    - 100% do espaço disponível representa o volume da maior ordem daquele tipo (Compra ou Venda).
        - A maior ordem é calculada como **preço * qtd**
    - Tendo o número da maior ordem, as barras são calculadas proporcionalmente a este valor.
    - No exemplo acima, na aba de COMPRA, vemos que a segunda ordem ocupada 100% pois ela é a maior (2 * 999) e a primeira ordem ocupa aproximadamente metade do espaço disponível.
    
Regras
- Quando não houver ordens, exibir a mensagem "Ainda não existem ordens" na primeira linha das listas.

### Arquitetura
As ações de compra e venda devem emitir uma `Action` (do Vuex) chamada `sendOrder`. Essa action deve comitar uma `Mutation` chamada `pushOrder` que é responsável por adicionar a ordem no array de ordens do estado.

O livro de ofertas deve exibir todas as ordens do estado, separando-as em ordens do tipo COMPRA e VENDA.
Nesse exercício não será necessário nenhum tipo de comunicação com API. Nossa intenção é reproduzir o comportamento de uma boleta e livro de ofertas de forma estática.

### Bibliotecas
É permitido o uso de qualquer biblioteca externa desde que seu uso seja justificado.
