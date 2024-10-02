## Objetivo 
How about trying to match a regular expression

Additional details will be available after launching your challenge instance.
## Solución  
```bash

	function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}


```
## Notas Adicionales 
primeramente lanzamos la instancia y vemos el codigo del form donde hace referencia a el script de javascript, al inspeccionarlo vemos que en el codigo hay un comentario que dice:
`// ^p.....F!?`, asi que probe ese codigo como input y me dio la flag.
picoCTF{succ3ssfully_matchtheregex_8ad436ed}
### Referencias

