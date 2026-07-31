<div align="center">

# 🖥️ Comparativo de Terminais
### CMD × PowerShell × Git Bash

*Guia rápido para entender as diferenças e encontrar o comando equivalente em cada terminal*

</div>

---

## 📑 Sumário

- [Qual a diferença entre eles?](#-qual-a-diferença-entre-eles)
- [Como identificar cada terminal](#-como-identificar-cada-terminal)
- [Navegação e diretórios](#-navegação-e-diretórios)
- [Arquivos](#-arquivos)
- [Editor de texto no terminal (Nano)](#-editor-de-texto-no-terminal-nano)
- [Utilitários gerais](#-utilitários-gerais)
- [Pontos de atenção](#-pontos-de-atenção)

---
### O que cada um é

**CMD (Prompt de Comando)**

- É o terminal mais antigo do Windows, existe desde os anos 80/90 (herdeiro do MS-DOS)
- Usa uma linguagem de comandos simples e limitada
- Ainda existe hoje mais por compatibilidade do que por ser a melhor opção

**PowerShell**

- Terminal mais moderno, criado pela Microsoft para substituir o CMD
- Não trabalha só com texto simples — trabalha com **objetos** (dados estruturados), o que permite fazer coisas mais avançadas, como manipular resultados, filtrar propriedades, automatizar tarefas do sistema
- Os comandos "de verdade" têm nomes no padrão `Verbo-Substantivo` (ex: `Get-ChildItem`, `Remove-Item`, `Get-Process`)
- Muitos comandos do CMD (`dir`, `cls`, `type`) funcionam nele só porque são *aliases* (apelidos) apontando pra esses comandos reais — por isso às vezes aceitam parâmetros diferentes do que você espera (foi o que aconteceu com seu `ls -a` e `type nul >`)

**Git Bash**

- Não é um terminal do Windows — é um programa instalado junto com o Git que simula um terminal **Linux** (mais especificamente, usa o Bash, o shell padrão do Linux)
- Serve pra quem quer usar comandos Linux (`ls`, `cat`, `touch`, `nano`, etc.) mesmo estando no Windows
- Muito usado por desenvolvedores porque a maioria dos tutoriais, cursos e documentações de programação assume um ambiente Linux


## 🧩 Qual a diferença entre eles?

| | CMD | PowerShell | Git Bash |
|---|---|---|---|
| **Origem** | Windows antigo (herdeiro do MS-DOS) | Windows moderno | Simula um terminal Linux |
| **Trabalha com** | Texto simples | Objetos estruturados | Texto simples |
| **Sintaxe dos comandos** | Curta (`dir`, `cd`, `del`) | Verbo-Substantivo (`Get-ChildItem`, `Remove-Item`) | Estilo Unix (`ls`, `cd`, `rm`) |
| **Poder de automação** | Baixo | Alto (scripts `.ps1`) | Alto (scripts `.sh`) |
| **Uso mais comum hoje** | Tarefas simples e rápidas | Administração do Windows | Programação, Git, tutoriais de dev |

> ✅ **Recomendação:** para trabalhar com Git, o **Git Bash** é o mais indicado — a sintaxe é igual em qualquer sistema operacional e é o padrão usado na maioria dos cursos e documentações.

---

## 🔍 Como identificar cada terminal

| Terminal | Prompt característico |
|---|---|
| **CMD** | `C:\Users\usuario>` |
| **PowerShell** | `PS C:\Users\usuario>` |
| **Git Bash** | `usuario@PC MINGW64 ~` |

---

## 📁 Navegação e diretórios

| Ação | CMD | PowerShell | Git Bash / Linux |
|---|---|---|---|
| Listar arquivos e pastas | `dir` | `Get-ChildItem` / `ls` | `ls` |
| Listar incluindo ocultos | `dir /a` | `Get-ChildItem -Force` / `ls -Force` | `ls -a` |
| Ver pasta atual | `cd` | `pwd` | `pwd` |
| Entrar em uma pasta | `cd nome_pasta` | `cd nome_pasta` | `cd nome_pasta` |
| Sair um nível | `cd..` | `cd ..` | `cd ..` |
| Ir para a raiz do drive | `cd\` | `cd \` | `cd /` |
| Ir para a pasta do usuário | `cd %userprofile%` | `cd ~` | `cd ~` |
| Trocar de drive e entrar em pasta | `cd /d D:\pasta` | `cd D:\pasta` | `cd /d/pasta` |
| Criar pasta | `mkdir nome_pasta` | `mkdir nome_pasta` | `mkdir nome_pasta` |
| Remover pasta vazia | `rmdir nome_pasta` | `Remove-Item nome_pasta` | `rmdir nome_pasta` |
| Remover pasta com conteúdo | `rmdir /s nome_pasta` | `Remove-Item nome_pasta -Recurse` | `rm -r nome_pasta` |

---

## 📄 Arquivos

| Ação | CMD | PowerShell | Git Bash / Linux |
|---|---|---|---|
| Criar arquivo vazio | `type nul > arquivo` | `New-Item arquivo` | `touch arquivo` |
| Copiar arquivo | `copy origem destino` | `Copy-Item origem destino` | `cp origem destino` |
| Mover/renomear arquivo | `move origem destino` | `Move-Item origem destino` | `mv origem destino` |
| Renomear arquivo | `ren antigo novo` | `Rename-Item antigo novo` | `mv antigo novo` |
| Apagar arquivo | `del arquivo` | `Remove-Item arquivo` | `rm arquivo` |
| Ver conteúdo de um arquivo | `type arquivo` | `Get-Content arquivo` | `cat arquivo` |
| Editar arquivo no terminal | *(sem editor nativo)* | *(sem editor nativo)* | `nano arquivo` |

---

## ✏️ Editor de texto no terminal (Nano)

Disponível no **Git Bash**. Permite editar arquivos direto no terminal, sem sair dele.

```bash
nano nome_do_arquivo.txt
```

| Atalho | Ação |
|---|---|
| `Ctrl + O` | Salvar o arquivo |
| `Ctrl + X` | Sair do Nano |
| `Ctrl + K` | Recortar a linha inteira |
| `Ctrl + U` | Colar a linha recortada |
| `Ctrl + W` | Buscar um texto no arquivo |
| `Ctrl + G` | Mostrar a ajuda completa |

---

## 🛠️ Utilitários gerais

| Ação | CMD | PowerShell | Git Bash / Linux |
|---|---|---|---|
| Limpar a tela | `cls` | `cls` / `Clear-Host` | `clear` |
| Exibir texto | `echo texto` | `echo texto` | `echo texto` |
| Fechar o terminal | `exit` | `exit` | `exit` |
| Ver informações de rede | `ipconfig` | `ipconfig` | `ifconfig` |
| Testar conexão | `ping endereco` | `ping endereco` | `ping endereco` |
| Listar processos | `tasklist` | `Get-Process` | `ps aux` |
| Encerrar processo | `taskkill /IM nome.exe /F` | `Stop-Process -Name nome` | `kill -9 PID` |
| Ajuda geral | `help` | `Get-Help` | `man comando` |
| Ajuda de um comando específico | `comando /?` | `Get-Help comando` | `comando --help` |

---

## ⚠️ Pontos de atenção

> **1. `type nul >` funciona diferente em cada terminal.**
> No **CMD**, `nul` é um dispositivo especial do sistema — por isso `type nul > arquivo` cria um arquivo vazio sem erro.
> No **PowerShell**, `nul` não existe como dispositivo, então o comando **gera erro** — mas o arquivo acaba sendo criado mesmo assim, por causa do redirecionamento `>`, que age antes do erro aparecer. O correto no PowerShell é usar `New-Item`.

> **2. `ls -a` não funciona no PowerShell.**
> No PowerShell, `ls` é apenas um apelido (*alias*) para `Get-ChildItem`, que usa parâmetros diferentes dos comandos Linux. O equivalente correto é `Get-ChildItem -Force` ou `ls -Force`.

> **3. Muitos comandos "estilo CMD" (como dir, cls, type) funcionam no PowerShell.**
> Comandos como `dir`, `cls` e `type` funcionam no PowerShell porque são *aliases* apontando para comandos reais do PowerShell (`Get-ChildItem`, `Clear-Host`, `Get-Content`). Por isso funcionam parcialmente, mas nem sempre aceitam os mesmos parâmetros.

---

<div align="center">

📌 *Parte do [Manual de Git & GitHub](README.md) — consulte lá o passo a passo completo de Git e GitHub.*

</div>
