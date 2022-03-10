# Objetivos

1-`Explicar como manipulá-las`
2-`Explicar oque sao Promises`
3-`Apresentar as palavras-chave "Async" e "Await"`

*Definicao*

Assíncrono
**"Que não ocorre ou não se efetiva ao mesmo tempo."**


O javascript roda de maneira síncrona.

[Synchronous]
Client      Server
requisita -> .
espera a resposta
.         <- manda a resposta

[Asynchronous]

[Client]      `Server`
[requisita]  .
[continua-trabalhando]
[pega-a-resposta-e-trabalha-na-resposta]      `manda a resposta`


## Promises

Objeto de processamento assíncrono

`Inicialmente,seu valor é desconhecido. Ela pode,então, ser resolvida ou rejeitada.`


Uma promisse pode ter 3 estados

1-*pending*
2-`Fulfilled`
3-**Rejected**

Estrutura

Exemplo:

const myPromise = new Promise((resolve, reject)=>{
    window.setTimeout(()=>{
        resolve(console.log('Resolvida!'));
    },2000);
});



## Manipulacao

const myPromise = new Promise((resolve, reject)=>{
    window.setTimeout(()=>{
        resolve(console.log('Resolvida!'));
    },2000);
});

await myPromise
    .then((result)=> result + 'passando pelo then')
    .then((result)=> result + 'e agora acabou!')
    .catch((err)=> console.log(err.message));

//após 2 segundos,retornará o valor



## Async/Await

`Funcoes assincronas precisam dessas duas palavras chave.`

async function resolvePromise(){
    const myPromise = new Promise((resolve, reject)=>{
    window.setTimeout(()=>{
        resolve(console.log('Resolvida!'));
    },2000);
});

const resolved = await myPromise
    .then((result)=> result + 'passando pelo then')
    .then((result)=> result + 'e agora acabou!')
    .catch((err)=> console.log(err.message));

    return resolved;
}

`SEMPRE QUE VC QUISER QUE A PROMISSE SEJA RESOLVIDA, É OBRIGATORIO USAR O AWAIT, PARA QUE O JAVASCRIPT ENTENDA QUE O CODIGO IRA PARAR ALI ATÉ QUE RESOLVA A PROMISE, CASO CONTRARIO O JAVASCRIPT IRA PULAR ESTE BLOCO E SEGUIRA SEM RESOLVELA`

*Funcoes assincronas tambem retornam promises*

Utilizando try..catch


async function resolvePromise(){
    const myPromise = new Promise((resolve, reject)=>{
    window.setTimeout(()=>{
        resolve(console.log('Resolvida!'));
    },3000);
});
let result;

try{
result = await myPromise
    .then((result)=> result + 'passando pelo then')
    .then((result)=> result + 'e agora acabou!')
    }
    .catch((err){ 
        console.log(err.message));
    }
    return resolved;
}
