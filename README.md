# Tutorial prático sobre Git no Debian 12 (por exemplo)

## Instalação do Git
No Debian 12, instale o Git executando:
```bash
sudo apt update && sudo apt install git -y
```

Verifique a instalação com:
```bash
git --version
```

## Configuração Inicial
Defina seu nome e e-mail:
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```

## Criando o Repositório
Crie as pastas:
```bash
mkdir -p ~/Projetos/GIT && cd ~/Projetos/GIT
```

Inicialize um repositório Git:
```bash
git init
```

Crie um arquivo chamado `guia_git`:
```bash
echo "Guia Prático de Git" > guia_git
```

Adicione todos os arquivos ao repositório:
```bash
git add .
```

Faça o primeiro commit:
```bash
git commit -m "Inicialização do repositório"
```

## Criando e Trabalhando com Branches
Crie e alterne para a branch `desenvolvimento`:
```bash
git checkout -b desenvolvimento
```

Adicione alterações ao `guia_git`:
```bash
echo "Adicionando mais conteúdo." >> guia_git
```

Adicione e confirme a mudança:
```bash
git add guia_git
git commit -m "Atualização do guia_git"
```

## Desfazendo Mudanças
### Desfazer alterações antes do `git add`:
```bash
git checkout -- guia_git
```

### Desfazer um commit antes do push:
```bash
git reset --soft HEAD~1
```

Para remover completamente a alteração:
```bash
git reset --hard HEAD~1
```

## Fazendo Merge da `desenvolvimento` para `main`
Volte para a `main`:
```bash
git checkout main
```

Faça o merge:
```bash
git merge desenvolvimento
```

## Listando Commits
Para listar os commits realizados no repositório, use:
```bash
git log --oneline
```
Isso exibirá uma lista compacta dos commits com seus IDs únicos, permitindo identificar qual commit desfazer.

## Desfazendo um Merge Errado
Se o merge do arquivo `guia_git.v02` foi enviado da `desenvolvimento` para a `main` por engano, use:
```bash
git checkout main
git reset --hard HEAD~1
```
Se o merge já foi enviado ao repositório remoto, utilize:
```bash
git revert -m 1 <ID_DO_COMMIT_DO_MERGE>
```

## Criando e Incrementando Tags
Adicione uma tag `guia_git.v01`:
```bash
git tag -a guia_git.v01 -m "Versão inicial do guia"
```

Faça outra alteração no `guia_git`:
```bash
echo "Mais melhorias no guia." >> guia_git
```

Confirme e crie uma nova tag `guia_git.v02`:
```bash
git add guia_git
git commit -m "Melhoria no guia_git"
git tag -a guia_git.v02 -m "Segunda versão do guia"
```

## Conclusão
Agora você sabe como:
- Instalar e configurar o Git
- Criar repositórios e branches
- Adicionar e desfazer mudanças
- Listar commits para identificar alterações
- Realizar merge entre branches
- Criar e incrementar versões com tags
- Desfazer um merge incorreto

Esse é um guia básico para o uso eficiente do Git!




