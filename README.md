# Pojeto AWS Cloudformation CFN METADATA

 Nesse projeto foi usado o Desinger,Interface graica Init cloudformation no console da AWS
 para criar instâncias EC2 mudar o formato YML para JSON ou vice versa.

Metadata

• Metadata fornece detalhes sobre o modelo CFN.  
Syntax: 
   Metadata
     Intances:
       Description: "Information aboute the instances"
     Database:
       Description: "Information aboute the databases"

AWSTemplateFormatVersion: 2010-09-09

Metada:
  Instances:
    Description: My VM Instance

Temos três tipos de teclas de metadados listadas abaixo.
Metadata Keys 
AWS::CloudFormation::Designer 
AWS::CloudFormation::Interface 
AWS::CloudFormation::Init

• Metadata Keys

AWS::CloudFormation::Designer 
Gerado automaticamente durante os recursos arrastar e cair para a tela.

AWS::CloudFormation::Interface 
Usado para agrupamento de parâmetros.

AWS::CloudFormation::Init 
Usado para instalação e configurações de aplicativos em nossa computação AWS (EC2
posições).
Esta é uma característica central e importante da CloudFormation.
Temos uma seção completa, descrevendo os detalhes de ponta a ponta do init.

================================================================================

Metadata AWS::CloudFormation::Designer 

• AWS::CloudFormation::Designer 

Designer, Visually depicts how our 
resources are laid out  
Designer automatically add this 
information when we use it to 
create view and update templates. 
Its  a system generated metadata.  
It defines the information about our 
resources such as their size and 
relative position in template 
metadata. All layout information is 
stored in designer metadata.


AWS::CloudFormation::Designer 
Syntax:
Metadata: 
  'AWS::Cloudformation::Designer':
    6b56eaae-0bb6-4215-aad6-12345EXAMPLEE:
      size:
        width: 60
        height: 60
      position:
        x: 340
        'y': 430
      z: 2
      parent: 21ccc9b0-29ee9-4a86-9cf2-12345EXAMPLE
      embeds: []
      ismeberof:
        - c3eead73-6a76-4532-9268-12345EXAMPLE

Designer, Mostra visualmente como nosso
Recursos são dispostos

Designer Adicionar automaticamente isso
informação quando o usamos para
Crie modelos de visualização e atualização.
É um sistema gerado por metadados.

Define as informações sobre o nosso
recursos como seu tamanho e
posição relativa no modelo
metadados.Todas as informações de layout são
armazenados em metadados de designer.


No designer, drag and drop  os recursos.
Quando criamos modelos no designer, ele aplica alguns básicos
relacionamentos entre recursos para nos ajudar a criar um modelo válido.
Exemplo: não podemos adicionar diretamente a instância do EC2 em um VPC, devemos adicionar
uma sub -rede em um VPC.
Também podemos validar o modelo diretamente no designer.
Podemos trazer nosso modelo que escrevemos manualmente e
Validar no designer usando o modelo Validate.

• Integrated Editor: 
Podemos fazer todas as nossas modificações de modelo com este editor.
Ele também fornece o recurso de preenchimento automático que lista todos os nomes de propriedades para um
recurso para que não precisemos memorizar todas as propriedades de um recurso ou
Consulte a documentação.
Podemos usar o editor integrado para converter de JSON para YAML e vice -versa.

• Como eu uso o designer?

Em primeiro lugar, escrevo meus modelos CFN manualmente no editor, referindo a documentação
O que me dá maior confiança nesse recurso específico para o qual estou escrevendo modelo.
Eu uso o código do Visual Studio como meu editor devido ao fato de que lidar com os espaços da YAML é simplificado neste editor.
Eu apenas uso as guias e o editor de código VScode cuida dos espaços YAML.
Copiar modelo para o editor integrado e o modelo de validar.
Converter modelo de JSON para YAML ou YAML para JSON.
Arraste os recursos para a tela e veja suas propriedades (algumas vezes).
Modelo de copiar para o editor integrado e modelo de revisão visualy on canvas

=============================================================================

AWS::CloudFormation::Interface 
Syntax:  
Metadata:
  AWS::CloudFormation::Interface:
    ParameterGroups:
      - ParameterGroup 
    ParameterLabels:
      ParameterLAbel

Metadata:
  AWS::CloudFormation::Interface:
    ParameterGroups:
      - Label:
          default: "EC2 Instance Configuration"
        Parameters:
          - InstaceType 
          - KeyName 
      - Label:
          default: "Environment Configuration" 
        Prameters:
          - EnvironmentName 
    ParameterLabels:
      EnviromentName:
        default: "Wich enviroment we are planning to create?"    

Quando criamos ou atualizamos stacks em
no console, o console lista a entrada
parâmetros em ordem alfabética por
seus IDs lógicos.

Ao usar esta chave, podemos definir nosso
próprio agrupamento de parâmetros e pedidos
para que os usuários possam especificar com eficiência
valores de parâmetros.

Também podemos definir labels para
parâmetros.

Uma label é um nome amigável ou
Descrição que o console exibe
em vez do ID lógico de um parâmetro
o que ajuda os usuários a entender o
valores a serem especificados para cada parâmetro.