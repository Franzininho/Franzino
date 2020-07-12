Franzino


by Fábio Souza

![](./imagens/image5.jpg)

A placa Franzino é um Arduino standalone de baixo custo. Como seu próprio nome sugere, é uma placa enxuta que possui os componentes básicos para que você possa usar o microcontrolador ATmega328, tanto para estudo quanto para a aplicações em projetos.

Diferente dos standalones disponíveis no mercado, a placa Franzino possui pinagem Arduino UNO Rev 3 e conector para fácil ligação da interface serial. A facilidade de acesso aos pinos da interface serial, possibilita que você ligue módulos de comunicação conforme a necessidade do projeto. Você conseguirá facilmente ligar conversores de níveis seriais como: USB, RS232, RS485 e até mesmo um módulo Bluetooth, sem a necessidade do uso de shields.

A Franzino vem com o bootloader do Arduino UNO facilitando o processo de upload do seu scketch. Você poderá facilmente fazer o upload do seu sketch para placa usando um conversor USB/Serial, seguindo os mesmos passos que já está acostumado a fazer com a placa Arduino UNO.


## Características:

- Pinagem Padrão UNO R3
- Microcontrolador ATmega328P;
- Alimentação: 7,5 V a 20 V DC;
- Proteção contra inversão de polaridade da fonte;
- Conector para ligação de interface serial;
- LED para indicação de alimentação;
- LED conectado ao pino 13 para uso geral

A seguir é apresentada a pinagem para interface serial:

![](./imagens/image8.png)

Os pino D2 e D4 podem ser utilizados para uma comunicação soft serial, como pino de controle da comunicação RS485 ou outras aplicações de entrada ou saída.

Outra vantagem interessante é que as linhas de alimentação(VCC e GND) também estão disponíveis nesse conector.

Assim, com esse conector você pode facilmente ligar um  conversor USB/Serial para comunicação com um computador, seja para upload dos sketchs quanto para troca de informações.

![](./imagens/image10.jpg)

Se o seu projeto não necessitar da comunicação USB/Serial durante o seu funcionamento, você poderá usar o mesmo conversor para fazer upload em outra Franzinos.


Algumas aplicações necessitam de comunicação serial no padrão RS232. Dessa forma você pode ligar facilmente um conversor TTL/RS232.

![](./imagens/image15.png)

Também é comum aplicações que necessitem da comunicação RS485. Para isso você pode facilmente ligar um módulo conversor TTL/RS485:

![](./imagens/image2.png)

Outra aplicação interessante para comunicação e o uso de módulos Bluetooth. Esse tipo de módulo pode ser facilmente ligado a Franzino tanto para uso dos pinos padrões de comunicação TX e RX quanto para comunicação soft serial:

![](./imagens/image9.png)

Como observado acima, há muitas possibilidades de comunicações e você pode facilmente ligar outros módulos para diversas aplicações conforme sua necessidade.

## Limitações da Franzino

A Franzino é uma placa standalone que possui diversas vantagens. Porém como foi desenvolvida em face simples e com o mínimo de componente necessários para o uso do microcontrolador, possui algumas limitações em relação ao Arduino UNO, que são:

- Não há regulador 3,3 V, dessa forma o pino 3.3V não está conectado;
- O pino Vin não está conectado a alimentação;
- Os pinos SCL e SDA não estão conectados as pinos A4 e A5;
- Não possui conversor USB/Serial
- Precisa de um conversor USB/Serial para upload dos sketchs

## Alimentação

A Franzino pode ser alimentada das seguintes formas:

- Conector P4 com tensão de 7,5 V a 20 V como positivo no centro;
- Pino 5V e GND - tensão de alimentação fixa em 5 VDC
- Através nos pinos VCC e GND disponíveis conector de expansão serial;


### Atenção

Não LIGAR o VCC do conversor USB/SERIAL a placa se a fonte externa estiver ligada. Nesse caso ligar apenas os pinos DTR, RXI, TXO e GND.


## Blink com a Franzino

Upload via conversor USB/SERIAL

Para fazer o famoso blink com a Franzino, primeiro é necessário ligar o conversor USB/Serial a placa, como exibido na figura abaixo:

![](./imagens/image10.png)

Selecione na IDE do Arduino a Placa Arduino/Genuino UNO. Também selecione a porta COM que foi criada ao ser inserido o conversor USB/SERIAL:

![](./imagens/image13.png)

Faça o UPLOAD:

![](./imagens/image3.png)

## Gravando a Franzino com um placa Arduino UNO

Se você não possui um conversor USB/Serial você pode gravar a Franzino através de um Arduino. Para isso vamos configurar a placa Arduino UNO com programador.

Escolha a opção ArduinoISP, conforme figura abaixo:

![](./imagens/image17.png)

Faça o upload para a placa Arduino UNO que será usada como programador.

Feito o UPLOAD, agora vamos as conexões do Arduino UNO na Franzino:

- Ligue o pino RESET da FRANZINO ao pino 10 do Arduino
- Ligue o pino 11 da FRANZINO ao pino 11 do Arduino
- Ligue o pino 12 da FRANZINO ao pino 12 do Arduino
- Ligue o pino 13 da FRANZINO ao pino 13 do Arduino
- Ligue o pino 5V da FRANZINO no pino 5V do Arduino
- Ligue o pino GND da FRANZINO ao GND do Arduino

![](./imagens/image7.png)

## Configurando o avrdude ( se estiver usando o ATmega328 e não o ATmega328P)

A versão 0 da Franzino vem com o ATmega328-PU, dessa forma precisamos configurar o avrdude para gravar esse microcontrolador. Na pasta do arduino acesse: C:\arduino-1.6.8\hardware\tools\avr\etc, abra o arquivo avrdude.conf

Procure a assinatura do ATMEGA328P:

![](./imagens/image11.png)

Troque a assinatura por:

![](./imagens/image16.png)

Salve o arquivo.

Após a gravação, volte a assinatura para o valor original:  signature= 0x1e 0x95 0x0F;
UPLOAD de Sketchs usando a Arduino UNO

Pronto, agora abra o programa que será gravado na Franzino. Para esse exemplo vamos usar o exemplo Blink, mas você poderá fazer esse procedimento para gravar suas aplicações;

![](./imagens/image6.png)


Agora vamos preparar para gravação. Configure o Programador como ArduinoISP:


![](./imagens/image12.png)

Pronto, agora é só fazer o UPLOAD para a Franzino:

![](./imagens/image14.png)

## Esquema elétrico da placa

![](./imagens/image1.png)

## Layout

![](./imagens/image4.png)


Todos os arquivos de projeto estão disponíveis no Github: https://github.com/FBSeletronica/Franzino

### Referências

Artigo no Embarcados: https://www.embarcados.com.br/franzino-open-hardware-de-baixo-custo/

Arquivos no GITHUB:
https://github.com/FBSeletronica/Franzino




Controle de revisões do Manual

RV0 - primeiro documento
RV1 - inserido programação através do Arduino UNO
RV2 - Links
