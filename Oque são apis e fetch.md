Objetivos

1-`Explicar oque sao apis`
2-`Ensinar como lidar com requisições dessas APIs`
3-`Apresentar o metodo fetch`


## Application Programming Interface

Uma API é uma forma de intermediar os resultados do back-end com oque é apresentado no front-end.

Você consegue acessá-la por meio de URLs


[JSON]: `Javascript Object Notation`

É muito comum que APIs retornem seus dados no formato .json, portanto precisamos tratar esses dados quando os recebermos.


## Fetch

Consumindo APIs

fetch(url,options)
.then (response=>response.json())
.then(json=>console.log(json))

// retorna uma promise


### Operações no banco (POST,GET,PUT,DELETE,etc)


exemplo:1

fetch('https://endereco-api.com/',{method:'GET',cache:'no-cache',})
.then(response => response.json())
.then(json => console.log(json))


exemplo:2

fetch('https://endereco-api.com/',{
    method:'POST',cache:'no-cache',
    body:JSON.stringify(data)
    })

.then(response => response.json())
.then(json => console.log(json))