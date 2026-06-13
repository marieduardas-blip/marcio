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
*
    box-sizing: border-box;
    font-family: "Space Mono", serif;
}
 
:root {
    --green-100: #f3f9fa;
    --green-200: #c5e4e7;
    --green-300: #7f9d9f;
    --green-400: #5e7a7d;
    --green-500: #547878;
    --green-800: #00494d;
    --white: #ffffff;
    --light-green: #26c0ab;
    --green-hover: #9FE8DF;
    --danger: #e17457;
}
 
body {
    background-color: var(--green-200);
}
 
header {
    display: flex;
    justify-content: center;
    padding-block: 2.8rem;
}
 
main {
    background-color: var(--white);
    padding: 2rem;
    border-radius: 1.5625rem 1.5625rem 0 0;
}
 
.conta,
.gorjeta,
.pessoas {
    margin-bottom: 2rem;
}
 
.conta label,
.gorjeta label,
.pessoas label {
    color: var(--green-500);
    font-weight: 700;
}
 
.conta div,
.pessoas .input-box {
    margin-top: 0.4rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-radius: 0.3125rem;
}
 
.conta input,
.pessoas input {
    border: none;
    width: 100%;
    font-size: 1.5rem;
    font-weight: 700;
    text-align: right;
    background: transparent;
    color: var(--green-800);
    outline: none;
}
 
/* Corrigido: faltava vírgula no seletor */
.conta input::-webkit-inner-spin-button,
.pessoas input::-webkit-inner-spin-button,
.gorjeta #outra::-webkit-inner-spin-button {
    display: none;
}
 
.gorjeta #outra:focus {
    outline: 2px solid var(--light-green);
}
 
.conta:has(input:focus) div,
.conta:has(input:hover) div,
.pessoas:has(input:focus) .input-box,
.pessoas:has(input:hover) .input-box {
    outline: 2px solid var(--light-green);
    cursor: pointer;
}
 
.gorjeta div {
    margin-top: 1rem;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
}
 
.gorjeta input {
    font-size: 1.5rem;
    font-weight: 700;
    border: none;
    border-radius: 0.3125rem;
    padding: 0.4rem;
    text-align: center;
    cursor: pointer;
    background-color: var(--green-800);
    color: var(--white);
}
 
/* Corrigido: faltava ponto e vírgula */
.gorjeta .botao-ativo {
    background-color: var(--light-green);
    color: var(--green-800);
}
 
.gorjeta input[type="button"]:hover,
.resultados button:hover {
    background-color: var(--green-hover);
    color: var(--green-800);
}
 
.gorjeta #outra {
    background-color: var(--green-100);
    color: var(--green-800);
}
 
.gorjeta #outra::placeholder {
    color: var(--green-300);
}
 
/* Corrigido: regra órfã removida, estrutura reorganizada */
.pessoas .textos {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
 
.pessoas #erro-div {
    outline: 2px solid var(--danger);
}
 
.pessoas #erro {
    font-size: 0.75rem;
    color: var(--danger);
    font-weight: 700;
    display: none;
}
 
.pessoas .input-box.erro-ativo {
    outline: 2px solid var(--danger);
}
 
.resultados {
    background-color: var(--green-800);
    border-radius: 0.9375rem;
    padding: 1.5rem;
}
 
.resultados div div {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
 
.resultados p {
    color: var(--green-400);
    font-size: 0.8125rem;
}
 
.resultados p strong {
    color: var(--white);
    font-size: 1rem;
}
 
.resultados div > strong {
    color: var(--light-green);
    font-size: 2rem;
}
 
.resultados .gorjeta-total {
    margin-bottom: 1.25rem;
}
 
.resultados .total {
    margin-bottom: 2rem;
}
 
.resultados button {
    width: 100%;
    background: var(--light-green);
    border: none;
    border-radius: 0.3125rem;
    padding: 0.8rem;
    font-size: 1.2rem;
    font-weight: 700;
    color: var(--green-800);
    cursor: pointer;
    text-transform: uppercase;
}
 
@media (min-width: 920px) {
 
    /* Corrigido: bloco movido para dentro do @media correto */
    .gorjeta #outra::-webkit-inner-spin-button {
        display: none;
    }
 
    body {
        display: flex;
        flex-direction: column;
        min-height: 100svh;
        justify-content: center;
        gap: 5rem;
    }
 
    header {
        padding: 0;
    }
 
    main {
        display: flex;
        gap: 2rem;
        max-width: 57.5rem;
        margin-inline: auto;
        border-radius: 1.5625rem;
    }
 
    main section {
        width: 100%;
    }
 
    .gorjeta div {
        grid-template-columns: 1fr 1fr 1fr;
    }
 
    .resultados {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        padding: 2.5rem;
    }
 
    .resultados div > strong {
        font-size: 3rem;
    }
}
Corrigido: chave extra removida 

let conta = 0
let pessoas = 0
let porcentagem = 0
 
Corrigido: declaração duplicada removida, seletor correto
const contaInput = document.querySelector("#conta")
contaInput.addEventListener("input", receberValorConta)
 
function receberValorConta(evento) {
    conta = Number(evento.target.value)
    calcular()
}
 
const pessoasInput = document.querySelector("#pessoas") 
Corrigido: listener duplicado e sem função removido
pessoasInput.addEventListener("input", receberQuantidadePessoas)
 
function receberQuantidadePessoas(evento) {
    const paragrafoErro = document.querySelector(".pessoas #erro")
    const divErro = document.querySelector(".pessoas .input-box")
 
    // Corrigido: bloco if/else unificado e lógica de erro corrigida
    if (evento.target.value === "0" || evento.target.value === "") {
        paragrafoErro.style.display = "block"
        divErro.classList.add("erro-ativo")
    } else {
        paragrafoErro.style.display = "none"
        divErro.classList.remove("erro-ativo")
        pessoas = Number(evento.target.value)
        calcular()
    }
}
 
const botoesGorjeta = document.querySelectorAll(".gorjeta input[type='button']")
 Corrigido: dois listeners por botão colapsados em um só
botoesGorjeta.forEach(botao => {
    botao.addEventListener("click", receberPorcentagemBotao)
})
 
function receberPorcentagemBotao(evento) {
    botoesGorjeta.forEach(botao => {
        botao.classList.remove("botao-ativo")
        if (botao.value === evento.target.value) {
            botao.classList.add("botao-ativo")
        }
    })
 
    Corrigido: valor com "%" parseado corretamente
    porcentagem = parseFloat(evento.target.value) / 100
    calcular()
}
 
Input manual de gorjeta
const outraGorjeta = document.querySelector("#outra")
outraGorjeta.addEventListener("input", (evento) => {
    botoesGorjeta.forEach(b => b.classList.remove("botao-ativo"))
    porcentagem = Number(evento.target.value) / 100
    calcular()
})
 
function calcular() {
    if (pessoas <= 0 || conta <= 0) return
 
    const gorjetaTotal = conta * porcentagem
    const gorjetaPorPessoa = gorjetaTotal / pessoas
    const totalPorPessoa = (conta + gorjetaTotal) / pessoas
 
    document.querySelector(".gorjeta-total strong:last-child").textContent =
        "R$" + gorjetaPorPessoa.toFixed(2)
    document.querySelector(".total strong:last-child").textContent =
        "R$" + totalPorPessoa.toFixed(2)
}
 
 Botão resetar
const btnResetar = document.querySelector(".resultados button")
btnResetar.addEventListener("click", () => {
    conta = 0
    pessoas = 0
    porcentagem = 0
    contaInput.value = ""
    pessoasInput.value = ""
    outraGorjeta.value = ""
    botoesGorjeta.forEach(b => b.classList.remove("botao-ativo"))
    document.querySelector(".gorjeta-total strong:last-child").textContent = "R$0,00"
    document.querySelector(".total strong:last-child").textContent = "R$0,00"
    document.querySelector(".pessoas #erro").style.display = "none"
    document.querySelector(".pessoas .input-box").classList.remove("erro-ativo")
})














