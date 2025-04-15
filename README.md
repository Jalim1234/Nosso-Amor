# Nosso-Amor
from zipfile import ZipFile
from io import BytesIO

html_content = """
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Nosso Amor ❤️</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            background-color: #1a1a1a;
            color: #f2f2f2;
            text-align: center;
        }

        .container {
            max-width: 800px;
            margin: 50px auto;
            background-color: #2c2c2c;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 0 10px #ff4d4d;
        }

        h1 {
            color: #ff4d4d;
        }

        .counter {
            font-size: 2em;
            margin: 20px 0;
        }

        .photo {
            margin: 30px 0;
        }

        .photo-placeholder {
            width: 100%;
            max-width: 400px;
            height: 300px;
            background-color: #444;
            border: 2px dashed #ff4d4d;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #ff4d4d;
            font-size: 1.2em;
            margin: 0 auto;
        }

        .text-box {
            margin-top: 30px;
            font-size: 1.2em;
            line-height: 1.6;
            color: #e6e6e6;
            padding: 10px;
        }

        footer {
            margin-top: 40px;
            font-size: 0.9em;
            color: #777;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Feliz 4 meses de nós ❤️</h1>
        <div class="counter" id="counter"></div>

        <div class="photo">
            <div class="photo-placeholder">
                Sua foto aqui ❤️
            </div>
        </div>

        <div class="text-box">
            <!-- Coloque aqui seu texto personalizado -->
            <p>[Seu texto especial vai aqui...]</p>
        </div>
    </div>

    <footer>
        Feito com amor 💕
    </footer>

    <script>
        function calcularDias() {
            const dataInicio = new Date('2024-12-15');
            const hoje = new Date();
            const diffTime = hoje - dataInicio;
            const diffDias = Math.floor(diffTime / (1000 * 60 * 60 * 24));

            document.getElementById('counter').innerText = `Estamos juntos há ${diffDias} dias! 💘`;
        }

        calcularDias();
    </script>
</body>
</html>
"""

with open("index.html", "w", encoding="utf-8") as f:
    f.write(html_content)

with ZipFile("site_namorados.zip", "w") as zipf:
    zipf.write("index.html")
