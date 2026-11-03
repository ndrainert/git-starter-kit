# Comandos básicos do Git

Este guia reúne comandos frequentes com exemplos práticos. Execute-os no terminal, dentro da pasta do projeto, exceto quando indicado.

## 1. Configurar sua identificação

Configure o nome e o e-mail que aparecerão nos seus commits. A opção `--global` aplica a configuração a todos os repositórios do usuário neste computador:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "voce@exemplo.com"
```

Confira os valores:

```bash
git config --global --list
```

## 2. Obter ou iniciar um repositório

### Clonar um projeto existente

```bash
git clone https://github.com/usuario/projeto.git
cd projeto
```

`git clone` cria uma cópia local do repositório. Substitua o endereço e o nome da pasta pelos valores do projeto real.

### Começar a acompanhar uma pasta existente

Na pasta do projeto, execute:

```bash
git init
```

Isso cria um repositório Git local. Para conectá-lo a um repositório remoto que já foi criado:

```bash
git remote add origin https://github.com/usuario/projeto.git
git branch -M main
```

Use o endereço real do seu repositório. Se `origin` já estiver configurado, não adicione o remoto novamente; confira-o com `git remote -v`.

## 3. Conferir alterações

```bash
git status
```

Mostra os arquivos modificados, novos ou preparados para o próximo commit.

Para ver as diferenças que ainda não foram preparadas:

```bash
git diff
```

Para ver as diferenças já preparadas:

```bash
git diff --staged
```

## 4. Preparar e registrar alterações

Adicione um arquivo específico:

```bash
git add README.md
```

Ou adicione todas as alterações da pasta atual:

```bash
git add .
```

`git add` prepara o conteúdo para o próximo commit; ele não cria o commit. Confira o que foi preparado e registre as alterações:

```bash
git diff --staged
git commit -m "Adiciona instruções de instalação"
```

Escreva mensagens curtas que expliquem a mudança, por exemplo: `Corrige validação do formulário`.

## 5. Consultar o histórico

```bash
git log --oneline
```

Exibe os commits recentes em formato compacto. Para ver também as alterações de cada commit:

```bash
git log -p
```

## 6. Trabalhar com branches

Branches permitem trabalhar em uma mudança sem alterar diretamente a branch principal:

```bash
git switch -c adiciona-pagina-contato
```

O comando cria a branch e muda para ela. Para listar as branches:

```bash
git branch
```

Para mudar para uma branch existente:

```bash
git switch main
```

## 7. Sincronizar com o repositório remoto

Veja os remotos configurados:

```bash
git remote -v
```

Baixe e integre as alterações da branch remota atual:

```bash
git pull
```

Envie os commits locais:

```bash
git push
```

Na primeira vez que enviar uma branch nova, defina o vínculo com o remoto:

```bash
git push -u origin adiciona-pagina-contato
```

Depois disso, `git push` e `git pull` normalmente identificam a branch correspondente sem opções extras.

## 8. Desfazer com cuidado

Remover um arquivo da área de preparação mantém as alterações no arquivo:

```bash
git restore --staged README.md
```

Descartar alterações locais ainda não commitadas em um arquivo é uma ação destrutiva: o conteúdo modificado será perdido. Use somente se tiver certeza:

```bash
git restore README.md
```

## Exemplo completo

Um ciclo comum para uma alteração em um projeto clonado:

```bash
git pull
git switch -c corrige-texto
# Edite os arquivos do projeto
git status
git add README.md
git diff --staged
git commit -m "Corrige texto do README"
git push -u origin corrige-texto
```

Os comandos comentados com `#` são apenas indicações; não é necessário digitá-los. O envio cria a branch no remoto, pronta para ser compartilhada ou incluída em uma solicitação de mudança.
