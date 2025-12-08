<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Sistema Guaraní UNS</title>
<link rel="stylesheet" href="style.css">
<script>
function login() {
    let user = document.getElementById("user").value;
    let pass = document.getElementById("pass").value;

    if (user === "jeremiasvisconti" && pass === "75174637") {
        sessionStorage.setItem("usuario", user);
        window.location.href = "panel.html";
    } else {
        alert("Usuario o contraseña incorrectos");
    }
}
</script>
</head>

<body>

<div class="login-container">
    <h2>Acceso al Sistema</h2>

    <input placeholder="Usuario" id="user" type="text">
    <input placeholder="Contraseña" id="pass" type="password">

    <button onclick="login()">Ingresar</button>
</div>

</body>
</html><!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Panel Académico</title>
<link rel="stylesheet" href="style.css">

<script>
window.onload = () => {
    const usuario = sessionStorage.getItem("usuario");
    if (!usuario) window.location.href = "index.html";
    document.getElementById("nombreAlumno").innerText = usuario.toUpperCase();
}
</script>

</head>
<body>

<div class="header">
    <h2>Sistema Guaraní UNS</h2>
</div>

<div class="sidebar">
    <p>Materias</p>
    <p>Calificaciones</p>
    <p>Inscripción</p>
    <p>Perfil</p>
</div>

<div class="main">

    <h3>Alumno: <span id="nombreAlumno"></span></h3>
    <h2>Ingeniería Civil - Materias</h2>

    <div class="materia">
        <h4>Cálculo I</h4>
        Estado: Regular<br>
        Tareas: TP Nº2 mañana
    </div>

    <div class="materia">
        <h4>Estabilidad I</h4>
        Estado: Cursando<br>
        Tareas: Problemas 3,4,7
    </div>

    <div class="materia">
        <h4>Hormigón Armado</h4>
        Estado: Regular<br>
        Tareas: Carpeta firmada
    </div>

    <div class="materia">
        <h4>Física II</h4>
        Estado: Cursando<br>
        Tareas: Guía Nº8
    </div>

</div>

</body>
</html>body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #eef1f7;
}

/* LOGIN */
.login-container {
    background: white;
    width: 350px;
    margin: 120px auto;
    padding: 25px;
    border-radius: 8px;
    box-shadow: 0px 0px 10px #aaa;
    text-align: center;
}

.login-container input {
    width: 90%;
    margin: 10px 0;
    padding: 8px;
    border-radius: 5px;
    border: solid 1px #ccc;
}

.login-container button {
    width: 95%;
    padding: 10px;
    background: #00408a;
    font-weight: bold;
    color: white;
    border: none;
    cursor: pointer;
}

/* PANEL */
.header {
    width: 100%;
    background: #002856;
    color: white;
    padding: 10px;
}

.sidebar {
    width: 210px;
    height: 100vh;
    background: #123c8a;
    padding: 20px;
    float: left;
    color: white;
}

.sidebar p {
    margin-bottom: 16px;
    border-bottom: solid 1px rgba(255,255,255,0.5);
    padding-bottom: 6px;
    cursor: pointer;
}

.main {
    margin-left: 260px;
    padding: 20px;
}

.materia {
    background: white;
    padding: 15px;
    margin-bottom: 18px;
    border-radius: 8px;
    box-shadow: 0px 0px 10px #bbb;
}
