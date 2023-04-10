# servidor-SoAP
const express = require('express') //aqui estamos fazendo a importação da biblioteca
const app = express() //criando uma instância para a constante app
const bodyParser = require('body-parser')/*importando a biblioteca para pegar o corpo da requisição
antes da importação precisamos instalar o pacote npm install --save body-parser*/
app.use(bodyParser.urlencoded({ extended: true })) //passando os dados aninhados


app.post('/', (req, res) => {
    //pegando os dados da requisição do postman
    const nome = req.body.nome;
    const instag = req.body.instag;
    return res.json([nome, instag]);
  });

app.listen(8080,() =>{
    console.log("Servidor funcionando ") //o que aparece no terminal
})
