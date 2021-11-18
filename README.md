# Instalando npm

Caso você esteja usando o Ubuntu numa VM, talvez você encontre alguns problemas para executar o comando `npm`. 

## Erro "/usr/bin/env: ‘bash\r’: No such file or directory"

Se você se deparar com essa mensagem de erro, execute os comandos abaixo:

```console
$ sudo touch /etc/wsl.conf
$ sudo nano /etc/wsl.conf
```

Em seguida, escreva as linhas abaixo no arquivo e salve:

```
[interop]
apprendWindowsPath = false
```

Por fim, feche o terminal e abra-o novamente. O comando `npm` deve funcionar corretamente.

# Instalando o cypress
```console
$ npm -i init
$ npm install cypress --save-dev
```

# Rodando o cypress
```console
$ node_modules/.bin/cypress open
```

Talvez você precise alterar essa configuração no seu computador:
1. No Power Shell, digite o comando: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned`.
2. Digite 'Yes'.

# Rodando os testes
Pela linha de comando, os testes são rodados de forma _headless_, ou seja, o navegador não é aberto na tela, e tudo é feito por baixo dos panos.

Para rodar todos os testes:

```console
$ node_modules/.bin/cypress run
```

Para rodar testes específicos:
```console
$ npm run cy:run -- --record --spec "cypress/integration/my-spec.js"
```

Caso você queira ver o navegador durante os testes, você pode rodá-los pela interface do cypress, ou adicionar o seguinte parâmetro no console:

```console
$ node_modules/.bin/cypress run --headed
```

Para alterar o navegador, adicione o parâmetro `--browser` e o navegador que deseja usar, e.g. `--browser firefox`.

# Sobre o cypress

* Cypress recomenda rodar os seus testes no navegador Electron. Essa é uma versão mais leve do Chrome, voltada para testes automatizados.
