const nomes = [];

function adicionarNome() {
    const nomeInput = document.getElementById("nome");
    const nome = nomeInput.value.trim();
   
    if (nome) {
        nomes.push(nome);
        document.getElementById("listaNomes").innerText = "Nomes: " + nomes.join(", ");
        nomeInput.value = "";
    } else {
        alert("Digite um nome válido!");
    }
}

function sortearNome() {
    if (nomes.length === 0) {
        alert("Adicione pelo menos um nome antes de sortear!");
        return;
    }
   
    const indiceSorteado = Math.floor(Math.random() * nomes.length);
    alert("Nome sorteado: " + nomes[indiceSorteado]);
}

// HTML para exibir os botões e entrada de texto
document.body.innerHTML = `
    <input type="text" id="nome" placeholder="Digite um nome">
    <button onclick="adicionarNome()">Adicionar Nome</button>
    <button onclick="sortearNome()">Sortear Nome</button>
    <p id="listaNomes">Nomes: Nenhum</p>
`;
