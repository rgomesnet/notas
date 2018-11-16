# Teste 

Escrever um teste de unidade é mais um ato de projeto do que de verificação. Trata-se mais de documentar do que de verificar. O ato de escrever um teste de unidade fecha vários ciclos de informação, o menor dos quais é o relativo à verificação de funções.

Desenvolvimento guiado por testes
E se você seguisse estas três regras simples?

1. Não escrever código de produção até que você tenha escrito um teste de unidade que falhe.
2. Não escrever mais de um teste de unidade do que o suficiente para falhar ou que não compile.
3. Não escrever mais que qualquer código de produção do que o suficiente para passar no teste falho.

Se seguíssemos esses passos, trabalharíamos em ciclos muito curtos. Escreveríamos apenas o suficiente de um teste de unidade para fazê-lo falhar e, depois, apenas o suficiente de código de produção para fazê-lo passar. Altenaríamos entre essas etapas a cada um ou dois minutos.

A primeira e mais evidente consequência é que toda função do programa tem testes que verificam seu funcionamento. Esse conjunto de testes funciona como um impedimento para mais desenvolvimento. Ele nos diz quando danificamos inadvertidamente alguma funcionalidade já existente. Podemos adicionar funções no programa ou alterar sua estrutura sem receio de que, no processo, estraguemos algo importante. Os testes nos informam que o programa ainda está se comportando corretamente. Assim, estamos muito mais livre para fazer alterações e melhorias em nosso programa.

Um efeito mais importante, porém menos evidente, é que o ato de escrever primeiro o teste nos obriga a um ponto de vista diferente. Devemos ver o programa que estamos para escrever a partir da perspectiva de um chamador desse programa. Assim, ficamos imediatamente preocupados com a interface do programa e também com sua função. Escrevendo primeiro o teste, projetamos o software de modo a poder ser chamado *convenientemente*. 

Além disso, escrevendo o teste primeiro, nos obrigamos a projetar o programa de modo que ele possa ser *testado*. Projetar o programa de modo que ele possa ser chamado e testado é muito importante. Para que isso seja possível, o software precisa estar desacoplado de seu ambiente. Assim, o ato de escrever os testes primeiro nos obriga a desacoplar o software!

Outro efeito importante de escrever testes antes é que eles funcionam como uma forma de documentação valiosa. Se você quer saber como chamar uma função ou como criar um objeto, existe um teste que mostra isso. Os testes atuam como um conjunto de exemplos que ajudam os outros programadores a saber como trabalhar com o código. Essa documentação pode ser compilada e executada. Ela permanecerá atualizada. E não pode mentir.

## Progamação intencional

Escrever o teste de maneira que você quer que ele seja lido. Você pode fazer o teste passar escrevendo o código que se adapte à estrutura decorrente do teste. Você expressa sua intenção em um teste antes de implementá-lo, mostrando-a da maneira mais simples e clara possível. Você confia em que essa simplicidade e clareza apontem para uma boa estrutura para o programa.
Exemplo: Todo o código abaixo foi escrito antes de qualquer parte de WumpusGame:

    
    [Test]
    public void TestMove()
    {
        WumpusGame g = new WumpusGame();
        g.Connect(4,5,"E");
        g.GetPlayerRoom(4);
        g.East();
        Assert.AreEqual(5, g.GetPlayerRoom());
    }   

    Essa função cria um novo WumpusGame, liga a câmara 4 à câmara 5 por meio de uma passagem para leste, 
    coloca o jogador na câmara 4, executa o comando para mover para leste e, então, declara que o jogador 
    deve estar na câmara 5.

## Testes de aceitação

Os testes de unidade são necessários, mas insuficientes como ferramentas de verificação.
Os testes de unidade verificam se os pequenos elementos do sistema funcionam como deveriam, mas não verificam se o sistema como um todo funciona corretamente. Os testes de unidade são testes de caixa branca - um teste que conhece e depende da estrutura interna do módulo que está sendo testado - que verificam os mecanismos individuais do sistema. 
Os testes de aceitação são testes de caixa preta - um teste que não conhece nem depende da estrutura interna do módulo que está sendo testado - que verificam se os requisitos do cliente estão sendo cumpridos.

Os testes de aceitação são escritos por pessoas que não conhecem os mecanismos internos do sistema. Esses testes podem ser escritos diretamente pelo cliente ou por analistas de negócio, testadores ou especialistas em garantia da qualidade. Os testes de aceitação são automatizados. Normalmente eles são redigidos em uma linguagem de especificação especial que pode ser lida e escrita por pessoas sem muitos conhecimentos técnicos.

Os testes de aceitação são a documentação definitiva de uma funcionalidade. Uma vez que o cliente tenha escrito os testes de aceitação que verificam se uma funcionalidade está correta, os programadores podem ler esses testes para realmente entender a funcionalidade. Portanto, assim como os testes de unidade servem como uma documentação das funcionalidades do sistema, que também pode ser compilada e executada. Em resumo, *os testes de aceitação se tornam o verdadeiro documento de requisitos*.

Além disso, o ato de escrever testes de aceitação primeiro tem um impacto profundo na arquitetura do sistema. Para que o sistema possa ser testado, ele precisa ser desacoplado no nível alto da arquitetura. Por exemplo, a interface do usuário precisa ser desacoplada das regras de negócio de tal maneira que os testes de aceitação possam acessar essas regras de negócio sem passar pela IU.

Nas primeiras iterações de um projeto, a tentação é fazer testes de aceitação manualmente. Isso é desaconselhável, pois tira dessas primeiras iterações a pressão pelo desacoplamento exercida pela necessidade de automatizar os testes de aceitação. Quando você começa a primeira iteração sabendo perfeitamente que deve automatizar os testes de aceitação, assume compromissos arquitetônicos muito diferentes. Assim como os testes de unidade o motivam a tomar decisões de projeto melhores em pequena escala, os testes de aceitação o motivam a tomar decisões arquitetônicas melhores em grande escala.

## Conclusão

Quanto mais simples for a execução de um conjunto de testes, mais frequentemente esses testes serão executados. Quanto mais testes forem executados, mais cedo qualquer desvio deles será encontrado. Se pudermos executar os testes várias vezes por dia, então o sistema nunca estará danificado por mais do que alguns minutos. Essa é uma meta razoável. Simplesmente não permitimos que o sistema se deteriore. Uma vez que ele funcione em certo nível, nunca se deteriorará para um nível inferior.

* Possivelmente, a vantagem mais importante de todos esses testes é o impacto que eles têm na arquitetura e no projeto. Para que um módulo ou um aplicativo se torne passível de teste, o módulo ou o aplicativo também deve ser desacoplado. Quanto mais passível de teste ele for, mais desacoplado será.

MARTIN, R.; MARTIN, M. Princípios, Padrões e Práticas Ágeis em C#, p.55-62
