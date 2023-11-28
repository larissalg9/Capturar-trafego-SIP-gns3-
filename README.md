#Capturar do trafego SIP com GNS3
Apresentação do projeto de Redes Convergentes referente a capturar tráfego SIP utilizando GNS3.

# Oque seria o SIP?

O protocolo SIP é utilizado em chamadas de voz sobre IP ou VoIP. Isso permite que dois usuários se conectem e realizem uma comunicação, através de dois dispositivos, e assim se realizar a comunicação através de uma rede IP.

# Topologia de uma rede com implementação de SIP

![image](https://github.com/larissalg9/Capturar-trafego-SIP-gns3-/assets/58262383/2f92713d-30c1-4e1d-a2e2-e4e30706d85e)

#Passo 1: Instalação do GNS3
Faça o download e instale o GNS3 no seu sistema operacional.
Execute o GNS3 e configure as opções básicas, como caminho do Dynagen, caminho do VirtualBox/Vmware, etc.

#Passo 2: Adição de Roteadores Virtuais#
No GNS3, adicione dois roteadores virtuais (por exemplo, Cisco Router c7200) ao seu projeto.
Conecte os roteadores usando links Ethernet e atribua endereços IP às interfaces conectadas.

#Passo 3: Adição de Máquinas Virtuais
Adicione duas máquinas virtuais (por exemplo, máquinas virtuais Linux) ao seu projeto.
Conecte as máquinas virtuais aos roteadores usando links Ethernet.

#Passo 4: Configuração de Servidor SIP
Instale um servidor SIP em uma das máquinas virtuais. Por exemplo, use o Asterisk ou FreeSWITCH.
Configure as contas SIP no servidor e assegure-se de que o serviço esteja em execução.

#Passo 5: Configuração de Captura de Tráfego
Adicione um servidor de captura ao projeto (por exemplo, Wireshark).
Conecte o servidor de captura a uma das interfaces do roteador ou diretamente à rede, dependendo da sua preferência.

#Passo 6: Configuração de Rotas
Configure as rotas nos roteadores para permitir a comunicação entre as máquinas virtuais e o servidor SIP.

#Passo 7: Inicialização e Testes

Antes de tudo é necessário a instalação de softwares para captura desse tráfico recomendamos o SNGREP e WIRESHARK, lembrando que isso deve fazer no local que deseja fazer a captura desse tráfico sendo uma máquina virtual ou no próprio servidor da URA.

# Como instalar sngrep?

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

# Como instalar o wireshark - 

$ sudo apt install wireshark

$ sudo dpkg-reconfigure wireshark-common

$ sudo usermod -aG wireshark (user)

Inicie o roteador, máquinas virtuais, servidor SIP e o servidor de captura.

Realize chamadas SIP entre as máquinas virtuais e monitore o tráfego SIP no servidor de captura.


LINK do PROJETO: 
