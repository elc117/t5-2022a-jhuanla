![LibGDX_logo svg](https://user-images.githubusercontent.com/85958775/184716882-7a4ee881-4f25-4a23-a9f4-2a3eb0aa7ccd.png)

# Minicurso: LIBGDX


## Objetivos
Ao decorrer desta disciplina você com certeza teve contato com a biblioteca libGDX, sendo assim, neste minicurso você irá se aprofundar um pouco mais em algumas funcionalidades e particularidades desta podereosa biblioteca. Conhecendo támbem outras bibliotecas que provavelmente poderá te ajudar em seus jogos.

## Pré-requisitos
- [biblioteca libGDX](https://docs.google.com/presentation/d/18k3x_pKYT1mptiTYN74qq5MVoNm9mFv6uAnEbrjzBS4/edit?usp=sharing) (créditos à Profª Andrea Schwertner Charão)
- Conhecimento básico na instalação
- Conhecimento básico na ultilização da libGDX
- Usarei o [T4](https://github.com/elc117/t4-2022a-jhuanl-e-eduardof) para demonstrar alguns exemplos nas ultilizações.


## Começando
Quando for criar o projeto na libGDX, lembre de ativar a opção de extensão Box2d. Será importante para fazer os objetos que tem contato físico.


![image](https://user-images.githubusercontent.com/85958775/184734605-86e121c7-240b-4c31-aa35-367c0cceb728.png)

### Música
Começando pelo mais simples. Importaremos essas duas bibliotecas, uma vai acessar a música e a outra dará o play.
![image](https://user-images.githubusercontent.com/85958775/184747113-58b3ad42-8aac-4f83-9c03-4b6ca31f2644.png)

Temos que declarar o objeto que vai acessar a música.

![image](https://user-images.githubusercontent.com/85958775/184749511-443115cd-fdcb-4238-b9f8-48829abd3367.png)


Em seguida, o instânciamos e carregamos ele(não demos play ainda).

![image](https://user-images.githubusercontent.com/85958775/184750235-ff057ef0-c88b-4c56-906e-61bb56ac2db7.png)

OBS: Tudo que fizemos para a música até aqui foi na classe inicial do seu jogo, esta classe, no meu caso, é a que eu chamo a tela inicial.

#### Play na música

Para dar o play, faremos as modificações na classe onde queremos que a música toque. Nela declaramos o objeto da música.
![image](https://user-images.githubusercontent.com/85958775/184753586-6ef94120-1e17-45b0-bcb7-f0ee2f27d926.png)

e após isso o instânciamos usando o objeto manager instânciado anteriormente. Onde ele acessa os assets, no meu caso tem uma pasta audio/music e dentro dela tem o .mp3 com a música, e demos o play.
![image](https://user-images.githubusercontent.com/85958775/184752574-c5db8455-ca0e-427a-ac3e-cbf795386762.png)



### TiledMap
Todo jogo você geralmente inicia tendo um mapa em mente, mas como fazer um mapa do zero? quais ferramentas ultilizar? Apresentarei uma ferramenta chamada [TiledMap](https://www.mapeditor.org/), onde irá facilitar a criação do seu jogo. Leve em consideração que haverá outras ferramentas que irão se comunicar com o [TiledMap](https://www.mapeditor.org/).

Após baixar e executar o [TiledMap](https://www.mapeditor.org/) você irá se deparar com esta imagem

![image](https://user-images.githubusercontent.com/85958775/184728200-f1fab78a-1194-44c0-bca1-55ad383e5adb.png)

onde você iniciará seu projeto. Clicaremos em Novo Mapa.

![image](https://user-images.githubusercontent.com/85958775/184728876-57cd60f4-e9b2-408a-b883-5fd318861351.png)

Alguns exemplos de orientação(modo que você vê o jogo):
Ortogonal: Mario Bross, Sonic.
Isométrico: Age of Empires, Diablo.

Para metódos de aprendizado, deixaremos tudo como padrao(menos a orientação que será de sua escolha).

Após isso você vai se deparar com esta tela.

![image](https://user-images.githubusercontent.com/85958775/184731650-8639454f-ae97-408e-88b2-ed76b9592b5e.png)

Para prosseguirmos, usaremos tilesets para fazer o mapa, que seria mais ou menos como um conjunto de blocos prontos que você tem a total liberdade de "desenhar" o mapa do jeito que quiser. Escolha neste site o [tilesets](https://terminalroot.com.br/2022/04/baixe-de-graca-5-tilesets-para-seus-games.html) ou procure um de sua preferência.

Clique em Novo Tileset

![image](https://user-images.githubusercontent.com/85958775/184732851-98a4ad99-505f-4540-aa43-9a5daf20b35a.png)

Após isso, Escolha o seu conjunto de blocos(arquivo .png que você baixou anteriormente).
Obs: atente-se de ter escolhido o conjunto inteiro e não apenas um bloco. Visto a opção de escolher apenas um bloco, note que podemos escolher diferentes blocos e fazer diferentes mapas.

![image](https://user-images.githubusercontent.com/85958775/184733463-8de5d1cc-48ec-4e32-8652-3cc1dc47acc7.png)
Escolhendo um bloco do conjunto, você pode começar a desenhar o mapa. Faça o seu mapa e explore as funcionalidades do tiledmap.

IMPORTANTE: Separe o mapa por camadas. Coisas que estão no chão em uma , coisas que estão flutuando em outra. Sempre tenha em mente que precisamos fazer as colisões.

#### Renderização do mapa

Ao salvar o mapa, você terá um arquivo .tmx onde terá que colocar ele em assets do seu projeto da libgdx e também fazer os imports necessários do tiledmap.

![image](https://user-images.githubusercontent.com/85958775/184735213-ac868cd5-96c4-4361-bd4f-12fa6788d36a.png)

Começamos declarando os objetos necessárias em sua classe Create(), ou se ja estiver mais avançado, será a sua classe de tela do jogo.

![image](https://user-images.githubusercontent.com/85958775/184735702-c701d7e8-c241-4847-b6bb-fa9c1176f1f8.png)

Em seguida, instaciamos nossos objetos.
map vai receber um mapLoader que estará pegando o nosso tmx.
renderer será nosso objeto renderizador, ele irá renderizar nosso mapa na tela. Ele vai receber o mapa e um float(veja o que ele muda).

![image](https://user-images.githubusercontent.com/85958775/184736205-314f4f3e-35ab-4535-bdb7-5f072761df71.png)

E então renderizamos o renderer na classe render().

![image](https://user-images.githubusercontent.com/85958775/184741531-d1b627f3-bc17-42a6-9bf1-16a6f9c0397e.png)


### Animações

Existem vários métodos de criar uma animação, o modo que será apresentado a seguir usa de algumas bibliotecas unificadas. Ultilizaremos também uma ferramenta chamada [texturepacker](https://code.google.com/archive/p/libgdx-texturepacker-gui/downloads) ela será necessária para fazer arquivo com várias imagens, facilitando o uso de imagens.
Após "compilar" várias imagens, teremos dois arquivos importantes, um .pack e um .png que será mais ou menos assim.

![poswrrior](https://user-images.githubusercontent.com/85958775/184758503-c9637f56-81ca-4dae-b630-76c753add334.png)

na classe de tela do jogo, importaremos uma biblioteca chamada TextureAtlas. Ela pegará "regiões" do arquivo .pack que foi criado. Cada png usado no texturepacker para criar a compilação é chamado no .pack de região.

![image](https://user-images.githubusercontent.com/85958775/184759072-ab4232f8-04a3-4b57-901a-4b8c89202331.png)

Declaremos um objeto para pegar o .pack

![image](https://user-images.githubusercontent.com/85958775/184759357-3a3a48a1-7245-46a6-9e66-9ed19b7ddab6.png)

Após isso instânciamos o objeto necessário.

![image](https://user-images.githubusercontent.com/85958775/184759567-1849188d-75c1-4bee-98d7-6d5687d8b4f2.png)

e também criamos uma classe para retornar o atlas que será usado futuramente.

OBS: Tudo que fizemos para a animação até aqui foi na classe da tela do jogo.

Agora será usado em uma classe que faremos o nosso player e também a animação.

Importaremos algumas bibliotecas que serão usadas.

![image](https://user-images.githubusercontent.com/85958775/184762082-e5f34b0f-8fa7-471f-8cd6-1961e8608038.png)

Declaramos os objetos necessários, no nosso exemplo, tinhamos animações de ficar parado, morrer, andar e atacar.
Em Animation<TextureRegion> são realmente animações, que tem movimento, ja em TextureRegion é animação estática, sem movimento.

![image](https://user-images.githubusercontent.com/85958775/184765056-014cb679-a56a-4cd5-9856-94ba2ddfb7cb.png)

Na classe do player, demos um super passando uma região do .pack
Obs: Se você abrir o .pack no vscode, vai ver que cada .png tem um nome, no nosso caso um seria o png do personagem parado(front).

![image](https://user-images.githubusercontent.com/85958775/184767196-1053d99f-d041-4ce6-bab8-d00841dcd772.png)
  
Instânciamos um array de frames, ele receberá pequenos pedaços de uma imagem(texture region). No exemplo ele tem 58 de altura e largura, e a cada iteração do for ele pula 65 bite. e o objeto de andar recebe uma animation com a quantidade de frame e os frames do array. No nosso caso o i começa em 2 pois de 9 "bonecos" eu queria começar no segundo
  
![image](https://user-images.githubusercontent.com/85958775/184772113-9f60633b-99cb-4fe5-ac4a-c90a975270f0.png)
 
Os códigos anteriores foram feitos para uma animação dinâmica.
Para animações estáticas pegamos a posição do x e do y na matriz do png(eu fui testando até achar).
  
![image](https://user-images.githubusercontent.com/85958775/184773953-be90b113-13ec-48a2-bdca-3817d9539f9c.png)





















