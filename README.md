# tictactoe-minimal
A minimalist solution of the classic tic tac toe game using the least characters possible.

Character count: 457

The code:
```html
<body onload="u=(n,e)=>{!(((s[0]|s[1])>>n)%2)&&(s[p]|=(1<<n),v[d](c=>((c&s[p])==c)&&alert('win')),e.target.className='a'+p,p=p?0:1)},s=[0,0],p=0,v=[7,56,224,292,146,36,273,84],d='forEach',k=document,[0,1,2,3,4,5,6,7,8][d](i=>{k.body.appendChild(e=k.createElement('div'),e.onclick=e=>u(i,e))})"/><style>div{width:30px;height:30px;margin:5px;border:black solid 1px;float:left;}div:nth-of-type(3n+1){clear:left;}.a0{background:blue}.a1{background:red}</style>
```

The board state is represented as a binary number such as:

```
000
110 => 000110001 => 49
001
```

Every action could be described as a binary operator.

Annotated code:
```javascript

u=(n,e)=>{					// update game state method

	!(((s[0]|s[1])>>n)%2)	// check current cell ticked

	&&						// if so..

	(s[p]|=(1<<n),			// update board state

	v[d](c=>				// forEach winning board state

		((c&s[p])==c)		// check winning consition

		&&					// if so..

		alert('win')),		// alert

		e.target.className='a'+p,	// update UI

		p=p?0:1				// change player
	)
},

s=[0,0],							// board state for two players
p=0,								// actual player (0,1)
v=[7,56,224,292,146,36,273,84],		// winning board states
d='forEach',						// used more than once
k=document,							// used more than once


[0,1,2,3,4,5,6,7,8][d](i=>			// render initial UI

	{k.body.appendChild(
		e=k.createElement('div'),
		e.onclick=e=>u(i,e))})		// add update handler

```
