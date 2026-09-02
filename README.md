3. Computação Gráfica / Síntese de Imagens
3.1 Conceito
A Computação Gráfica é a área responsável pela criação e manipulação de representações visuais utilizando computadores.

Na síntese de imagens, o computador parte de informações como objetos geométricos, modelos tridimensionais, materiais, iluminação e posição de câmera para produzir uma representação visual.

Entre suas principais aplicações estão:

Jogos digitais;
Filmes e efeitos especiais;
Animações;
Realidade virtual;
Simuladores;
Projetos CAD;
Modelagem tridimensional;
Visualização arquitetônica.
Uma das principais características dessa área é que a imagem pode ser gerada a partir de uma representação matemática ou geométrica.

3.2 Aplicação escolhida
Para demonstrar essa área foi escolhido um exemplo de criação de um objeto tridimensional utilizando a biblioteca Open3D.

O Open3D é uma biblioteca de código aberto voltada para processamento de dados 3D e possui suporte a geometria, visualização, nuvens de pontos e malhas triangulares.

O projeto oficial pode ser consultado no repositório do Open3D.

4. Processamento de Imagens
4.1 Conceito

O Processamento de Imagens é a área da Computação Visual responsável pelo processamento e transformação de imagens digitais utilizando técnicas computacionais.

Diferentemente da Computação Gráfica, que pode criar uma imagem a partir de modelos e informações geométricas, o Processamento de Imagens normalmente utiliza uma imagem existente como entrada.

O objetivo pode ser melhorar a qualidade da imagem, modificar sua aparência, reduzir ruídos ou extrair determinadas características.

Entre suas principais aplicações estão:

Melhoria de imagens;
Redução de ruído;
Ajuste de brilho e contraste;
Aplicação de filtros;
Detecção de bordas;
Conversão para escala de cinza;
Binarização;
Segmentação de imagens;
Reconhecimento e análise de padrões.

Uma das principais características dessa área é trabalhar diretamente com os pixels de uma imagem, realizando operações que modificam ou extraem informações da representação digital.

4.2 Aplicação escolhida

Para demonstrar essa área, foi escolhido um exemplo de limiarização de imagens, também conhecido como thresholding, utilizando a biblioteca OpenCV.

O OpenCV
 é uma biblioteca de código aberto amplamente utilizada para processamento de imagens, visão computacional e análise de vídeos.

Neste experimento, uma imagem colorida será carregada e posteriormente convertida para escala de cinza. Em seguida, será aplicado um processo de limiarização, transformando a imagem em uma representação binária.

O projeto oficial pode ser consultado no repositório do OpenCV
.

Fluxo da aplicação
Imagem original
       ↓
Conversão para escala de cinza
       ↓
Aplicação do Threshold
       ↓
Imagem binária


Nesse experimento, os pixels da imagem são classificados de acordo com um determinado valor de intensidade.

Foi utilizado o valor de limiar 127. De forma simplificada:

Pixel <= 127 → Preto (0)

Pixel > 127 → Branco (255)


Dessa forma, a imagem original é transformada em uma imagem composta basicamente por pixels pretos e brancos.

4.4 Explicação

Inicialmente, a imagem é carregada utilizando a função:

cv2.imread()


Depois, a imagem é convertida para escala de cinza através da função:

cv2.cvtColor()


Uma imagem em escala de cinza possui apenas informações relacionadas à intensidade dos pixels.

Posteriormente, é utilizada a função:

cv2.threshold()


para realizar a limiarização.

O valor utilizado como limiar foi:

limiar = 127


Assim, os pixels são classificados de acordo com sua intensidade.

O resultado final é uma imagem binária, na qual os pixels assumem principalmente os valores 0 ou 255.

4.5 Resultado

A execução do programa produz uma comparação entre a imagem em escala de cinza e a imagem após a aplicação do threshold.

Figura 2 — Aplicação de limiarização utilizando OpenCV.

Observação: a imagem acima deve ser substituída pelo screenshot obtido durante a execução do programa.

4.6 Análise

Esse experimento representa uma aplicação de Processamento de Imagens, pois uma imagem existente é utilizada como entrada e posteriormente transformada.

O objetivo principal não é identificar o objeto presente na imagem, mas realizar uma operação sobre os pixels.

O processo pode ser resumido como:

Imagem existente
       ↓
Processamento dos pixels
       ↓
Transformação
       ↓
Nova representação da imagem


Portanto, o experimento demonstra uma das principais características do Processamento de Imagens: a transformação e manipulação de imagens digitais.

5. Visão Computacional
5.1 Conceito

A Visão Computacional é a área da Computação Visual responsável pelo desenvolvimento de técnicas capazes de permitir que computadores obtenham informações e realizem interpretações a partir de imagens e vídeos.

Enquanto o Processamento de Imagens está principalmente relacionado à transformação de imagens, a Visão Computacional busca extrair informações e significado do conteúdo visual.

Entre suas principais aplicações estão:

Reconhecimento de objetos;
Reconhecimento facial;
Detecção de pessoas;
Reconhecimento de placas;
Veículos autônomos;
Robótica;
Análise de imagens médicas;
Inspeção industrial;
Sistemas de segurança;
Classificação de imagens.

Uma das principais características da Visão Computacional é transformar dados visuais em informações que podem ser utilizadas por um sistema computacional.

Um exemplo simples pode ser representado por:

Imagem
   ↓
Algoritmo de Visão Computacional
   ↓
Análise da imagem
   ↓
Informação sobre o conteúdo

5.2 Aplicação escolhida

Para demonstrar essa área, foi escolhida uma aplicação de classificação de imagens utilizando Inteligência Artificial.

Para isso, será utilizada uma rede neural convolucional ResNet-50, disponibilizada através da biblioteca TorchVision.

O TorchVision
 faz parte do ecossistema PyTorch e disponibiliza modelos, conjuntos de dados e ferramentas voltadas para aplicações de visão computacional.

Neste experimento, uma imagem será fornecida ao modelo ResNet-50, que tentará determinar quais categorias são mais prováveis para o conteúdo apresentado.

O projeto oficial pode ser consultado no repositório do TorchVision
.

Fluxo da aplicação
Imagem
   ↓
Pré-processamento
   ↓
Rede Neural ResNet-50
   ↓
Classificação
   ↓
Categorias e probabilidades


Diferentemente do exemplo de Processamento de Imagens, o objetivo aqui não é apenas modificar os pixels da imagem.

O objetivo é interpretar o conteúdo visual e produzir uma informação sobre o que provavelmente está presente na imagem.

5.4 Explicação

Inicialmente são carregados os pesos pré-treinados do modelo:

weights = ResNet50_Weights.DEFAULT


Depois, a arquitetura ResNet-50 é criada:

model = resnet50(weights=weights)


Os pesos pré-treinados permitem que o modelo seja utilizado para realizar classificações sem que seja necessário treiná-lo novamente do zero.

A imagem utilizada como entrada também precisa passar por um pré-processamento compatível com o modelo:

preprocess = weights.transforms()


Após o pré-processamento, a imagem é enviada para a rede neural:

prediction = model(batch)


O modelo retorna valores associados às diferentes categorias que ele conhece.

Esses valores são transformados em probabilidades através da função:

softmax()


Por fim, são selecionadas as cinco categorias com maiores probabilidades.

5.5 Resultado

O programa apresenta no terminal as cinco categorias consideradas mais prováveis pelo modelo.

Um exemplo de saída possui o seguinte formato:

Principais previsões:

categoria_1: XX.XX%
categoria_2: XX.XX%
categoria_3: XX.XX%
categoria_4: XX.XX%
categoria_5: XX.XX%


Figura 3 — Resultado da classificação utilizando ResNet-50.

Observação: os resultados dependem da imagem utilizada. Os valores apresentados no projeto devem corresponder à execução realizada.

5.6 Análise

Esse experimento representa uma aplicação de Visão Computacional, pois o sistema recebe uma imagem e tenta extrair informações sobre seu conteúdo.

O objetivo não é apenas transformar a imagem, mas utilizar um modelo computacional para interpretá-la.

O processo pode ser representado por:

Imagem
   ↓
Pré-processamento
   ↓
Rede neural
   ↓
Análise
   ↓
Classificação
   ↓
Informação sobre a imagem


Esse exemplo demonstra como técnicas de Inteligência Artificial podem ser utilizadas para interpretar informações presentes em imagens.

Portanto, uma característica fundamental da Visão Computacional é a capacidade de transformar dados visuais em informações que podem ser utilizadas para tomada de decisões ou outras tarefas computacionais.

6. Visualização Computacional
6.1 Conceito

A Visualização Computacional é a área responsável pela representação visual de dados utilizando recursos computacionais.

Seu principal objetivo é transformar conjuntos de dados, que muitas vezes podem ser complexos ou difíceis de interpretar diretamente, em representações visuais que facilitem sua compreensão e análise.

Os dados podem ser representados em duas ou três dimensões e podem possuir diferentes formatos.

Entre suas principais aplicações estão:

Visualização científica;
Visualização médica;
Gráficos;
Mapas;
Visualização geográfica;
Simulações;
Visualização de dados financeiros;
Modelos tridimensionais;
Nuvens de pontos;
Análise de dados científicos.

Uma das principais características dessa área é utilizar recursos gráficos para permitir que uma pessoa consiga identificar padrões, estruturas e relações presentes nos dados.

6.2 Aplicação escolhida

Para demonstrar essa área, foi escolhida a visualização de uma nuvem de pontos tridimensional utilizando a biblioteca Open3D.

Uma nuvem de pontos é um conjunto de pontos que representam posições no espaço tridimensional.

Cada ponto pode ser representado por três coordenadas:

(x, y, z)


Um grande conjunto desses pontos pode representar objetos, ambientes ou superfícies tridimensionais.

O Open3D possui ferramentas específicas para leitura, processamento e visualização de nuvens de pontos.

O projeto oficial pode ser consultado no repositório do Open3D
.

Fluxo da aplicação
Dados tridimensionais
          ↓
Leitura dos dados
          ↓
Organização dos pontos
          ↓
Representação visual
          ↓
Análise pelo usuário


Neste caso, os dados já existem. O objetivo principal é criar uma representação visual que permita ao usuário observar e analisar a estrutura tridimensional.

6.4 Explicação

Inicialmente, o programa obtém uma nuvem de pontos de exemplo através de:

o3d.data.PCDPointCloud()


Em seguida, os dados são carregados utilizando:

o3d.io.read_point_cloud()


A nuvem de pontos contém diversas posições no espaço tridimensional.

Cada ponto pode ser representado conceitualmente como:

(x, y, z)


O número total de pontos pode ser obtido utilizando:

len(nuvem.points)


Por fim, os dados são apresentados através da função:

o3d.visualization.draw_geometries()


Essa ferramenta permite visualizar a estrutura tridimensional e interagir com a representação, realizando operações como rotação e zoom.

6.5 Resultado

O resultado esperado é uma representação tridimensional da nuvem de pontos.

Figura 4 — Visualização de uma nuvem de pontos tridimensional utilizando Open3D.

Observação: substitua a imagem acima pelo screenshot obtido durante a execução do programa.

6.6 Análise

Esse experimento representa uma aplicação de Visualização Computacional, pois o objetivo é representar visualmente um conjunto de dados tridimensionais.

Diferentemente da Computação Gráfica, o foco não está necessariamente na criação de um objeto artificial para gerar uma imagem.

Também não existe como objetivo principal modificar os pixels de uma imagem ou identificar automaticamente seu conteúdo.

O foco está na representação visual dos dados para facilitar sua análise.

O processo pode ser representado por:

Dados
  ↓
Processamento/organização
  ↓
Representação visual
  ↓
Interação
  ↓
Análise dos dados


Dessa maneira, a Visualização Computacional permite que estruturas e informações presentes nos dados sejam observadas de maneira mais intuitiva.

Um exemplo de aplicação real seria a visualização de dados obtidos por sensores 3D, scanners, equipamentos médicos ou sistemas de mapeamento.
