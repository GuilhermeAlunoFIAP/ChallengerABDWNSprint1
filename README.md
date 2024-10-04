## Objetivo proposto pela OdontoPrev

Os alunos serão desafiados a criar soluções inovadoras focadas na 
redução de sinistros no setor odontológico. Especificamente, o desafio 
envolve o uso de análise preditiva para antecipar e mitigar situações de 
sinistro relacionadas aos atendimentos odontológicos.
O objetivo central é criar soluções que utilizem análise preditiva para 
reduzir sinistros.


## Escopo

A ideia é um app software de triagem de dados da consulta antes de realizar a marcação, onde é feito um relatório  
através da descrição do usuário e de uma imagem de seus dentes, e então uma análise que indica a porcentagem de  
necessidade de uma consulta odontológica, dessa forma auxiliariamos as clínicas na priorização dos atendimentos. 
Vale ressaltar que essa porcentagem não substitui a análise de um profissional da OdontoPrev, a ideia é que os 
profissionais da OdontoPrev irão priorizar e analisar os casos com maior porcentagem de "veracidade" do problema.


## Requisitos Funcionais 

- cadastro, atualização de dados e listagem dos clientes.
- cadastro, login e atualização de dados da clínica.
- cadastro, atualização de dados e listagem dos relatórios.

## Requisitos Não Funcionais

- A aplicação deve ser responsiva e fácil de usar.
- Garantir a segurança de dados dos usuários.


## Clean Architecture

O projeto considera a utilização de uma arquitetura limpa para separar responsabilidades, facilitando a manutenção
e o teste do código. No momento as camadas do projeto incluem Models e DTOs. A camada models contém as entidades
necessárias para o projeto e suas regras de negócio, e a camada DTOs contém as classes DTOs necessárias para isolar
a camada models, garantindo assim que não ocorra a exposição direta das entidades e manter o controle sobre quais
dados são transmitidos.

## Domínio 
As principais entidades do domínio incluem:

- **Clinica** representa as clínicas ondontológicas e seus atributos necessários.
- **Cliente** representa os pacientes e seus atributos necessários.
- **Relatorio** contém os detalhes sobre as consultas realizadas.
- **Endereco** armazena informações de endereços relacionadas as clinicas e aos clientes.

## Classes Implementadas

- **Clinica** contém os dados necessários da clínica, já sendo definido qual é [Required] e qual não é preciso ser
e apresenta as regras de negócio necessárias, sendo a que valida o cnpj através da função que considera apenas os 
números e verifica se o tamanho é o adequado, e a que valida o formato do email através do [EmailAddress]

- **Cliente** contém os dados do cliente, já definindo os que serão [Required] e valida o cpf considerando apenas
os números e verificando se tem o tamanho adequado.

- **Relatorio** Detalha as informações sobre a consulta.

- **Endereco** Gerencia os dados dos endereços, além disso, é feita a validação do cep, onde apenas os números são
considerados e é verificado se o tamanho está adequado ao padrão.

- **LoginDTO** essa classe foi criada para efetuar o login da clínica sem precisar manipular a entidade e todos seus
atributos.

- **ClienteDTO** criada para atualizar os dados dos cliente, e como tem dados que não podem ser alterados esse DTO
é para manipular apenas os dados necessários.

- **ClinicaDTO** criada para a listagem da clínica, esse DTO é usado para a segurança de dados, evitando manipular
a entidade e proteger dados como cnpj e senha.