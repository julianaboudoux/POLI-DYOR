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
- As três partes (objetos puros) do suporte da “caster wheel” (roda da frente) do robô -> Formando um suporte da "caster wheel". 

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
- Uma vertical para o suporte da caster wheel.

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

As joints do suporte da "caster wheel" e da "caster wheel" em so devem ser colocadas em modo "free":

![image](https://github.com/user-attachments/assets/732d445f-5365-4585-a40a-ff9e331bbb11)

As joints dos braços devem ser colocadas no modo "position":

![image](https://github.com/user-attachments/assets/4aceed3f-2146-446c-802d-0a20457d2a07)


### 4. Hierarquia e configuração da massa de objetos (debugging massa). 

Após a configuração das joints e dos objetos puros, iremos fazer a hierarquia de cena necessária para o funcionamento correto do nosso robô. Esse processo confirma
a conexão entre o robô em si e todos os objetos/joints/objetos puros configurados anteriormente.

Primeiro, vamos configurar as "wheel"s laterais. Os objetos puros sempre estarão como "filho" da joint e o objeto original, como a seguir:

![image](https://github.com/user-attachments/assets/ace753e4-5a2a-43e7-8d1f-fc91cbe8fcd9)

Em seguida, faremos o mesmo processo com os braços ("left_arm_joint" e "right_arm_joint").

![image](https://github.com/user-attachments/assets/a65f88af-42a5-4828-8f3f-cc79124f93b9)

Por fim, as "caster wheel"s. Lembrando que,  "caster_joint" está conectando o "caster_support" à base do robô, e "caster_support" em si está conectado à roba em si, a "caster_wheel", a partir da joint "caster_wheel_joint". Veja a seguir

![image](https://github.com/user-attachments/assets/56a844ff-9755-4e53-a884-878b5a773c76)

No final, sua hierarquia de cena deve estar parecido como abaixo:

![image](https://github.com/user-attachments/assets/84a0d9ab-7c3f-425c-bc61-8ee639a4ee7f)

Para finalizar o tópico, iremos mudar a massa do "left_arm_pure", "left_arm_pure" e da "caster_wheel", pois o robô está pendendo para frente no momento, por causa da distribuição errada dos objetos. para "left_arm_pure" e "left_arm_pure", acesse as propriedades dinâmicas dos objetos, e em "Mass", coloque o valor '0.001438'.

![image](https://github.com/user-attachments/assets/d57b71b0-f0ff-4840-8948-7d06db61c2b7)

Já para a "caster_wheel" coloque o valor '0.1066'.

![image](https://github.com/user-attachments/assets/e2d1289e-226d-4db9-b8a4-6905d3a52fb3)


### 5. Explicação do código do robô manual (incluíndo LED).

Nesse momento, iremos analisar o códido que fará nosso robô se movimentar de maneiras diferentes. Iremos usar a linguagem Lua. Primeiro, precisamos adicionar o script no nosso robo. clique com o botao direito no "Robot", e siga o caminho na imagem a seguir, criando um script sem Threads em Lua. O código consiste em:

- Controle de velocidade linear e angular por sliders.
- Comando para abrir/fechar a garra do robô.
- Botões de movimento: Frente, Ré, Esquerda, Direita e Parar.
- Interface interativa criada via simUI.

![image](https://github.com/user-attachments/assets/0a1302c7-2d0b-4f0a-8fa2-fdf7ac713b7c)

Esse script deve aparecer no final da hierarquia de cenas, dentro do objeto "Robot", como a seguir. ![image](https://github.com/user-attachments/assets/16d5d8f1-ffe6-4bd9-8212-01c21d5c80e9)

Dê dois cliques com o botao esquerdo para abrir o script.

![image](https://github.com/user-attachments/assets/eddd1998-4e01-497c-a764-f088b8647cca)

Para começar o código em si, vamos à função SysCall_init(). Essa função é a primeira a ser executada quando começamos a simulação. Temos abaixo as variáveis equivalentes aos dois braços e às duas rodas laterais. Em seguida, definimos parâmetros que serão usados futuramente. esses são: raio da roda, velocidade máxima e giro, a distância entre rodas e a velocidade e giro inicias.

```
function sysCall_init()
    left_arm=sim.getObjectHandle('left_arm_joint')
    right_arm=sim.getObjectHandle('right_arm_joint')
    left_wheel=sim.getObjectHandle('left_joint')
    right_wheel=sim.getObjectHandle('right_joint')
    wheel_radius=0.03
    max_speed=0.03
    max_turn=0.3
    speed=0
    turn=0
    b=0.0565
    gripper_open=false
end
```

Para a movimentação em si, vamos começar com a função "move", que irá fazer o cálculo de movimento diferencial (velocidade linear e angular), sendo v = velocidade linear, w = velocidade angular, b = metade da distância entre rodas e wheel_radius = raio das rodas. É criada fora do SysCall_init().

```
function move(v,w)
    sim.setJointTargetVelocity(left_wheel,(v-b*w)/wheel_radius)
    sim.setJointTargetVelocity(right_wheel,(v+b*w)/wheel_radius)
end
```

Essa função será chamada nas funções "onSpeedChange" e "onTurnChange", que por si serão chamadas na UI que vamos fazer em seguida. "onSpeedChange" calcula a nova velocidade real: speed = newValue * max_speed / 100 e "onTurnChange" Calcula a nova velocidade angular: turn = newValue * max_turn / 100. Esses dois métodos são criados fora do SysCall_init().

```
function onSpeedChange(uiHandle, id, newValue)
    speed=newValue*max_speed/100
    move(speed,turn)
end
function onTurnChange(uiHandle, id, newValue)
    turn=newValue*max_turn/100
    move(speed,turn)
end
```

Para o Gripper, temos uma função para abrir e uma para fechar, além de outra função que alterna o estado da garra (aberta/fechada).

```
function onGripper()
  if gripper_open then
    closeGripper()
    gripper_open=false
  else
    openGripper()
    gripper_open=true
  end
end
function openGripper()
    sim.setJointTargetPosition(left_arm,30*math.pi/180)
    sim.setJointTargetPosition(right_arm,-30*math.pi/180)
end
function closeGripper()
    sim.setJointTargetPosition(left_arm,-10*math.pi/180)
    sim.setJointTargetPosition(right_arm,10*math.pi/180)
end
```

Agora temos um conjunto de funções que controlam diretamente a movimentação do robô, e serão adicionadas como botões na UI. moveForward() faz o robô andar com 505 da velocidade máxima para frente, moveBackwards() 505 para trás, turnLeft() faz o robô ficar girando à esquerda, turnRight() para a direita e stop() faz o robô para completamente. 

```
function moveForward()
    sim.setJointTargetVelocity(left_wheel,0.5*max_speed/wheel_radius)
    sim.setJointTargetVelocity(right_wheel,0.5*max_speed/wheel_radius)
end
function moveBackwards()
    sim.setJointTargetVelocity(left_wheel,-0.5*max_speed/wheel_radius)
    sim.setJointTargetVelocity(right_wheel,-0.5*max_speed/wheel_radius)
end
function turnLeft()
    sim.setJointTargetVelocity(left_wheel,-0.5*max_speed/wheel_radius)
    sim.setJointTargetVelocity(right_wheel,0.5*max_speed/wheel_radius)
end
function turnRight()
    sim.setJointTargetVelocity(left_wheel,0.5*max_speed/wheel_radius)
    sim.setJointTargetVelocity(right_wheel,-0.5*max_speed/wheel_radius)
end
function stop()
    sim.setJointTargetVelocity(left_wheel,0)
    sim.setJointTargetVelocity(right_wheel,0)
end
```

Temos todas as funções necessárias, agora criaremos a UI. voltando à function sysCall_init(), faremos modificações. 'ui=simUI.create' faz a criação da UI e podemos agora adicionar botos com as funções que criamos anteriormente.

```
function sysCall_init()
    -- do some initialization here
    left_arm=sim.getObjectHandle('left_arm_joint')
    right_arm=sim.getObjectHandle('right_arm_joint')
    left_wheel=sim.getObjectHandle('left_joint')
    right_wheel=sim.getObjectHandle('right_joint')
    wheel_radius=0.03
    max_speed=0.03
    max_turn=0.3
    speed=0
    turn=0
    b=0.0565
    gripper_open=false
    ui=simUI.create('<ui enabled="true" modal="false" title="DYOR" closeable="true" layout="vbox" placement="relative" position="20,20">' ..
    '<label enabled="true" text="Linear Speed"></label>' ..
    '<hslider enabled="true" minimum="-100" maximum="100" on-change="onSpeedChange"></hslider>' ..
    '<label enabled="true" text="Angular Speed"></label>' ..
    '<hslider enabled="true" minimum="-100" maximum="100" on-change="onTurnChange"></hslider>' ..
    '<button enabled="true" text="Open/Close" checkable="true" on-click="onGripper"></button>' ..
    '<button enabled="true" text="Forward" on-click="moveForward"></button>' ..
    '<button enabled="true" text="Backwards" on-click="moveBackwards"></button>' ..
    '<button enabled="true" text="Left" on-click="turnLeft"></button>' ..
    '<button enabled="true" text="Right" on-click="turnRight"></button>' ..
    '<button enabled="true" text="Stop" on-click="stop"></button>' ..
    '</ui>')
end
```

Aqui segue o código completo:

```
function onSpeedChange(uiHandle, id, newValue)
    speed=newValue*max_speed/100
    move(speed,turn)
end
function onTurnChange(uiHandle, id, newValue)
    turn=newValue*max_turn/100
    move(speed,turn)
end
function onGripper()
  if gripper_open then
    closeGripper()
    gripper_open=false
  else
    openGripper()
    gripper_open=true
  end
end
function openGripper()
    sim.setJointTargetPosition(left_arm,30*math.pi/180)
    sim.setJointTargetPosition(right_arm,-30*math.pi/180)
end
function closeGripper()
    sim.setJointTargetPosition(left_arm,-10*math.pi/180)
    sim.setJointTargetPosition(right_arm,10*math.pi/180)
end
function move(v,w)
    sim.setJointTargetVelocity(left_wheel,(v-b*w)/wheel_radius)
    sim.setJointTargetVelocity(right_wheel,(v+b*w)/wheel_radius)
end
function moveForward()
    sim.setJointTargetVelocity(left_wheel,0.5*max_speed/wheel_radius)
    sim.setJointTargetVelocity(right_wheel,0.5*max_speed/wheel_radius)
end
function moveBackwards()
    sim.setJointTargetVelocity(left_wheel,-0.5*max_speed/wheel_radius)
    sim.setJointTargetVelocity(right_wheel,-0.5*max_speed/wheel_radius)
end
function turnLeft()
    sim.setJointTargetVelocity(left_wheel,-0.5*max_speed/wheel_radius)
    sim.setJointTargetVelocity(right_wheel,0.5*max_speed/wheel_radius)
end
function turnRight()
    sim.setJointTargetVelocity(left_wheel,0.5*max_speed/wheel_radius)
    sim.setJointTargetVelocity(right_wheel,-0.5*max_speed/wheel_radius)
end
function stop()
    sim.setJointTargetVelocity(left_wheel,0)
    sim.setJointTargetVelocity(right_wheel,0)
end
function sysCall_init()
    -- do some initialization here
    left_arm=sim.getObjectHandle('left_arm_joint')
    right_arm=sim.getObjectHandle('right_arm_joint')
    left_wheel=sim.getObjectHandle('left_joint')
    right_wheel=sim.getObjectHandle('right_joint')
    wheel_radius=0.03
    max_speed=0.03
    max_turn=0.3
    speed=0
    turn=0
    b=0.0565
    gripper_open=false
    ui=simUI.create('<ui enabled="true" modal="false" title="DYOR" closeable="true" layout="vbox" placement="relative" position="20,20">' ..
    '<label enabled="true" text="Linear Speed"></label>' ..
    '<hslider enabled="true" minimum="-100" maximum="100" on-change="onSpeedChange"></hslider>' ..
    '<label enabled="true" text="Angular Speed"></label>' ..
    '<hslider enabled="true" minimum="-100" maximum="100" on-change="onTurnChange"></hslider>' ..
    '<button enabled="true" text="Open/Close" checkable="true" on-click="onGripper"></button>' ..
    '<button enabled="true" text="Forward" on-click="moveForward"></button>' ..
    '<button enabled="true" text="Backwards" on-click="moveBackwards"></button>' ..
    '<button enabled="true" text="Left" on-click="turnLeft"></button>' ..
    '<button enabled="true" text="Right" on-click="turnRight"></button>' ..
    '<button enabled="true" text="Stop" on-click="stop"></button>' ..
    '</ui>')
end
function sysCall_actuation()
    -- put your actuation code here
end
function sysCall_sensing()
    -- put your sensing code here
end
function sysCall_cleanup()
    -- do some clean-up here
end
```

Agora, iremos fazer e analisar o código da matriz de led. Abra o script da "led_matrix" ![image](https://github.com/user-attachments/assets/f390dbd1-6763-4706-8114-ceeddea7fd8e)
Criaremos uma interface gráfica com botões para a exibição visual das expressões em tempo real utilizando cor vermelha nos LEDs acesos. A matriz é 8x8, manipulada via código Lua. Faremos as expressões a seguir:

Happy (Feliz)
Sad (Triste)
Angry (Bravo)
Love (Apaixonado)
Off (Desliga a matriz)


Vamos definir as funções a serem utilizadas na UI. lshift e rshift são usadas para converter inteiros em sequências binárias e controlar os LEDs individualmente. As expressões são vetores com 8 inteiros, cadda uma de uma maneira

```
local function lshift(x)
  return x * 2
end

local function rshift(x)
  return math.floor(x / 2)
end

function onOff()
setExpression({0,0,0,0,0,0,0,0})
end

function onHappy()
setExpression({48,24,12,12,12,12,24,48})
end

function onSad()
setExpression({12,24,48,48,48,48,24,12})
end

function onLove()
setExpression({48,120,124,62,62,124,120,48})
end

function onAngry()
setExpression({64,34,36,8,8,36,34,64})
end
```

A função principal de renderização itera por cada linha e coluna da matriz, converte os valores decimais em binário e acende ou apaga os LEDs de acordo com o bit correspondente.

```
function setExpression(values)
    for i=1,8,1 do
      value=values[i]
      for j=1,8,1 do
        local rv=value%2
        if (rv>0) then
            sim.setShapeColor(leds[j][i],NULL,sim.colorcomponent_emission,led_on_color)
        else
            sim.setShapeColor(leds[j][i],NULL,sim.colorcomponent_emission,led_off_color)
        end
        value=rshift(value)
      end
    end
end

```

A inicialição sysCall_init() define as cores dos LEDs: vermelho ligado e preto desligado. Também monta a matriz bidimensional leds[i][j] para facilitar acesso e controle. A UI é criada usando simUI com layout de grade (grid) e posicionamento fixo na tela:

```
function sysCall_init()
    -- do some initialization here
    led_matrix=sim.getObjectHandle('led_matrix')
    leds={};
    led_off_color={0,0,0}
    led_on_color={1,0,0}
    for i=1,8,1 do
        leds[i]={}
      for j=1,8,1 do
        leds[i][j]=sim.getObjectHandle('led' .. i .. '_' .. j)
        sim.setShapeColor(leds[i][j],NULL,sim.colorcomponent_emission ,led_off_color)
      end
    end
    ui=simUI.create('<ui enabled="true" modal="false" title="LED Matrix" closeable="true" resizable="false" layout="grid" placement="relative" position="20,420"><button enabled="true" text="Off" on-click="onOff"></button><button enabled="true" text="Happy" on-click="onHappy"></button><button enabled="true" text="Sad" on-click="onSad"></button><button enabled="true" text="Angry" on-click="onAngry"></button><button enabled="true" text="Love" on-click="onLove"></button></ui>')
end
```

Ao finalizar a simulação, todos os LEDs são desligados (cor preta) no sysCall_cleanup()

```
function sysCall_cleanup()
    -- do some clean-up here
    for i=1,8,1 do
        leds[i]={}
      for j=1,8,1 do
        leds[i][j]=sim.getObjectHandle('led' .. i .. '_' .. j)
        sim.setShapeColor(leds[i][j],NULL,sim.colorcomponent_emission,led_off_color)
      end
    end
end
```

Aqui segue o código completo:

```
local function lshift(x)
  return x * 2
end

local function rshift(x)
  return math.floor(x / 2)
end

function onOff()
setExpression({0,0,0,0,0,0,0,0})
end

function onHappy()
setExpression({48,24,12,12,12,12,24,48})
end

function onSad()
setExpression({12,24,48,48,48,48,24,12})
end

function onLove()
setExpression({48,120,124,62,62,124,120,48})
end

function onAngry()
setExpression({64,34,36,8,8,36,34,64})
end

function sysCall_init()
    -- do some initialization here
    led_matrix=sim.getObjectHandle('led_matrix')
    leds={};
    led_off_color={0,0,0}
    led_on_color={1,0,0}
    for i=1,8,1 do
        leds[i]={}
      for j=1,8,1 do
        leds[i][j]=sim.getObjectHandle('led' .. i .. '_' .. j)
        sim.setShapeColor(leds[i][j],NULL,sim.colorcomponent_emission ,led_off_color)
      end
    end
    ui=simUI.create('<ui enabled="true" modal="false" title="LED Matrix" closeable="true" resizable="false" layout="grid" placement="relative" position="20,420"><button enabled="true" text="Off" on-click="onOff"></button><button enabled="true" text="Happy" on-click="onHappy"></button><button enabled="true" text="Sad" on-click="onSad"></button><button enabled="true" text="Angry" on-click="onAngry"></button><button enabled="true" text="Love" on-click="onLove"></button></ui>')
end

function sysCall_actuation()
    -- put your actuation code here
    
end

function sysCall_sensing()
    -- put your sensing code here
end

function sysCall_cleanup()
    -- do some clean-up here
    for i=1,8,1 do
        leds[i]={}
      for j=1,8,1 do
        leds[i][j]=sim.getObjectHandle('led' .. i .. '_' .. j)
        sim.setShapeColor(leds[i][j],NULL,sim.colorcomponent_emission,led_off_color)
      end
    end
end

function setExpression(values)
    for i=1,8,1 do
      value=values[i]
      for j=1,8,1 do
        local rv=value%2
        if (rv>0) then
            sim.setShapeColor(leds[j][i],NULL,sim.colorcomponent_emission,led_on_color)
        else
            sim.setShapeColor(leds[j][i],NULL,sim.colorcomponent_emission,led_off_color)
        end
        value=rshift(value)
      end
    end
end

-- See the user manual or the available code snippets for additional callback functions and details
```
