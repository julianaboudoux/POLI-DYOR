# Do Your Own Robot (DYOR)

Descrição do projeto blablablablabla

### 0. Imporando arquivos

### 1. 

### 2. Agrupamento dos objetos e propriedade das rodas

Vamos agrupar algumas os seguintes objetos puros recém extraídos do nosso robô:

- Parte de baixo dos braços com a parte de cima dos braços (fazemos isso para os dois braços) -> Formando um braço direito e um braço esquerdo.
- A base horizontal com a base vertical do robô -> Formando um objeto que será base tanto vertical quanto horizontal do robô.
- As três partes (objetos puros) do suporte da “castor wheel” (roda da frente) do robô -> Formando um suporte da "castor wheel". 

Conseguimos agrupar objetos ao clicar em um dos objetos a ser agrupado, pressionar a tecla SHIFT e, enquanto pressionamos a tecla, clicamos no outro objeto a ser agrupado.



https://github.com/user-attachments/assets/fb94a37d-234b-4087-af4c-0f824bf3a1f8

Vamos também tornar o material das rodas mais próximo da realidade. Para isso, vamos clicar duas vezes no nome do objeto (nesse caso, uma roda) e aprecererá o painel abaixo:

![image](https://github.com/user-attachments/assets/c5054208-1356-4881-891b-ca411f84036c)

Iremos selecionar a opção "Dynamic properties dyalog" e iremos para esse painel:

![image](https://github.com/user-attachments/assets/58520836-b844-4460-8282-07bd3bcb042c)

Clicaremos em "Engine Properties" e no código que surgirá, devemos buscar pela palavra "friction" e alterar seu valor para 1:

![image](https://github.com/user-attachments/assets/64bfbcc5-21db-4396-95d9-1100230044db)


### 3. Colocação e configuração das joints

O nosso robô terá 6 joints.

- Uma horizontal para para cada roda (3 no total).
- Uma vertical para cada braço (2 no total).
- Uma vertical para o suporte da castor wheel.

O tipo da joint será “revolute” para todas. A colocação das joints no centro dos objetos é feita do seguinte modo:

1. Clicamos na joint
2. Pressionamos a telca SHIFT
3. Cicamos no objeto que terá a joint acoplada
4. Clicamos no simbolo de "Object Shift"
5. Na caixa de texto que abriu, selecionamos a aba "position"
6. Clicamos em "Apply to selection"

Obs 1: o tamanho da joint geramente não impacta no funcionamento, então podemos apenas criar num tamanho que faça sentindo para nosso robô.
Obs 2: quando necessário, devemos fazer uma rotação na joit para que ela fique na posição correta (vertical ou horizontal).

Demonstração no vídeo abaixo:

https://github.com/user-attachments/assets/b96c4580-49b3-435f-8826-128e3b391080

Para as joints nos braços, devemos criar um objeto temporário, que deverá ser apagado depois. Esse objeto nos ajudará a centralizar as joints dos braços. Devemos criar esses objetos para ambos os lados do robô, e após posicionar as joints, vamos apagá-los.

![image](https://github.com/user-attachments/assets/76609c7d-8123-4d5c-bcd3-1c2950434484)

Após todas as joints serem posicionadas, o objeto deve-se parecer com a seguinte imagem:

![image](https://github.com/user-attachments/assets/3818624d-dd0b-4cc7-91dd-8ddc93178169)

Agora vamos configurar as propriedades das joints:

As duas joints das rodas laterais devem ser colocadas em modo "velocity":

![image](https://github.com/user-attachments/assets/b4e65513-e040-45f6-b3cb-1395615b8842)

As joints do suporte da "castor wheel" e da "castor wheel" em so devem ser colocadas em modo "free":

![image](https://github.com/user-attachments/assets/732d445f-5365-4585-a40a-ff9e331bbb11)

As joints dos braços devem ser colocadas no modo "position":

![image](https://github.com/user-attachments/assets/4aceed3f-2146-446c-802d-0a20457d2a07)







