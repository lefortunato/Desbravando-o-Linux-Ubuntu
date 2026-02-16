# 


<div align="center">
  
# 🛡️ Desbravando o Linux Ubuntu

![Status](https://img.shields.io/badge/Status-Concluído-success)
![Metodologia](https://img.shields.io/badge/Metodologia-Ethical%20Hacking-blue)
![Nível](https://img.shields.io/badge/Nível-Iniciante%20/%20Intermediário-yellow)

</div>

---

## 📋 Sumário
* [🎯 Objetivo deste tópico](#-objetivo-deste-tópico)
* [⚙️ Detalhes da Instalação e Versões](#-objetivo-deste-t%C3%B3pico)
* [🛠️ Configuração do Ambiente](#%EF%B8%8F--configura%C3%A7%C3%A3o-do-ambiente)
* [🛠️ Criando uma máquina virtual com Linux Ubuntu na AWS](#%EF%B8%8F-criando-uma-m%C3%A1quina-virtual-com-linux-ubuntu-na-aws) 
* [🛠️ Simulando acesso remoto do windows na máquina virtual do VirtualBox](#%EF%B8%8F-simulando-acesso-remoto-do-windows-na-m%C3%A1quina-virtual-do-virtualbox)
* [🛠️ Simulando acesso remoto do windows na máquina virtual da AWS](#%EF%B8%8F-simulando-acesso-remoto-do-windows-na-m%C3%A1quina-virtual-da-aws)
* [🛠️ Trabalhando com arquivos](#%EF%B8%8F-simulando-acesso-remoto-do-windows-na-m%C3%A1quina-virtual-da-aws) 
  
* [🔗 Como Contribuir / Contato](#-como-contribuir--contato)

---

## 🎯 Objetivo deste tópico

Abordarei funcinalidades básicas para utilizar o SO Linux Ubuntu, entre instalação, preparação de ambiente virtualizado, acesso remoto e comandos

> ⚠️ **Disclaimer:** Este projeto foi realizado estritamente em um ambiente de laboratório isolado, utilizando máquinas virtuais propositalmente vulneráveis (Metasploitable 2 e DVWA), com o único propósito de aprendizado e auditoria de segurança.

## ⚙️ Detalhes da Instalação e Versões

| Ferramenta | Link | Versão Utilizada
| :---: | :---: | :---: |
| VirtualBox	| https://download.virtualbox.org/virtualbox/7.2.2/VirtualBox-7.2.2-170484-Win.exe |	7.2.2
| Linux Ubuntu	| https://ubuntu.com/download/server/thank-you?version=20.04.6&architecture=amd64&lts=true | 20.04.6 LTS
| Putty	| https://the.earth.li/~sgtatham/putty/latest/w64/putty.exe |	64-bit x86
| PuttyGen	| https://the.earth.li/~sgtatham/putty/latest/w64/puttygen.exe | 64-bit x86

## 🛠️  Configuração do Ambiente

1. **Instalação do VirtualBox -** A instalação é bem simples, no meu caso, segui com as opções padrões até a finalização.
2. **Configurações iniciais para uso da virtualização -** Precisamos seguir os passos antes da instalação da ISO:
   </br></br>
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2.1. **Abra o CMD em modo admistrador -** No CMD digite o seguinte comando `BCDEDIT` e clique em enter. </br></br>
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2.2. **Verifique o item hypervisorlauchtype -** Verique se o item está como `off`, se não estiver, digite o seguinte comando para deixá-lo, `BCDEDIT /SET hypervisorlauchtype OFF`. O objetivo é desabilitá-lo para permitir a criação de máquina virtual. Observe a imagem abaixo. </br></br>

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Preparação do ambiente]
    </summary>
    <img src="images/img2.png" alt="preparação do ambiente" width="600">
  </details>
</div>

   
3. **Baixando o ISO do Linux Ubuntu -** Baixe o ISO para, posteriormente, fazendo a instalação no VirtualBox. (Link no item `Detalhes da Instalação e Versões`)
4. **Instalando o ISO no VirtualBox -** Com o VirtualBox aberto, clique no botão New(novo), escolha um nome para a imagem e selecione o arquivo ISO apontando para o diretório onde foi feito o download. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Configuração da ISO]
    </summary>
    <img src="images/img1.png" alt="Configuração da ISO" width="600">
  </details>
</div>
 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4.1. **Tamanho da Memória -** Neste item mantenha o tamanho de 1024 mb.  </br></br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4.2. **Criar disco rígido virtual -** Neste item mantenha o tamanho do disco em 20 gb. Depois disso clique em `criar`.  </br></br>
  
5. **Configuração de rede -** Com a máquina virtual criada, vá em `configurações` e selecione o item `rede`. Faça as configurações conforme imagem abaixo:

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Configuração de rede]
    </summary>
    <img src="images/img3.png" alt="Configuração de rede" width="600">
  </details>
</div>

6. **Subindo a máquina virtual -** Clique em `Iniciar` para subir a máquina e começarmos a instação / configuração do SO.
7. **Configuração do Sistema Operacional Linux Ubuntu -** Siga os passos abaixo: </br>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7.1 **Configuração de Idioma -** Selecione o idioma Português. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Configuração do Idioma]
    </summary>
    <img src="images/img4.png" alt="Configuração do Idioma" width="600">
  </details>
</div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7.2 **Proximo passo -** Selecione a opção `Continue without updating`. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Configuração do SO]
    </summary>
    <img src="images/img5.png" alt="Configuração do SO" width="600">
  </details>
</div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7.3 **Configuração de Teclado -** Em `Layout`, selecione a opção `Portuguese (Brazil)`, depois selecione `Concluído` e aperte enter. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Configuração do teclado]
    </summary>
    <img src="images/img6.png" alt="Configuração do teclado" width="600">
  </details>
</div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7.4 **Definição de rede -** Neste ponto não faremos nada, apenas selecione `Concluído` e aperte enter.  </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7.5 **Definição de proxy -** Neste ponto não faremos nada, apenas selecione `Concluído` e aperte enter.  </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7.6 **Definição de Servidor Espelho -** Neste ponto não faremos nada, apenas selecione `Concluído` e aperte enter.  </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7.7 **Definição de Disco Virtual -** Neste ponto não faremos nada, apenas selecione `Concluído` e aperte enter.  </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7.8 **Definição de Partição -** Neste ponto não faremos nada, apenas selecione `Concluído` e aperte enter.  </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 7.9 **Finalizando Instalação -** Selecione o item `Continue` e aperte enter. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Concluindo instalação]
    </summary>
    <img src="images/img7.png" alt="Concluindo instalação" width="600">
  </details>
</div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8.0 **Definindo Usuário do sistema -** Defina conforme abaixo: </br></br> 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8.0.1 **Your Name -** Insira seu nome. </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8.0.2 **Your server's name -** Insira um nome para o servidor. </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8.0.3 **Pick a username -** Insira um usuário. </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8.0.4 **Chosse a password -** Insira uma senha. </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8.0.5 **Confirm your password -** Confirme a senha. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Configuração de usuário]
    </summary>
    <img src="images/img8.png" alt="Configuração de usuário" width="600">
  </details>
</div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8.1 **Definição de Token -** Neste ponto não faremos nada, apenas selecione `Concluído` e aperte enter.  </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8.2 **Definição de Token -** Neste ponto não faremos nada, apenas selecione `Concluído` e aperte enter.  </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8.3 **Instalação do OpenSSH -** Neste ponto não faremos nada, apenas selecione `Concluído` e aperte enter.  </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 8.4 **Instalação de serviços -** Neste ponto não faremos nada, apenas selecione `Concluído` e aperte enter.  </br></br>

8. **Concluíndo a Instalação -** A partir deste ponto a instalação iniciará e devemos aguardar a conclusão. Quando finalizar, selecione `Reboot Now` e aperte enter. Observe a imagem abaixo. 

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Conclusão da instalação]
    </summary>
    <img src="images/img9.png" alt="Conclusão da instalação" width="600">
  </details>
</div>

9. **Subindo a máquina virtual -** Depois de subir a máquina virtual, digite o usuário e senha que foram criados no item `8.0`, e aperte enter. Observe a imagem abaixo. 

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Subindo MV]
    </summary>
    <img src="images/img10.png" alt="Subindo MV" width="600">
  </details>
</div>

10. **Verificando SO ativo -** Após digitar o usuário e senha, verifique se realmente está no sistema operacional. Na linha de comando deve aparecer `nome-usuário@nomeservidor`. Observe a imagem abaixo. 

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Sistema Operacional ativo]
    </summary>
    <img src="images/img11.png" alt="Sistema Operacional ativo" width="600">
  </details>
</div>

## 🛠️ Criando uma máquina virtual com Linux Ubuntu na AWS

> ⚠️ **Observação:** Para seguirmos com este passo, é necessário ter uma conta na AWS. Não abordarei este tópico e considerarei que vc já tenha uma conta para seguirmos com a criação da máquina virtual.

1. **Serviço EC2 da AWS-** No serviço EC2 é onde criaremos nossa máquina virtual. Na barra de pesquisa, digite `EC2`, quando aparecer a opção, clique para acessar o ambiente.  Observe a imagem abaixo. 

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Pesquisando o EC2]
    </summary>
    <img src="images/img12.png" alt="Pesquisando o EC2" width="600">
  </details>
</div>

2. **Serviço EC2 da AWS-** Clique em `Executar instância`.  Observe a imagem abaixo. 

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Acessando o EC2]
    </summary>
    <img src="images/img13.png" alt="Acessando o EC2" width="600">
  </details>
</div>

3. **Serviço EC2 da AWS-** Digite o nome da máquina virtual no campo `Nome` e selecione o Sistema Operacional.  Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Configurando a MV no EC2]
    </summary>
    <img src="images/img14.png" alt="Configurando a MV no EC2" width="600">
  </details>
</div>

4. **Serviço EC2 da AWS-** No item `Par de chaves (Login)` clique em `Criar novo par de chaves`.  Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Configurando a MV no EC2]
    </summary>
    <img src="images/img15.png" alt="Configurando a MV no EC2" width="600">
  </details>
</div>

5. **Serviço EC2 da AWS-** No campo `Nome do par de cahves`, de um nome e clique em `Criar par de chaves`.  Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Configurando par de chaves]
    </summary>
    <img src="images/img16.png" alt="Configurando par de chaves" width="600">
  </details>
</div>

6. **Serviço EC2 da AWS-** Após o clique em `Criar par de chaves`, será feito automaticamente um download do `nomedoarquivo.pem`. Este arquivo usaremo posteriormente para realizar acesso remoto.
7. **Serviço EC2 da AWS-** Para finalizar, clique em `Executar Instância`. Ao final, teremos a criação finalizara, depois disso clique no botão `Visualizar todas as instâncias`. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Verificando instância criada]
    </summary>
    <img src="images/img17.png" alt="Verificando instância criada" width="600">
  </details>
</div>

8. **Serviço EC2 da AWS-** Agora devemos ter a instância de uma máquina virtual rodando com o Linux Ubuntu. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Instância em execução]
    </summary>
    <img src="images/img18.png" alt="Instância em execução" width="600">
  </details>
</div>

## 🛠️ Simulando acesso remoto do windows na máquina virtual do VirtualBox.

> Criamos 2 maquinas virtuais roando o Linux Ubuntu, uma no VirtualBox e uma na AWS. A partir de agora vamos simular acesso remoto de uma máquina Windows em ambas máquinas virtuais.

1. **Passo 1 -** Suba a imagem do Linux Ubuntu no VirtualBox para simular um servidor remoto. Em seguida, usaremos o Windows para acessar essa máquina virtual como se estivéssemos nos conectando a um computador em outro local. </br>
2. **Passo 2 -** Com o SO ativo, na linha de comando digite `ip a`, para listar os dados da rede ao qual a imagem está conectada. Precisaremos da informação do IP para realizar o acesso remoto. Precisado do ip localizado no `inet`, abaixo do item `enp0s3`, Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Ip da rede da Máquina Virtual]
    </summary>
    <img src="images/img19.png" alt="Ip da rede da Máquina Virtual" width="600">
  </details>
</div>

3. **Passo 3 -** Execute o putty.exe (Link no item `Detalhes da Instalação e Versões`), digite no campo `Host Name (or IP address)` o IP da máquina virtual, listado no passo anterior.  Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Executando o Putty]
    </summary>
    <img src="images/img20.png" alt="Executando o Putty" width="600">
  </details>
</div>

4. **Passo 4 -** É possível que ocorra um erro de `Conexão recusada`, caso isso aconteça, será necessário instalarmos o SSH na imagem do Linux Ubuntu e executarmos uma série de comando. 
  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3.1 **Instalando o SSH na imagem do Linux** - no prompt de comando, digite o comando abaixo:
  ```bash
  sudo apt-get install openssh-server
  ```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3.2 **Instalando o SSH na imagem do Linux** - Será solicitado a senha para seguir com a instalação. Após colocar a senha, ele pedirá a confirmação para seguir com a instalação. Confirme e tecle enter. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Instalando o SSh]
    </summary>
    <img src="images/img21.png" alt="Instalando o SSh" width="600">
  </details>
</div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3.2 **Verifique se o serviço está rodando -** Digite o comando abaixo:
  ```bash
sudo systemctl status ssh
  ```
Se aparecer `active (running)`, o serviço está pronto.

Se aparecer `inactive` ou `dead`, execute os comandos abaixo.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3.3 **Inicie e habilite o serviço -** Digite o comando abaixo:
  ```bash
sudo systemctl start ssh
sudo systemctl enable ssh
  ```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3.4 **Confirme a porta de escuta -** Para ter certeza absoluta que o Linux está ouvindo na porta 22, use:
  ```bash
ss -tlpn | grep :22
  ```
Deve aparecer uma linha indicando que o processo sshd está em LISTEN

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3.5 **Force a execução do serviço -**  No terminal do seu Ubuntu, execute o comando para forçar o início do serviço:
  ```bash
sudo systemctl start ssh
  ```
Após executar o comando acima, valide se ele subiu com:
  ```bash
sudo systemctl status ssh
  ```
O que observar: O campo Active deve mudar de inactive `dead` para active `running` em verde.

5. **Passo 5 -** Execute o putty.exe (Link no item `Detalhes da Instalação e Versões`), digite no campo `Host Name (or IP address)` o IP da máquina virtual. Clique em `Accept`. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Acesso Remoto]
    </summary>
    <img src="images/img22.png" alt="Acesso Remoto" width="600">
  </details>
</div>

6. **Passo 6 -** Agora ele vai pedir o usuário e senha. A partir deste ponto, estaremos conectados remotamente na máquinha com o SO Linux. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Acesso Remoto]
    </summary>
    <img src="images/img23.png" alt="Acesso Remoto" width="600">
  </details>
</div>

## 🛠️ Simulando acesso remoto do windows na máquina virtual da AWS.

1. **Passo 1 -** Neste instante, precisaremos executar o `PuttyGen`. Clique no botão `Load` e selecione o arquivo `.pem` com a chave que criamos no passo da criação da máquina virtual na AWS. Após carregar, clique no botão `Save private key`, neste momento ele criará um arquivo com a extensão  `.ppk`. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Convertendo arquivo com a chave de acesso]
    </summary>
    <img src="images/img24.png" alt="Convertendo arquivo com a chave de acesso" width="600">
  </details>
</div>

2. **Passo 2 -** Agora vamos atribuir esse arquivo `.ppk` no putty para realizar o acesso remoto. Na arvore, clique na opção `Connection / SSH / Auth`, procure pelo campo `Private key file for authentication`, e carregue o arquivo `.ppk` gerado no passo anterior.  Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Carregando a chave .PPK no Putty]
    </summary>
    <img src="images/img25.png" alt="Carregando a chave .PPK no Putty" width="600">
  </details>
</div>

3. **Passo 3 -** Agora vamos pegar o IP da máquina virtual na AWS.  Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [IP da MV AWS]
    </summary>
    <img src="images/img26.png" alt="IP da MV AWS" width="600">
  </details>
</div>

4. **Passo 4 -** Inclua o endereço IP no putty e clique em `Open`.  Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Conexão via putty]
    </summary>
    <img src="images/img27.png" alt="Conexão via putty" width="600">
  </details>
</div>

5. **Passo 5 -** Agora finalizaremos a conexão. Neste momento ele irá pedir o usuário, que na AWS ele cria por padrão o usuário `Open`. Como a chave foi importada, não há necessidade de digitar senha.  Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Conexão realizada]
    </summary>
    <img src="images/img28.png" alt="Conexão realizada" width="600">
  </details>
</div>

6. **Passo 6 -** Neste ponto mostra a interface do ubuntu e podemos digitar comandos unix para teste.  Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Interface Ubuntu]
    </summary>
    <img src="images/img29.png" alt="Interface Ubuntu" width="600">
  </details>
</div>

## 🛠️ Trabalhando com arquivos.
> Neste tópico abordarei a utilização de comandos unix. Todos os comandos serão realizados na interface de acesso remoto do putty. Para isso, carrege a imagem no VirtualBox, pegue o IP e acesse remotamente via Putty.

## 🐧 Comandos Essenciais do Terminal Linux

| Comando | Descrição | Exemplo
| :---: | :---: | :---: |
| ls	  | Lista arquivos e diretórios  	            | ls -la
| cd	  | Navega entre pastas	                      | cd documentos/projetos
| pwd	  | Exibe o caminho do diretório atual	      | pwd
| mkdir	| Cria um novo diretório (pasta)	          | mkdir nova_pasta
| touch	| Cria um arquivo vazio	                    | touch index.html
| rm	  | Remove arquivos ou diretórios	            | rm -rf pasta_antiga
| cp	  | Copia arquivos ou diretórios	            | cp arquivo.txt copia.txt
| mv	  | Move ou renomeia arquivos/pastas	        | mv antigo.txt novo.txt
| cat	  | Exibe o conteúdo de um arquivo	          | cat script.py
| grep	| Filtra textos dentro de arquivos	        | grep "erro" log.txt
| chmod	| Altera permissões de acesso	              | chmod +x script.sh
| sudo	| Executa comandos com privilégios de admin | sudo apt update

## 🐧 Comandos Linux: Variações e Atalhos Úteis

| Comando | O que faz (Variação) | Exemplo Prático
| :---: | :---: | :---: |
| cd         | olta para a pasta pessoal (Home)                      | cd ~
| cd         | olta para o diretório raiz do sistema                 | cd /
| cd         | olta para o diretório anterior (atalho)               | cd -
| ls -R      | ista arquivos recursivamente (pastas e subpastas)     | ls -R
| ls -lh     | Lista tamanhos de arquivos de forma legível (MB, GB)  | ls -lh
| mkdir -p   | Cria uma estrutura de pastas aninhadas de uma vez     | mkdir -p src/assets/images
| rm -rf     | Remove uma pasta e tudo que tem dentro (Cuidado!)     | rm -rf node_modules/
| cp -r      | Copia uma pasta inteira e seu conteúdo                | cp -r pasta_origem/ destino/
| tail -f    | Monitora um arquivo de log em tempo real              | tail -f logs/access.log
| grep -i    | Busca texto ignorando letras maiúsculas/minúsculas    | grep -i "erro" log.txt
| find       | Procura arquivos por nome em qualquer lugar           | find . -name "*.js"
| df -h      | Mostra o espaço livre em disco de forma legível       | df -h
| top / htop | Mostra processos e consumo de RAM/CPU no momento      | htop

## 🚀 Atalhos de Produtividade (Bônus)
Além dos comandos, vale mencionar estes atalhos de teclado que todo mundo usa:
| Atalho | O que faz (Variação) |
| :---: | :---: | 
| Tab | Autocompleta o nome de arquivos e pastas (O melhor amigo do dev) 
| Ctrl + C | Interrompe um comando que está sendo executado
| Ctrl + L | Limpa a tela do terminal (equivalente ao comando clear)
| history | Mostra todos os últimos comandos que você digitou

## 🔐 Gerenciamento de Permissões (chmod)

As permissões são divididas em Dono, Grupo e Outros. Cada ação tem um valor:
4 (Leitura - r)
2 (Escrita - w)
1 (Execução - x)

| Comando | O que faz | Exemplo Prático
| :---: | :---: | :---: |
| chmod 777	| Permissão total para todos (Leitura/Escrita/Execução)	  | chmod 777 script.sh
| chmod 755	| Dono pode tudo; outros apenas leem e executam	          | chmod 755 public_html/
| chmod 644	| Dono lê/escreve; outros apenas leem (Padrão arquivos)	  | chmod 644 config.txt
| chmod +x	| Torna um arquivo executável (atalho rápido)	            | chmod +x deploy.sh
| chown	    | Altera o dono do arquivo ou pasta	                      | sudo chown usuario:usuario index.html

> ⚠️ **Disclaimer:** Tenha muito cuidado ao usar rm -rf ou chmod 777 em diretórios raiz (/), pois isso pode comprometer a estabilidade do seu sistema.

## ⚡ Dicas de Ouro (Shortcuts & Tricks)

| Comando	| Descrição da "Mágica" | Por que usar?
| :---: | :---: | :---: |
| !!	      | Executa o último comando digitado	                   | Esqueceu o sudo? Digite sudo !!
| ctrl + r	| Pesquisa no histórico de comandos	                   | Para achar aquele comando complexo de ontem
| grep -r	  | Busca uma palavra em TODOS os arquivos da pasta	     | grep -r "API_KEY"
| alias	    | Cria um apelido para um comando longo	               | alias gs='git status'
| watch	    | Executa um comando repetidamente a cada X segundos   | watch -n 1 date
| du -sh *	| Mostra o tamanho de cada pasta no diretório atual	   | Ótimo para limpar disco cheio

## 🔐 Liberando acesso remoto do usuário root
> Agora vou realizar o procedimento para permitir que o usuário `ROOT` possa acessar remotamente a imagem do SO.

1) No prompt de comando, vamos acessar o arquivo onde ficam as configurações de usuário e é lá que precisamos habilitar o usuáro ROOT para fazer acesso remoto. Digite o comando:
  ```bash
sudo nano /etc/ssh/sshd_config
  ```
 Neste caso, usaremos o editor chamado `NANO`, que já vem instalado no Ubuntu. O comando `cat`, abre um arquivo texto e permite a visualização de seu conteúdo, porém não permite a edição. </br>
 E para realizarmos a edição no arquivo, precisamos digidar o `sudo` antes, caso contrário o arquivo não permitirá ser editado.

2) Localize a linha com este trecho `#PermitRootLogin prohibit-password`.  Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Liberando acesso remoto do usuário Root]
    </summary>
    <img src="images/img30.png" alt="Liberando acesso remoto do usuário Root" width="600">
  </details>
</div>

3) Altera o conteúdo da linha para `PermitRootLogin yes`. Agora salve com o comando `ctrl + o (Write out)`. Confirme o nome do arquivo com `Enter` e `ctrl + x` para sair do arquivo. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Liberando acesso remoto do usuário Root]
    </summary>
    <img src="images/img31.png" alt="Liberando acesso remoto do usuário Root" width="600">
  </details>
</div>

4) Agora precisaremos reiniciar o serviço `ssh`, para que as alterações replitam. Digite o comando abaixo:
  ```bash
sudo systemctl restart sshd
  ```
5) Abra uma nova sessão do putty e agora digite o usuário `root` e a senha. A partir de agora, estaremos com o usuário `root` fazendo acesso remoto. 

## 👤 Trabalhando com Usuários
> Agora apresentar comandos para manipular usuários.

1. **Criando e excluindo usuários**

| Comando/Caminho | Descrição | Exemplo de Uso |
| :--- | :--- | :--- |
| useradd        | Cria um novo usuário no sistema.                                 | sudo useradd -m novo_usuario |
| passwd         | Altera a senha de um usuário.                                    | sudo passwd novo_usuario |
| usermod        | Modifica as propriedades de um usuário.                          | sudo usermod -aG sudo usuario |
| userdel        | Remove um usuário do sistema.                                    | sudo userdel -r usuario |
| id             | Exibe UID, GID e grupos do usuário.                              | id usuario |
| whoami         | Mostra o nome do usuário logado.                                 | whoami |
| /home          | Diretório raiz onde ficam as pastas pessoais de cada usuário.    | ls /home |
| userdel	       |  Remove um usuário do sistema.	                                  | sudo userdel joao
| userdel --help | Exibe o menu de ajuda do comando userdel.	                      | userdel --help
| userdel -r	   | Remove o usuário e deleta seu diretório home e arquivos.	        | sudo userdel -r joao
| userdel -rf	   | Remove o usuário e diretório de forma forçada (mesmo se logado). |	sudo userdel -rf joao
| useradd --help | Exibe o menu de ajuda do comando useradd.	                      | useradd --help
| su	           | Alterna para outro usuário (Switch User).	                      | su joao


**Exemplo prático:** </br></br>
O comando completo useradd `joao -m -c "João da Silva" -s /bin/bash` faz o seguinte: </br>

`useradd joao`: Cria o usuário com o nome de login "joao". </br>
`-m`: Cria automaticamente o diretório pessoal (home) do usuário em /home/joao. </br>
`-c "João da Silva"`: Adiciona um comentário ao cadastro, geralmente usado para o nome completo do usuário. </br>
`-s /bin/bash`: Define qual interpretador de comandos (shell) o usuário usará ao logar, neste caso, o Bash. </br>

Os comandos seguintes: </br>

`passwd joao`: Define uma senha para a conta recém-criada (o sistema pedirá para digitar e confirmar a senha).</br>
`su joao`: Abre uma sessão no terminal como o usuário "joao" (solicitará a senha dele).</br></br>

> Nota sobre a pasta /home:
No Unix/Linux, o diretório /home é o local centralizado onde o sistema armazena os dados, configurações e documentos de cada usuário comum (ex: /home/joao, /home/maria). É o espaço privado de cada conta.


2. **Editando informações do usuários**

O usermod é a ferramenta "canivete suíço" para essas alterações. </br>
Aqui está a tabela focada em edição, seguida pela explicação detalhada dos comandos.

| Comando/Caminho | Descrição | Exemplo de Uso |
| :--- | :--- | :--- |
| usermod -l | Altera o nome de login (login name) do usuário.	  | sudo usermod -l novo_nome guest
| usermod -c | Altera o comentário/nome real do usuário.	      | sudo usermod -c "Novo Nome" guest
| usermod -s | Altera o shell padrão do usuário.	              | sudo usermod -s /bin/sh guest
| usermod -e | Define ou altera a data de expiração da conta.	  | sudo usermod -e 2026-12-31 guest
| usermod -L | Bloqueia (Lock) a conta do usuário.	              | sudo usermod -L guest
| usermod -U | Desbloqueia (Unlock) a conta do usuário.	          | sudo usermod -U guest
| chage -M	 | Define o número máximo de dias que uma senha vale. | sudo chage -M 90 guest


**Explicação dos Comandos:** </br></br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2.1. **O que é o parâmetro -e?** </br>
O -e (de expire) define uma data de validade para a conta. No exemplo useradd guest ... -e 25/03/2026, a conta do usuário "guest" será desativada automaticamente após essa data. É muito útil para funcionários temporários ou estagiários.

> Nota técnica: O formato da data depende da sua distribuição, mas o padrão Unix mais comum é AAAA-MM-DD.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2.2. **usermod guest -s /bin/bash** </br>
Este comando altera o shell padrão do usuário "guest" para o Bash. Se o usuário estava usando um shell mais simples (como o sh), agora ele terá acesso aos recursos avançados do Bash ao abrir o terminal.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2.3. **passwd guest -e** </br>
Aqui o -e significa expire aplicado à senha. Este comando força o usuário "guest" a alterar a senha obrigatoriamente no próximo login. É uma excelente prática de segurança após criar uma senha inicial padrão para alguém.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2.4. **cat /etc/passwd** </br>
Este comando exibe o conteúdo do arquivo /etc/passwd. Esse arquivo é o "banco de dados" de texto do sistema onde ficam armazenadas as informações de todos os usuários (nome, UID, diretório home, shell, etc.). </br>

Cada linha representa um usuário, e esta é a melhor forma de verificar se o seu comando useradd funcionou corretamente. </br></br>

Exemplo Prático de Verificação:
Após rodar seus comandos, você pode filtrar o arquivo passwd para ver apenas o "guest":
  ```bash
grep "guest" /etc/passwd
  ```


## 🔗 **Como Contribuir / Contato**</br></br>
Este projeto foi desenvolvido como parte de um desafio prático de segurança cibernética. Sinta-se à vontade para explorá-lo, cloná-lo e adaptá-lo!

| Botão | Ação |
| :--- | :--- |
| ⭐ Dar Estrela | Se gostou do projeto, considere dar uma estrela no GitHub. |
| 🤝 Conecte-se | **<img src="https://img.shields.io/badge/-LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white" alt="Link para o LinkedIn" align="center"> <a href="https://www.linkedin.com/in/leandro-antonio-fortunato/" target="_blank">  Visite meu linkedin</a>**  |
| 📧 Fale Comigo | 📧 [E-mail para contato](mailto:leandroantonio.fortunato@hotmail.com) |

