<!-- LOGOTIPO DO PROJETO -->
<div style="display: flex; justify-content: center;">
   <a href="https://github.com/edftechnology/shellcheck">
     <img src="docs/figures/logo.png" alt="Logo" width="200" height="100">
   </a>
</div>

<h3 align="center">ShellCheck</h3>

<div style="display: flex; justify-content: center;">
  <a href="https://doi.org/10.5281/zenodo.14711872">
    <img src="https://zenodo.org/badge/10.5281/zenodo.14711872.svg" alt="DOI">
  </a>
</div>

<p align="center">
 Ferramenta de análise estática para scripts de shell.
 <br />
 <a href="https://github.com/edftechnology/shellcheck"><strong>Explore os documentos »</strong></a>
 <br />
 <br />
 <a href="https://github.com/edftechnology/shellcheck">Ver demonstração</a>
 ·
 <a href="https://github.com/edftechnology/shellcheck">Relatar bug</a>
 ·
 <a href="https://github.com/edftechnology/shellcheck">Solicitar recurso</a>
</p>

# Como instalar/configurar/usar o `shellcheck` no `Linux Ubuntu`

## Resumo

Guia para instalar o `shellcheck` no `Linux Ubuntu` pelo `Terminal Emulator`, usando o pacote oficial dos repositórios do `Ubuntu` com `apt`.

## _Abstract_

_A guide to install `shellcheck` on `Linux Ubuntu` through the `Terminal Emulator`, using the official Ubuntu repository package with `apt`._


## Descrição

### `shellcheck`

O `shellcheck` é uma ferramenta de análise estática para scripts de shell. Ela identifica problemas de sintaxe, práticas inseguras e possíveis erros em scripts `sh` e `bash`.


## Pré-requisitos

- Permissão para usar `sudo`
- Conexão com a internet para atualizar os índices e instalar o pacote
- `apt` funcional no sistema
- Repositório `universe` habilitado, onde o pacote está publicado


## 1. Abrir o `Terminal Emulator`

1. Abrir o `Terminal Emulator`. Você pode fazer isso pressionando:

    ```bash
    Ctrl + Alt + T
    ```


2. Certifique-se de que seu sistema esteja limpo e atualizado.

    2.1 Limpar o `cache` do gerenciador de pacotes `apt`. Especificamente, ele remove todos os arquivos de pacotes (`.deb`) baixados pelo `apt` e armazenados em `/var/cache/apt/archives/`. Digite o seguinte comando:

    ```bash
    sudo apt clean
    ```

    2.2 Remover pacotes `.deb` antigos ou duplicados do `cache` local. É útil para liberar espaço, pois remove apenas os pacotes que não podem mais ser baixados (ou seja, versões antigas de pacotes que foram atualizados). Digite o seguinte comando:

    ```bash
    sudo apt autoclean
    ```

    2.3 Remover pacotes que foram automaticamente instalados para satisfazer as dependências de outros pacotes e que não são mais necessários. Digite o seguinte comando:

    ```bash
    sudo apt autoremove -y
    ```

    2.4 Buscar as atualizações disponíveis para os pacotes que estão instalados em seu sistema. Digite o seguinte comando e pressione `Enter`:

    ```bash
    sudo apt update
    ```

    2.5 **Corrigir pacotes quebrados**: Isso atualizará a lista de pacotes disponíveis e tentará corrigir pacotes quebrados ou com dependências ausentes:

    ```bash
    sudo apt --fix-broken install
    ```

    2.6 Limpar o `cache` do gerenciador de pacotes `apt` novamente:

    ```bash
    sudo apt clean
    ```

    2.7 Para ver a lista de pacotes a serem atualizados, digite o seguinte comando e pressione `Enter`:

    ```bash
    sudo apt list --upgradable
    ```

    2.8 Realmente atualizar os pacotes instalados para as suas versões mais recentes, com base na última vez que você executou `sudo apt update`. Digite o seguinte comando e pressione `Enter`:

    ```bash
    sudo apt full-upgrade -y
    ```


## 3. Instalar o `shellcheck` via `apt`

O pacote `shellcheck` está disponível nos repositórios do `Ubuntu`, na seção `universe`. Se necessário, habilitar essa seção e atualizar o índice de pacotes.

1. Habilitar o repositório `universe` e atualizar os índices de pacotes:

    ```bash
    sudo add-apt-repository universe
    sudo apt update
    ```

2. Instalar o `shellcheck`:

    ```bash
    sudo apt install shellcheck -y
    ```

3. Confirmar a instalação e consultar a versão:

    ```bash
    shellcheck --version
    ```


## 4. Usar o `shellcheck`

1. Analisar um script:

    ```bash
    shellcheck caminho/do_script.sh
    ```

2. Analisar todos os arquivos `.sh` do diretório atual:

    ```bash
    find . -type f -name '*.sh' -print0 | xargs -0 -r shellcheck
    ```

3. Consultar as opções disponíveis:

    ```bash
    shellcheck --help
    ```


## 5. Desinstalar o `shellcheck` (opcional)

Para remover o pacote instalado pelo `apt`, executar:

```bash
sudo apt remove shellcheck -y
```


## 6. Código completo para configurar/instalar/usar

Para configurar/instalar/usar o `shellcheck` no `Linux Ubuntu` sem precisar digitar linha por linha, você pode seguir estas etapas:

1. Abrir o `Terminal Emulator`. Você pode fazer isso pressionando:

    ```bash
    Ctrl + Alt + T
    ```

2. Digitar os comandos abaixo e pressionar `Enter`:

    ```bash
    sudo apt clean
    sudo apt autoclean
    sudo apt autoremove -y
    sudo apt update
    sudo apt --fix-broken install
    sudo apt clean
    sudo apt list --upgradable
    sudo apt full-upgrade -y
    sudo add-apt-repository universe
    sudo apt update
    sudo apt install shellcheck -y
    shellcheck --version
    shellcheck caminho/do_script.sh
    ```


## Compatibilidade

- O pacote `shellcheck` consta nos repositórios do `Ubuntu` para versões como `Jammy` (22.04 LTS) e `Noble` (24.04 LTS), na seção `universe`.
- A versão instalada depende da versão do `Ubuntu` e dos repositórios habilitados.
- O método descrito instala o próprio `shellcheck` pelo `apt`; não compila o código-fonte.


## Licença

Este repositório inclui o arquivo `LICENSE.txt`.

## Contato e suporte

Para dúvidas ou problemas, consulte o repositório oficial do `shellcheck` e a documentação da sua versão do `Linux Ubuntu`.


## Referências

[1] OPENAI.
**Instalar o `shellcheck` no `linux ubuntu` pelo `terminal emulator`**.
Disponível em: <https://chatgpt.com/g/g-p-6980caf949648191ad6acfcdbe590f9e-instalar/c/6ac7e15c-ee78-83e9-8b08-cbd493e08ee7>.
ChatGPT.
Acessado em: 08/10/2026.

[2] KOALAMAN.
**ShellCheck, ferramenta de análise estática para scripts de shell**.
Disponível em: <https://github.com/koalaman/shellcheck>.
GitHub.
Acessado em: 08/10/2026.

[3] UBUNTU.
**Pacote `shellcheck`**.
Disponível em: <https://packages.ubuntu.com/search?exact=1&keywords=shellcheck&searchon=names&section=all&suite=all>.
Ubuntu Packages.
Acessado em: 08/10/2026.

