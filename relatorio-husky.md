# PONDSEM3PROG

## Relatorio-husky.md

## Objetivo

O objetivo desta atividade foi configurar o Husky em um repositório GitHub para garantir:

- Execução do lint e build no momento do pré-commit
- Execução dos testes no momento do pré-push
- Garantia de qualidade antes da integração do código

## Estrutura Inicial do Projeto

1. Inicializei o repositório com `git init` e `npm init -y`.
2. Instalei o Husky com:

```bash
npm install --save-dev husky
npx husky install
````

3. Adicionei o script `prepare` ao `package.json`:

```json
"scripts": {
  "prepare": "husky install",
  "lint": "echo 'Linting...' && exit 0",
  "build": "echo 'Building...' && exit 0",
  "test": "echo 'Running tests...' && exit 0"
}
```

## Configuração dos Hooks

### Hook de Pré-commit

Arquivo: `.husky/pre-commit`

```sh
#!/usr/bin/env sh
. "$(dirname -- "$0")/_/husky.sh"

npm run lint && npm run build
```

### Hook de Pré-push

Arquivo: `.husky/pre-push`

```sh
#!/usr/bin/env sh
. "$(dirname -- "$0")/_/husky.sh"

npm run test
```

## Execução dos Hooks

### Execução do Pré-commit

> 🖼️ **INSIRA AQUI UM PRINT** mostrando o terminal executando `npm run lint && npm run build` automaticamente após `git commit`.


### Execução do Pré-push

![Npm run testes sendo executado](/images/Push.png)


## Commits Semânticos

Utilizei a convenção de commits semânticos para organização, como por exemplo:

```bash
git commit -m "feat: configurações iniciais do husky"
git commit -m "fix: corrigido caminho do husky.sh"
```
