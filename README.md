<form id="configForm">
    <label for="theme">Tema:</label>
    <select id="theme" name="theme">
        <option value="light">Claro</option>
        <option value="dark">Escuro</option>
    </select>
    
    <label for="notifications">Notificações:</label>
    <input type="checkbox" id="notifications" name="notifications">
    
    <button type="submit">Salvar Configurações</button>
</form>
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Site</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Bem-vindo ao Meu Site</h1>
        <button id="modo-escuro">🌙 Modo Escuro</button>
    </header>
    
    <main>
        <section>
            <h2>Sobre Nós</h2>
            <p>Este é um site de exemplo para demonstrar um layout inicial com HTML, CSS e JavaScript.</p>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 Meu Site. Todos os direitos reservados.</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>
/* Estilos gerais */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    text-align: center;
    background-color: #f4f4f4;
    color: #333;
}

/* Cabeçalho */
header {
    background: #008cba;
    color: white;
    padding: 20px;
}

/* Botão modo escuro */
button {
    padding: 10px;
    border: none;
    cursor: pointer;
    background: #555;
    color: white;
    border-radius: 5px;
}

/* Seção principal */
main {
    padding: 20px;
}

/* Rodapé */
footer {
    background: #333;
    color: white;
    padding: 10px;
    position: fixed;
    width: 100%;
    bottom: 0;
}

/* Modo escuro */
.dark-mode {
    background-color: #222;
    color: white;
}// Alternar entre modo claro e escuro
document.getElementById("modo-escuro").addEventListener("click", function () {
    document.body.classList.toggle("dark-mode");
});
