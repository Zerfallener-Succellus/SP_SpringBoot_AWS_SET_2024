# Resolução de Conflito no Git 🚀

Este documento explica como resolver conflitos no Git com um exemplo prático onde há um conflito no arquivo `README.md` entre as branches `feature/semana-03` e `main`.

## 1. Simulação do Conflito ⚠️

Para simular um conflito, siga os seguintes passos:

### Passo 1: Preparar as Branches 🌿

1. **Na branch `feature/semana-03`:**

    - Edite o arquivo `README.md` da Semana 03 e adicione uma descrição.
    - Faça commit das mudanças:

      ```bash
      git checkout feature/semana-03
      echo "Descrição da Semana 03 na branch feature/semana-03" >> Semana-03/README.md
      git add Semana-03/README.md
      git commit -m "Adiciona descrição na Semana 03 na branch feature/semana-03"
      ```

2. **Na branch `main`:**

    - Edite o mesmo arquivo `README.md` da Semana 03 e adicione um conteúdo diferente.
    - Faça commit das mudanças:

      ```bash
      git checkout main
      echo "Conteúdo diferente na Semana 03 na branch main" >> Semana-03/README.md
      git add Semana-03/README.md
      git commit -m "Adiciona conteúdo diferente na Semana 03 na branch main"
      ```

### Passo 2: Tentar Realizar o Merge 🔄

1. **Faça o merge da branch `feature/semana-03` na branch `main`:**

    ```bash
    git checkout main
    git pull
    git merge feature/semana-03
    ```

    Neste ponto, ocorrerá um conflito no arquivo `Semana-03/README.md`, pois ambos os branches modificaram o mesmo arquivo.

## 2. Resolução do Conflito 🛠️

Para resolver o conflito:

1. **Localize o arquivo com conflito e edite-o manualmente:**

    - Abra `Semana-03/README.md` em seu editor de texto. Você verá seções delimitadas por marcações de conflito, como:

      ```markdown
      <<<<<<< HEAD
      Conteúdo diferente na Semana 03 na branch main
      =======
      Descrição da Semana 03 na branch feature/semana-03
      >>>>>>> feature/semana-03
      ```

    - Modifique o arquivo para incluir o conteúdo desejado e remova as marcações de conflito. Por exemplo:

      ```markdown
      Descrição da Semana 03 na branch feature/semana-03
      Conteúdo diferente na Semana 03 na branch main
      ```

2. **Marque o conflito como resolvido e faça commit das mudanças:**

    ```bash
    git add Semana-03/README.md
    git commit -m "Resolve conflito no README.md da Semana 03"
    ```

3. **Empurre as mudanças para o repositório remoto:**

    ```bash
    git push origin main
    ```

## 3. Documentar a Resolução 📄

Crie um arquivo chamado `docs/resolucao-conflitos.md` para documentar o processo. O conteúdo pode ser semelhante ao descrito acima, explicando cada etapa e as ferramentas utilizadas para resolver o conflito.

## Exemplo de Arquivo de Documentação

```markdown
# Resolução de Conflito no Git 🛠️

## Contexto

Um conflito foi encontrado ao tentar fazer o merge da branch `feature/semana-03` na branch `main`. O conflito ocorreu no arquivo `Semana-03/README.md`, que foi modificado em ambas as branches.

## Passos para Resolução

1. **Simulação do Conflito ⚠️**

    - Modificações feitas na branch `feature/semana-03` e `main` resultaram em alterações conflitantes no arquivo `Semana-03/README.md`.

2. **Resolução do Conflito 🛠️**

    - Edite o arquivo para combinar as mudanças desejadas.
    - Marque o conflito como resolvido e faça o commit.
    - Empurre as mudanças para o repositório remoto.

## Ferramentas Utilizadas 🧰

- **Git**: Para realizar o merge, resolver conflitos e fazer commit das mudanças.
- **Editor de Texto**: Para editar manualmente o arquivo com conflito.

