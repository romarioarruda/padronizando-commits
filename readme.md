#### Passos para configurar o padronizador de commits

> Passo 1

```
$ npm init -y ou npm install
```

> Passo 2

```
$ npm install -g commitizen

$ commitizen init cz-conventional-changelog --save-dev --save-exact
```

> Passo 3
```
$ npm install husky -D

Edit package.json:

"scripts": {
    "prepare": "husky install",
    "husky": {
        "hooks": {
            "prepare-commit-msg": "exec < /dev/tty && node_modules/.bin/cz --hook || true"
        }
    }
}

$ npm run prepare
```

> Passo 4

```
Add um hook:

$ npx husky add .husky/prepare-commit-msg "exec < /dev/tty && node_modules/.bin/cz --hook || true"
```

> Passo 5

Na hora de fazer o commit execute apenas:

```
$ git commit
```


**Links de referências**:
`https://github.com/commitizen/cz-cli`
`https://typicode.github.io/husky/#/`