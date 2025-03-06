<<!doctype html>
<html>
<head>
  <title></title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <script src="script.js"></script>
</body>
</html><!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login - Meu Site</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <!-- Cabeçalho -->
    <header>
        <h1>Meu Site</h1>
        <button id="btn-login">🔑 Login</button>
        <button id="btn-config">⚙️ Configurações</button>
    </header>

    <!-- Formulário de Login -->
    <div id="login-modal" class="hidden">
        <h2>Faça Login</h2>
        <label>Email:</label>
        <input type="email" id="login-email" placeholder="Digite seu email...">

        <label>Senha:</label>
        <input type="password" id="login-senha" placeholder="Digite sua senha...">

        <button id="entrar">🔓 Entrar</button>
        <p>Não tem conta? <a href="#" id="criar-conta-link">Criar Conta</a></p>
        <button id="fechar-login">Fechar</button>
    </div>

    <!-- Formulário de Cadastro -->
    <div id="cadastro-modal" class="hidden">
        <h2>Criar Conta</h2>
        <label>Email:</label>
        <input type="email" id="cadastro-email" placeholder="Digite seu email...">

        <label>Senha:</label>
        <input type="password" id="cadastro-senha" placeholder="Digite sua senha...">

        <button id="criar-conta">📝 Cadastrar</button>
        <button id="fechar-cadastro">Fechar</button>
    </div>

    <!-- Seção Principal -->
    <main>
        <h2>Bem-vindo!</h2>
        <button id="btn-iniciar">🚀 Iniciar</button>
    </main>

    <!-- Rodapé -->
    <footer>
        <p>&copy; 2025 Meu Site. Todos os direitos reservados.</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>
   <body>
     <div>
       <img
/* Reset e estilo básico */
body {
    font*-family: Arial, sans-serif;
    marg*in: 0;
    padding: 0;
    text-align: center;
    background-color: #f4f4f4;
    color: #333;
}

/* Cabeçalho */
header {
    background: #008cba;
    color: white;
    padding: 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* Botões */
button {
    padding: 10px;
    border: none;
    cursor: pointer;
    border-radius: 5px;
}

#btn-iniciar {
    background: green;
    color: white;
}

#btn-login {
    background: orange;
    color: white;
}

#btn-config {
    background: gray;
    color: white;
}

/* Formulários de login e cadastro */
#login-modal, #cadastro-modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: white;
    padding: 20px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
    display: none;
    width: 300px;
    text-align: left;
}

input {
    width: 100%;
    padding: 8px;
    margin: 5px 0;
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

/* Esconder elementos */
.hidden {
    display: none;
}// Mostrar e ocultar modais
document.getElementById("btn-login").addEventListener("click", function () {
    document.getElementById("login-modal").style.display = "block";
});

document.getElementById("fechar-login").addEventListener("click", function () {
    document.getElementById("login-modal").style.display = "none";
});

document.getElementById("criar-conta-link").addEventListener("click", function (event) {
    event.preventDefault();
    document.getElementById("login-modal").style.display = "none";
    document.getElementById("cadastro-modal").style.display = "block";
});

document.getElementById("fechar-cadastro").addEventListener("click", function () {
    document.getElementById("cadastro-modal").style.display = "none";
});

// Criar Conta e Salvar no LocalStorage
document.getElementById("criar-conta").addEventListener("click", function () {
    let email = document.getElementById("cadastro-email").value;
    let senha = document.getElementById("cadastro-senha").value;

    if (!email || !senha) {
        alert("Preencha todos os campos!");
        return;
    }

    if (localStorage.getItem("userEmail")) {
        alert("Já existe uma conta cadastrada!");
        return;
    }

    localStorage.setItem("userEmail", email);
    localStorage.setItem("userSenha", senha);
    alert("Conta criada com sucesso!");

    document.getElementById("cadastro-modal").style.display = "none";
});

// Fazer Login
document.getElementById("entrar").addEventListener("click", function () {
    let email = document.getElementById("login-email").value;
    let senha = document.getElementById("login-senha").value;

    let storedEmail = localStorage.getItem("userEmail");
    let storedSenha = localStorage.getItem("userSenha");

    if (email === storedEmail && senha === storedSenha) {
        alert("Login bem-sucedido! Bem-vindo, " + email);
        document.getElementById("login-modal").style.display = "none";
    } else {
        alert("Email ou senha incorretos!");
    }
});