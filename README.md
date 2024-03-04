# Transmitter
Programa Transmitter para LNM
# Transmissor Online de Voo Virtual

## O que é "Transmissor Online de Voo Virtual"?

É um pequeno aplicativo do Windows que transmite sua posição no Microsoft Flight Simulator para um banco de dados online onde sua última posição relatada é mantida por 1 minuto.
O site então produz um arquivo formatado "whazzup" que pode ser usado pelo LittleNavMap para traçar posições de aeronaves ao vivo em um mapa.

## Por que?

Se você e seus amigos quiserem se ver em um software de mapeamento como o LittleNavMap para executar suas próprias sessões de controle de tráfego aéreo para voos em grupo,
você sem dúvida terá descoberto que o Microsoft Flight Simulator apenas comunica aeronaves de IA para aplicativos de mapeamento externos, como LittleNavMap - não para usuários.
O aplicativo Virtual Flight Online Transmitter resolve isso.

## Como funciona
O aplicativo de desktop se conecta a uma cópia em execução do Microsoft Flight Simulator por meio da interface SimConnect e lê a latitude, longitude, altitude e velocidade no ar da sua aeronave.
Ele combina os dados com seu indicativo digitado, tipo de aeronave e nome, e os envia para um servidor na internet através do "URL do servidor" inserido no aplicativo.
O servidor então fornece uma URL que exibe todas as aeronaves que foram atualizadas nos últimos 5 minutos no formato "whazzup" 
(um formato de dados comumente usado com empresas como VATSIM e IVAO - e principalmente LittleNavMap)
A URL do servidor pode ser usada para configurar o LittleNavMap para mostrar aeronaves para você e seus amigos no mapa.

## Executando o Programa
* Inicie o Microsoft Flight Simulator.
* Execute o "VirtualFlight.Online Transmitter".
* Preencha as caixas de texto para seu indicativo, tipo de aeronave, nome e nome do grupo
* Clique em Conectar

Após clicar em conectar, o aplicativo transmitirá sua localização dentro do simulador para a internet uma vez por segundo.

## Executando seu próprio servidor
O subdiretório /server contém os recursos necessários para criar seu próprio servidor. Você precisará de alguma experiência em servidores web MySQL e PHP
Um arquivo database.sql está incluído para criar o banco de dados apropriado para rastrear posições de aeronaves (usado por send.php e whazzup_ivao.php). O código deve ser autoexplicativo.
Lembre-se de que seus usuários também precisarão alterar a URL do servidor para refletir a localização de "send.php" do seu servidor.

## Configurando o LittleNavMap

Se você gostaria de ver todos transmitindo sua posição com o Virtual Flight Online Transmitter, siga estas etapas no LittleNavMap:

* Clique no menu Ferramentas
* Clique em Opções
* Selecione a seção Voo Online no painel Opções
* Escolha o botão de opção "Personalizado" na seção Voo Online
* Preencha o URL http://nome_do_seu_servidor/whazzup_ivao no campo URL
* Defina a taxa de atualização para algo sensato (por exemplo, 5 segundos)
* Certifique-se de que IVAO esteja escolhido no menu suspenso de formato
* Clique em Aplicar e OK

## Versâo: 10.1.16

O transmissor agora possui funcionalidade de número PIN - onde um número PIN pode ser definido no servidor e os clientes precisam inserir o número PIN para poder usar o servidor com sucesso. Isso ajudará os grupos privados a proteger seus servidores contra usuários indesejados.

## Fonte e créditos

https://github.com/jonbeckett/virtualflightonlinetransmitter
Autor: Jonathan Beckett
