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

 
# state
 a primeira coisa que devemos fazer para usar o **state** é importar-lo `import React,{useState} from 'react';` 
 para criar um **state** usamos
```` js
const [nome,setNome]=useState('o valor de inicio');
```` 
e para usarmo usamos: 
```` js
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
```` js
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
```` js
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
```` js
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

# eventos em react
 esse projeto consiste em uma lampada que acende e desliga conforme os clicks no botão
* no arquivo app.js 
 aqui passamos os parametros ligado e setLigado
```` js
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
```` js
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
```` js
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


# rendenizaçao condicional 
## exemplo 1
 essa função mostrara um cumprimento de acordo com as horas que sao no computador da pessoa;
```` js
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

```` js 
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


# trabalhando com a função map
## exemplo 1 
nesse caso vai imprimir os carros na tela dessa forma: "HRVGOLFFOCUSCRUZEARGO"
```` js
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
```` js
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
```` js
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
```` js
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

 
# formularios em React
## exemplo 1 
abaixo a useState nome inicia como uma stirng vazia e o value do input é o variavel o onChange faz com que qualquer mudança no value do input o setNome recebe a value só input  
```` js
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
```` js
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
```` js
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
```` js
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

# elevação de state
## exemplo 1 
nesse app captura o valor dos values do formulario e coloca dentro do objeto form  
qualquer alteração na values dos inputs chama a função handleForm que verifica o nome do input caso seja ele que sofreu alteração ja é colocado novamente o valor do value
```` js
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

# elevação de state  
 este projeto é um sistema para ver se o aluno foi aprovado ou nao  
 no app  
 aqui passamos os props para o arquivo nota e resultado.
 para o resultado mandamos a funçao notaSomada soma as notas 
```` js
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
```` js
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
```` js
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


# desafio da aula 17;  
 no app
```` js
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


https://github.com/igorrzinho/reactreturn(
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
```` js
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
```` js
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


# contenação  
 a contenação nada mais é que voce ultilizar um elementos como uma div e usar o props para chamar oque tiver dentro dela veja abaixo:
 no arquivo app
```` js
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
```` js
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
```` js
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


# useEffect 
 primeiro importamos ele: `import React,{useEffect}from 'react';`
 agora podemos usa-lo, o **useEffect** é chamado toda vez que a pagina é carregada ou atualizada por exemplo:
 aqui ao você abrir a pagina sera dado o console.log('pagina carregada') porque a pagina foi carregada
```` js
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
```` js
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
```` js
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


# localStorage
o **localStorage** é formado basicamente por 3 funções são elas: `setItem` que vai criar ou mudar o valor da chave,`getItem` vai chamar a chave e `removeItem` vai remover a chave
```` js

import React,{useState} from 'react';

function App() {
  localStorage.setItem('nome',"igor")// vai criar ou mudar o valor de nome
  localStorage.getItem('nome')// vai chamar o nome
  localStorage.removeItem('nome')// vai remover a chave nome


  return (
    <>
      <p>como vai a vida</p>
    </>
  );
}

export default App;

```` 
## exemplo 1
nesse exemplo criei um app que ao voce clicar nos botoes (cada um chama uma função) você pode gravar, mudar, ver, ou apagar um nome do seu **localStorage**.
* o botão gravar nome chama a função armazenar e passa os parametros:'ls_nome' como chave e nome como valor
* o botão ver nome chama a função consultar e passa 'ls_nome' como parametro 
* o botão apagar nome chama a função remover e passa 'ls_nome' como parametro
```` js

import React,{useState} from 'react';

function App() {

  const [nome,setNome]=useState('')

  const armazenar=(chave,valor)=>{
    localStorage.setItem(chave,valor)
  }

  const consultar=(chave)=>{

    alert(localStorage.getItem(chave))
  }
  const remover=(chave)=>{
    localStorage.removeItem(chave)
  }


  return (
    <div>
      <label>digite um nome</label><br/>
      <input type="text" value={nome} onChange={(e)=>setNome(e.target.value)}/><br/>
      <button onClick={()=>armazenar('ls_nome',nome)}>gravar nome</button><br/>
      <button onClick={()=>consultar('ls_nome')}>ver nome</button><br/>
      <button onClick={()=>remover('ls_nome')}>apagar nome</button>
    </div>
  );
}

export default App;

```` 

___

# componentes de classe (inicio do POO)
para criar um componentes com classe usamos:
```` js
 import React from 'react';

class nomeDoComponente extends React.Component{
  render(){
    return(
      <p>hello word</p>
    )
  }
}

export default classe;

```` 

## props em componentes de classe
vai mudar apenas no componente de classe mas a forma de passar é a mesma:
```` js

import React,{useState} from 'react';
import Classe from './components/classe'

function App() {

  return (
    <>
      <Classe nome="igor"/>
    </>
  );
}

export default App;

```` 
mas na forma de colocar no outro componente muda um pouco
1. primeiro temos que colocar o método construtor nesse caso `constructor(props){}`
1. e quando formos colocar no componente usamos o this antes do props assim: `this.props.nome`
1. e colocar o super com props `super(props)` dentro do construtor mas não é obrigatório
```` js
import React from 'react';

class classe extends React.Component{
  constructor(props){//metodo construtor
    super(props)
  }

  render(){
    return(
      <p>meu nome é: {this.props.nome}</p>
    )
  }
}

export default classe;

```` 

___


# state em componetes de classe
as diferenças começam na hora de declarar uma variavel comum precisamos colocada dentro do `constructor` veja abaixo  
e antes de usar o nome da variável usamos `this.nomeDaVariavel`
```` js
import React from 'react';

class classe extends React.Component{
  constructor(){//metodo construtor
    super()

    this.nome='igor'
  }

  render(){
    return(
      <p>me chamo {this.nome}</p>
    )
  }
}

export default classe;

````

na hora de usarmos **useState** fica parecido com um arquivo json:
```` js
import React from 'react';

class classe extends React.Component{
  constructor(){//metodo construtor
    super()

    this.state={//o state aqui
      nome: 'igor',
      apelido: 'igorrzinho'
    }
  }

  render(){
    return(
      <>
        <p>me chamo :{this.state.nome}</p>
        <p>tambem conhecido como :{this.state.apelido}</p>
      </>
    )
  }
}

export default classe;


````

 agora iremos refazer o projeto da lampada, é basicamente o mesmo mudando apenas que essa é feita com componentes de classe  
* ao clicar no **button** ele vai chamar a função ligarDesligar que atribui a setState.ligado o contrario de ligado
* na imagem caso **ligado** seja 'true' vai mostrar a imagem ligada e caso seja falso aparece a imagem desligada
* e no button caso **ligado** seja 'true' vai mostrar apagar e caso seja falso aparece ligar
```` js
import React from 'react';
import Desligada from './6.png'
import Ligada from './7.png'


class luz extends React.Component{
  constructor(){//metodo construtor
    super()

    this.state={//o state aqui
      ligado: true,
    }
  }
  ligarDesligar(){
    this.setState({
      ligado:!this.state.ligado//atribui a setState.ligado o contrario de ligado
    })
  }

  render(){
    return(
      <>
      <img src={this.state.ligado ? Ligada: Desligada} />{/*caso *ligado* seja 'true' vai mostrar a imagem ligada e caso seja falso aparece a imagem desligada*/}
      <button onClick={()=>this.ligarDesligar()}>{this.state.ligado ? 'apagar': 'ligar'}</button>{/*caso *ligado* seja 'true' vai mostrar apagar e caso seja falso aparece ligar*/}
      </>
    )
  }
}

export default classe;
 
```` 

___

# parte dois state em componetes de classe
agora usamos na função que o **botão** chama, uma aerofunction dentro da função para não ter erro e ele adicionar +1 no numero
```` js
import React from 'react';



class Calc extends React.Component{
  constructor(){//metodo construtor
    super()

    this.state={//o state aqui
      numero: 0
    }
  }


  adicionar(){
    this.setState(
      ()=>({numero: this.state.numero+1})//usamos uma aerofunction para nao ter erro e ele adicionar +1 no numero
      )
  }

  render(){
    return(
      <>
      <h1>adicionar</h1>
        <button onClick={()=>this.adicionar()}>adicionar</button>{/* chama a funçao adicionar */}
        <p>o numero é: {this.state.numero}</p>{/* mostra o state numero */}
      </>
    )
  }
}
export default Calc;

````

___


## BIND em react
 o BIND vai permitir que mudar o conceito do this de um determinado elemento  
faremos um BIND para a função `ligarDesligar()` eo codigo ficou assim
* adicionamos `this.ld=this.ligarDesligar.bind(this)` para chamar a função `ligarDesligar()`
```` js
import React from 'react';
import Desligada from './6.png'
import Ligada from './7.png'


class luz extends React.Component{
  constructor(){//metodo construtor
    super()

    this.state={//o state aqui
      ligado: true,
    }
    this.ld=this.ligarDesligar.bind(this)/* foi adicionada essa funçao */
  }
  ligarDesligar(){
    this.setState({
      ligado:!this.state.ligado//atribui a setState.ligado o contrario de ligado
    })
  }

  render(){
    return(
      <>
      <img src={this.state.ligado ? Ligada: Desligada} />
      <button onClick={this.ld}>{this.state.ligado ? 'apagar': 'ligar'}</button>{/*agora nao precisa mais de ultilizar uma aerofunction para chamar a funçao*/}
      </>
    )
  }
}

export default luz;

````

* podemos ultilizar  o seguinte metodo quando ultilizamos o **BIND** para mudar um state `this.setState({ligado:!this.state.ligado})` 
```` js
import React from 'react';
import Desligada from './6.png'
import Ligada from './7.png'


class luz extends React.Component{
  constructor(){//metodo construtor
    super()

    this.state={//o state aqui
      ligado: true,
    }
    this.ld=this.ligarDesligar.bind(this)/* foi adicionada essa funçao */
  }
  ligarDesligar(){
    this.setState({ligado:!this.state.ligado})/* podemos usar esse método para mudar um state com BINDS*/
  }

  render(){
    return(
      <>
      <img src={this.state.ligado ? Ligada: Desligada} />
      <button onClick={this.ld}>{this.state.ligado ? 'apagar': 'ligar'}</button>{/*agora nao precisa mais de ultilizar uma aerofunction para chamar a funçao*/}
      </>
    )
  }
}

export default luz;

```` 

___


## ciclo de vida dos componentes 
1. Na montagem, quando uma instancia do componente esta sendo criada no DOM
	1. constructor()
	2. static getDerivedStateFromProps()
	3. render()
	4. componentDidMount()
2. na atualização do componente, por alterações causadas em props ou state, quando o componente esta sendo renderizado
	1. static getDerivedStateFromProps()
	2. shouldComponenteUpdate()
	3. getSnapshotBeforeUpdate()
	4. componentDidUpdate()
3. na desmontagem, quando o componente esta sendo removido do DOM.
	1. componentWillUnmount()
4. em tratamantos de erros, quando existir algum erro em algum momento do compente.
	1. static getDerivedStstrFromError()
	2. componentDidCatch()
ciente disso vamos começa  
o `componentDidMount()` é chamado toda vez que a pagina é criada por exemplo ao colocar na Luz apos os ligarDesligar() o seguinte codigo:
```` js

  ligarDesligar(){
    this.setState({ligado:!this.state.ligado})
  }

/* parte adicionada inicio */
  componentDidMount(){
    console.log('pagina criada');
  }
/* parte adicionada final */

  render(){
    return(

```` 
ao carregarmos a pagina **luz**
 aparecera apenas um console.log com 'pagina criada' podemos ter varias alteraçoes na pagina que so aparecera um  
mas se usarmos o `componentDidUpdate()` toda vez que luz for apagada aparecera um console.log com 'pagina atualizada'
```` js
  ligarDesligar(){
    this.setState({ligado:!this.state.ligado})
  }
/* parte adicionada inicio */
  componentDidMount(){
    console.log('pagina criada');
  }

  componentDidUpdate(){
    console.log('pagina atualizada');
  }
/* parte adicionada final */
  render(){
    return(
```` 
e o `componentWillUnmount()` vai ser chamado toda vez que a pagina **luz** for removida
```` js
  ligarDesligar(){
    this.setState({ligado:!this.state.ligado})/* podemos usar esse metodo para fazer a chamada */
  }
/* parte adicionada inicio */
  componentDidMount(){
    console.log('pagina criada');
  }

  componentDidUpdate(){
    console.log('pagina atualizada');
  }

  componentWillUnmount(){
    console.log('objeto removido');
  }
/* parte adicionada final */
  render(){
    return(
```` 
e no arquivo app
```` js

import React,{useState} from 'react';
import Luz from './components/luz'

function App() {

  const [tirar,setTirar]=useState(true)
  const tirarLuz=()=>{
    setTirar(!tirar)
  }
  return (
    <>
      {tirar ?<Luz/>:''}
    <button onClick={()=>tirarLuz()}>{tirar?'tirar a luz':'colocar a luz'}</button>
    </>
  );
}

export default App;

```` 
sempre que apertamos em tirar a luz aparecera um console.log com 'objeto removido' e quando apertarmos em colocar a lus aparecera um console.log com 'pagina carregada' pois estamos carregando a pagina **luz** 

___


# estrutura de um componentes de classes
```` js 
import React from "react";

export default class BaseClasse extends React.Component{
    constructor(props){
        //Para permitir o uso de props
        super(props)
        
        //state
        this.state={
            canal:'CFB Cursos',
            curso:'React',
            ativo:true,
            nome:this.props.nomeAluno
        }
        this.status=this.props.status
        
        //bindagem
        let ad=ativarDesativar.bind(this)

        //Instruções do construtor
    }

    //Função para manipular state
    ativarDesativar(){
        this.setState(
            state=>({
                ativo=!state.ativo
            })
        )
    }

    componentDidMount(){
        console.log('O componente foi criado')
    }

    componentDidUpdate(){
        console.log('O componente foi atualizado')
    }

    componentWillUnmount(){
        console.log('O componente foi removido')
    }

    render(){
        return(
            <>
                <h1>Componente de Classe</h1>
                <button onClick={this.ad}>Ativar Desativar</button>
                <button onClick={()=>this.ativarDesativar}>Ativar Desativar</button>
            </>
        )
    }
}
```` 

___


# variáveis globais 
 para declarar variáveis globais usamos o seguinte `static nomeVariavel='oque ela recebe'` veja no exemplo abaixo onde declaramos as variáveis nome e idd: 
```` js
export default class Global {
    static nome = 'igor'
    static idd = 15
}; 
```` 
para usarmos em outro componente primeiro importamos e depois usamos `nomeComponente.nomeVariavel` como abaixo 
```` js
import React from 'react';
import Global from './components/global';

function App() {

  return (
    <>
        <p>me chamo {Global.nome}</p>
        <p>tenho {Global.idd} de idade</p>
    </>
  );
}

export default App;

```` 
lembrando que são **VARIÁVEIS** e não muda o valor que é mostrado na tela porque não é uma useState

___


# navegando entre telas no react sem extensões 
vamos simular a navegação entre paginas no React de forma nativa  
primeiro vamos criar dois arquivos nomeados de pg1 e pg2 com uma estrutura bem simples como essa e repita para o segundo mudando apenas o numero:
```` js
import React from 'react';

export default class pg1 extends React.Component {
    render() {
        return (
             <div>
                 <h1>pagina 1</h1>
             </div>
        );
    }
};
````  
e no arquivo app colocamos o seguinte: veja nos comentarios dentro do codigo a explicação
```` js
import React,{useState,useEffect} from 'react';
import Pg1 from './components/pg1';
import Pg2 from './components/pg2';


function App() {

    const [pagina,setPagina]=useState(0)

    const links=(p)=>{
        if (p==1) {//caso p for igual a um ele abre a url a seguir
            window.open('http://localhost:3000?1','_self')
            
        } else if(p==2) {//caso p for igual a dois ele abre a url a seguir
            window.open('http://localhost:3000?2','_self')
            
        }
    }

    const retPag=()=>{
        if(pagina==1){//se pagina seja igual a um retorna pg1
            return<Pg1/>
        }else if(pagina==2){//se pagina seja igual a dois retorna pg2
            return<Pg2/>
        }else{//caso nao seja nem 1 ou 2 ele retorna a pagina a seguir
            return<div>
                        <button onClick={()=>links(1)}>pagina 1</button>{/* ao ser clicado passa o parametro 1 para a função links */}
                        <button onClick={()=>links(2)}>pagina 2</button>{/* ao ser clicado passa o parametro 2 para a função links */}
                    </div>
        }
    }

    useEffect(/* ao carregar a pagina é execultado*/
        ()=>{
        const url=window.location.href /* pega o endereço da pagina */
            const res=url.split('?')/* pega oque tem depois do ? na url */
            setPagina(res[1])/* pega a segunda parte de res */
        }
    )
  return (
    <>
        {retPag()}{/* chama a função retPag */}
    </>
  );
}

export default App;
```` 
vai aparecer inicialmente uma pagina com dois botoes, ao clicar em algum deles vai ser redirecionado para ou a pagina 1 ou a pagina 2 

___


# exercício pratico 
nesse fiz um filtro de pesquisa onde a pessoa pode pesquisar uma das 5 especies de cobra que coloquei na tabela veja a explicação no comentarios do codigo
```` js
import React,{useState} from 'react';

const cobras=[
    {nome:'cascavel', peconhenta:'sim', familia:'vibora'},
    {nome:'jararaca', peconhenta:'sim', familia:'vibora'},
    {nome:'surucucu Pico de jaca', peconhenta:'sim', familia:'vibora'},
    {nome:'coral', peconhenta:'sim', familia:'Micrurus'},
    {nome:'jiboia', peconhenta:'nao', familia:'Boidae'},
]/* matris com as especies de cobra  */

const linhas=(cat)=>{/* recebe cat como parametro e retorna as linhas da tabela */
    const li=[]
    cobras.forEach(
        (cobras)=>{
            if (cobras.nome.toUpperCase()==cat.toUpperCase() || cat.toUpperCase()== '') {/* caso cobra seja igual ao parametro cat é retornado a linha ou se cat for '' sera retornado todas as linhas */
               li.push(
                   <tr>
                       <td>{cobras.nome}</td>
                       <td>{cobras.peconhenta}</td>
                       <td>{cobras.familia}</td>
                   </tr>
               ) 
            }
        }
    )
    return li/* retorna li */
}


const tabelaCobras=(cat)=>{/* recebe cat como parametro e retorna a tabela*/
    return(
        <table>
            <thead>
                <tr>
                    <th>nomes</th>
                    <th>familia</th>
                    <th>peçonhenta</th>
                </tr>
            </thead>
            <tbody>{linhas(cat)}</tbody>{/* é o corpo da tabela e recebe as li da funçao linhas */}
        </table>
    )
}

const  pesquisa=(cat,scat)=>{/* recebe cat e scat como paremetro e retorna uma div com um label e um input */
    return(<div>
        <label>pesquise aqui o nome</label>
        <input type="text" value={cat} onChange={(e)=>scat(e.target.value)}/>{/* o onChange faz com que o scat receba o value do input ea value é o cat */}
    </div>)
}

function App() {

    const [nome,setNome]=useState('')

  return (
    <>
        {pesquisa(nome,setNome)}{/* passa o nome como cat e setNome como scat */}
        {tabelaCobras(nome)}{/* passa o nome para a função tabela cobras para fazer a pesquisa */}
    </>
  );
}

export default App;

```` 

___


# fazer uma calculadora de imc com react
ea o meu codigo é o seguinte:
```` js
import React,{useState} from "react";

const tabela=()=>{
  return(
   <table>
     <thead>
       <tr>
         <th>classificaçao</th>
         <th>IMC</th>
       </tr>
     </thead>
     <tbody>
       <tr>
         <td>abaixo do peso</td>
         <td>abaixo de 18,5</td>
       </tr>
       <tr>
         <td>peso normal</td>
         <td>entre 18,5 e 24,9</td>
       </tr>
       <tr>
         <td>sobre pesso</td>
         <td>entre 25 e 29,9</td>
       </tr>
       <tr>
         <td>obesidade grau 1</td>
         <td>entre 30 e 34,9</td>
       </tr>
       <tr>
         <td>obesidade grau 2</td>
         <td>entre 35 e 39,9</td>
       </tr>
       <tr>
         <td>obesidade grau 3</td>
         <td>acima de 40</td>
       </tr>
     </tbody>
   </table>
  )
}

/* captura o peso */
const peso=(p,sp)=>{//p representa peso e sp representa o setPeso
  return(
    <div>
      <label htmlFor="#peso">digite o peso</label>
      <input type="text" placeholder="peso" value={p} onChange={(e)=>sp(e.target.value)}/>{/* sp recebe o value do elemento quando tem alguma alteração */}
    </div>
  )
}


/* captura a altura */
const altura=(a,sa)=>{//a representa altura e sa representa o setAltura
  return(
    <div>
      <label htmlFor="#peso">digite a altura</label>
      <input type="text" placeholder="altura" value={a} onChange={(e)=>{sa(e.target.value)}}/>{/* sa recebe o value do elemento quando tem alguma alteração */}
    </div>
  )
}

/* calcula o imc */
 const calcular=(p,a,sr)=>{
  const calc = () =>
  {
    sr(p/(a*a))/* sr recebe o imc */
  };
  return (
    <button onClick={calc}>calcular</button> 
  );
  {/* ao clicar chama a funçao calc */}
}

/* mostra o resultado */
const resultado=(r)=>{
  return(
    <p>resultado {r.toFixed(2)}</p>
  )
  {/* mostra o r e não deixa ele ter mais de 2 cassas decimais */}
}

export default function App() {
  
    const [upeso,setUpeso]=useState('')
    const [ualtura,setUaltura]=useState('')
    const [uresultado,setUresultado]=useState(0)

    return (
       <>

       {peso(upeso,setUpeso)}
       {altura(ualtura,setUaltura)}
       {calcular(upeso,ualtura,setUresultado)}
       {resultado(uresultado)}
       {tabela()}

       </>
    );
}; 
```` 



___

 # fazer a calculadora receber componentes de props
eu criei mais 5 componente e ficou assim  
no app
```` js
import React,{useState} from "react";
import Tabela from './components/tabela';
import Altura from './components/altura';
import Peso from './components/peso';
import Resultado from "./components/resultado";
import Calcular from "./components/calcular";



/* calcula o imc */
 const calcular=(p,a,sr)=>{
  const calc = () =>
  {
    sr(p/(a*a))/* sr recebe o imc */
  };
  return (
    <button onClick={calc}>calcular</button> 
  );
  {/* ao clicar chama a funçao calc */}
}


export default function App() {
  
    const [upeso,setUpeso]=useState('')
    const [ualtura,setUaltura]=useState('')
    const [uresultado,setUresultado]=useState(0)

    return (
       <>
        <Altura a={ualtura} sa={setUaltura}/>
        <Peso p={upeso} sp={setUpeso}/>
        <Calcular p={upeso} a={ualtura} sr={setUresultado}/>
       <Resultado r={uresultado}/>
       <Tabela/>

       </>
    );
};
```` 
na tabela
```` js
import React from 'react';

export default class tabela extends React.Component{
    render() {
        return (
            <table>
            <thead>
              <tr>
                <th>classificaçao</th>
                <th>IMC</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>abaixo do peso</td>
                <td>abaixo de 18,5</td>
              </tr>
              <tr>
                <td>peso normal</td>
                <td>entre 18,5 e 24,9</td>
              </tr>
              <tr>
                <td>sobre pesso</td>
                <td>entre 25 e 29,9</td>
              </tr>
              <tr>
                <td>obesidade grau 1</td>
                <td>entre 30 e 34,9</td>
              </tr>
              <tr>
                <td>obesidade grau 2</td>
                <td>entre 35 e 39,9</td>
              </tr>
              <tr>
                <td>obesidade grau 3</td>
                <td>acima de 40</td>
              </tr>
            </tbody>
          </table>   
        );
    }
};

```` 
 no arquivo peso
```` js
import React from "react";

export default class peso extends React.Component {
    constructor(props) {
        super(props)
    }
    render() {
        return (
        <div>
            <label htmlFor="#peso">digite o peso</label>
            <input type="text" placeholder="peso" value={this.props.p} onChange={(e)=>this.props.sp(e.target.value)}/>{/* sp recebe o value do elemento quando tem alguma alteração */}
        </div>
        );
    }
};

```` 
no arquivo altura
```` js
import React from "react";

export default class peso extends React.Component {
    constructor(props) {
        super(props)
    }

    render() {
        return (
        <div>
            <label htmlFor="#peso">digite a altura</label>
            <input type="text" placeholder="altura" value={this.props.a} onChange={(e)=>{this.props.sa(e.target.value)}}/>{/* sa recebe o value do elemento quando tem alguma alteração */}
        </div>
        );
    }
};

```` 
no arquivo calcular
```` js
import React from "react";

export default class Calcular extends React.Component {
    constructor(props) {
        super(props)
    }
    render(){
        const calc = () =>{
    this.props.sr(this.props.p/(this.props.a*this.props.a))/* sr recebe o imc */
  };


  return (
    <button onClick={calc}>calcular</button> 
  );
    }
};

```` 
e no arquivo resultado
```` js]
import React from "react"

export default class Resultado extends React.Component {
    constructor(props) {
        super(props)
    }
    render() {
        return (
                <p>resultado {this.props.r.toFixed(2)}</p>
        );{/* mostra o r e não deixa ele ter mais de 2 cassas decimais */}
    }
};

```` 

___

# construindo uma calculadora com react
```` js
import React, { Fragment } from "react";

import './calculator.css';

export default class Calculator extends React.Component {
    
    constructor() {
    super()
       

    this.state={
        result:0,
        tela:' ',
    }
    }

    adigito(num){
        this.setState(
            ()=>({tela:this.state.tela+num})
        )
    }

    clear(){
        this.setState(
            ()=>({
                tela:'',
                result:0
            })
        )
    }
    
    removeOne(){
        let vtela=this.state.tela
        vtela=vtela.substring(0,(vtela.length-1))
        this.setState(
            ()=>({tela:vtela})
        )
    }

    calc (){
        this.setState(
            ()=>({result:eval(this.state.tela)})
        )
    }

    render() {
       
       return(
       <Fragment>
                <h1>calculator</h1>
                <div className="calculator"> 
                <div className="input">
                    <p className="tela">{this.state.tela}</p>
                    <p className="result">{this.state.result}</p>
                </div>
                    <button onClick={()=>this.clear()} className="btnGreen">AC</button>
                    <button onClick={()=>this.adigito('(')} className="btnBlue">(</button>
                    <button onClick={()=>this.adigito(')')} className="btnBlue">)</button>
                    <button onClick={()=>this.adigito('/')} className="btnBlue">&divide;</button>

                    <button onClick={()=>this.adigito('7')} className="btn1">7</button>
                    <button onClick={()=>this.adigito('8')} className="btn1">8</button>
                    <button onClick={()=>this.adigito('9')} className="btn1">9</button>
                    <button onClick={()=>this.adigito('*')} className="btnBlue">&times;</button>

                    <button onClick={()=>this.adigito('4')} className="btn1">4</button>
                    <button onClick={()=>this.adigito('5')} className="btn1">5</button>
                    <button onClick={()=>this.adigito('6')} className="btn1">6</button>
                    <button onClick={()=>this.adigito('-')} className="btnBlue">&ndash;</button>

                    <button onClick={()=>this.adigito('1')} className="btn1">1</button>
                    <button onClick={()=>this.adigito('2')} className="btn1">2</button>
                    <button onClick={()=>this.adigito('3')} className="btn1">3</button>
                    <button onClick={()=>this.adigito('+')} className="btnBlue">+</button>

                    <button onClick={()=>this.adigito('0')} className="btn1">0</button>
                    <button onClick={()=>this.adigito(',')} className="btn1">,</button>
                    <button onClick={()=>this.removeOne()} className="btn1">c</button>
                    <button onClick={()=>this.calc()} className="btnRes">=</button>

             </div>
             </Fragment>
       );
    }
};

```` 

___

# construindo uma aplicação para consumir com node js
o codigo da aplicaçao é a seguinte
```` js
var felinos='['+
'{"id":1, "nome":"Tigre", "nomecientifico": "Panthera tigris"},'+
'{"id":2,"nome":"Leao", "nomecientifico":"Panthera leo"},'+
'{"id":3,"nome":"Onca", "nomecientifico": "Panthera onca"},'+
'{"id":4,"nome":"Leopardo", "nomecientifico":"Panthera pardus"},'+
'{"id":5,"nome":"puma","nomecientifico":"puma concolor"}'+
']';

var http=require('http');
var server=http.createServer (function
(request, response) { response.setHeader
('Access-Control-Allow-Origin','*');
response.writeHeader (200,
{"Content-Type": "text/html"});
response.write(felinos);
response.end();
});

server.listen(3000);

````

___

# consumindo uma api usando axios 
para instalar o axios usamos se estiver usando **yarn** `yarn add axios` caso esteja ultilizando o **npm** `npm install react-axios`
## em componentes de classes 
```` js
import React from 'react';
import axios from 'axios';//importa o axios

export default class Lista extends React.Component {
    state={
        felinos:[],//state felinos
    }

    componentDidMount(){//quando o componente esta sendo criado chama essa funçao automaticamente
        let url='https://apifelinos.igorrzinho.repl.co'
        axios.get(url)
            .then(res=>{
                const dados=res.data//dados recebe os dados da api
                this.setState({felinos:dados})//state felinos recebe a constante dados
                console.log(typeof(this.state.felinos));//confere se o state felinos é realmente um objeto
            })
    }

    render() {
        return (
             <div>{this.state.felinos.map(//a funçao map percore o objeto todo e para todos oque tiver dentro e rendeniza na tela
                 felino=><div key={felino.id}>{felino.id} - {felino.nome} - {felino.nomecientifico}</div>
             )}</div>
        );
    }
};

````

___

## em componentes de funçao
```` js
import React,{useState,useEffect} from 'react';
import axios from 'axios';//importa o axios

export default function Lista (){
    const [felinos,setFelinos]=useState([])

    useEffect(()=>{//quando o componente é criado ou sofre alteração chama essa funçao automaticamente
        let url='https://apifelinos.igorrzinho.repl.co'
        axios.get(url)
            .then(res=>{
                const dados=res.data//dados recebe os dados da api
                setFelinos(dados)//state felinos recebe a constante dados
                console.log(typeof(felinos));//confere se o state felinos é realmente um objeto
            })
    })


        return(
             <div>{felinos.map(//a funçao map percore o objeto todo e para todos oque tiver dentro e rendeniza na tela
                 felino=><div key={felino.id}>{felino.id} - {felino.nome} - {felino.nomecientifico}</div>
             )}</div>
        );
};


```` 

___

 # consumindo uma API com fetch
para usar o **fetch** não precisa usar o axios
```` js
import React from 'react';

export default class Lista extends React.Component {
    state={
        felinos:[],//state felinos
    }

    componentDidMount(){//quando o componente esta sendo criado chama essa funçao automaticamente
        let url='https://apifelinos.igorrzinho.repl.co'
        fetch(url)
            .then((res)=>res.json())
            .then(
                (resultado)=>{//resultado recebe os dados da api
                const dados=resultado//dados recebe resultado
                this.setState({felinos:dados})//state felinos recebe a constante dados
                console.log(typeof(this.state.felinos));//confere se o state felinos é realmente um objeto
            }
            )
    }

    render() {
        return (
             <div>{this.state.felinos.map(//a funçao map percore o objeto todo e para todos oque tiver dentro e rendeniza na tela
                 felino=><div key={felino.id}>{felino.id} - {felino.nome} - {felino.nomecientifico}</div>
             )}</div>
        );
    }
};

````

___

# React Router
para instalar o **React Router** no yarn usamos `yarn add react-router-dom react-router` e no npm usamos `npm i react-router-dom react-router`  

criamos tres arquivos nomeados de pg1 pg2 e pg3 para usarmos como exemplo  

no arquivo index.js precisamos fazer a importação do **BrowserRouter** e usar no lugar do **React.StrictMode** assim:
```` js
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';
import {BrowserRouter} from 'react-router-dom'// importamos aqui 


ReactDOM.render(
  <BrowserRouter>{/* usamos aqui */}
    <App />
  </BrowserRouter>,
  document.getElementById('root')
);

reportWebVitals();

````

no arquivo app  
* o **Link** no `to='/'` indica para onde vai ser direcionado
* o **Route** usamos o `path=""` idicando para o endereço desejado e `element={<o que vai rendenizar}` **todos** links precisam de um desse exeto os que vão para "/" pois é a pasta padrao
```` js
import React from 'react';
import {Route,Routes,Link,BrowserRouter} from 'react-router-dom';//importamos do react router
import Pg3 from './components/pg3';
import Pg2 from './components/pg2';
import Pg1 from './components/pg1';

export default function App(){
 return(
<>
      <header>
        <ul>
            <li><Link to="/" > Home </Link> </li> {/* esse é o UNICO que não precisa criar route pois ele leva para a padrão */}
            <li><Link to="/pag1" > Página 1 </Link></li> {/* o to='' indica para onde vai ser direcionado  */}
            <li><Link to="/pag2" > Página 2 </Link></li>
            <li><Link to="/pag3" > Página 3 </Link></li>
        </ul>
      </header>
      <main>
          <Routes>
            <Route exact path="/pag1" element={<Pg1/>}/>{/* usamos o path="" idicando para o endereço desejado e element={<o que vai rendenizar} todos links precisam de um desse exeto os que vão para "/" pois é a pasta padrao/>} */}
            <Route exact path="/pag2" element={<Pg2/>}/>
            <Route exact path="/pag3" element={<Pg3/>}/>
          </Routes>
      </main>
    </>
 )
}
````

___

# o atributo key
a key deve ser usada como um id principalmente para listas onde são obrigatorias
```` js
import React from 'react';

function ListaNumeros(props){
    const num=props.numeros

    const lista_numeros=num.map(/* vai percorer a lista_numeros e retornar uma li com o numero da posição */
        (n)=><li key={n}>{n}</li>
    )
    return(<ul>{lista_numeros}</ul>)/* retorna uma lista com os numeros */
}

const Mnumeros=[1,2,3,4,5,6,7,8,9]

export default function App(){

 return(
    <>
    
        <ListaNumeros numeros={Mnumeros}/>{/* passa a array Mnumeros como parametro props  */}
    
    </>
 )
}
````