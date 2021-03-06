# Tray Login Component
Web Component para realizar login no Checkout das lojas da Tray.

## Instalação

`bower install -S tray-tecnologia/tray-login`

## Atributos
Atributo      | Descrição
--------      | -----------
api-otp       | URL de geração do código (POST, params: email)
api-otp-login | URL de login (GET, params: email, code)
url-callback  | URL de callback caso o login esteja correto

## Eventos

Lista de eventos disparados pelo componente.

Evento          | Descrição
--------        | -----------
tray-login      | Dispara quando finalizou o processo de login
tray-login#main | Dispara quando abre a tela inicial do componente
tray-login#otp  | Dispara quando abre a tela do OTP

Exemplo de utilização do evento:
```js
$(document).on('tray-login', function(event, response, type) {
    if (type === 'finished') {
        console.log('Success!');
    } else {
        console.error('Error!');
    }
});
```

## Uso

1. Adicione o polyfill e importe o componente no `<head>`:
```HTML
<script src="bower_components/webcomponentsjs/webcomponentsjs.min.js">
<link rel="import" href="dist/tray-login.html">
```

2. Adicione o elemento no seu HTML substituindo as URLs da aplicação.

```HTML
<tray-login
	data-email="teste@tray.com.br"
    api-otp="/otp/"
    api-otp-login="/otp/login"
    url-callback="/callback.html">
</tray-login>
```

## Contribuindo

Para configurar o ambiente de dev, execute:
```sh
npm install
bower install
gulp watch
```

Não altere os arquivos da pasta `dist/`, é apenas o build. O `dist/tray-login.html` deverá existir no controle de versão.
