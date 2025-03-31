# Do Your Own Robot (DYOR)

Projeto DYOR – Robô Autônomo Inteligente
DYOR é um robô autônomo modelado na IDE CoppeliaSim, projetado para navegação inteligente, exploração e interação com o ambiente. Equipado com sensores LiDAR, ultrassônicos e câmeras, ele utiliza SLAM para mapear e evitar obstáculos, além de IA e machine learning para otimizar seus movimentos.

Com rodas omnidirecionais ou esteiras, DYOR adapta-se a diferentes terrenos e pode ser usado para exploração, monitoramento e assistência. 

DYOR se destaca como um robô versátil, simulável no CoppeliaSim, e ideal para pesquisa, inovação e aplicações no mundo real. 

### 0. Importando Arquivos 

Em primeiro ponto temos que importar os "mesh's" já baixados na descrição do vídeo para importação no coppelia.
Segue o link em anexo: https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbHFVVW9pWVZIQWpEMWpkel9SS2l1Wk5BS3RPQXxBQ3Jtc0tsdkN2NXdPaFAzSEtNdnhPZGRncHEzZGhMYkJVZVNfUXpodVBmc0MyNGJmdElmSml3MU9LTkFrVWw5NVVtSWZpc3NwRWdGTFRkVF81Z0t0dE1HODB5RVpGdXVtX2dreDdOZ0xlMi1ILW9xTFhwbUlvbw&q=https%3A%2F%2Froboticafacil.es%2Fcoppeliasim%2Fdyor%2Fdyor_coppeliasim_files.zip&v=jiIJFaTblhY

Na plataforma, teremos que realizar a importação da seguinte forma: 
Ao chegar nessa tela, seguiremos os seguintes passos:
Clicamos em "file", "import" e em "mesh". E assim, selecionamos o diretório onde estão localizadas os seguintes componentes que você deseja importar.
![image](https://github.com/user-attachments/assets/61bb5a06-dfd2-4898-b158-d3be83f7c21f)

Após isso, para agilizar o processo, podemos importar todos de uma só vez. Lembrando apenas de realizar as seguintes alterações localizadas no vídeo, que no caso, são:
![image](https://github.com/user-attachments/assets/cd2a6615-5ea5-4e24-aee4-d7e030b426c7)

As seguintes orientações do vídeo são: 
Colocar na escala de milímetros os elementos que serão importados, deixando a escala em "0.001" e logo em seguida formatar o eixo de orientação como Z, o "up-vector".
![image](https://github.com/user-attachments/assets/ac4914d2-8aac-42fd-8702-cf762b487e67)

Logo em seguida teremos o robô importado como "mesh", mas não como objetos puros:
![image](https://github.com/user-attachments/assets/dbf9e6fb-18f1-4ee4-bbc5-10e18bc09064)

E com isso você pode ajustar as nomenclaturas dos componentes conforme desejado.

Como vimos anteriormente, também é possível mudar a cor dos objetos conforme necessário: 
Nessa altura, os passos são conhecidos, mas segue as telas abaixo após clicar no componente.

![image](https://github.com/user-attachments/assets/2c1b8146-0ee0-435d-a8fe-665299128675)

Para importar componentes especiais, devemos realizar o "load model", como por exemplo o led_matrix, que também teve o download realizado: 
![image](https://github.com/user-attachments/assets/fe5cef95-08d3-45b3-ac3b-f14922650ed3)
![image](https://github.com/user-attachments/assets/6f918fad-c125-4cd9-875f-d2dbd1ec07d1)

Logo após a importação do led, falta apenas ajustar ele com a frente do robô:

![image](https://github.com/user-attachments/assets/66974a23-72ec-4d89-8733-7e5059271b2e)

Pronto, Está feito. :D


### 1. Transformando os objetos importados em "objetos puros"

Como era de se esperar, o "mesh" é formado por um conjunto de formas geométricas, nesse caso, de triângulos. 
Para realizar a transformação em objetos puros, seguiremos o seguinte esquema: 
Selecionaremos o objeto desejado e logo em seguida na opção "Toggle Shape"
![image](https://github.com/user-attachments/assets/be6ee260-bcc9-4b65-9230-3c500b7b0773)

Fica mais fácil a visualização se colocarmos objeto em outro layer: 
Por exemplo: 
![image](https://github.com/user-attachments/assets/c0d51320-6f4c-465a-973a-481d2e0d6880)

Realizando o processo, temos o seguinte: 
![image](https://github.com/user-attachments/assets/01ea40f8-6e00-4e4d-9d5a-b7c07cb4c4f2)

Agora, apertando a tecla "shift" e selecionando a quantidade de triângulos desejados, extrairemos a forma desejada, seja ela um "cuboid", um cilidro, ou até se possível, uma esfera.
![image](https://github.com/user-attachments/assets/e86523e8-d955-4d72-9081-bfedc8e36bca)

Após a seleção, teremos: 
![image](https://github.com/user-attachments/assets/c64ca661-8ee0-4890-a055-38d230efc9fd)

E podemos extrair a forma desejada. 
Para isso, transformaremos ele em um objeto "dynamic and responsable" conforme a opção selecionada:
![image](https://github.com/user-attachments/assets/5d797527-ddf8-4395-820b-d018a3ce3bfa)

Com o objeto extraído, podemos movê-lo para outra layer, onde ficará melhor o manuseio e realizar as devidas alterações. Faremos isso para todo o robô.
![image](https://github.com/user-attachments/assets/c9493e13-737f-4a27-9a3f-776bc7cd0172)

Um pequeno adendo ao importar os componentes de suporte da roda, para ficar igual no vídeo, como ele não mostra, selecione manualmente com a tecla Ctrl os 3 triângulos da base.
Eles são mostrados a seguir:
![image](https://github.com/user-attachments/assets/1d607107-e0e4-4258-9dd7-14a59cd65260)
Pronto, agora é só realizar para o outro lado, para parte superior do suporte e depois veremos como unir esses elementos mais à frente. 
Obrigado :D - Aline Soares, Caio Victor, Lucas Muniz.


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







