# Git Starter Kit

Este repositório é um guia de consulta para aprender e praticar os comandos mais usados do Git. Os exemplos mostram um fluxo comum: preparar uma pasta, registrar alterações e enviá-las para um repositório remoto.

## Comece por aqui

Se você ainda não tem uma cópia do projeto, clone o repositório:

```bash
git clone https://github.com/usuario/projeto.git
cd projeto
```

Troque o endereço de exemplo pelo endereço real do repositório.

Configure seu nome e e-mail uma única vez no computador. Esses dados ficam associados aos seus commits:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "voce@exemplo.com"
```

## Fluxo básico de trabalho

Depois de editar ou criar arquivos, confira o que mudou:

```bash
git status
```

Adicione ao próximo commit somente o arquivo que deseja registrar:

```bash
git add README.md
```

Para adicionar todas as alterações da pasta atual, use `git add .`. Confira novamente com `git status` e crie um commit descritivo:

```bash
git commit -m "Atualiza instruções do projeto"
```

Se o repositório remoto já estiver configurado, envie os commits:

```bash
git push
```

Para baixar e integrar alterações do remoto antes de trabalhar:

```bash
git pull
```

## Outros comandos úteis

- `git log --oneline`: mostra o histórico de commits em formato compacto.
- `git diff`: mostra alterações ainda não adicionadas ao próximo commit.
- `git branch`: lista as branches locais.
- `git switch -c nome-da-branch`: cria uma branch e muda para ela.
- `git switch main`: muda para a branch `main`.

Para ver mais exemplos — incluindo iniciar um repositório, configurar o remoto e corrigir alterações — consulte o [Guia de comandos básicos do Git](./COMANDOS-GIT.md).

## Dica

Um fluxo seguro é: `git status` → `git add` → `git diff --staged` → `git commit` → `git push`. Assim você confere o que será registrado antes de criar o commit.
