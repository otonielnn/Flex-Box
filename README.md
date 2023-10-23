# Flex-Box

## Flex Container

- O flex Container é a tag que envolve os itens flex, ao indicar display: flex; essa tag passa a ser um Flex Container.

### Display Flex
- Define o elemento como um flex container, tornando todos os seus filhos flex-itens.
- sintaxe: 
    `Display: flex; `
    
### Flex-Direction
- Define a direção dos flex intes. Por padrão ele é row, por isso quando o `display: flex;` é adicionado os elementos ficam em linha um do lado do outro.

- A mudança de row para column geralmente acontece quando estamos definindo os estilos em media queries para o mobile. Assim você garante que o conteúdo seja apresentado em coluna única.

- Row (Default):
    `Flex-Direction: row;`
    > Os itens ficam na mesma linha.

- Column:
    `Flex-Direction: column;`
    > Os itens ficam em uma única coluna, um embaixo do outro.

- Reverse-Row:
    `Flex-Direction: reverse-row;`
    > Os itens ficam em linha reversa, ou seja 3, 2 , 1.

- Column-reverse:
    `Flex-Direction: column-reverse;`
    > Os itens ficam em uma única coluna, um  embaixo do outro, porém em oerdem reversa: 3, 2 e 1.

### Flex-Wrap
- Define se os itens devem quebrar ou não a linha. Por padrão eles não quebram linha, isso faz com que os flex itens sejam compactos além do limite do conteúdo.

- Essa é geralmente uma propriedade que é quase sempre definida com `flex-wrap: wrap;` Pois assim quando um dos flex itens atinge o limite do conteúdo o último item passa para a coluna debaixo e assim por diante.

- NoWrap:
    `flex-wrap: nowrap`
    > Valor padrão, não permite a quebra de linha;

- Wrap:
    `flex-wrap: wrap;`
    > Quebra a linha assim que um dos flex itens não puder mais ser compacto.

- Wrap-Reverse:
    `flex-wrap: wrap-reverse;`
    > Quebra a linha assim que um dos flex itens não puder mais ser compacto. A quebra é na direção contrária, ou seja para a linha a cima.

### Flex-Flow

- O flex-flow é um atalho para as propiedades flex-direction e flex-wrap. Você não verá muito o seu uso, pois geralmente quando mudamos o flex-direction para column, mantemos o padrão do flex-wrap que é nowrap.

- E quando mudamos o flex-wrap para wrap, mantemos o padrão do flex-direction que é row.

- Sintaxe do flex-flow
    `flex-flow: (propriedade do flex-direction) (propriedade do flex-wrap);`

- Exemplos :
    `flex-flow: row nowrap;`
    > Coloca o conteúdo em linha e não permite a quebra de linha.

    `flex-flow: row wrap;`
    > Coloca o conteúdo em linha e permite a quebra de linha.

    `flex-flow: column nowrap;`
    > Coloca o conteúdo em coluna e não permite a quebra de linha.

### Justify-Content

- Alinha os itens flex no container de acordo com a direção. A propriedade só funciona se os itens atuais não ocuparem todo o container. Isso significa que ao definir `flex: 1;` ou algo similar nos itens, a propriedade não terá mais função.

- Excelente propriedade para ser usada em casos que você deseja alinhar um item na ponta esquerda e outro na direita, como em um simples header com marca e navegação.

- Flex-Start
    `justify-content: flex-start;`
    > Alinha os itens ao início do container.
- Flex-End
    `justify-content: flex-end;`
    > Alinha os itens no finaldo container.
- Center
    `justify-content: center;`
    > Alinha os itens no centro do container.
- Space-between
    `justify-content: space-between;`
    > Cria um espaçamento igual entre os elementos. Mantendo o primeiro grudado no início e o último no final.
- Space-Around
    `justify-content: space-around;`
    > Cria um espaçamento entre os elementos. Os espaçamentos do meio são duas vezes maiores que o inicial e o final.

### Align-Items

- O Align-Items alinha os flex itens de acordo com o eixo do container. O alinhamento é diferente para quando os itens estão em colunas ou linhas.

- Essa propriedade permite o tão sonhado alinhamento central no eixo vertical, algo que antes só era possível com diferentes hacks.

- Stretch
    `align-items: stretch;`
    > Valor padrão, ele que faz com que o flex itens cresçam igualemente.

- Flex-Start
    `align-items: flex-start;`
    > Alinha os itens ao início.
    
- Flex-End
    `align-items: flex-end;`
    > Alinha os itens ao final.

- Center
    `align-items: center;`
    > Alinha os itens ao centro.

- Baseline
    `align-items: baseline;`
    > Alinha os itens de acordo com a linha base da tipografia.

### Align-Content

- Alinha as linhas do container em relação ao eixo vertical. A propriedade só funciona se existir mais de uma linha de flex-itens. Para isso flex-wrap precisa ser wrap.

- Além disso o efeito dela apenas será visualizado caso o container seja maior que a soma das linhas dos itens. Isso significa que se você não definir height para o container, a propriedade não influencia no layour.

- Stretch
    `align-content: stretch;`
    > Valor padrão, ele que faz com que os flex itens cresçam igualmente na vertical.

- Flex-Start
    `align-content: flex-start;`
    > Alinha todas as linhas de itens do Início.

- Flex-end
    `align-content: flex-end;`
    > Alinha todas as linhas de itens ao final.

- Center
    `align-content: center;`
    > Alinha todas as linhas de itens ao centro.

- Space-Between
    `align-content: space-between;`
    > Cria um espaçamento igual entre as linhas. Mantendo a primeira grudada no topo e a última no bottom.

- Space-around
    `align-content: space-around;`
    > Cria um espaçamento entre as linhas. Os espaçamentos do meio são duas vezes maiores que o top e o bottom.

## Flex Item

- Os Flex itens são os filhos diretos do Flex Container, lembrado que uma tag se torna um flex container a partir do momento que você definir display: flex.

- É possível que um Flex Item seja também um Flex Container, basta definir display: flex; nele. Assim os filhos desse item também serão flex itens.

### Flex-Grow

- Define a habilidade de um flex item crescer. Por Padrão o valor é zero, assim os flex itens ocupam um tamanho máximo relacionado o conteúdo interno deles ou ao width definido.

- Ao definir 1 para todos os Flex Itens, eles tentarão ter a mesma largura e vão ocupar 100% do container. Digo tentarão pois caso um elemento possua um conteúdo muito largo, ele irá respeitar o mesmo.

- Se você tiver uma linha com quatro itens, onde três são flex-grow: 1 e um flex-grow: 2, o flex-grow: 2 tentará ocupar 2 vezes mais espaço extra do que os outros elementos.

- Justify-Content não funciona em items com flex-grow definido.

- `flex-grow: número;`
    > Basta definir um número

- `flex-grow: 0;`
    > Obedece o width do elemento ou flex-basis.

### Flex-Basis

- Indica o tamanho inicial do flex item antes da distribuição do espaço restante.

- Quando definimos o flex-grow: 1; e possuímos auto no basis, o valor restante para ocupar o container é distribuído aoredor do conteúdo do flex-item.

- `flex-basis: auto;`
    > Esse é o padrão, ele faz com que a Largura da base seja igual a do item. Se o item não tiver tamanho especificado, o tamanho será de acordo com o conteúdo.

- `flex-basis: unidade;`
    > Pode ser em %, em, px e etc.

- `flex-basis: 0;`
    > Se o grow for igual ou maior que 1, ele irá tentar manter todos os elementos com a mesma largura, independente do conteúdo (por isso 0 é o valor mais comum do flex-basis). Caso contrário o item terá a largura do seu conteúdo.

### Flex-Shrink

- Define a capacidade de redução de tamanho do item.

- `flex-shrink: 1;`
    > Valor padrão, permite que os itens tenham os seus tamanhos (seja esse tamanho definido a partir do width ou flex-basis) reduzidos para caber no container.

- `flex-shrink: 0;`
    > Não permite a diminuição dos itens, assim um item com flex-basis: 300px; nunca diminuirá menos do que 300px, mesmo que o conteúdo não ocupe todo esse espaço.

- `flex-shrink: número;`
    > Um item com shrink: 3 diminuirá 3 vezes mais que um item com 1.

### Flex

- Atalho para as propriedades flex-grow, flex-shrink e flex-basis. Geralmente você verá a propriedade flex nos flex itens ao invés de cada um dos valores separados.

- Para melhor consistência entre os browsers, é recomendado utilizar a propriedade flex ao invés de cada propriedade separada.

- `flex: 1;`
    > Define flex-grow: 1; flex-shrink: 1; e flex-basis: 0; (em alguns browsers define como 0%, pois estes ignoram valores sem unidade, porém a função de 0 de 0% é a mesma.)

- `flex: 0 1 auto;`
    > Esse é o padrão, se você não definir nenhum valor flex ou para as outras propriedades separadas, o normal será flex-grow: 0;, flex-shrink: 1; e flex-basis: auto.    

- `flex: 2;`
    > Define exatamente da mesma forma que o flex: 1; porém neste caso o flex-grow será de 2, o flex-shrink continuará 1 e o flex-basis 0.

- `flex: 3 2 300px;`
    > flex-grow: 3, flex-shrink: 2 e flex-basis: 300px.

### Order

- Modifica a ordem dos itens. Sempre do menor para o maior, assim order: 1, aparece na frente de order 5.

- `order: número;`
    > Número para modificar a ordem padrão. Pode ser negativo.

- `order: 0;`
    > 0 é o valor padrão e isso significa que a ordem dos itens será a ordem apresentada no HTML. Se você quiser colocar um item do meio da lista no início da mesma, sem modificar os demais, o ideal é utilizar um valor negativo para este item, já que todos os outros são 0.

### Align-Self

- O align-self serve para definirmos o alinhamento específico de um único flex item dentro do nosso container Caso um valor seja atribuido, ele passara por cima do que for atribuido no align-items do container.

- Vale lembrar que o alinhamento acontece tanto em linha quanto em colunas. Por exemplo o flex-start quando os itens estão em linhas, alinha o item ao topo da sua linha. Quando em colunas, alinha o item a início (esquerda) da coluna

- `align-self: auto;`
    > Valor inicial padrão. Vai respeitar o que for definido pelo align-items no flex-container.

- `align-self: flex-start;`
    > Alinha o item ao início.

- `align-self: flex-end;`
    > Alinh o item ao final.

- `align-self: center;`
    > Alinha o item ao centro.

- `align-self: baseline;`
    > Alinha o item a linha de base.

- `align-self: stretch;`
    > Estica o item