# Projeto Ágil
Em uma equipe ágil, a visão global evolui com o software. A cada iteração, a equipe melhora o projeto do sistema de modo que ele seja o melhor possível para o sistema conforme ele está *agora*. A equipe não perde muito tempo antecipando os requisitos e as necessidades futuras. Nem tenta construir hoje a infraestrutura para suportar as funcionalidades que talvez sejam necessárias amanhã. Em vez disso, a equipe se concentra na estrutura do sistema *atual*, tornando-a tão boa quanto possível. 

Isso não é um abandono da arquitetura e do projeto. Em vez disso, é uma maneira de evoluir progressivamente a arquitetura e o projeto mais adequados para o sistema. Também é uma maneira de manter esse projeto e essa arquitetura adequados, à medida que o sistema cresce e evolui com o tempo. O desenvolvimento ágil torna o processso de projeto e arquitetura *contínuo*.

Como sabemos se o projeto de um sistema de software é bom?

Podemos medir, de forma subjetiva ou objetiva, sintomas de um projeto ruim. Tais sintomas, também conhecidos por maus cheiros de projeto, frequentemente permeiam a estrutura global do software.

Esess sintomas têm natureza semelhante aos maus cheiros de código, mas estão em um nível mais alto. Eles são os maus cheiros que permeiam a estrutura global do software, em vez de uma pequena seção de código.
    
Os sintomas são:
* *Rigidez*. É difícil alterar o projeto.
        
        Rigidez é a tendência do software de ser difícil de alterar, mesmo de maneira simples.         
        Um projeto é rígido quando uma única modificação provoca uma sucessão de alterações subsequentes 
        em módulos dependentes. Quanto mais módulos precisam ser alterados, mais rígido é o projeto.

* *Fragilidade*. O projeto é fácil de estragar.
        
        
        Fragilidade é a tendência de um programa estragar em muitos lugares quando uma única alteração 
        é feita. Frequentemente, os novos problemas estão em áreas que não têm uma relação conceitual 
        com a área alterada. Corrigir esses problemas leva a ainda mais problemas e a equipe de 
        desenvolvimento começa a parecer um cachorro correndo atrás do rabo.
        À medida que a fragilidade de um módulo aumenta, a probabilidade de que uma alteração introduza 
        problemas inesperados aproxima-se da certeza. Isso parece absurdo, mais tais módulos não são 
        incomuns.
        Tratam-se dos módulos que constantemente precisam de reparos, aqueles que nunca ficam fora da 
        lista de bugs. São aqueles que todos sabem que precisam ser revisados, mas que ninguém quer encarar. 
        São os módulos que, quanto mais você os corrige, pior ficam.

* *Imobilidade*. É difícil reutilizar o projeto.
        
        
        Um projeto é imóvel quando contém partes que poderiam ser úteis em outros sistemas, mas o trabalho 
        e o risco envolvidos na separação dessas partes do sistema original são grandes demais.

* *Viscosidade*. É difícil fazer a coisa certa.
        
        A viscosidade aparece em duas formas: viscosidade do software e viscosidade do ambiente.

        Viscosidade do software, acontece quando os desenvolvedores normalmente encontram mais de uma 
        maneira de fazer uma alteração. Alguns deles preservam o projeto; outros, não (isto é, 
        produzem soluções malfeitas). Quando os métodos que preservam o projeto são mais difícies de 
        usar do que as soluções malfeitas, a viscosidade do projeto é alta. É fácil fazer a coisa errada, 
        mas difícil fazer a coisa certa. Queremos projetar nosso software de modo que as alterações que 
        preservam o projeto sejam fáceis de fazer.

        Viscosidade de ambiente, ocorre quando o ambiente de desenvolvimento é lento e ineficiente. 
        Por exemplo, se os tempos de compilação forem muitos longos, os 
        desenvolvedores ficarão tentados 
        a fazer alterações que não obriguem grandes recompilações, mesmo que essas alterações não preservem 
        o projeto. 
        Se o sistema de controle de código-fonte exigir horas para verificar apenas alguns arquivos, 
        os desenvolvedores ficarão tentados a fazer alterações que exijam o mínimo de check-ins possível,
        
        independentemente de o projeto ser preservado.
        Nos dois casos, um projeto viscoso é aquele no qual o projeto do software é difícil de preservar.

* *Complexidade desnecessária*. Projeto excessivo.

        Um projeto tem o mau cheiro da complexidade desnecessária quando contém elementos que não são úteis 
        no momento. Isso acontece com muita frequência, quando os desenvolvedores antecipam mudanças nos 
        requisitos e colocam recursos no software para lidar com essas mudanças em potencial. Isso pode 
        parecer bom em um primeiro momento. Afinal, a preparação para futuras mudanças deve manter nosso 
        código flexível e evitar alterações apavorantes mais adiante.

        Infelizmente, muitas vezes o efeito é justamente o oposto. Preparando-se para muitas possibilidades, 
        o projeto se torna sujo, contendo construções que nunca são utilizadas. Algumas dessas preparações 
        podem compensar, mas outras tantas não. Nesse meio-tempo, o projeto carrega o peso desses elementos 
        não utilizados. Isso torna o software complexo e difícil de entender.

* *Repetição*. Abuso do mouse (CTRL + C | CTRL + V).

        Recortar e colar podem ser operações de edição de texto úteis, mas podem ser desastrosas na edição 
        de código. Com muita frequência, os sistemas de software são baseados em dezenas ou centenas de 
        elementos de código repetidos.

        Quando o mesmo código aparece inúmeras vezes, de formas ligeiramente diferentes, está faltando uma 
        abstração para os desenvolvedores. Encontrar todas as repetições e eliminá-las com uma abstração 
        adequada pode não estar na lista de prioridade, mas tornaria o sistema mais fácil de entender 
        e manter.

        Quando existe código redundante no sistema, o trabalho de alterar o sistema pode se tornar árduo. 
        Os erros encontrados em tal unidade repetida precisam ser corrigidos em cada repetição. Contudo, 
        como cada repetição é ligeiramente diferente das outras, a correção nem sempre é a mesma.

* *Opacidade*. Expressão desorganizada.

        Opacidade refere-se à dificuldade de compreensão de um módulo. O código pode ser escrito de maneira 
        clara e intelegível ou de maneira opaca e enrolada. Ainda, o código tende a se tornar cada vez mais 
        opaco com o tempo. É necessário um esforço constante a fim de manter o código claro e a opacidade 
        diminuir.

        Quando os desenvolvedores escrevem um módulo pela primeira vez, o código parece claro para eles. 
        Afinal, eles trabalharam muito nele e o compreendem nos mínimos detalhes. Depois de um tempo, é 
        provável que se perguntem como foram capazes de escrever algo tão horrível. Para evitar isso, 
        os desenvolvedores precisam se colocar no lugar de seus leitores e fazer um esforço para refatorar 
        seu código a fim de que todos possam compreendê-lo. Seu código também precisa ser 
        revisado por outros.

Com frequência, o mau cheiro é causado pela violação de um ou mais princípios de projeto.

Princípios de projetos orientados a objetos, ajudam os desenvolvedores a eliminar os sintomas do projeto ruim, os maus cheiros de projeto, e criar os melhores projetos para o conjunto de funcionalidade atual.

Os princípios são:
* *O Princípio da Responsabilidade Única*
* *O Princípio do Aberto/Fechado*
* *O Princípio da Substituição de Liskov*
* *O Princípio da Inversão de Dependência*
* *O Princípio da Segregação de Interface*

As equipes ágeis aplicam os princípios apenas para resolver maus cheiros; elas não aplicam os princípios quando os maus cheiros não existem. ***Seria um erro obedecer a um princípio incondicionalmente apenas porque se trata de um princípio***. Os princípios existem para nos ajudar a eliminar os maus cheiros. Eles não são um perfume que deve ser borrifado por todo o sistema. A submissão excessiva aos princípios leva ao mau cheiro de projeto da complexidade desnecessária.

MARTIN, R.; MARTIN, M. Princípios, Padrões e Práticas Ágeis em C#, p.121-126