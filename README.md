<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400;1,700&display=swap" rel="stylesheet">
    <script src="main.js" defer></script>
    <title>Calculadora de Gorjeta</title>
</head>
<body>
    <header>
        <img src="logo.svg" alt="logo">
    </header>
    <main>
        <section>
            <form>
                <div class="conta">
                    <label for="conta">Valor da conta</label>
                    <div>
                        <input type="number" name="conta" id="conta" placeholder="0">
                    </div>
                </div>

                <div class="gorjeta">
                    <label for="outra">Selecione a gorjeta %</label>
                    <div>
                        <input type="button" value="5%">
                        <input type="button" value="10%">
                        <input type="button" value="15%">
                        <input type="button" value="25%">
                        <input type="button" value="50%">
                        <input type="number" id="outra" placeholder="Outra">
                    </div>
                </div>

                <div class="pessoas">
                    <div class="textos">
                        <label for="pessoas">Nº de pessoas</label>
                        <span id="erro">Não pode ser zero!</span>
                    </div>
                    <div class="input-box">
                        <input type="number" name="pessoas" id="pessoas" placeholder="0">
                    </div>
                </div>
            </form>
        </section>

        <section class="resultados">
            <div>
                <div class="gorjeta-total">
                    <div>
                        <p>Gorjeta <strong>por pessoa</strong></p>
                    </div>
                    <strong>R$0,00</strong>
                </div>
                <div class="total">
                    <div>
                        <p>Total <strong>por pessoa</strong></p>
                    </div>
                    <strong>R$0,00</strong>
                </div>
            </div>
            <button type="button">Resetar</button>
        </section>
    </main>
</body>
</html>