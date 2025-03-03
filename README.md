<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Multilazo Sostenible</title>
    <style>
        /* Estilos CSS */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #e0f2e9; /* Fondo verde claro */
            color: #333333; /* Texto oscuro para mejorar contraste */
        }

        /* Encabezado */
        header {
            background-color: #2a9d8f; /* Verde sostenibilidad */
            padding: 20px;
            text-align: center;
        }

        header h1 {
            margin: 0;
            font-size: 2.5em;
            color: #ffffff;
        }

        /* Menú */
        nav {
            background-color: #264653; /* Azul oscuro */
            padding: 15px;
            position: relative;
        }

        nav ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
        }

        nav ul li {
            margin: 0 20px;
        }

        nav ul li a {
            color: #ffffff;
            text-decoration: none;
            font-size: 1.2em;
        }

        nav ul li a:hover,
        nav ul li a:focus {
            color: #e9c46a; /* Amarillo suave al pasar el ratón */
        }

        /* Botón hamburguesa para móvil */
        .hamburger {
            display: none;
            background: none;
            border: none;
            font-size: 1.5em;
            color: #ffffff;
            cursor: pointer;
        }

        /* Contenido principal */
        .main-content {
            padding: 20px;
            max-width: 800px;
            margin: 20px auto;
            background-color: #2a9d8f; /* Verde para secciones */
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            color: #ffffff; /* Texto en blanco para buen contraste en fondo oscuro */
        }

        /* Formulario de registro */
        .register-form {
            background-color: #264653; /* Azul oscuro */
            padding: 20px;
            border-radius: 10px;
            margin-top: 20px;
        }

        .register-form h2 {
            margin-top: 0;
        }

        .register-form label {
            display: block;
            margin: 10px 0 5px;
        }

        .register-form input {
            width: 100%;
            padding: 8px;
            margin-bottom: 10px;
            border: none;
            border-radius: 5px;
            background-color: #ffffff;
            color: #000000;
        }

        .register-form button {
            background-color: #e9c46a; /* Amarillo para botones */
            color: #264653;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1.1em;
            transition: background-color 0.3s ease;
        }

        .register-form button:hover,
        .register-form button:focus {
            background-color: #f4a261; /* Amarillo más oscuro */
        }

        /* Pie de página */
        footer {
            background-color: #2a9d8f;
            text-align: center;
            padding: 10px;
            margin-top: 20px;
        }

        /* Estilos para enfoque (focus) para accesibilidad */
        a:focus, button:focus, input:focus {
            outline: 2px solid #e9c46a;
        }

        /* Estilos para menú móvil */
        @media (max-width: 768px) {
            nav ul {
                flex-direction: column;
                display: none;
            }
            nav ul.active {
                display: flex;
            }
            .hamburger {
                display: block;
                position: absolute;
                right: 20px;
                top: 15px;
            }
        }
    </style>
</head>
<body>
    <!-- Encabezado -->
    <header>
        <h1>Multilazo Sostenible</h1>
    </header>

    <!-- Menú de navegación -->
    <nav>
        <button class="hamburger" id="hamburgerBtn">&#9776;</button>
        <ul>
            <li><a href="#inicio">Inicio</a></li>
            <li><a href="#solicitar-retiro">Solicitar Retiro</a></li>
            <li><a href="#agendar-cita">Agendar Cita</a></li>
            <li><a href="#inventario">Mi Inventario</a></li>
            <li><a href="#cotizar">Cotizar Servicio</a></li>
            <li><a href="#perfil">Mi Perfil</a></li>
        </ul>
    </nav>

    <!-- Contenido principal -->
    <div class="main-content" id="inicio">
        <h2>Bienvenidos a Multilazo Sostenible</h2>
        <p>Transformamos residuos en recursos. Recuperamos, restauramos y reciclamos mobiliario para instituciones públicas y particulares, promoviendo la economía circular y la sostenibilidad.</p>
    </div>

    <!-- Formulario de registro -->
    <div class="main-content">
        <div class="register-form">
            <h2>Crear Cuenta</h2>
            <form id="registerForm">
                <label for="email">Correo Electrónico:</label>
                <input type="email" id="email" name="email" required placeholder="tuemail@ejemplo.com">

                <label for="password">Contraseña:</label>
                <input type="password" id="password" name="password" required placeholder="Mínimo 8 caracteres">

                <label for="confirm-password">Confirmar Contraseña:</label>
                <input type="password" id="confirm-password" name="confirm-password" required placeholder="Repite tu contraseña">

                <button type="submit">Registrarse</button>
            </form>
        </div>
    </div>

    <!-- Pie de página -->
    <footer>
        <p>&copy; 2023 Corporación Multilazo | Contacto: info@multilazo.com</p>
    </footer>

    <!-- Scripts para manejo del formulario y menú móvil -->
    <script>
        // Manejo del formulario de registro con validación de contraseña
        document.getElementById('registerForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;
            const confirmPassword = document.getElementById('confirm-password').value;
            
            // Validación de complejidad de la contraseña: al menos 8 caracteres, una mayúscula, un número y un carácter especial
            const passwordRegex = /^(?=.*[A-Z])(?=.*\d)(?=.*[!@#$%^&*]).{8,}$/;
            if (!passwordRegex.test(password)) {
                alert('La contraseña debe tener al menos 8 caracteres, incluir una letra mayúscula, un número y un carácter especial.');
                return;
            }
            
            if (password !== confirmPassword) {
                alert('Las contraseñas no coinciden.');
                return;
            }
            
            alert(`Usuario ${email} registrado con éxito (simulación).`);
            // Aquí se integraría la lógica para enviar los datos a un backend.
        });

        // Manejo del menú hamburguesa en dispositivos móviles
        document.getElementById('hamburgerBtn').addEventListener('click', function() {
            const navUl = document.querySelector('nav ul');
            navUl.classList.toggle('active');
        });
    </script>
</body>
</html>
