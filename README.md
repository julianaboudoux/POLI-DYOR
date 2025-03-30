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



