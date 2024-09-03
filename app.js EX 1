const express = require('express');
const path = require('path');
const app = express();

// Configurando o EJS como motor de visualização
app.set('view engine', 'ejs');
app.set('views', path.join(__dirname, 'views'));

// Servir arquivos estáticos (CSS)
app.use(express.static(path.join(__dirname, 'public')));

// Middleware para processar os dados do formulário
app.use(express.urlencoded({ extended: true }));

// Função para contar o número de vogais
function contarVogais(str) {
    const vogais = /[aeiouáéíóúãõâêîôûäëïöüàèìòùAEIOUÁÉÍÓÚÃÕÂÊÎÔÛÄËÏÖÜÀÈÌÒÙ]/g;
    const correspondencias = str.match(vogais);
    return correspondencias ? correspondencias.length : 0;
}

// Rota principal
app.get('/', (req, res) => {
    res.render('index', { resultado: null });
});

// Rota para processar o formulário
app.post('/contar-vogais', (req, res) => {
    const { texto } = req.body;
    const resultado = contarVogais(texto);
    res.render('index', { resultado });
});

// Iniciar o servidor
const PORT = 3000;
app.listen(PORT, () => {
    console.log(`Servidor rodando na porta ${PORT}`);
});
