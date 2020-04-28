---
title: "Introdu??o ao R"
author: "Alessandro Freire"
date: "`r format(Sys.time(), '%d %B, %Y')`"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

##Baixando o R
- Acesse: https://www.r-project.org/ 
- Clique em "CRAN", logo abaixo de "Download", no canto esquerdo da p?gina.
- Selecione um link do Brasil. 
- Selecione a vers?o desejada (Windows, MAC ou Linux).
- Se estiver baixando pela primeira vez, selecione a op??o "base". 



##Baixando o RStudio
- Acesse https://www.rstudio.com/products/rstudio/download/
- Selecione a op??o gratuita.
- Pronto! Basta clicar no ?cone da ?rea de trabalho para iniciar o RStudio.

##Op??es de Interface
O R possui mais de uma op??o de interface. Sua vers?o padr?o ? bastante simples e praticamente n?o possui quaisquer atalhos com bot?es. Por outro lado, existem interfaces com mais op??es e atalhos, o que pode facilitar a vida de quem nunca programou em R antes. A mais famosa delas ? o RStudio.

##Op??es de Interface (Padr?o)

<center>
 <img src="C:\\Users\\Alessandro Freire\\Pictures\\interface.png" height="450px" width="650px" />
</center>

##Op??es de Interface (RStudio)

<center>
 <img src="C:\\Users\\Alessandro Freire\\Pictures\\RStudio.png" height="500px" width="600px" />
</center>

##O Console
<center>
![](C:\\Users\\Alessandro Freire\\Pictures\\console_image.png)
</center>

<br>

? onde os comandos podem ser digitados e os resultados desses mesmos comandos (exceto gr?ficos) s?o exibidos. Ainda que possamos eventualmente digitar comandos diretamente no console, ? prefer?vel n?o ter que repet?-los sempre que iniciarmos uma nova sess?o no RStudio. Para isso, usamos o Editor de Scripts.

##O Editor de Scripts
<center>
<img src = "C:\\Users\\Alessandro Freire\\Pictures\\script_rstudio.png" height = "500px"" width = "650px"/>
</center>

<br>

? onde escrevemos e salvamos nossos c?digos com os comandos que queremos executar.
Usar um script ? sempre mais recomendado para evitar repeti??es desnecess?rias em an?lises.
Al?m disso, o script permite que outras pessoas repliquem o seu trabalho.

Podemos adicionar coment?rios ao script usando o sinal de hashtag, de forma que fique mais claro para n?s e para outras pessoas o que estamos fazendo. 

```{r}
summary(cars) #Isto ? um coment?rio, n?o um comando. 
```

##O Ambiente Global

<center>
![](C:\\Users\\Alessandro Freire\\Pictures\\environment_rstudio.png)
</center>

<br>

? onde ficam os objetos criados (vetores, dataframes, matrizes, listas, valores etc.).
Uma das grandes vantagens do R ? que, ao contr?rio de outros softwares como o SPSS ou o Stata, ele permite a utiliza??o de v?rias b?sicos de dados simultaneamente, em uma mesma janela.

##O Painel de Arquivos

<center>
![](C:\\Users\\Alessandro Freire\\Pictures\\rstudiopanes.png)
</center>

<br>

? onde s?o exibidos os gr?ficos, arquivos do ambiente de trabalho, pacotes e ajuda.
Podemos ver informa??es sobre um pacote ou fun??o na guia "Help" digitando "?" seguido do comando desejado:
```{r}
#?mean
```

</center>

##Abrindo e Salvando um Novo Script
Para criarmos um novo script, podemos simplesmente clicar no ?cone com uma cruz branca e um papel atr?s logo abaixo de "File" no canto superior esquerdo da tela do RStudio. Ap?s selecionarmos esse ?cone, basta clicar em "R Script".

Uma maneira mais r?pida de abrir um novo script ? usar atalhos no teclado. Em computadores com Windows basta digitar Ctrl + Shift + N para abrir um novo script. Para salvarmos nosso novo script, podemos clicar em "File" e, em seguida, em "Save as". Uma forma mais r?pida ? usar o atalho Ctrl + S no teclado.

##Executando Comandos no Script

Para executar comandos no Script, basta selecionar a linha de comando desejada e clicar no bot?o "Run" na barra superior do script. Como somos programadores experientes, n?o usaremos o bot?o, mas sim o comando Ctrl + Enter.

##R como Calculadora

<center>
<img src = "C:\\Users\\Alessandro Freire\\Pictures\\calculator.jpg" height = "400px"" width = "450px"/>
</center>

<br>

Antes de qualquer coisa, o R ? uma calculadora.
Experimente digitar os seguintes comandos no console, e aperte "Enter" em seguida, um a um.

```{r}
2 + 2 #Soma
7 - 2 #Subtra??o
2*3 #Multiplica??o
```


```{r}
9/3 #Divis?o
2^4 #Potencia??o
sqrt(64) #Ra?zes quadradas
log(10) #logaritmo
```

##Criando Objetos

Podemos criar objetos e salv?-los no ambiente global do R. Para isso, usamos o sinal `<-`. Isso significa que o R deve atribuir um deteminado valor a um objeto. 

Por exemplo, digite o seguinte comando no console:
```{r}
a <- 3
```
Agora digite "a" e aperte "Enter".

```{r}
a
```

Agora veja o que acontece quando tentamos criar um objeto usando s?mbolos especiais ou iniciando-o com n?meros.

```{r, error=TRUE}
a@ <- 3
```

```{r, error=TRUE}
1a <- 3
```

? importante destacar que nomes de objetos no R n?o podem ser inciados com n?meros nem devem conter caracteres tais como #, @, ! e outros, uma vez que estes s?mbolos s?o usados em fun??es do R. 

Podemos, contudo, adicionar n?meros a nomes de objetos, contanto que n?o seja no in?cio:

```{r, error=TRUE}
a1 <- 4
```

```{r, error=TRUE}
a.1 <- 5
```

Tamb?m podemos criar objetos com o resultado de opera??es ou de quaisquer fun??es de nosso interesse.

Por exemplo:

```{r}
a <- 3 + 2
a
b <- 8 - 4
b
```

```{r}
c <- a + b
c
d <- sqrt(c)
d
```


Tamb?m podemos usar a fun??o `print()` quando quisermos exibir o resultado de um objeto, obtendo o mesmo resultado. 
```{r}
print(a)
print(a+b)
```

##Substituindo e Eliminando Objetos

Tamb?m ? poss?vel substituir ou eliminar objetos. Por exemplo, podemos digitar o seguinte comando para substituirmos o resultado do objeto "a":
```{r}
a <- 12 - 3
a
```
Agora o objeto "a" corresponde ao resultado de uma subtra??o, 9. 

Finalmente, podemos eliminar um objeto por meio da fun??o `rm()`. Experimente o seguinte comando: 
```{r}
rm(a)
```
Veja o que acontece com o objeto "a" no ambiente global.

```{r, error=TRUE}
a
```

#Vetores
Os vetores s?o dados armazenados em uma ordem espec?fica. Por exemplo, suponha que tenhamos dados sobre o peso em kg de cinco pessoas. Podemos criar um vetor com esses dados usando a fun??o `c()`, que concatena os dados digitados. 

```{r}
peso_1 <- c(85, 96, 56, 68, 77)
peso_1
```

Tamb?m podemos combinar diferentes vetores.

```{r}
peso_2 <- c(62, 81, 66, 70)
peso_2

peso_3 <- c(peso_1, peso_2)
peso_3
```

Para selecionar elementos espec?ficos de um vetor, basta utilizar o sinal de chaves `[]`. Por exemplo, se quisermos selecionar o segundo elemento do vetor "peso_1", digitamos:

```{r}
peso_1[2]
```

Podemos fazer opera??es com valores espec?ficos de um vetor.

```{r}
peso_1[2]/4
```

Tamb?m ? poss?vel excluir determinados valores de um vetor.
```{r}
peso_1
peso_1[-3]
```

Embora os vetores sejam um dos mais simples tipos de objeto do R, o dom?nio de seu uso ? extremamente importante. Quando come?armos a lidar com outros tipos de objetos, algumas opera??es ser?o muito semelhantes ?s que fizemos nos slides anteriores. 

##Fun??es B?sicas do R

<center>
![](C:\\Users\\Alessandro Freire\\Pictures\\function_r.png)
</center>

<br>

O R possui uma infinidade de fun??es, mas hoje come?aremos com apenas algumas de suas fun??es mais b?sicas. Podemos descobrir o tamanho de um objeto com a fun??o length():

```{r}
length(peso_1)
```

J? as fun??es min() e max() nos d?o os valores m?nimo e m?ximo de um objeto, respectivamente. 

```{r}
min(peso_1)
max(peso_1)
```

A m?dia, a vari?ncia e o desvio-padr?o de um objeto s?o dados pelas fun??es mean(), var() e sd(). 

```{r}
mean(peso_2)
var(peso_2)
sd(peso_2)
```

? importante lembrar que, caso haja dados faltantes (`NA`), o R n?o calcular? as estat?sticas acima, al?m de outras (como soma, m?nimo e m?ximo, por exemplo) e nos retornar? o valor `NA`. Nesses casos, devemos usar o argumento `na.rm = TRUE`, para que o R ignore os dados faltantes e fa?a os c?lculos com base nas observa??es v?lidas. 

```{r}
peso_1_NA <- c(85, 96, 56, 68, 77, NA)
mean(peso_1_NA) #Sem o argumento para remo??o de NAs, o R nos retorna NA.
```

Corrigindo:

```{r}
mean(peso_1_NA, na.rm = TRUE) 
```


Podemos criar uma sequ?ncia de n?meros com a fun??o seq(). Devemos incluir no par?nteses os n?meros inicial e final da sequ?ncia desejada, usando os argumentos "from" e "to"" para defin?-los.

```{r}
seq(from = 1, to = 10)
```

Usando o argumento "by", podemos definir o intervalo desejado na sequ?ncia. Por exemplo, se quisermos apenas os n?meros pares de 2 a 30:

```{r}
seq(from = 2, to = 30, by = 2)
```

Tamb?m podemos obter a soma dos elementos de um objeto com a fun??o sum(). 

```{r}
sum(peso_1)
```

A fun??o range() nos d? os valores m?nimo e m?ximo de um objeto. 

```{r}
range(peso_1)
```

Podemos usar mais de uma fun??o em um mesmo comando no R. Na verdade, podemos usar v?rias fun??es.

```{r}
sqrt(max(peso_1))
```

##Operadores l?gicos ou booleanos

O R possui uma s?rie de operadores l?gicos os quais s?o bastante ?teis em uma variedade de situa??es. ? importante conhec?-los bem:

```{r}

4 == 4 #Igual a

4 > 5 #Maior que

7 != 6 #Diferente de

5 >= 5 #Maior ou igual a

4 <= 3 #Menor ou igual a

is.null(peso_1_NA) #? nulo

is.na(peso_1_NA) # ? faltante

```

Note que o R nos retorna os resultados `TRUE` ou `FALSE` dependendo se a condi??o foi ou n?o foi satisfeita, respectivamente. Por exemplo, 4 ? igual a 4, ent?o o R nos retorna `TRUE`, por?m 4 n?o ? menor ou igual a 3, ent?o o R nos retorna `FALSE`. Esses operadores ser?o usados com muita frequ?ncia quando estivermos manipulando bases de dados no R.  

##Definindo um diret?rio de trabalho

Podemos obter o diret?rio de trabalho (a pasta a partir da qual o R carrega e salva arquivos) atual do R usando a fun??o `getwd()`. 

```{r}
getwd()

```

Caso queiramos alterar o diret?rio de trabalho, usamos a fun??o `setwd()`. ? importante notar que devemos editar as barras do endere?o do diret?rio em rela??o ao padr?o do Windows, o qual ? `\`:

```{r}

setwd("C:/Users/Alessandro Freire/Downloads")


```

ou ent?o usamos duas barras `\\`:

```{r}

setwd("C:\\Users\\Alessandro Freire\\Downloads")


```


##Instalando e carregando pacotes

Para utilizarmos fun??es no R, devemos instalar e carregar pacotes (caso n?o fa?am parte do R b?sico). Para instala??o utilizamos o comando `install.packages()` e para carregamento utilizamos o comando `library()`. ? importante lembrar que n?o basta que um pacote esteja instalado no R para que possamos utilizar suas fun??es, mas tamb?m ? preciso carreg?-lo. Note que inclu?mos aspas no nome do pacote desejado ao usarmos a fun??o `install.packages()`.  

```{r, eval = FALSE}
install.packages("dplyr") #Instalando
library(dplyr) #Carregando
```

##Visualizando dados

Em geral, n?o visualizamos planilhas ao manipularmos dados no R. Entretanto ? poss?vel observar uma parte de um banco de dados com a fun??o `head()`.

```{r}
head(mtcars)

```

O padr?o da fun??o `head()` ? exibir as seis primeiras observa??es de um banco de dados. Entretanto, podemos aumentar ou diminuir esse n?mero. Por exemplo, se quisermos as primeiras dez observa??es do banco de dados `mtcars` podemos digitar:

```{r}
head(mtcars, 10)
```

A fun??o `tail()` permite a visualiza??o das **?ltimas** observa??es de um banco de dados. Assim como na fun??o `head()` tamb?m podemos aumentar ou diminuir o n?mero de observa??es. 

```{r}
tail(mtcars, 10)
```

Tamb?m podemos visualizar todo um banco de dados, como em uma planilha Excel, usando a fun??o `View()`:

```{r, eval = FALSE}
View(mtcars)
```

##Encerrando uma sess?o no R

Para encerrar uma sess?o no R, basta digitar o seguinte comando:

```{r, eval=FALSE}
quit()
```

Ou simplesmente:

```{r, eval=FALSE}
q()
```

# (N?o) Salvando o workspace

? importante lembrar que, via de regra, N?O devemos salvar o ambiente de trabalho ao encerrarmos o R. Isso porque queremos evitar que erros em uma sess?o acabem sendo salvos. Por exemplo, voc? poderia acidentalmente executar um comando deletando uma vari?vel de sua base de dados e isso seria salvo permamentemente. Dessa forma, N?O salve o seu workspace ao encerrar uma sess?o no R, exceto em circust?ncias muito espec?ficas. 

#Exerc?cios



<font size="3"> 1) Para os exerc?cios abaixo, crie um script, salve-o com o nome `?ntro_r` e todos os comandos dos exerc?cios nele. Lembre-se dos atalhos do teclado para criar e salvar o seu script. Nada de clicar em bot?es! </font>

<font size="3"> 2) A tabela abaixo exibe o consumo m?dio de combust?vel (mpg) e a pot?ncia do motor (hp) de 5 carros. Construa dois vetores chamados "consumo" e "potencia" com os dados exibidos na tabela. </font>

```{r echo=FALSE, results='asis'}
library(knitr)
kable(mtcars[1:5,c("mpg", "hp")], caption = "Tabela 1")
```

<font size="3"> 3) Calcule a m?dia e o desvio-padr?o do consumo e da pot?ncia dos carros. Salve os resultados criando objetos denominados "media_consumo", "dp_consumo", "media_potencia" e "dp_potencia". </font> 

<font size="3"> 4) Selecione o segundo elemento do vetor "consumo" e calcule a sua raiz quadrada. Salve o resultado em um objeto chamado "consumo_raiz". </font> 

<font size="3"> 5) Crie um novo vetor de consumo denominado "novo_consumo" removendo o dado do quarto carro. Remova o dado de pot?ncia do primeiro carro e crie um novo vetor chamado "novo_potencia". Calcule as m?dias dos novos vetores e salve os resultados como "media_novo_consumo" e "media_novo_potencia". </font>

<font size="3"> 6) Calcule a soma dos n?meros pares de 2 a 268. Salve o resultado em um objeto chamado "soma_pares". Calcule a soma dos n?meros ?mpares de 1 a 251. Salve o resultado em um objeto chamado "soma_impares". </font>

<font size="3"> 7) Instale e carregue o pacote `gapminder`. Visualize as seis primeiras observa??es da base de dados `gapminder`. Qual a popula??o (vari?vel `pop`) do Afeganist?o em 1952?</font>

