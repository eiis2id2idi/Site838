<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Middleman - Trocas Seguras</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            background: white;
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            max-width: 500px;
            width: 100%;
            text-align: center;
        }

        h1 {
            font-size: 3em;
            color: #667eea;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .subtitle {
            color: #666;
            margin-bottom: 40px;
            font-size: 1.2em;
        }

        .link-display {
            background: #f5f5f5;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 20px;
            word-break: break-all;
            font-family: monospace;
            color: #333;
        }

        .button {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.1em;
            border-radius: 10px;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
            margin: 10px;
            width: calc(100% - 20px);
            font-weight: bold;
        }

        .button:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
        }

        .button:active {
            transform: translateY(0);
        }

        .button.secondary {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }

        .button.secondary:hover {
            box-shadow: 0 10px 25px rgba(245, 87, 108, 0.4);
        }

        .info {
            margin-top: 30px;
            padding: 20px;
            background: #f0f4ff;
            border-radius: 10px;
            color: #555;
        }

        .info h3 {
            color: #667eea;
            margin-bottom: 10px;
        }

        .status {
            margin-top: 15px;
            padding: 10px;
            border-radius: 5px;
            display: none;
        }

        .status.show {
            display: block;
        }

        .status.success {
            background: #d4edda;
            color: #155724;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>MIDDLEMAN</h1>
        <p class="subtitle">Trocas Seguras no Roblox</p>

        <div class="link-display" id="linkDisplay">
            https://www.roblox.com/share?code=79127649cd21f84fb622655801eac4e4&type=Server
        </div>

        <button class="button" onclick="gerarLink()">
            🔗 Gerar Link Servidor Privado Middleman
        </button>

        <button class="button secondary" onclick="entrarServidor()">
            🎮 Entrar no Servidor
        </button>

        <div class="status" id="status"></div>

        <div class="info">
            <h3>ℹ️ Como funciona?</h3>
            <p>1. Clique em "Gerar Link" para criar um servidor privado</p>
            <p>2. Compartilhe o link com quem vai fazer a troca</p>
            <p>3. Clique em "Entrar no Servidor" para acessar</p>
            <p>4. Faça sua troca com segurança!</p>
        </div>
    </div>

    <script>
        const serverLink = 'https://www.roblox.com/share?code=79127649cd21f84fb622655801eac4e4&type=Server';

        function gerarLink() {
            const linkDisplay = document.getElementById('linkDisplay');
            const status = document.getElementById('status');
            
            // Copia o link para a área de transferência
            navigator.clipboard.writeText(serverLink).then(() => {
                status.className = 'status show success';
                status.textContent = '✅ Link copiado para a área de transferência!';
                
                setTimeout(() => {
                    status.className = 'status';
                }, 3000);
            }).catch(() => {
                status.className = 'status show success';
                status.textContent = '✅ Link gerado com sucesso!';
                
                setTimeout(() => {
                    status.className = 'status';
                }, 3000);
            });
        }

        function entrarServidor() {
            window.open(serverLink, '_blank');
        }
    </script>
</body>
</html>
