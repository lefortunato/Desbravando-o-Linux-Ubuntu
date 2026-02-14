# 


<div align="center">
  
# 🛡️ Desbravando o Linux Ubuntu

![Status](https://img.shields.io/badge/Status-Concluído-success)
![Metodologia](https://img.shields.io/badge/Metodologia-Ethical%20Hacking-blue)
![Nível](https://img.shields.io/badge/Nível-Iniciante%20/%20Intermediário-yellow)

</div>

---

## 📋 Sumário
* [🎯 Objetivo deste tópico](#-Objetivo-deste-tópico)
* [🛠️ Baixando o ISO e instalando no Oracle VirtualBox (Aplicativo de virtualização)](#%EF%B8%8F-tecnologias-e-ferramentas)
* [⚙️ Configuração do Ambiente](#%EF%B8%8F-detalhes-da-instalação-e-versões)
* [🚀 Enumeração de Serviços (Reconhecimento Ativo)](#-enumeração-de-serviços-reconhecimento-ativo)
* [📋 Criação das Wordlists (Lista de Tentativas)](#-criação-das-wordlists-lista-de-tentativas)
* [💥 1. Ataque de Força Bruta em Serviço FTP com Hydra](#-1-ataque-de-força-bruta-em-serviço-ftp-com-hydra)
* [💥 2. Ataque de Força Bruta em Serviço FTP com Medusa](#-2-ataque-de-força-bruta-em-serviço-ftp-com-medusa)
* [💥 3. Ataque de Força Bruta em Formulário Web (DVWA)](#-3-ataque-de-força-bruta-em-formulário-web-dvwa)
* [💥 4. Ataque de Força Bruta em Serviço SMB com Password Spraying e Enumeração (Hydra e Medusa)](#-4-ataque-de-força-bruta-em-serviço-smb-com-password-spraying-e-enumeração-hydra-e-medusa)
* [🛡️ Medidas de Mitigação e Recomendações de Segurança](#%EF%B8%8F-medidas-de-mitigação-e-recomendações-de-segurança-)
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
| Putty	| https://sourceforge.net/projects/metasploitable/files/latest/download |	2.0.0
| PuttyGen	| sudo apt install hydra (Se não estiver instalado)	hydra -V | 9.5

## 🛠️  Configuração do Ambiente

1. **Instalação do VirtualBox -** A instalação é bem simples, no meu caso, segui com as opções padrões até a finalização.
2. **Baixando o ISO do Linux Ubuntu -** Baixe o ISO para, posteriormente, fazendo a instalação no VirtualBox. 
3. **Instalando o ISO no VirtualBox -** Com o VirtualBox aberto, clique no botão New(novo), escolha um nome para a imagem e selecione o arquivo ISO apontando para o diretório onde foi feito o download. Observe a imagem abaixo.

<div align="right">
  <details>
    <summary font-weight: bold;">
      [Configuração Kali Linux]
    </summary>
    <img src="images/Kali01.png" alt="Configuração de VM" width="600">
  </details>
</div>
