#### Passos para configurar o padronizador de commits

> Passo 1
```
$ npm install husky -D

Edit package.json > prepare script:
"scripts": {
    "prepare": "husky install"
}

$ npm run prepare

Add a hook:

npx husky add .husky/prepare-commit-msg "exec < /dev/tty && node_modules/.bin/cz --hook || true"

```

> Passo 2

```
$ npm install -g commitizen

$ commitizen init cz-conventional-changelog --save-dev --save-exact
```