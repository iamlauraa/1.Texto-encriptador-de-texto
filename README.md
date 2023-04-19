<!DOCTYPE html>
<html>
<head>
    <title>Encriptador / Desencriptador de Texto</title>
</head>
<body>
    <h1>Encriptador / Desencriptador de Texto</h1>
    <label for="text-input">Texto:</label>
    <textarea id="text-input" rows="4" cols="50"></textarea>
    <br>
    <label for="radio-encrypt">Encriptar</label>
    <input type="radio" id="radio-encrypt" name="encriptar-desencriptar" checked>
    <label for="radio-decrypt">Desencriptar</label>
    <input type="radio" id="radio-decrypt" name="encriptar-desencriptar">
    <br>
    <button onclick="processText()">Procesar</button>
    <br>
    <label for="text-output">Resultado:</label>
    <textarea id="text-output" rows="4" cols="50" readonly></textarea>

    <script>
        function processText() {
            var inputText = document.getElementById('text-input').value;
            var outputText = '';
            var encrypt = document.getElementById('radio-encrypt').checked;

            for (var i = 0; i < inputText.length; i++) {
                var currentChar = inputText[i].toLowerCase();

                if (encrypt) {
                    switch (currentChar) {
                        case 'e':
                            outputText += 'enter';
                            break;
                        case 'i':
                            outputText += 'imes';
                            break;
                        case 'a':
                            outputText += 'ai';
                            break;
                        case 'o':
                            outputText += 'ober';
                            break;
                        case 'u':
                            outputText += 'ufat';
                            break;
                        default:
                            outputText += currentChar;
                    }
                } else {
                    switch (currentChar) {
                        case 'e':
                            if (inputText.substr(i, 5) === 'enter') {
                                outputText += 'e';
                                i += 4;
                            } else {
                                outputText += currentChar;
                            }
                            break;
                        case 'i':
                            if (inputText.substr(i, 4) === 'imes') {
                                outputText += 'i';
                                i += 3;
                            } else {
                                outputText += currentChar;
                            }
                            break;
                        case 'a':
                            if (inputText.substr(i, 2) === 'ai') {
                                outputText += 'a';
                                i += 1;
                            } else {
                                outputText += currentChar;
                            }
                            break;
                        case 'o':
                            if (inputText.substr(i, 4) === 'ober') {
                                outputText += 'o';
                                i += 3;
                            } else {
                                outputText += currentChar;
                            }
                            break;
                        case 'u':
                            if (inputText.substr(i, 4) === 'ufat') {
                                outputText += 'u';
                                i += 3;
                            } else {
                                outputText += currentChar;
                            }
                            break;
                        default:
                            outputText += currentChar;
                    }
                }
            }

            document.getElementById('text-output').value = outputText;
        }
    </script>
</body>
</html>
