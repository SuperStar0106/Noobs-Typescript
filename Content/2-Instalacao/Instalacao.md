# Instalando o Typescript

PS: antes de seguir com a instalação do typescript é importante ter o **node** previamente instalado.

A instalação em si é super simples e pode ser feita com apenas esse comando abaixo:

`npm install -g typescript`

Para checar a versão instalada basta rodar `tsc -v`, assim teremos segurança de que ele realmente foi instalado.

Após instalado, é interessante rodarmos `tsc --init` no terminal para que um arquivo `tsconfig.json` seja gerado. Esse arquivo é responsável por ditar como o Typescript irá se comportar no projeto: para qual versão do Javascript ele vai compilar, quais diretórios ele deve jogar seus arquivos, se ele vai ser mais ou menos "chato" com os erros, etc.

---

# Extra: Instalação com Yarn

Você também pode inicializar seu projeto Typescript usando o **Yarn** por questões de preferência.

Basta rodar:

`yarn init -y` para inicializar o Yarn em si no diretório

`yarn add -D typescript` para instalar o Typescript

`yarn tsc --init` para gerar o arquivo `tsconfig.json`

# Typescript + React

É possível inicializar um projeto react com um template para typescript de várias formas, uma delas se utilizando do create-react-app específico para o typescript, usando os seguintes comandos:

`yarn create react-app my-app --template typescript` ou `npx create-react-app my-app --template typescript` 

Exemplo de como fica um componente funcional com typescript: 

```ts
import React, { FunctionComponent, useState } from 'react'

interface Props {
  message: string
}

const App: FunctionComponent<Props> = props => {
  const [hasMessage, setHasMessage] = useState<boolean>(false)
  return <p>{hasMessage ? props.message : 'Default Message'}</p>
}

export default App
```