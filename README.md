# Digytal Code - Programação, Pesquisa e Educação
[www.digytal.com.br](http://www.digytal.com.br)

[(11) 95894-0362](https://api.whatsapp.com/send?phone=5511958940362)


#### Autores
- [Gleyson Sampaio](https://github.com/glysns)

## Conta Rural

![](contarual.png )

Uma grande instituição financeira resolveu promover uma competição para atrair estudantes e profissionais em tecnologia para assim selecionar os 05 que apresentarem uma solução mais aderente aos problemas que serão apresentados ao longo das fases e requisitos do projeto.

Trata-se de um produto que este banco pretende lançar no mercado que será conhecido como Conta Rural, uma conta para pessoas físicas e ou micro-empreendedores que não possuem tanto acesso à tecnologia e internet.

Os requisitos do projeto serão estruturados baseados em processos simples, que inicialmente não necessitarão de meios tecnológicos avançados, justamente para cada participante apresentar uma solução à baixo custo mais viável possível.

#### Itens de avaliação ao longo dos estudos
* Conhecimento e domínio aos fundamentos e recursos da linguagem escolhida
* Noções do paradígma da orientação a objetos e os pilares da P O O
* Compreensão quanto a leitura e escrita de documentos nos formatos: .json, .csv, .xls
* Interpretação de layouts de documentos como delimitado e posicional
* Engajamento com persistência de dados relacional de forma nativa ou utilizando algum framework ORM
* Configuração e controle de envio de e-mails
* Noções de arquitetura HTTP com base na linguagem e framework escolhido
* Conceito sobre níveis de maturidade dos recursos HTTP
* Prover os recursos da sua aplicação através de uma arquitetura REST
* Implementação de clientes HTTP
* Desenvolvimento de interfaces gráficas como desktop, web e mobile
* Integração entre aplicações

## Fase 01

Vamos iniciar o nosso MVP (Produto Mínimo Viável) considerando o seguinte aspecto:

Espera-se que através de visitas nos estabelecimentos rurais, o time de coleta de dados deverá através de preenchimento dos formulários impressos obter as seguintes informações:

1. Dados Pessoais: Nome, Data Nascimento, CPF/CNPJ, RG/I.E.,Renda Atual, Telefone, Celular, Email
1. Dados de Endereço: Cep, Logradouro, Numero, Bairro, Complemento, Municipio, Uf

> Nesta primeira etapa, devemos considerar a necessidade de explorar os conceitos da orientação a objetos, noções de UML e tipos de dados além da escrita e leitura em arquivos.

* [Anatomia de uma classe](https://www.youtube.com/watch?v=CrbSqRk9vw0&list=PL8NbPylKQ8NlRzFoqlC2iA1Dxcqvk7uSZ&index=12)
* [Sintaxe básica](https://sintaxe.netlify.app/topicos/linguagens/java/basico/sintaxe)
#### Fluxos do processo de coleta

1. Todos os consultores deverão entregar as suas fichas para o técnico realizar o processo de armazenamento dos dados (evite utilizar o console e ou Scanner, crie os objetos literalmente);
1. Os dados INICIALMENTE serão armazenados em um arquivo denominado de: **conta-rural-fichas-cadastrais.csv** (caso windows: c:\conta-rural, caso linux: /home/conta-rural);
1. Um arquivo csv contém suas colunas seperadas por ponto e vírgula ( ; );
1. A ordem das colunas para o arquivo csv será : Nome, Data Nascimento, CPF/CNPJ, RG/I.E., Renda Atual, Telefone, Celular, Email, Cep, Logradouro, Numero, Bairro, Complemento, Municipio, Uf
1. Após a coleta de todas as fichas e a atualização do arquivo conta-rural-fichas-cadastrais.csv através do sistema será necessário ler este arquivo para gerar um novo arquivo conforme especificações do BACEN. Ver requisitos do BACEN conforme abaixo:

#### Requisitos do BACEN

O BACEN solicitou para a nossa instituição financeira o envio dos cadastros coletados atráves de uma comunicação inicialmente por e-mail contendo em seu anexo o arquivo de nome **conta-rural-fichas-cadastrais-bacen.txt** conforme layout posicional abaixo:

INICIALMENTE o arquivo será gerado no diretório conforme descrição (caso windows: c:\conta-rural, caso linux: /home/conta-rural);

O envio de e-mail é de forma tradicional como um anexo em seu serviço de e-mail (simulação) onde o relevante é a geração do arquivo de forma consistente.

| Ordem | Campo        | Tamanho | Valor Originial - Inserido sem padrão                            | Valor Formatado (BACEN)          | Observação                                                                 |
|-------|--------------|---------|------------------------------------------------------------------|----------------------------------|----------------------------------------------------------------------------|
| 01    | Nome         | 30      | Raimundo Nonato Loureiro Castelo Branco                          | RAIMUNDO NONATO LOUREIRO CASTE   | Se o valor for superior ao tamanho máximo de caracteres, cortar o final do nome, caso inferior completar com espaços à esquerda|
| 02    | Data         | 08      | 16/04/1986                                                       | 19860416                         |                                                                            |
| 03    | CPF\CNPJ     | 14      | 135.217.791-18                                                   | 00013521779118                   |                                                                            |
| 04    | Renda Atual  | 10      | 1.275,48                                                         | 0000127548                       | Em caso não ter renda, preencher com 0000000000                            |
| 05    | Telefone     | 10      | (11) 3351-1010                                                   | 1133511010                       | Em caso não ter telefone, preecher com 10 espaços em braco                 |
| 06    | Celular      | 11      | (11) 94565-2353                                                  | 11945652353                      | Em caso não ter celular, preecher com 11 espaços em braco                  | 
| 07    | E-mail       | 70      | raimundo.nonato@gmail.com                                        | Garantir caracteres em mínúsculo | Se o valor for inferior completar com espaços à esquerda| 
| 08    | Lougradouro  | 60      | Ruas das laranjeiras                                             | RUAS DAS LARANJEIRAS             | Se o valor for superior ao tamanho máximo de caracteres, cortar o final do nome, caso inferior completar com espaços à esquerda | 
| 09    | Numero  | 5       | 123 ou S/N                                                             | 00123                          |Se for informar S/N preenhcer com com 00000 | 
| 10    | Bairro       | 30      | Vila Nazare                                                      | VILA NAZARE                      | Se o valor for superior ao tamanho máximo de caracteres, cortar o final do nome, caso inferior completar com espaços à esquerda | 
| 11    | Complemento  | 20      | Bl 03 ap 113                                                     | BL 03 AP 113                     | Se o valor for superior ao tamanho máximo de caracteres, cortar o final do nome, caso inferior completar com espaços à esquerda | 
| 12    | Cidade       | 50      | Teresina                                                         | TERESINA                         | Se o valor for superior ao tamanho máximo de caracteres, cortar o final do nome, caso inferior completar com espaços à esquerda | 
| 13    | Estado       | 2       | Pi                                                               | PI                               |  | 
| 14    | Cep       | 8       | 65.300-000                                                          | 65300000                         | Se não informar o cep preencher com 00000000 | 


No dia seguinte (D+1), o BACEN consturma disponibilizar o arquivo de retorno **conta-rural-fichas-cadastrais-bacen-YYYY-MM-DD.txt** onde Y=Ano, M=Mês, D=Dia com o mesmo layout do arquivo acima acrescentando três novas colunas que correspondem aos dados da conta: Numero da Agencia, Número da Conta e Data\Hora Abertura da Conta. Veja layout complementar abaixo:

| Ordem | Campo        | Tamanho | Valor Real  | Valor Formatado (BACEN)          | Observação                                                                 |
|-------|--------------|---------|------------------------------------------------------------------|----------------------------------|----------------------------------------------------------------------------|
| 15    | Número Agência | 06      | 623                          | 000623   | |
| 16    | Número Conta         | 08      | 19375                 | 00019375  |                                                                            |
| 17    | Data Hora Abertura     | 14   | 01/03/2023 16:27:37   | 20230301162737 |                     

Nota: Poderão surgir novas classes, novos atributos e novos relacionamentos entre as mesmas, é natural.

# Em breve novos desafios

![Aguarde](./thats-all.png)
