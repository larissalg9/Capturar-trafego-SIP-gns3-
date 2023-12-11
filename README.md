# Capturar do trafego SIP com GNS3
Apresentação do projeto de Redes Convergentes referente a capturar tráfego SIP utilizando GNS3.

## :memo: Descrição
* <b>Oque seria o SIP?</b>:

O protocolo SIP é utilizado em chamadas de voz sobre IP ou VoIP. Isso permite que dois usuários se conectem e realizem uma comunicação, através de dois dispositivos, e assim se realizar a comunicação através de uma rede IP.

* <b>Topologia de uma rede com implementação de SIP</b>:

![image](https://github.com/larissalg9/Capturar-trafego-SIP-gns3-/assets/58262383/eeb90342-7758-463e-bce5-884fccc0f220)

# Passo 1: Download, Instalação e configuração do GNS3
  
Acesse o site oficial do GNS3 em https://www.gns3.com/.
Clique na opção "Download GNS3" no menu principal.

O GNS3 usa um software de virtualização como VirtualBox ou VMware para executar máquinas virtuais. Escolha um dos seguintes:

* Instalação do GNS3

Execute o instalador do GNS3 que você baixou no Passo 1.
Siga as instruções do assistente de instalação. Certifique-se de selecionar as opções para instalar o GNS3, o GNS3 VM e os componentes necessários.

* Configuração do GNS3 VM

Após a instalação do GNS3, inicie o aplicativo.
Vá para Edit -> Preferences -> GNS3 VM para configurar a VM.
Crie uma nova VM ou selecione uma existente. O assistente de configuração irá guiá-lo através do processo.

* Adição de Imagens de Roteadores

Faça o download das imagens do roteador que você planeja usar no GNS3. Estas podem ser imagens Cisco IOS, por exemplo.
Em Edit -> Preferences -> IOS Routers, adicione o caminho para as imagens do roteador.

* Configuração do Dynamips (Opcional)

Se estiver usando roteadores Cisco, você pode configurar o Dynamips para melhor desempenho:
Vá para Edit -> Preferences -> Dynamips.
Ajuste as configurações de memória e recursos de acordo com a capacidade do seu sistema.

Observaçãop importante: Conecte as máquinas virtuais aos roteadores usando links Ethernet.

# Passo 4: Configuração de Servidor SIP
  
Nessa atividade utilizaramos o servidor já criado na apresentação do projeto que utiliza as tecnologias FREEPBX e Asterisck.
Link da máquina virtual: https://www.freepbx.org/
Porém já possui a mesma pronta no LINK do PROJETO.

# Passo 5: Inicialização e Testes

Antes de tudo é necessário a instalação de softwares para captura desse tráfico recomendamos o SNGREP e WIRESHARK, lembrando que isso deve fazer no local que deseja fazer a captura desse tráfico sendo uma máquina virtual ou no próprio servidor da URA.
Nas máquinas virtuais no qual possui SoftFone, possui o Wireshark, e no servidor que roda o asterisk possui o SINGREP.

## :rocket: Como instalar sngrep?

```
$ sudo -i

$ cd /home/user/Downloads

$ wget https://github.com/irontec/sngrep/archive/master.zip

$ apt-get install unzip

$ unzip master.zip

$ cd sngrep-master/

$ ./bootstrap.sh

$ apt-get install autoconf

$ ./bootstrap.sh

$ apt-get install libpcap0.8-dev

$ apt-get install libncurses5-dev

$ ./configure

$ make

$ make install

$ sngrep

```

## :rocket: Como instalar o wireshark? 

```
$ sudo apt install wireshark

$ sudo dpkg-reconfigure wireshark-common

$ sudo usermod -aG wireshark (user)
```

Inicie o roteador, máquinas virtuais, e o servidor SIP e o servidor (máquina virtual) de captura.

Realize chamadas SIP entre as máquinas virtuais e monitore o tráfego SIP no servidor de captura.

## 🗂 LINK do PROJETO: 

https://drive.google.com/drive/folders/1iEToCL4f2Z52SSn85ITAC2oHOOJNUEBh?usp=sharing
