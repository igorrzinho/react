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
`<button onClick={event} className='btn'> clique aqui</button>`repare que não se coloca os parenteses'()'