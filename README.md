### jQuery

Estes são alguns projetos trabalhados durante o estudo da biblioteca JavaScript 'jQuery', usando como base o livro 'jQuery, a Biblioteca do Programador JavaScript' de Maurício Samy Silva. O livro está disponível para venda, contudo pode-se encontrar material de estudos, notas, resenhas e outros no site do autor, sendo o <a href="https://livrosdomaujor.com.br/jquery//jq2/index.php" target="_blank">site para a segunda edição do livro disponível pelo link</a>.

jQuery é uma biblioteca JS focada em interatividade, design e simplicidade, sendo hoje uma das mais populares entre os desenvolvedores web. Sua sintaxe é curta e objetiva, fazendo largo uso de ferramentas CSS como os seletores e funções, por exemplo. Se mostra muito útil ao, por exemplo, adicionar algum efeito de estilização animado em poucas linhas de código, o que normalmente seria inviável para o JS puro. Contudo, sua utilidade não para por aí, é claro.

#### Para saber mais sobre jQuery, vide sua documentação disponível no site gratuitamente: (disponível em < https://api.jquery.com > para visualização).

##

`$()` é o construtor jQuery. 
Caso queira, pode-se usar a função construtora alternativa (alias) `jQuery()`
Declare um novo alias para não entrar em conflito com outras bibliotecas JS! Use:

```
var $newAlias = jQuery.noConflict();
$newAlias().ready(function { ... });
```

A var pode ser a que você preferir. 

Estes construtores armazenam tudo o que encontram automaticamente em um array,
o que é mais simples quando comparado ao JavaScript convencional, que requer o uso de loops.

Para buscar elementos no sistema usando jQuery, use os seletores CSS.
#id, .class, tags etc. Exemplo:
`$('body p:nth-child(3)')` busca o terceiro parágrafo dentro do corpo do documento.

`$('div').children('p').fadeOut().addClass('paragraph')`
Esse código diz, basicamente:
"Construtor, encontre todos os parágrafos filhos de divs, aplique o efeito de esmaecimento
e adicione, em seguida, a classe paragraph a eles."

É possível, ainda, guardar o valor de um atributo de algum elemento dentro de uma variável, de forma muito simples, e ainda manipulá-lo posteriormente:
`var valorAtributo = $('h1').attr('title');`
Agora, a variável `valorAtributo` guarda o valor do atributo `title` da tag `h1`.

Caso queira, pode-se inserir atributos em algum elemento, dessa forma:
```
$('img').css('display', 'block').attr({
	src: "imagem.png",
	alt: "Texto alternativo da imagem"
	});
```
Neste caso, inseriu-se um elemento `img` vazio e o ocultou com a delcaração CSS `img { display: none; }`
Basicamente, ao disparar o evento designado (que está implícito no código citado, mas que pode ser um clique, passar o mouse por cima de alguma coisa, etc.) a imagem aparece. Pode-se manipular isso de uma série de formas: ao aparecer a imagem, por exemplo, ela não precisa aparecer subitamente - adicione uma animação! O jQuery possibilita a estilização de formas muito fáceis de se somar ao projeto.

Caso se queira adicionar apenas um atributo (bem como seu respectivo valor), pode-se otimizar a escrita do código usando a linha:
`seletorjQuery.attr('atributo', 'valor');`
Com ela adiciona-se apenas um (ao contrário do último, que pode adicionar múltiplos atributos).

E, assim como adicionar um atributo, é possível removê-lo com a mesma simplicidade:
`$('#remover').removeAttr('id')`
Essa linha apaga o identificador (id) do elemento buscado (neste exemplo, buscou-se usando a própria id!).
Isso implica algumas coisas: por exemplo, se você remover um atributo que foi usado como seletor no próprio CSS, o elemento perderá essa estilização, ou em linguagens de programação que pode tentar acessar o elemento por algum atributo que não existe mais; é preciso tomar cuidado, é claro, mas muitas vezes esse pode ser o efeito buscado.

Caso se queira adicionar uma classe, usa-se o método `addClass('nameClass')`. Caso se queira adicionar mais de uma classe, separa-se por espaços. Pode-se remover uma classe usando `removeClass('nameClass')`. Há um método "meio termo" entre estes dois: o `toggleClass('nameClass')` - ele adiciona uma classe caso ela ainda não exista, e a remove caso já esteja presente.

Agora, caso se queira manipular o próprio HTML, pode-se usar o método `html()`. Veja um exemplo no script "mudarHtml".

Para se manipular textos, usa-se o método `text()`.

O método `append()` manipula conteúdo (que pode ser tanto texto puro como marcação HTML), adicionando seu valor logo após o elemento selecionado. O método `appendTo()` é equivalente. Já os métodos `prepend()`/`prependTo()` desempenham papel semelhante, mas com a diferença que o fazem *logo antes* do elemento usado como referência.

##### Importante: Seletores CSS como o background-color por exemplo, que são compostas por duas palavras e separadas por hífen, devem ser acessadas pelo jQuery usando a notação camelCase - ou seja, background-color passa a ser backgroundColor etc. Isso também é válido para outros itens, tais como line-height (que torna-se lineHeight) etc.

