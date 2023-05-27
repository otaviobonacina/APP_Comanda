<!DOCTYPE html>
<html>
<head>
	<title>Comanda</title>
</head>
<style>
    body{
    font-family: Arial, Helvetica, sans-serif;
    background-image: linear-gradient(45deg,rgb(49, 204, 243),rgb(176, 221, 241));
 }
 
 h1{color:rgb(49, 204, 243);}
    div{
        background-color: rgb(0, 0, 0,0.8);
        position: absolute;
        top:50%;
        left: 50%;
        transform: translate(-50%,-50%);
        padding: 80px;
        border-radius: 15px;
        color:white;
    }
    input{padding: 15px;
    border: none;
    outline: none;
    font-size: 15px;    
}
    label{padding: 15px;
    border: none;
    outline: none;
    font-size: 15px;    
}
button{
    background-color: rgb(49, 204, 243);
    border: none;
    padding: 15px;
    width: 100%;
    border-radius: 10px;
    color: white;  
    font-size: 15px;  
}
button:hover{
    background-color: dodgerblue;
}
 </style>
<body>
    <div>
	<h1>COMANDA</h1>
	<label for="comand">N.Comanda:</label>
	<input type="number" placeholder="N.Comanda" id="comand" name="comand" min="1" max="150"><br><br>
	<label for="data">Data:</label>
	<input type="date" placeholder="Data" id="data" name="data"><br><br>
	<label for="nome">Nome Cliente:</label>
	<input type="text" placeholder="Nome Cliente" id="nome" name="nome"><br><br>
	<label for="telefone">N.Telefone:</label>
	<input type="tel" placeholder="N.Telefone" id="telefone" name="telefone"><br><br>
	<label for="endereco">Endereço:</label>
	<input type="text" placeholder="Endereço" id="endereco" name="endereco">
	<input type="number" placeholder="Numero" id="numerocasa" name="numerocasa"><br><br>
	<label for="bairro">Bairro:</label>
	<input type="text" placeholder="Bairro" id="bairro" name="bairro"><br><br>
	<label for="tamanho">Tamanho:</label>
	<select name="tamanho" id="tamanho">
		<option value="Pequena">Pequena</option>
		<option value="Média">Média</option>
		<option value="Grande">Grande</option>
	</select><br><br>
	<label for="sabor1">Sabor 1:</label>
	<select name="sabor1" id="sabor1">
		<option value="">Escolha um sabor</option>
		<option value="Calabresa">Calabresa</option>
		<option value="Frango">Frango</option>
		<option value="Mussarela">Mussarela</option>
	</select><br><br>
			<label for="sabor2">Sabor 2:</label>
		<select name="sabor2" id="sabor2">
			<option value="">Escolha um sabor</option>
			<option value="Calabresa">Calabresa</option>
			<option value="Frango">Frango</option>
			<option value="Mussarela">Mussarela</option>
		</select><br><br>
        <label for="OBS">Observação:</label>
	<input type="text" placeholder="OBS" id="obs" name="obs"><br><br>
	</div1>
	<label for="total">Valor total:</label>
	<input type="number" placeholder="Valor total" id="total" name="total"><br><br>
	<label for="formpag">Forma de Pagamento:</label>
	<select name="formpag" id="formpag">
		<option value="CartaoDebito">Cartão Debito</option>
		<option value="CartaoCredito">Cartão Crédito</option>
        <option value="Dinheiro">Dinheiro</option>
        <option value="Pix">Pix</option>
        </select><br><br>
        <button type="button" onclick="generateOrder()">Fazer pedido</button>
        <script>
          
        
            function generateOrder() {
                 
                const nome = encodeURIComponent(document.getElementById('nome').value);
                const comand = encodeURIComponent(document.getElementById("comand").value);
                const data = encodeURIComponent(document.getElementById("data").value);
                const telefone = encodeURIComponent(document.getElementById("telefone").value);
                const endereco = encodeURIComponent(document.getElementById("endereco").value);
                const numerocasa = encodeURIComponent(document.getElementById("numerocasa").value);
                const bairro = encodeURIComponent(document.getElementById("bairro").value);
                const tamanho = encodeURIComponent(document.getElementById("tamanho").value);
                const sabor1 = encodeURIComponent(document.getElementById("sabor1").value);
                const sabor2 = encodeURIComponent(document.getElementById("sabor2").value);
                const OBS = encodeURIComponent(document.getElementById("obs").value);
                const total = encodeURIComponent(document.getElementById("total").value);
                const formpag = encodeURIComponent(document.getElementById("formpag").value);
  
                const message = `
                Novo Pedido:%0A%0A
                Número da comanda: ${comand}%0A
                Data do pedido: ${data}%0A
                Nome do cliente: ${nome}%0A
                Telefone do cliente: ${telefone}%0A
                Endereço do cliente: ${endereco}%0A
                Nº Casa: ${numerocasa}%0A 
                Bairro: ${bairro}%0A
                Tamanho da pizza: ${tamanho}%0A
                Sabores da pizza: ${sabor1} //  ${sabor2}%0A%0A
                Observação:${OBS}%0A%0A
                Total a pagar: R$${total}%0A
                Forma de pagamento: ${formpag}%0A
                `;
                const linkWhatsApp = `https://wa.me/5514991267196?text=${message}`;

			window.open(linkWhatsApp);
		
}            
    </script>
    </div>
</body>
</html> 
