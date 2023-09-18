# Criando projeto NEXTJS 13 e TYPESCRIPT

## Estou estudando NextJS e quero compartilhar uma de exemplo **configuração** de projeto.

<hr>

### Link

[https://nextjs.org/docs](https://nextjs.org/docs)

```jsx
npx create-next-app@latest
```

Entrar na pasta do projeto ```cd nome-projeto```

```jsx
cd "nome-do-projeto"
npx eslint --init
```

Instalar Plugins

[](https://github.com/facebook/react/tree/main/packages/eslint-plugin-react-hooks)

`yarn add eslint-plugin-react-hooks --dev`

No arquivo .eslintrc.json  acrescentar o plugins - `"react-hooks"` e também as regras.

```
{
  "plugins": [
    // ...
    "react-hooks"
  ],
  "rules": {
    // ...
    "react-hooks/rules-of-hooks": "error",
    "react-hooks/exhaustive-deps": "warn"
  }
}
```

Acrescentar configuração no .eslintrc.json 

```json
"settings": {
        "react":{
            "version": "detect"
        }
    },
```


[Instalar o Prettier](https://prettier.io/docs/en/install)

```jsx
yarn add --dev --exact prettier
```

Criar arquivo .prettierrc e colocar as configurações

```json
{
    "trailingComma": "none", 
    "semi": true,
    "singleQuote": true
}
```

Fazendo integração do Eslint com o Prettier

```jsx
yarn add --dev eslint-config-prettier
yarn add --dev eslint-plugin-prettier
```

Passar as configurações no .prettier no extends

```json
"extends": [
      //...
				"eslint:recommended",
        "plugin:react/recommended",
        "plugin:@typescript-eslint/recommended",
        "plugin:prettier/recommended",
        "prettier"
    ],
```

```json
"rules": {
        // ...
    
        "prettier/prettier": "error"
    }
```

Criar o arquivo .vscode/setting.json com as linhas abaixo

```json
{
  "editor.formatOnSave": false,
  "editor.codeActionsOnSave": {
    "source.fixAll": true
  }
}
```

Instalar o plugin `eslint-plugin-import-helpers`

```jsx
yarn add --dev eslint-plugin-import-helpers
```

Passar o plugin

```jsx
"plugins": [
						//...

						 "eslint-plugin-import-helpers"
],
```

Adicionar a configuração abaixo no  .eslintrc.json

```jsx
{// Configuração dos imports
                "newlinesBetween": "always",
                "groups": [
                    ["/^react/", "/^next/", "/@next/"],
                    "/components/",
                    "module",
                    "/^@shared/",
                    "/absolute/",
                    ["parent", "sibling", "index"]
                ],
                "alphabetize": { "order": "asc", "ignoreCase": true }
            }
```



This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Para rodar o projeto.
Primeiro, execute o servidor de desenvolvimento.


```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

Abra o projeto no link [http://localhost:3000](http://localhost:3000) com seu navegador para ver o resultado.


Este projeto usa [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) 
para otimizar e carregar automaticamente o INTER, uma fonte personalizada do Google.