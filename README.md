# tictactoe-minimal
My solution of the classic tic tac toe game using the least characters possible

Annotated code:
<pre>
<code>

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

</code>
</pre>
