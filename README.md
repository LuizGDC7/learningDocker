# Docker

Sistema de Virtualização não tradicional. É uma engine de administração de containers.

Containers são processos isolados associados a sistemas de arquivos isolado. 

A execução não é totalmente isolada do host. Existe compartilhamento de recursos, como memória e Kernel, por exemplo.

Utiliza tecnologia LXC (Linux Containers). Ou seja, não podemos usar um host MacOS, por exemplo. Mas essa limitação não tem muito impacto porque a maior parte dos sistemas usam o Kernel Linux.

Usamos containers ao invés de Máquinas Virtuais pois:

Conseguimos iniciar um container mais rapidamente (pois o Kernel é compartilhado)

Usamos menos recursos

Definimos quantos recursos iremos usar

## Containers 

Isolação de processos no mesmo Kernel

Sistema de arquivos criados a partir de uma imagem

Ambientes leves e portáteis no qul aplicações são executadas

Encapsula todos os binários e bibliotecas necessárias para execução de um App

Algo entre chroot e uma Virtual Machine

A boa prática é separar a aplicação entre vários containers.

## Imagens Docker

Modelo de sistema de arquivo read-only para criar containers.

Imagens são criadas a partir do processo Build. Esse build é um processo descritor, que descreve passo a passo as instruções para criar uma imagem.

São armazenadas em repositórios Registry (DockerHub, por exemplo). 

São compostas por uma ou mais camadas (layers). Uma camada representa uma ou mais mudanças no sistema de arquivos. Uma camada é também chamada de imagem intermediária.

A junção de camadas forma a imagem.

Apenas a última camada pode ser alterada quando o container for iniciado.

AUFS (Advanced multi-layered unification filesystem) é muito usado.

O grande objetivo de se ter várias camadas é o reuso.

É possível comport imagens a partir de camadas de outras imagens.

## Imagens X Containers

A Imagem é um modelo que é usado para criar containers. De forma alegórica, a Imagem é como uma classe, e o container uma instância polimórfica.