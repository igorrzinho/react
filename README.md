# estrutura de pastas 
## node_modules
temos em *node_modules** os módulos  que temos importados que podemos usar no nosso aplicativo
 
## public
em **public**  esta tudo oque vai ser externo e tudo que vem de fora do aplicativo 

## src
dentro do **src** esta o app react então tudo que esta na pasta **src** esta do lado do app

# vamos começar 
para criar um arquivo react sempre deve colocar:  
```` js
import React from 'react'
```` 
a funçao deve ter o mesmo nome do arquivo 
```` js
function App(){
	return(
		<>
			<p>igorrzinho</p>
		</>
	)
}
export default app()
```` 
ou pode usar:
```` js
export default function App(){
	return(
		<>
			<p>igorrzinho</p>
		</>
	)
}
```` 
só pode ser exportado **UM** componente e tem que colocar o fechamento por exemplo ao usar o  
` <br> `  
no html não precisamos fechar essa tag no react precisamos   fechar **TODAS AS TAGS**  usamos nesse caso para fechar  
`<br/>`   
constantes  
`const idade = 15`  
`const nome ='igorrzinho'`  
para usarmos constantes no html usamo {}(chaves), veja a seguir:
```` js
export default function App(){
const idade = 15  
const nome ='igorrzinho'  
	return(
		<>
			<p>{nome}</p>
			<p>{idade}</p>
		</>
	)
}
```` 
também pode usar as constantes junto com texto veja:
```` js
export default function App(){
const idade = 15  
const nome ='igor'  
	return(
		<>
			<p>{'me chamo '+ nome}</p>
			<p>{'tenho' idade + ' de idade'}</p>
		</>
	)
}
```` 
lembrando que essa sintaxe também pode ser usada para funções veja 

````js
export default function App(){
const nome =()=>{
 return('nome')
}
const idade = 15  
	return(
		<>
			<p>{'me chamo '+ nome}</p>
			<p>{'tenho' idade + ' de idade'}</p>
		</>
	)
}
```` 
___
# inserir imagens no react
para usarmos imagens no nosso aplicativo usamos 
`import nomeDeSuaPreferencia from 'nomeDaImagem.extensão'`  
e para colocar ela usamos:  
`<img src={nomeDeSuaPreferencia}/>`
note que diferente do html usamos {}(chaves) para buscar a imagem
```` js
import React from 'react'
import Imagem from 'nomeDaImagen.extensão'
export default function App(){
	return(
		<>
			<img src={Imagem}/>
		</>
	)
}
```` 
___
# criar componentes
crie um novo componente .jsx faça a importação usando 
```` jsx
import Nome from './nome'
````  
 para usarmos isso no nosso app usamos dentro do componente do app:
```` jsx
<Header/>
```` 
___
# props
para utilizarmos os props criamos uma função que tenha como parametro props
```` jsx
export default function Dados(props){
  return(
    <div>
      <p>meu nome é :{props.name}</p>
      <p>tenho a idade de :{props.idade} anos</p>
    </div>
  )
````  
e nos nosso app fazemos a importação do componentes e ultilizamos o seguinte no app:
```` jsx
function App() {
  return (
    <body>
    <Header/>
    <Dados
    name=' Igor'
    idade='15'
    />
    </body>
  );
}
```` 
podemos tambem usar constantes mas para isso usamos {} eo nome da constante:
```` jsx
function App() {
  const ida = 15;
  const name ='Igor de jesus silva';
  return (
    <body>
      <Header/>
      <Dados
		nome={name}
		idade={ida}
/>
    </body>
  );
}
export default App;
```` 
 podemos usar props dentro de outros componentes para isso so precisamos importar e usar como usamos acima:
```` jsx 
export default function user() {
  const ida = 15;
  const name ='Igor de jesus silva';
  return (
    <div>
      <Dados
		nome={name}
		idade={ida}
   		/>
    </div>
  );
}
```` 
___
# enviar funções com props
primeiro crie um props normalmente:
``` jsx
export default function Dados(props){
  return(
    <section>
      <p>nome={props.name}</p>
    </section>
  )
};
```` 
e no outro componente ao invés de passar uma constante passa uma função lembre-se de:
````jsx
export default function mydados(){
const nomedeususario=()=>{
return 'igor'
}

  return(
    <div>
    <number
    name={nomedeususario()}
    />
    </div>
  )
}
```` 
podemos por também passar funções com variáveis de parametro:
````jsx
export default function Number(props){
  const n1 = 10;
  const n2 = 15;
  return(
    <div>
    <p>{'a soma de '+n1+ ' com '+n2+ ' resulta ' + props.soma(n1,n2)}</p>
    <p> meu nome é {props.name}</p>
    </div>
  )
};
```` 
e no componente que vai receber colocamos:
````jsx
  const sum=(n1,n2)=>{
    return n1+n2
  }
  const nomedeususario=()=>{
return 'igor'
}
  return(
    <div>
    <Number
    soma={sum}
    name={nomedeususario()}
    />    
    </div>
  )
```` 
**não pode colocar () quando não é retornado uma string use somente para strings**
___
# css no react:
para importar um css podemos ultilizar duas formas:

```` js
import './nome.css'
```` 
ou
```` js
import style from './nome.modules.css' 
```` 
para ultilizar o segundo usamos:
````css
.div1{
  background: #f0f;
  width: 300px;
  height: 300px;
  margin: auto;
}
```` 
e no arquivo jsx
```` js
<div className={style.div1}></div>
```` 
## 
* para criar classes ultilize `className`;
* voce no react não pode usar classes com traço '-'
## o css global
 o css pode ser adicionado de forma global por meio do arquivo **index.css** 
## voce tambem pode ustilizar o css modules 
 voce coloca o nome do arquivo que vai estilizar e cria um arquivo css com nome de "Nome.module.css"
___
* [x] aula 9  
# fragments
é basicamente você usar o `<></>` no lugar de uma div.por exemplo para criar uma ul voce pode usar isso no lugar de uma div veja:
```` js
export default function List(){
  return(
    <>
    <ul>
    <li>ola tudo bem?</li>
    <li>como vai?</li>
    </ul>
    </>
  )
}
```` 

```` js
export default function List(){
  return(
    <div>
    <ul>
    <li>ola tudo bem?</li>
    <li>como vai?</li>
    </ul>
    </div>
  )
}
```` 

não tem porque adicionarmos mais uma div.
___
# props types
para usarmos o propTypes precisamos importar o propTypes `import PropTypes from 'prop-types'` 
```` jsx
Dados.propTypes = {
name: string,
}
```` 
o componente name so pode receber strings no momento
```` jsx
Dados.propTypes = {
name: PropTypes.string.isRequired,
}
```` 
agora o componente name so pode receber strings e é requerido
```` jsx
Dados.propTypes = {
idade: PropTypes.number,
}
````  
o componente idade so pode receber numeros no momento:
```` jsx
Dados.propTypes = {
idade: PropTypes.number.isRequired,
}
````  
agora o componente idade so pode receber números e é requerido  
esses dois não forem preenchidos e você queira que eles fossem preenchidos com algo por padrão usamos:
```` jsx
Dados.defaultProps={
  name: 'seu nome',
  idade: 0,
}
```` 
neste caso o `isRequired` não é necessário 
___ 
# eventos em react 
* os eventos do react são os mesmos do DOM
* nao tem muita diferença exeto por uma coisa bem siples: ao ultilizar o onClik ou outras funcoes do tipo nao se coloca os paranteses'()'
```` jsx
import React from 'react';
import '../App.css';

export default function Eventos(){
  function event(){
    document.write('você clicou')
  }
  return(
    <div>
     <button onClick={event} className='btn'> clique aqui</button>
    </div>
  )
};
```` 

 `<button onClick={event} className='btn'> clique aqui</button>` repare que não se coloca os parenteses'()'
---
# rendenezição
* [x] aula 09   
  no react a rendenização funcion de forma com que apenas oque sofreu alteração sera mudado
 ao criarmos uma função de relogio
```` jsx 
import React from "react";

export default function Relogio(props){
    return(
            <h1>
                {new Date().toLocaleTimeString()}
            </h1>     
    )
}
````

 e no app colocarmos ela
```` jsx 
import React from 'react';
import Ola from './relogio'

function App() {

  return (
    <div className="App">
      <Ola/>
    </div>
  )
}

export default App;

````

e no arquivo **index.js** criarmos uma funçao e chamala com o **setInterval** como no exemplo abaixo
````jsx
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';

function tick(){
ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
}
 setInterval(tick, 1000)

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();
````

ao irmos no navegador veremos que apenas oque esta sendo mudado é o **h1** onde o relogio se encontra.

___

* [x] aula 10  
# state
 a primeira coisa que devemos fazer para usar o **state** é importar-lo `import React,{useState} from 'react';` 
 para criar um **state** usamos
````
const [nome,setNome]=useState('o valor de inicio');
```` 
e para usarmo usamos: 
````
import React,{useState} from 'react';

function App() {
  const [nome,setNome]=useState('igor');

  return (
    <>
      <p>o nome é: {nome}</p>
    </>
  );
}

export default App;
```` 
 sera mostrado na tela 'o nome é: igor' 
 para mudar o valor do **useState** colocamos `setNome(oque vai receber)` nao conseguimos mudar apenas com o nome pois é uma constante. 
 a principal razão para usarmo o **useState** no lugar de uma variável é que caso o valor for mudado durante a execução sera mostrado na tela por exemplo se colocarmos um botão chamando uma função que muda o nome para Gustavo sera mostrado na tela se essa alteração acontecer em programação não sera mostrado 
````
import React,{useState} from 'react';

function App() {
  const [nome,setNome]=useState('igor');
  const mudaNome = () => {
    setNome('Gustavo')
  }
  return (
    <>
      <p>o nome é: {nome}</p>
      <button onClick={mudaNome}>muda nome</button>
    </>
  );
}

export default App;
```` 
no exemplo acima isso é demostrado ao clicar no botão muda nome chama a função `mudaNome` que altera o valor do **setNome** para Gustavo e mostar na tela 'o nome é: Gustavo' se usarmos uma variavel no lugar do setNome nao sera mostrado a alteração na tela

agora criei um componente que recebe props no app oque aparece é:
````
import React,{useState} from 'react';
import Nome from './componentes/nome';

function App() {
  const [nome,setNome]=useState('igor');
  const mudaNome = () => {
    setNome('Gustavo')
  }
  return (
    <>
    <Nome nome={nome} muda={mudaNome}/>
    </>
  );
}

export default App;

```` 
e no componente é:
````
import React,{useState} from 'react';

export default function nome(props) {

  return (
    <>
      <p>o nome é: {props.nome}</p>
      <button onClick={props.muda}>muda nome</button>
    </>
  );
}
```` 
 o resultado é o mesmo do anterior porem passaos as funçoes e o state ultilizando **props**
___

* [x] aula   11  
# eventos em react
 esse projeto consiste em uma lampada que acende e desliga conforme os clicks no botão
* no arquivo app.js 
 aqui passamos os parametros ligado e setLigado
````
import React,{useState} from 'react';
import Luz from './componentes/luz';

function App() {
    const [ligado,setLigado]=useState(false);

  return (
    <>
    <Luz ligado={ligado} setLigado={setLigado}/>
    </>
  );
}

export default App;

```` 
* no arquivo luz.jsx 
 aqui receberemos os props ligado e setLigado  
no button recebe o setLigado e retorna o contrario do ligado e caso seja true vai voltar a ser false, temos o operador ternario que caso ligado seja verdade (true) vai mostrar desligar e se nao vai mostrar ligar 
````
import React,{useState,} from 'react';
import Apagada from '../img/apagada.png';
import Acesa from '../img/acesa.png'

export default function luz(props) {

  return (
    <>
    <img src={props.ligado?Acesa:Apagada}/>
    <button onClick={()=>props.setLigado(!props.ligado)}>{props.ligado?'Desligar':'ligar'}</button>
    </>
  );
}
```` 

no react para um link nao redirecionar usamos 
````
import React,{useState} from 'react';

function App() {    
    const cancelar=(obj)=>{
      return obj.preventDefault()
}
  return (
    <>
    <a href="https://pt-br.reactjs.org/docs/getting-started.html" 
    target="_blank" 
    onClick={(e)=>cancelar(e)}> aprenda reactjs</a>
    </>
  );
}

export default App;
```` 
ao clicar no link não sera redirecionado
___

* [x] aula 12  
# rendenizaçao condicional 
## exemplo 1
 essa função mostrara um cumprimento de acordo com as horas que sao no computador da pessoa;
````
import React,{useState} from 'react';

function App() {
   const cumprimento=()=>{
     const hora= new Date().getHours();
     if (hora >= 0 && hora <13) {
       return <p>bom dia</p>
     } else if (hora >= 13 && hora < 18){
       return <p>boa tarde</p>
     }else{
       return <p>boa noite</p>
     }
   }


  return (
    <>
     {cumprimento()}
    </>
  );
}

export default App;
```` 
## exemplo 2
 nesse a função login vai mudar o valor do setLogin para o contrario do log;  
 o <p/> verfica se o log é verdade(true) caso seja chama a função msgLogin caso nao seja verdade(false) chama a função noLogin 
 ao clicar no button chama a  função login  

````
import React,{useState} from 'react';

function App() {
    const [log,setLogin]=useState(false)
    
    const login=()=>{
        setLogin(!log)
    }

    const msgLogin=()=>{
        return 'usuario logado'
    }

    const noLogin=()=>{
        return 'nao logado'
    }
     
    return (
        <>
        <p>{log?msgLogin():noLogin()}</p>
        <button onClick={login}>{log?'faça login':'sair'}</button>
        </>
    );
}

export default App;
```` 
___

* [x] aula 13 
# trabalhando com a função map
## exemplo 1 
nesse caso vai imprimir os carros na tela dessa forma: "HRVGOLFFOCUSCRUZEARGO"
````
function App() {
     const carros=['HRV','GOLF','FOCUS','CRUZE','ARGO']
    return (
        <>
            {carros}
        </>
    );
}

export default App;
````

agora nesse exemplo a funcao listaCarros vai retornar cada string do array ja tratada cada elemento sera retornada como um <p>, mas podia ser qualquer elemento HTML(p, li, button, etc...)
````
function App() {
     const carros=['HRV','GOLF','FOCUS','CRUZE','ARGO'];
     const listaCarros=carros.map(
         (c)=>
             <p>{c}</p>
     )
    return (
        <>
            {listaCarros}
        </>
    );
}

export default App;
```` 
## exemplo 2
 ### nesse usaremos uma matriz
caso deixarmos do mesmo jeito do outro nada sera retornado
````
import React,{useState} from 'react';

function App() {
     const carros=[
         {categoria:"esporte",preço:"110.000",modelo:"gof-GTI"},
         {categoria:"esporte",preço:"120.000",modelo:"camaro"},
         {categoria:"suv",preço:"85.000",modelo:"HRV"},
         {categoria:"suv",preço:"83.000",modelo:"t-cross"},
     ];
     const listaCarros=carros.map(
         (c)=>
             <p>{c}</p>
     )
    return (
        <>
            {listaCarros}
        </>
    );
}

export default App;
```` 

por isso usamos a seguinte forma 
````
import React,{useState} from 'react';

function App() {
     const carros=[
         {categoria:"esporte",preço:"110.000",modelo:"gof-GTI"},
         {categoria:"esporte",preço:"120.000",modelo:"camaro"},
         {categoria:"suv",preço:"85.000",modelo:"HRV"},
         {categoria:"suv",preço:"83.000",modelo:"t-cross"},
     ];
     const listaCarros=carros.map(
         (c)=>
             <p>{c.categoria} | {c.preço} | {c.modelo} </p>
     )
    return (
        <>
            {listaCarros}
        </>
    );
}

export default App;
```` 
agora sim cada objeto sera tratado
___

* [x] aula 14  
# formularios em React
## exemplo 1 
abaixo a useState nome inicia como uma stirng vazia e o value do input é o variavel o onChange faz com que qualquer mudança no value do input o setNome recebe a value só input  
````
import React,{useState} from 'react';

function App() {

    const [nome,setNome]=useState('');

    return (
        <>
           <label htmlFor="formNome">digite seu nome</label>
           <input type="text" name="formNome" id="formNome" value={nome} onChange={(e)=>setNome(e.target.value)} />
           <p>nome digittado:{nome}</p>
        </>
    );
}

export default App;

```` 
 abaixo é igual a anterior mas com a diferença que agora o onChange chama a função handleChangeNome que faz com que qualquer mudança no value do input o setNome recebe a value do input o funcionamento é igual
````
import React,{useState} from 'react';

function App() {

    const [nome,setNome]=useState('');
    const handleChangeNome=(e)=>{
        setNome(e.target.value)
    }
    return (
        <>
           <label htmlFor="formNome">digite seu nome</label>
           <input type="text" name="formNome" id="formNome" value={nome} onChange={(e)=>handleChangeNome(e)} />
           <p>nome digitado: {nome}</p>
        </>
    );
}

export default App;

```` 
## exemplo 2
nesse vai ser igual porem com um select
````
import React,{useState} from 'react';

function App() {

    const [carro,setCarro]=useState('hrv');
    return (
        <>
           <label htmlFor="">selecione um carro</label>
           <select value={carro} onChange={(e)=>setCarro(e.target.values)}>
               <option value="hrv">hrv</option>
               <option value="golf">golf</option>
               <option value="cruze">cruze</option>
               <option value="argo">argo</option>
           </select>
           <p>o carro selecionado: {carro}</p>
        </>
    );
}

export default App;
```` 
essa é igual a de cima mas com uma função que é chamada no onChange
````
import React,{useState} from 'react';

function App() {
    const mudaCarro=(e)=>{
        setCarro(e.target.value)
    }
    const [carro,setCarro]=useState('hrv');
    return (
        <>
           <label htmlFor="">selecione um carro</label>
           <select value={carro} onChange={(e)=>mudaCarro(e)}>
               <option value="hrv">hrv</option>
               <option value="golf">golf</option>
               <option value="cruze">cruze</option>
               <option value="argo">argo</option>
           </select>
           <p>o carro selecionado: {carro}</p>
        </>
    );
}

export default App;
```` 
___

* [x] aula 15 
# elevação de state
## exemplo 1 
nesse app captura o valor dos values do formulario e coloca dentro do objeto form  
qualquer alteração na values dos inputs chama a função handleForm que verifica o nome do input caso seja ele que sofreu alteração ja é colocado novamente o valor do value
````
import React,{useState} from 'react';

function App() {
    const [form,setForm]=useState({"dia":"","mes":"","ano":""})
    
    const handleForm=(e)=>{
        if(e.target.getAttribute('name')=='fdia'){
            setForm({"dia":e.target.value,"mes":form.mes,"ano":form.ano})

        }else if(e.target.getAttribute('name')=='fmes'){
            setForm({"dia":form.mes,"mes":e.target.value,"ano":form.ano})

        }else if(e.target.getAttribute('name')=='fano'){
            setForm({"dia":form.dia,"mes":form.mes,"ano":e.target.value})
        }
    }
    return (
        <>
        <label htmlFor="">dia</label>
        <input type="text" name="fdia" value={form.dia} onChange={(e)=>handleForm(e)} /><br />
        <label htmlFor="">mes</label>
        <input type="text" name="fmes" value={form.mes} onChange={(e)=>handleForm(e)} /><br />    
        <label htmlFor="">ano</label>
        <input type="text" name="fano" value={form.ano} onChange={(e)=>handleForm(e)} /><br />
        <p>dia digitado: {form.dia}</p>
        <p>mes digitado: {form.mes}</p>
        <p>ano digitado: {form.ano}</p>    
        </>
    );
}

export default App;

```` 

___

* [x] aula 16 
# elevação de state  
 este projeto é um sistema para ver se o aluno foi aprovado ou nao  
 no app  
 aqui passamos os props para o arquivo nota e resultado.
 para o resultado mandamos a funçao notaSomada soma as notas 
````
import React,{useState} from 'react';
import Resultado from './componentes/resultado';
import Notas from './componentes/nota';

function App() {

    const [nota1,setNota1]=useState(0)
    const [nota2,setNota2]=useState(0)
    const [nota3,setNota3]=useState(0)
    const [nota4,setNota4]=useState(0)

    const notaSomadas=()=>{

        return(parseFloat(nota1)+parseFloat(nota2)+parseFloat(nota3)+parseFloat(nota4))
    }

return(
    <>
    <Notas num={1} nota={nota1} setNota={setNota1}/>
    <Notas num={2} nota={nota2} setNota={setNota2}/>
    <Notas num={3} nota={nota3} setNota={setNota3}/>
    <Notas num={4} nota={nota4} setNota={setNota4}/>
    <Resultado somaNotas={notaSomadas()}/>
    </>
    );
}

export default App;

```` 
 no arquivo notas  
 o props.setNota vai capturar o valor digitado e passar para a nota e props.nota vai deixar o valor digitado sempre atualizado
````
import React from "react";

export default function Notas(props){

    return(
        <>
            <label >informe a nota: {props.num}</label>
            <br/>
            <input type="text" value={props.nota}  onChange={(e)=>props.setNota(e.target.value)}/>
            <br />
        </>
    );
}
```` 
 no arquivo resultado   
 mostra quanto é o props 
 verifica se o props é maior que 60 para mostrar aprovado ou nao aprovado
````
import React from "react";

export default function Resultado(props){
    return(
        <div>
        <p>soma das notas{props.somaNotas}</p>
        <p>{props.somaNotas >= 60? 'aprovado':'nao aprovado'}</p>
        </div>
    );
};>setContagem=>(contagem+1
```` 
___

* [x] aula 17
# desafio da aula 17;  
 no app
````
import React,{useState} from 'react';
import Resultado from './componentes/resultado';
import Nota from './componentes/nota';

function App() {

    const [notas,setNotas]=useState({"nota1":0,"nota2":0,"nota3":0,"nota4":0})

    const handleNotas=(e)=>{
        if (e.target.getAttribute('name')=='nota1'){
            setNotas({"nota1":e.target.value,"nota2":notas.nota2,"nota3":notas.nota3,"nota4":notas.nota4})
        } else if (e.target.getAttribute('name')=='nota2'){
            setNotas({"nota1":notas.nota1,"nota2":e.target.value,"nota3":notas.nota3,"nota4":notas.nota4})
        }else if(e.target.getAttribute('name')=='nota3'){
            setNotas({"nota1":notas.nota1,"nota2":notas.nota2,"nota3":e.target.value,"nota4":notas.nota4})
        }else if(e.target.getAttribute('name')=='nota4'){
            setNotas({"nota1":notas.nota1,"nota2":notas.nota2,"nota3":notas.nota3,"nota4":e.target.value})
        }
    }

    const notaSomada=()=>{
        return(parseFloat(notas.nota1)+parseFloat(notas.nota2)+parseFloat(notas.nota3)+parseFloat(notas.nota4))
    }


return(
    <>
    <Nota num={1} nome={'nota1'} nota={notas.nota1} setNota={handleNotas}/>
    <Nota num={2} nome={'nota2'} nota={notas.nota2} setNota={handleNotas}/>
    <Nota num={3} nome={'nota3'} nota={notas.nota3} setNota={handleNotas}/>
    <Nota num={4} nome={'nota4'} nota={notas.nota4} setNota={handleNotas}/>
    <Resultado somaNotas={notaSomada()}/>
    </>
    );
}

export default App;

```` 
 no arquivo nota
````
import React from "react";

export default function Notas(props){

    return(
        <>
            <label >informe a nota: {props.num}</label>
            <br/>
            <input type="text" name={props.nome} value={props.nota}  onChange={(e)=>props.setNota(e)}/>
            <br />
        </>
    );
}
```` 
 no arquivo resultado
````
import React from "react";

export default function>setContagem=>(contagem+1 Notas(props){

    return(
        <>
            <label >informe a nota: {props.num}</label>
            <br/>
            <input type="text" name={props.nome} value={props.nota}  onChange={(e)=>props.setNota(e)}/>
            <br />
        </>
    );
}
```` 
___

* [x] aula 18  
# contenação  
 a contenação nada mais é que voce ultilizar um elementos como uma div e usar o props para chamar oque tiver dentro dela veja abaixo:
 no arquivo app
````
import React from 'react';
import Caixa from './componentes/caixa';

export default function App() {

return(
    <>

    <Caixa>
        <p>primeiro elemento</p>
        <p>segundo elemento</p>
        <p>terceiro elemento</p>
        <p>quarto elemento</p>
        <p>quinto elemento</p>
    </Caixa>
    </>
    );
}
```` 
 no arquivo caixa:
````
import React from 'react';

export default function Caixa(props){


    return(
    <>
    
    {props.children}
    </>
    );
}
```` 
 como estamos chamando todos os children ele vai mostrar todos
 caso chamaçemos como uma array ele mostraria apenas os chamados  
````
import React from 'react';

export default function Caixa(props){


    return(
    <>
    
    {props.children[0]}
    {props.children[4]}
    </>
    );
}
```` 
 agora so vai mostrar o primeiro eo qunto elementos

___

* [x] aula 19 
# useEffect 
 primeiro importamos ele: `import React,{useEffect}from 'react';`
 agora podemos usa-lo, o **useEffect** é chamado toda vez que a pagina é carregada ou atualizada por exemplo:
 aqui ao você abrir a pagina sera dado o console.log('pagina carregada') porque a pagina foi carregada
````
import React from 'react';

export default function App() {

    useEffect(
        ()=>console.log('pagina carregada')
    )
return(
    <>

    </>
    );
}
```` 
 aqui toda vez que clicarmos no **button** aparecera um console.log("pagina carregada") porque a pagina foi atualizada 
````
import React,{useState,useEffect}from 'react';

export default function App() {
    const [contagem,setContagem]=useState(0)
    useEffect(
        ()=>console.log('pagina carregada')
    )
return(
    <>
        <p>contagem: {contagem}</p>
        <button onClick={()=>setContagem(contagem+1)}>contar</button>
    </>
    );
}
```` 
 aqui toda vez que clicar no botão vai adicionar **'contagem'+contagem** no titulo do site, perceba que tera um pequeno delay apos atualizar o valor da *contagem* ate atualizar o titulo da pagina
````
import React,{useState,useEffect}from 'react';

export default function App() {
    const [contagem,setContagem]=useState(0)
    useEffect(
        ()=>{console.log('pagina carregada')
        document.title=('contagem: '+contagem)
    }
    )
return(
    <>
        <p>contagem: {contagem}</p>
        <button onClick={()=>setContagem(contagem+1)}>contar</button>
    </>
    );
}
```` 

___ 

* [ ] aula 20 

___

* [ ] aula 21 

___

* [ ] aula 22 

___

* [ ] aula 23 

___

* [ ] aula 24 

___

* [ ] aula 25 

___

