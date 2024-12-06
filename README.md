<h1 align="center">Atividade Docker e AWS</h1>

<p align="center">
Atividade na qual deve ser criada uma aplicação baseada na arquitetura proposta, dentro da nuvem AWS e com foco no uso do Docker.
</p>

<p align="center"><img src="./images/title-image.png"></p>

## Arquitetura proposta
<p align=center><img src="./images/image1.png"></p>
Obeservando a imagem à cima, é possível determinar os requerimentos da arquitetura, que são estes:

1. VPC
2. Load Balancer
3. Auto Scaling Group em 2 availability zones
4. Uma instância EC2 para cada availability zone
5. Wordpress instalado nas instâncias
6. Banco de dados RDS, que fornecerá os dados às instâcias EC2

### VPC
Como pode ser visto na arquitetura, será necessário criar o alicerce para que possamos realizar o deploy da nossa aplicação.

O que deve ser criado antes de tudo é a VPC, que será a base para montarmos um sistema de redes. Abaixo está o esquema de subnets, route tables e gateways:

<p align=center><img src="./images/image2.png"></p>

Aqui temos 6 subnets, são 3 para cada availability zone. Sendo uma pública para o Load balancer, uma privada para a instância EC2, e uma privada para o RDS.

Nas route tables nós temos uma tabela para cada subnet, a tabela pública é compartilhada entre as duas subnets públicas, que servirão de acesso para o Load Balancer, enquanto as privadas serão para trafego interno, assim como pode ser observado na arquitetura.

Isso é importante para manter o isolamento das instâncias e do banco de dados

### 1. instalação e configuração do DOCKER ou CONTAINERD no host EC2

<h3>2. Efetuar Deploy de uma aplicação Wordpress com:<br>
• container de aplicação<br>
• RDS database Mysql<h3>

### 3. configuração da utilização do serviço EFS AWS para estáticos do container de aplicação Wordpress

### 4. configuração do serviço de Load Balancer AWS para a aplicação Wordpress
