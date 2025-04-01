<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cadastro de Divergências em Notas Fiscais</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            min-height: 100vh;
            overflow-y: auto;
            padding: 20px;
        }

        .form-container {
            background: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 1000px;
        }

        h2 {
            text-align: center;
            margin-bottom: 20px;
            font-size: 24px;
            color: #4CAF50;
        }

        .form-group {
            margin-bottom: 20px;
            display: flex;
            align-items: center;
        }

        label {
            font-size: 14px;
            font-weight: bold;
            margin-right: 15px;
            min-width: 150px;
        }

        input, select {
            flex: 1;
            padding: 10px;
            font-size: 14px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }

        .checkbox-group {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .checkbox-group input {
            margin-right: 5px;
        }

        .note {
            font-size: 12px;
            color: #777;
            margin-top: 5px;
        }

        .form-group button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 12px;
            border-radius: 5px;
            font-size: 16px;
            width: 100%;
            cursor: pointer;
        }

        .form-group button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h2>Divergências em Notas Fiscais</h2>
        <form action="https://formspree.io/f/{your_form_id}" method="POST">
            <!-- Campo Filial -->
            <div class="form-group">
                <label>Filial</label>
                <div class="checkbox-group">
                    <label><input type="checkbox" name="filial" value="ARTUR"> ARTUR</label>
                    <label><input type="checkbox" name="filial" value="FLORIANO"> FLORIANO</label>
                    <label><input type="checkbox" name="filial" value="JOTA"> JOTA</label>
                    <label><input type="checkbox" name="filial" value="MODA"> MODA</label>
                    <label><input type="checkbox" name="filial" value="PONTO"> PONTO</label>
                </div>
            </div>

            <!-- Campo Transportadora -->
            <div class="form-group">
                <label>Transportadora</label>
                <div class="checkbox-group">
                    <label><input type="checkbox" name="transportadora" value="BRASPRESS"> BRASPRESS</label>
                    <label><input type="checkbox" id="chkOutros" value="OUTROS"> OUTROS</label>
                </div>
            </div>

            <div class="form-group" id="outrosTransportadora" style="display: none;">
                <label for="outraTransportadora">Qual é a Transportadora?</label>
                <input type="text" id="outraTransportadora" name="outraTransportadora">
            </div>

            <!-- Restante do formulário -->
            <div class="form-group">
                <label for="dataRecebimento">Data de Recebimento</label>
                <input type="date" id="dataRecebimento" name="dataRecebimento" required>
            </div>

            <div class="form-group">
                <label for="notaFiscal">Número da Nota Fiscal</label>
                <input type="text" id="notaFiscal" name="notaFiscal" required>
            </div>

            <div class="form-group">
                <label for="serieNota">Série da Nota Fiscal</label>
                <input type="text" id="serieNota" name="serieNota" required>
            </div>

            <div class="form-group">
                <label for="referencia">Referência</label>
                <input type="text" id="referencia" name="referencia" maxlength="4" required>
            </div>

            <div class="form-group">
                <label for="cor">Cor</label>
                <input type="text" id="cor" name="cor" maxlength="6" required>
            </div>

            <div class="form-group">
                <label for="tamanho">Tamanho</label>
                <input type="text" id="tamanho" name="tamanho" required>
            </div>

            <div class="form-group">
                <label for="quantidade">Quantidade</label>
                <input type="number" id="quantidade" name="quantidade" required>
            </div>

            <div class="form-group">
                <label>Divergência</label>
                <select name="divergencia" required>
                    <option value="">Selecione uma opção</option>
                    <option value="MERCADORIA PASSANDO">MERCADORIA PASSANDO</option>
                    <option value="MERCADORIA FALTANDO">MERCADORIA FALTANDO</option>
                </select>
            </div>

            <div class="form-group">
                <button type="submit">Enviar</button>
            </div>
        </form>
    </div>

    <script>
        document.getElementById('chkOutros').addEventListener('change', function() {
            document.getElementById('outrosTransportadora').style.display = this.checked ? 'block' : 'none';
        });
    </script>
</body>
</html>
