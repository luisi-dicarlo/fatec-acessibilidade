# Botões para ajuste de tamanho da fonte

## 📌 Descrição
Foram adicionados dois botões (A+ e A-) na interface do sistema, permitindo ao usuário aumentar e diminuir o tamanho da fonte da página dinamicamente.

## 🎯 Objetivo
Melhorar a acessibilidade e usabilidade do sistema, permitindo que usuários ajustem o tamanho do texto conforme sua necessidade.

## 📝 Algoritmo 
**HTML:**
```
<button onclick="changeFont(1)">A+</button>
<button onclick="changeFont(-1)">A-</button>
```
* Cada botão chama a função ```changeFont```
* A+ envia ```1``` → aumenta a fonte
* A- envia ```-1```→ diminui a fonte

**CSS (controle da fonte):**
```
:root {
  --base-font: 16px;
}

html {
  font-size: var(--base-font);
}
```
* Cria uma variável ```--base-font```
* Essa variável define o tamanho da fonte de toda a página

**JavaScript (lógica):**
```
let currentSize = 16;

function changeFont(action) {
  currentSize += action;

  if (currentSize < 12) currentSize = 12;
  if (currentSize > 24) currentSize = 24;

  document.documentElement.style.setProperty('--base-font', currentSize + 'px');
}
```
* Guarda o tamanho atual da fonte (```currentSize```)
* Soma ou subtrai o valor recebido (```action```)
* Impede que o tamanho fique menor que 12 ou maior que 24
* Atualiza a variável CSS, mudando a fonte da página

## link para o projeto
https://github.com/luisi-dicarlo/fatec-acessibilidade/tree/atividade1

