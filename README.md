# laravel-mix-stand-alone-projects
Este tutorial ensina como criar em 5 minutos um projeto usando Vue Js e Laravel Mix em um projeto que não seja no laravel.

1º Passo
```batch
npm init -y
```

2º Passo
Substituir o conteúdo do passo 1 por este:
```json
{
   "name": "mix-teste",
   "version": "1.0.0",
   "description": "",
   "main": "index.js",
   "scripts": {
       "test": "echo \"Error: no test specified\" && exit 1"
   },
   "keywords": [],
   "author": "",
   "license": "ISC",
   "dependencies": {
       "vue": "^2.6.14"
   },
   "devDependencies": {
       "laravel-mix": "^6.0.43",
       "vue-loader": "^15.9.8",
       "vue-template-compiler": "^2.6.14"
   }
}
```

3º Passo
Executar o comando 
```npm install```

4º Passo
Criar o arquivo ``src/app.js`` na raiz do projeto.

5º Passo
Adicionar o seguinte conteúdo ao arquivo src/app.js
```js
import Vue from 'vue';
import Exemplo from './components/Exemplo.vue';
new Vue({
   el: '#app',
   components: { Exemplo }
});
```

6º Passo
Criar o arquivo  webpack.mix.js na raiz do projeto e adicionar a ele o seguinte conteúdo:
```js
let mix = require('laravel-mix');
mix.js('src/app.js', 'public/js').vue();
```

7º Passo
Criar o arquivo Exemplo.vue na pasta src/components.
9º Passo
Adicionar o seguinte conteúdo ao arquivo src/components/Exemplo.vue
```vue
<template>
   <div class="alert" v-text="message"></div>
</template>
 
<script>
export default {
   data() {
       return {
           message: 'I am an alert.'
       };
   }
};
</script>
<style>
.alert {
   background: red;
}
</style>
```
10º Passo
Criar o arquivo index.html na raiz do projeto e adicionar o seguinte conteúdo a ele.
```html
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <meta http-equiv="X-UA-Compatible" content="IE=edge">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <title>Document</title>
</head>
<body>
   <div id="app"> <Exemplo /> </div>
   <script src="public/js/app.js"></script>
</body>
</html>
```
11º Passo
Finalmente, execute este npx mix comando na raiz do projeto.

12º Passo
Abrir o arquivo index.html no navegador.
