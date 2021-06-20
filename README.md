# formatear-input-js
formatear input 
<br>
example:
<br>
<img src="https://i.ibb.co/RvRPwrk/ejemplo.png" alt="ejemplo" >
<br>
<h3>
Code
</h3>
<pre>
<code>
'use strict';
	const input={palabra:""}	
	const numeroPartir=3;
	const letra="X"
	const separador="."
	const inpt=document.getElementById("algunId");
	inpt.addEventListener("change",(e)=>{
		inpt.value=partir(input.palabra,numeroPartir,letra,separador);
	})
	inpt.addEventListener("keypress",(e)=>{
		e.preventDefault();
		input.palabra+=e.key;
		inpt.value=partir(input.palabra,numeroPartir,letra,separador);
	});
inpt.addEventListener("keydown",(e)=>{
		if(e.key=="Backspace"){
			e.preventDefault();
			input.palabra= input.palabra.slice(0,-1);
			inpt.value= partir(input.palabra,numeroPartir,letra,separador);
		}		
	});
	const partir=(palabra,numeroPartir,letra,separador)=>{
		const inArray=palabra.split("");
		const nueva=inArray.reduce((format,actual,i)=>format + ((i+1)%numeroPartir==0 ? `${letra}${separador}`:letra) ,"");
		return (palabra.length%numeroPartir)==0 ? nueva.substring(0,nueva.length-1):nueva;
	}
</code>
</pre>
