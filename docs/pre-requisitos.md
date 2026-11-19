# Pré-requisitos: o que instalar antes da primeira aula

Instale os programas abaixo em casa, antes do primeiro dia, com uma internet boa. Leva de 30 minutos a 1 hora, quase tudo esperando download.

Travou em algum passo? Traga o notebook assim mesmo. No começo da aula, o instrutor demonstra a instalação do omp e o próprio agente confere e instala o que faltar.

## O que você vai instalar

| Programa | Para quê | Obrigatório? |
|---|---|---|
| omp | O agente de IA, que conversa com você e faz o trabalho | Sim |
| Python | Os scripts que organizam o vídeo | Sim |
| ffmpeg | O motor de vídeo e áudio | Sim |
| Node.js (versão 20 ou mais nova) | Grava as telas animadas quadro a quadro | Sim |
| Google Chrome | Desenha as telas animadas e é o navegador que o agente usa | Sim |
| Git | Baixa e atualiza o material do curso e as skills de animação | Sim |
| Kdenlive | Editor de vídeo para ajuste à mão | Não |
| adb (Android Platform-Tools) | Manda o vídeo para um celular Android | Não |

Os complementos que rodam por cima desses programas (bibliotecas do Python, o Playwright do Node.js, a extensão do omp no Chrome e as skills de animação) são instalados na aula, pelo próprio agente.

O notebook precisa de Windows 10 ou 11, macOS ou Linux, e de uns 10 GB livres no disco.

## Windows 10 e 11

1. Abra o **PowerShell**: aperte a tecla Windows, digite `PowerShell` e tecle Enter.
2. Instale o omp:

   ```powershell
   irm https://omp.sh/install.ps1 | iex
   ```

3. Instale os outros programas, um comando por vez. Se o Windows pedir permissão, clique em **Sim**.

   ```powershell
   winget install -e --id Python.Python.3.13
   winget install -e --id Gyan.FFmpeg
   winget install -e --id OpenJS.NodeJS.LTS
   winget install -e --id Google.Chrome
   winget install -e --id Git.Git
   ```

   Opcionais:

   ```powershell
   winget install -e --id KDE.Kdenlive
   winget install -e --id Google.PlatformTools
   ```

4. **Feche o PowerShell e abra de novo**, para o Windows enxergar os programas novos.

Se aparecer "winget não é reconhecido", atualize o **Instalador de Aplicativo** na Microsoft Store e tente de novo.

## macOS

1. Abra o **Terminal**: aperte Command + Espaço, digite `Terminal` e tecle Enter.
2. Instale o **Homebrew**, o instalador de programas do Mac. Ele pede a senha do Mac (a digitação não aparece na tela; é normal):

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

   No fim, o Homebrew mostra em "Next steps" dois ou três comandos para copiar e colar. Rode esses comandos antes de seguir.

3. Instale o omp:

   ```bash
   curl -fsSL https://omp.sh/install | sh
   ```

4. Instale os outros programas:

   ```bash
   brew install python@3.13 ffmpeg node git
   brew install --cask google-chrome
   ```

   Opcionais:

   ```bash
   brew install --cask kdenlive android-platform-tools
   ```

5. Feche o Terminal e abra de novo.

## Linux (Ubuntu, Linux Mint e Debian)

1. Abra o **Terminal** (Ctrl + Alt + T no Ubuntu e no Mint).
2. Instale o Python, o ffmpeg, o curl e o Git:

   ```bash
   sudo apt update
   sudo apt install -y python3 python3-venv python3-pip ffmpeg curl git
   ```

3. Instale o Node.js. O que vem no Ubuntu 24.04 é a versão 18, antiga demais para o curso; este comando instala a versão atual:

   ```bash
   curl -fsSL https://deb.nodesource.com/setup_26.x | sudo -E bash -
   sudo apt install -y nodejs
   ```

4. Instale o Google Chrome:

   ```bash
   curl -fLO https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
   sudo apt install -y ./google-chrome-stable_current_amd64.deb
   ```

5. Instale o omp:

   ```bash
   curl -fsSL https://omp.sh/install | sh
   ```

   Opcionais:

   ```bash
   sudo apt install -y kdenlive adb
   ```

6. Feche o Terminal e abra de novo.

Em outras distribuições (Fedora, Arch...), instale os mesmos programas pelo gerenciador de pacotes dela; o omp usa o mesmo comando do passo 5.

## Conferir se deu tudo certo

Com o terminal aberto de novo, rode um comando por vez. Cada um deve responder com um número de versão:

| Programa | Windows (PowerShell) | macOS (Terminal) | Linux (Terminal) |
|---|---|---|---|
| omp | `omp --version` | `omp --version` | `omp --version` |
| Python | `py -3.13 --version` | `python3.13 --version` | `python3 --version` |
| ffmpeg | `ffmpeg -version` | `ffmpeg -version` | `ffmpeg -version` |
| Node.js | `node --version` (20 ou mais) | `node --version` (20 ou mais) | `node --version` (20 ou mais) |
| Git | `git --version` | `git --version` | `git --version` |

Algum respondeu "não encontrado" ou "não é reconhecido"? Anote qual foi e traga o notebook: resolvemos no começo da aula.

## Antes da aula, também

- Crie as contas da [lista de contas](contas.md).
- Baixe este material: `git clone https://github.com/fberbert/curso-video-ia-kit.git` no terminal, ou, sem o Git, clique em **Code** e depois em **Download ZIP** no alto da página do repositório.

## Fontes

- omp: https://github.com/can1357/oh-my-pi
- Homebrew: https://brew.sh
- Node.js para Ubuntu e Debian (NodeSource): https://github.com/nodesource/distributions
- adb (Android SDK Platform-Tools): https://developer.android.com/tools/releases/platform-tools
