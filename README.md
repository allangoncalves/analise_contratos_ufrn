## Análise dos Contratos entre a UFRN e Pessoas Jurídicas
Retiramos nossos dados do [Portal de Dados Abertos da UFRN](http://dados.ufrn.br/) e do [Portal da Transparência](http://www.portaltransparencia.gov.br/) da Controladoria-Geral da União

Ao início da nossa análise, haviam algumas hipóteses que decidimos investigar. São elas:

1. Haveriam empresas criadas em um período próximo ao início do contrato.
2. Haveriam empresas cadastradas com um nome completamente diferente do informado ao Cadastrado na Receita Federal.
3. Acúmulo de empresas em um único endereço e/ou em endereços muito próximos.
4. Concentração de dinheiro em um endereço e/ou endereços muito próximos.

Em nosso [Dataset Inicial](http://dados.ufrn.br/dataset/815eb806-715e-4204-a67a-ca45f4b630f6/resource/c11863d5-c86f-44df-874d-33ac4d6ba7b5/download/contratos.csv), as únicas informações sobre as empresas eram o _CNPJ_ e o _Nome Empresarial_.
Sendo assim, necessitariamos de mais dados para validar nossas hipóteses.

Por possuir os CNPJs das empresas, pudemos fazer uma consulta direta ao ***Portal de Transparência*** para coletar informações como Endereço, Razão Social, Situação Cadastral e Quadro de Sócios.
Entretanto, o Portal não disponibiliza API para extração dos dados e tivemos que [raspar os dados](https://pt.wikipedia.org/wiki/Screen_scraping).

Para realizar o Web Scraping, utilizamos as bibliotecas [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) e [Requests](http://docs.python-requests.org/en/master/). Alguns desafios foram encontrados nessa etapa
devido a forma como a página/html é estruturada. O Portal não utiliza identificadores para seus campos e foi necessário criar uma logistica de extração.

Uma vez com o endereço das empresas, precisaríamos de suas geocoordenadas para poder criar as visualizações em formato de Mapas e consequentemente validar as Hipóteses 3 e 4.
Para coletar tais dados, utilizamos a API do Google [Geocoding](https://developers.google.com/maps/documentation/geocoding/start).

Foi necessário coletar mais alguns dados como ***demarcação do território das cidades*** mas infelizmente não foi encontrada nenhuma API que disponibilizava tais dados e o processo teve de ser manual.

> Para trabalhos futuros, planejamos investigar o quadro de sócio das empresas e tentar encontrar ligações em uma rede de pessoas.

#### Membros:
* [Ailson F. dos Santos](https://github.com/ailsonfds):
ailsonforte@hotmail.com
* [Allan Gonçalves](https://github.com/allangoncalves):
allangoncalves@outlook.com
(Análise, Coleta e Limpeza)
* [Cinthia Katiane](https://github.com/CinthiaKatiane):
cinthia.cka@gmail.com
(Análise e revisão)
* [Wellington Miguel](https://github.com/I-am-Miguel):
miguelwelligton@gmail.com

