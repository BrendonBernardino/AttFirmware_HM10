# AttFirmware_HM10

Se seu HM-10 não responde a comandos AT, possivelmente ele é um HM-10 clonado. (Provavelmente quando você tentar procurar o bluetooth, irá aparecer um nome diferente de HMSoft.)  Então será necessário a atualização de firmware para que ele se comporte como um HM-10 genuíno.
Para a atualização de firmware, será preciso o Arduino UNO(ou o Mini Pro) e o CC2541.

É necessário soldar fios no HM-10 para entao conectar aos pinos do Arduino, DEBUG_CLOCK, DEBUG_DATA, RESET_N.

**CONEXÕES**
------------------------

**DEBUG_CLOCK**

CC2541 – Pino 7

Arduino UNO – Pino 5

**DEBUG_DATA**

CC2541 – Pino 8

Arduino UNO – Pino 6

**RESET_N**

CC2541 – Pino 11 (RESETB)

Arduino UNO – Pino 4

Agora os pinos relacionados a alimentação:

**GND**

CC2541 – Pino 13

Arduino UNO – Pino GND

**3.3V**

CC2541 – Pino 12

Arduino UNO – Pino 3V3

------------------------

Você deve baixar a pasta que está nesse repositório. Nela contém 3 arquivos, o .bin, .ino e o .exe.
Então você deve abrir o .ino na sua IDE Arduino e configurar a porta COM, placa, programador e taxa de transmissão. Depois compile e grave na placa Arduino UNO

Agora realize as conexões do HM-10 com o Arduino UNO.

Agora iremos gravar o firmware para o CC2541. Para isso, deixe juntos na mesma pasta, os 3 arquivos que foram baixados.
Abra o prompt de comando (aperte Windows+R e depois Enter).
Pelo prompt de comando, vá até onde o CCLoader.exe está localizado.
Então escreva e execute:

**CCLoader.exe [COM Port]** **[Firmware.bin]** **[Arduino Type]**

Legenda:

[COM Port] = 2 ou 3 ou 4 ou 5 ... (Não digite a palavra ‘COM’, apenas o numero da porta)
  
[Firmware.bin] = CC2541hm10v540.bin
  
[Arduino Type] = 0 ou 1 (Se o seu for o Arduino UNO, então é 0. Se for o Arduino Mini Pro, então é 1)

Um exemplo: (Se minha porta COM é a 5 e o meu Arduino é o UNO)
  
## **CCLoader.exe 5 CC2541hm10v540.bin 0**
  
Pronto, o firmware foi instalado.
  
O que irá aparecer no seu prompt de comando deve ser algo similar a imagem abaixo:
  
![image](https://user-images.githubusercontent.com/47569587/133661375-14f3b297-bdd6-4c05-a387-3f87065d0d5d.png)

Após o update do firmware, o nome do dispositivo ao ser buscado deve ser HMSoft.

  
Para mais detalhes, consulte este link: https://capsistema.com.br/index.php/2021/02/02/guia-de-como-atualizar-o-firmware-no-modulo-clone-hm-10-ble-usando-o-arduino-uno/
