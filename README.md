# php
php
<?php
header("Content-type:text/html; charset=utf8");
//var_dump($_POST);
//variaveis
$nome = "";
$email = "";
$senha = "";
$endereco = "";
$perfil = "";
//logica
if( isset($_POST["salvar"])){ // tela de cadastro de usuario
    if(isset($_POST["nome"]) && !empty($_POST["nome"])
    && isset($_POST["email"]) && !empty($_POST["email"])
    && isset($_POST["senha"]) && !empty($_POST["senha"])
    && isset($_POST["endereco"]) && !empty($_POST["endereco"])
    && isset($_POST["perfil"]) && !empty($_POST["perfil"])){
        $nome = $_POST["nome"];
        $email = $_POST["email"];
        $senha = $_POST["senha"];
        $endereco = $_POST["endereco"];
        $perfil = $_POST["perfil"];
        //echo "Usuário cadastrado com sucesso!!";
        //header("location: index.html");
        // exibir uma mensagem para o usuario utilizando o javascript
        echo "<script>
                alert('Usuário cadastrado com sucesso!!'); // exibindo a mensagem
                window.location.href = 'login.html'; // redirecionando para o login
             </script>";
    }else{ // o usuario nao preencheu todos os campos do cadastro
        header("location: cadastrousuario.html");
    }

}else if(isset($_POST["entrar"])){ // tela de login do usuario
//Atividade para casa, fazer a função de validar o e-mail e senha do sitelogin em anexo.
   echo "tela de login";
}else{ // usuario tentou burlar o sistema entrou sem preencher os formularios
    header("location: login.html");
}

?>
