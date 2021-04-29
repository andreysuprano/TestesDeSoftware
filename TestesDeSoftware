Quais são os <mark>**tipos de teste**</mark>? 
Quais são as <mark>**técnicas de teste**</mark> para aplicá-los?
Como construir uma <mark>**estratégia de teste**</mark> na minha squad? 🕵️‍♀️

Nessa page o Capítulo de Qualidade compartilha referências e breves definições sobre os conceitos que envolvem Testes de Software 🧐
[[_TOC_]]

# Tipos de Teste
## Unitário🎯
---
### O que é?🤔
> O teste de unidade tem como foco as menores unidades de um programa, que podem ser funções, procedimentos, métodos ou classes. Nesse contexto, espera-se que sejam identificados erros relacionados a algoritmos incorretos ou mal implementados, estrutura de dados incorretas ou simples erros de programação. Como cada unidade é testada separadamente, o teste de unidade pode ser aplicado à medida que ocorre a implementação das unidades e pelo próprio desenvolvedor, sem a necessidade de dispor-se do sistema totalmente finalizado.
<p style="text-align:right"><i> Delamaro, M.; Maldonado, J.; Jico, M. em Introdução ao Teste de Software. 2016, pg 25. </i></p>

Os testes unitários são responsáveis por garantir o funcionamento de pequenas partes do código, por exemplo os testes de uma função que calcula o valor de cada parcela de um empréstimo de acordo com determinados requisitos/parâmetros (como exemplo temos as taxas, ou até mesmo a quantidade de parcelas), ou também o teste da implementação de uma [Factory](https://www.tutorialspoint.com/design_pattern/factory_pattern.htm)  que deve retornar um objeto de construção específica.
É muito comum se encontrar em testes unitários o pattern [AAA "Arrange, Act and Assert"](https://medium.com/@pjbgf/title-testing-code-ocd-and-the-aaa-pattern-df453975ab80) que possui uma construção não complexa, onde se tem um objeto de referência que é usado como comparação para o resultado de factory, ou o valor esperado é comparado ao retornado de uma função para que se tenha completa certeza de seu funcionamento. 
| Arrange | Act | Assert  |
|---------|-----|---------|
| 10      | result = somar(5,5) | 10 == result |
### Importância🃏
Os testes unitários são de grande importância pois são agentes imediatos ao se finalizar uma manutenção em um trecho de código, podendo se executar apenas o teste unitário da unidade ao qual foi alterada garantindo que as regras de negócio e expectativas com o trecho de código sejam mantidas.
Além de garantir o funcionamento da unidade os testes unitários são muito mais baratos que um teste [end to end](http://www.stephanybatista.com/2018/05/01/voce-sabe-o-que-e-teste-e2e/) por exemplo, pois um teste de unidade é muito rápido consome menos recurso para sua execução além de sua manutenção ser muito mais ágil.

### Referências
[Curso - Introdução ao Teste de Software (Coursera[ FREE ])](https://www.coursera.org/learn/intro-teste-de-software)
[Davyson Lima, Entenda de uma vez por todas o que são testes unitários, para que servem e como fazê-los](https://medium.com/@dayvsonlima/entenda-de-uma-vez-por-todas-o-que-s%C3%A3o-testes-unit%C3%A1rios-para-que-servem-e-como-faz%C3%AA-los-2a6f645bab3)

## Mutante
---
### O que é?
Os testes de mutação por sua vez não são testes que validam o programa desenvolvido por natureza, mas sim a acuracidade do conjunto de testes desenvolvido. Nesse caso os testes de mutação são responsáveis por efetuar mudanças dentro do código em alguma funcionalidade (Ou seja criar um mutante) e verificar o comportamento do teste que valida tal funcionalidade. A partir do momento em que um teste falha um mutante é morto, pois suas validações obtiveram resultados diferentes do esperado correspondendo as expectativas.
Uma das formas de medir a eficácia dos testes com o teste de mutação é executar o calculo de uma pequena formula bem simples : 
|  Cálculo de Escore de Mutação   |
|-----|
|Escore De Mutacao = Mutantes Mortos / Total De Mutantes|

Com isso podemos avaliar com números a acuracidade do nosso conjunto de testes!
### Importância
Em busca de validar a qualidade do software desenvolvido o teste de mutação vem com a responsabilidade de garantir que nosso conjunto de testes não esta emitindo falsos positivos ou se até mesmo estão sendo eficazes de acordo com sua função.

### Referências
[Curso - Introdução ao Teste de Software (Coursera[ FREE ])](https://www.coursera.org/learn/intro-teste-de-software)

## Componente
---
### O que é?
Conforme a complexidade da aplicação aumenta a quantidade de comunicações entre aplicações aumentam e com isso como validar se o código que está sendo testado está com problema? Ou se o problema está em outra aplicação ao qual nos comunicamos?
Com o intuito de resolver estes problemas temos os testes de componentes onde a aplicação é testada totalmente isolada das demais ao qual se comunica. Para proporcionar este ambiente isolado, é construído através de [Mocks](https://pt.wikipedia.org/wiki/Objeto_mock#:~:text=Objetos%20mock%2C%20objetos%20simulados%20ou,o%20comportamento%20de%20outros%20objetos.) que fornecem as informações exatas ao qual a aplicação necessita para executar seus testes, sendo assim é possível validar o funcionamento da aplicação sem a interferência ou dependência de aplicações externas.

Existem várias bibliotecas para se criar mocks: 
Para testes de microsserviços: 
[MounteBank:](http://www.mbtest.org/)

Pra Testes de Interface:
[Jest](https://jestjs.io/docs/en/mock-functions)
[React Testing Library](https://testing-library.com/docs/react-testing-library/intro/)

###Importância 
Os testes de componentes são importantes nada mais nada menos que para se obter o resultado real da aplicação sem validar suas integrações mas sim o funcionamento do código implementado.

### Referências
[Curso - Introdução ao Teste de Software (Coursera[ FREE ])](https://www.coursera.org/learn/intro-teste-de-software)
[Documentação Jest](https://jestjs.io/docs/en/mock-functions)
[Documentação React Testing Library](https://testing-library.com/docs/react-testing-library/intro/)
[Engineering at Spotify - Testing of Microsservices](https://engineering.atspotify.com/2018/01/11/testing-of-microservices/)

##Contrato
---
### O que é?
Os testes de contrato são responsáveis por validar as interfaces do sistema, como exemplo o contrato com a API estar sendo cumprido. Além de validar o contrato válida também como a API lida de acordo com o [Payload](https://www.devmedia.com.br/forum/rest-o-que-e-payload/600168) que ela recebe por exemplo:

Uma API para retornar os dados de uma pessoa necessita que seja enviado um requisição GET com o parâmetro CPF
sendo assim temos os seguintes casos -> 
| Contrato | Requisição | Resultado |
|----------|------------|-----------|
|CPF com no mínimo 11 caracteres|123.456.78| { ERRO: CPF deve conter no mínimo 11 caracteres }|
|CPF com no mínimo 11 caracteres| 123.456.789-78| { Nome: Joberval Rodrigues, CPF: 123.456.789-78, Endereço ... } |

Podemos ver que no primeiro cenário temos uma requisição que não respeita o contrato ao qual a API exige para que os dados sejam fornecidos, sendo assim a aplicação esta tratando o erro de contrato com uma mensagem de erro.

Já no segundo exemplo temos uma requisição que respeita o contrato com a API, sendo assim a aplicação retorna os dados esperados corretamente.

###Importância
O teste de contrato vem com a importância de validar que a aplicação está correspondendo de acordo com seu contrato, validando e tratando dados de entrada e saída.
###Referências
[Curso - Introdução ao Teste de Software (Coursera[ FREE ])](https://www.coursera.org/learn/intro-teste-de-software)
[
Maximiliano Alves - Testes de contrato de API ](https://medium.com/cwi-software/testes-de-contrato-de-api-com-joi-1ce552fe2531)

##Integração
---
###O que é?
> No teste de integração, que deve ser realizado após serem testadas as unidades individualmente, a ênfase é dada na construção da estrutura do sistema. À medida que as diversas partes do software são colocadas para trabalhar juntas, é preciso verificar se a interação entre elas funciona de maneira adequada e não leva a erros.
<p style="text-align:right"><i> Delamaro, M.; Maldonado, J.; Jico, M. em Introdução ao Teste de Software. 2016, pg 25. </i></p>

Os testes de Integração tem como objetivo validar se os componentes de um sistema interagem corretamente uns com os outros, sendo eles comunicação entre banco de dados, outros micro serviços ou componentes externos. Quando falamos de micro serviços isso se torna mais visível, pois a transferência e troca de informações entre estes componentes é o que faz o sistema funcionar. Podemos ver os testes de integração também validando o funcionamento da comunicação entre a interface e um micro serviço!

### Importância 
Assim como os testes unitários os testes de Integração são baratos e simples de se construir, e conseguem entregar a validação de toda a comunicação da aplicação, podendo garantir que todos os serviços e dependências da aplicação estão se comunicando e se comportando como esperado.

### Referências
[Curso - Introdução ao Teste de Software (Coursera [ FREE ])](https://www.coursera.org/learn/intro-teste-de-software)
[Adriano Wilbert - Desenvolvendo Testes de Integração](https://medium.com/cwi-software/desenvolvendo-testes-de-integra%C3%A7%C3%A3o-c642bb15909b)

---

# Técnicas de Teste
No cenário atual ao qual nos encontramos existem várias técnicas de testes funcionais que nos ajudam a ser mais assertivos e construirmos uma menor quantidade de testes e mesmo assim cobrirmos a maior quantidade de comportamentos possíveis, dentre elas temos:
 
## 1. Partição de Equivalência

Esta técnica consiste em dividir os valores utilizados em conjuntos que em si possuem um mesmo comportamento esperado. Como exemplo podemos ter que ao inserir valores **válidos** em um sistema esperamos que a aplicação execute com sucesso porém se inserirmos dados **inválidos** a mesma aplicação o comportamento esperado seria o retorno de uma crítica de erro informando que os dados são inválidos.

Sendo assim podemos entender que dados **válidos** são uma partição de equivalência onde qualquer dado válido devera ter o mesmo comportamento, também valendo para dados **inválidos** onde ao inserir qualquer dado inválido também é esperado o mesmo comportamento.

### Referências 
[Delamaro, M.; Maldonado, J.; Jico, M. em Introdução ao Teste de Software. 2016](https://www.amazon.com/Introdu%C3%A7%C3%A3o-Teste-Software-Portuguese-Brasil/dp/8535283528)
[Artigo Técnica de Teste — Particionamento de Equivalência](https://medium.com/revista-tspi/t%C3%A9cnica-de-teste-particionamento-de-equival%C3%AAncia-d32a7d689d82)
## 2. Valor Limite


 
---
#Estratégia de Teste
## 1. Estratégia de testes para Microserviços

Uma das estratégias de testes mais utilizadas em sistemas mais complexos é a que vemos representada pela pirâmide de testes:
      
                                   
![](https://miro.medium.com/max/620/1*hn4MGJVM9m1XSOuRqdF3aQ.png)

Porém como principal foco da estratégia podemos ter a combinação entre diversos tipos de testes que garantem por si respectivas áreas do microserviço cada um com sua responsabilidade, proporcionando uma maior cobertura.

A pirâmide divide cada tipo de teste de acordo com a proporção (em quantidade) que cada teste deve ser distribuído dentro da estratégia. Olhando de baixo para cima, podemos fazer algumas comparações, entre elas custo, tempo de manutenção/construção e complexidade que são muito importantes para se criar uma estratégia efetiva onde consegue-se extrair uma maior eficiência com menor custo.

Fazendo um paralelo entre complexidade e custo, podemos ver que a proporção de testes unitários é bem maior que a de testes e2e pois garantir pequenas partes do software é muito menos complexo e custoso, não tirando a importância dos demais testes pois na prática testes de unidade não validam a persistência de dados, coisa que um teste de integração trás como função. Contudo tendo as mínimas partes do software em funcionamento, garantir que a integração está acontecendo corretamente se torna uma tarefa menos complexa e de simples execução.

Olhando para o paralelo traçado a cima podemos ver que uma estratégia de teste bem construída permite que cada teste tenha apenas uma responsabilidade, sendo muito mais performático e assertivo além de termos a possibilidade de entrar no conceito de testes independentes e paralelismo.    
### Testes de Microserviços e o Paraná Banco 
#### Squad Plataforma
Dentro do plataforma, os testes são divididos em vários tipos, para que cada um com sua responsabilidade garanta o funcionamento prévio para execução do próximo teste.

Sequência de testes plataforma:

Unitário -> Mutantes -> Componente -> Contrato -> Integração -> Performance

Olhando para a premissa que cada teste garante o funcionamento prévio para a execução do próximo, podemos dizer que os testes unitários fazem a validação de cada unidade, seguindo pelo teste de mutantes que valida se os testes de unidade estão sendo eficazes, logo em seguida temos os testes de componente onde se testa isoladamente uma funcionalidade da aplicação garantindo que sem dependência externa ela possui o comportamento esperado, consecutivamente testa-se o contrato para validar como a Aplicação se comporta de acordo com os dados de entrada, depois testes de Integração que validam as comunicações externas da aplicação(que podem ser banco de dados ou outra aplicação), e por fim após a garantia de que tudo está funcionando testamos a Performance de acordo com a demanda esperada para a aplicação e seu comportamento em caso de sobrecarga. 

#Referências
[Paulo Vitor - Estratégias de testes em micro serviços](https://medium.com/@paulovitor88/estrat%C3%A9gias-de-testes-em-micro-servi%C3%A7os-42e547e6b2f1)
[Martin Fowler - Testing Strategies in a Microservice Architecture](https://martinfowler.com/articles/microservice-testing/#conclusion-test-pyramid)
Trechos do livro [Building Microservices, Sam Newman ](https://www.oreilly.com/library/view/building-microservices/9781491950340/)


