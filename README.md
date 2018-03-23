Majesty
===============

majesty é um *bitcode* de testes para [ThrustJS](https://github.com/thrustjs/thrust), que utiliza [Chai](http://chaijs.com/) como biblioteca de asserção.

Majesty use [Chai](http://chaijs.com/).
Chai souce is on [GitHub](https://github.com/chaijs/chai)

v0.1.0 - Versão inicial
# Instalação

Posicionado em um app [ThrustJS](https://github.com/thrustjs/thrust), no seu terminal:

```bash
thrust install majesty
```

## Tutorial

```javascript
let majesty = require('majesty')

function exec (describe, it, beforeEach, afterEach, expect, should, assert) {
  afterEach(function() {
    //Função a ser executada antes de cada teste
  })

  beforeEach(function() {
    //Função a ser executada após cada teste
  })

  describe("Caso de teste 1", function () {

    describe("Caso de teste 1.1", function () {

      it("Executando algum teste", function (){
        expect(true).to.equal(true)
      }

    }

  }
}

let res = majesty.run(exec)

print(res.success.length, " scenarios executed with success and")
print(res.failure.length, " scenarios executed with ailure.\n")

res.failure.forEach(function (fail) {
  print("[" + fail.scenario + "] =>", fail.execption)
})
```

Para ver um caso real de uso do *bitcode*, acesse [thrust-bitcodes/database](https://github.com/thrust-bitcodes/database), lá temos vários casos de teste que contemplam toda a API do database.


## What's new

v0.1.1 - Fix: limpando histórico de execução de testes
* Correção para execuções subsequentes do método [run]
* Criação de suite test case para avaliação do _majesty_