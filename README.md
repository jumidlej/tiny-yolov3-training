# Tiny YOLOv3 Training on Darknet

## Criar dataset

Para criar um dataset, precisamos rotular as imagens que serão utilizadas destacando os objetos que serão detectados. Para rotular as imagens pode ser usada a ferramenta labelImg que pode ser baixada no link a seguir: https://github.com/tzutalin/labelImg.

![image](https://user-images.githubusercontent.com/49077115/158436628-b63c63bb-4185-4ab8-a536-793aee804c19.png)

Esse ferramenta irá criar um arquivo .txt para cada imagem informando os bounding boxes de cada objeto da imagem no seguinte formato: class x y width height. A variável class informa a classe do objeto e será sempre um número. Essa variável estará relacionada ao arquivo classes.txt do qual falaremos a seguir. Os pontos (x, y) correspondem ao centro do objeto, width corresponde a largura do objeto e height corresponde a altura do objeto. Todos os valores se encontram divididos pela largura (x, width) ou altura (y, height) da imagem, estando, dessa maneira, normalizados. Cada linha do arquivo criado corresponde a um objeto da imagem.

![image](https://user-images.githubusercontent.com/49077115/158441017-9f37b6e0-7b82-4997-99e9-907cb411b4f2.png)

Também será criado um arquivo chamado classes.txt que informará o nome das classes dos objetos. Na imagem abaixo, podemos perceber que temos 5 objetos, e todo objeto representado pelo número de classe 0 nas linhas mostradas na imagem acima será azul, 1 será roxo, e assim por diante.

![image](https://user-images.githubusercontent.com/49077115/158447114-457189e2-e054-47e0-acb9-2187cd29bdb7.png)

## Criar arquivos de treinamento e validação

Antes de separar nossos arquivos entre arquivos de teste e validação para a rede neural em que iremos treinar, teremos primeiro que converter o formato de localização dos objetos das nossas imagens para o correspondente: image_name.jpg xmin,ymin,xmax,ymax,class xmin,ymin,xmax,ymax,class. Apenas um arquivo irá conter todas as imagens e em cada linha serão especificados a imagem e todos os seus objetos.

![image](https://user-images.githubusercontent.com/49077115/158444722-90f0f6f4-f35a-4839-af9e-eb21b4889064.png)

Devemos possuir dois arquivos nesse formato. O arquivo de teste e o arquivo de validação.

## Criar arquivo de informações sobre o treinamento

Por fim, iremos fazer um arquivo informando a localização de arquivos e pastas importantes para o treinamento. Esse arquivo conterá o número de classes, a localização dos arquivos de teste e validação, a localização do arquivo de classes, e a localização da pasta de backup onde serão salvos os pesos do nosso treinamento.

![image](https://user-images.githubusercontent.com/49077115/158445571-44b0a811-47fb-4024-98f1-17469c5d1a71.png)

## Criar arquivo de configurações da rede neural

O último arquivo necessário para treinarmos nossa rede neural é o arquivo de configurações da rede. Esse arquivo será criado automaticamente no notebook de treinamento ao ser definido o número de classes de objetos que serão treinados.

## Rodar o Google Colab Notebook

Com todos os arquivos prontos, podemos rodar o notebook de treinamento da rede.
