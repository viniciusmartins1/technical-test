#### 1️⃣ Altere o texto do menu “Atendimento” (circulado em amarelo) para texto “Teste-CRO”

 
- Use seletores Javascript para alterar o texto do último botão de nome “Atendimento” para “Teste-CRO”;
```jsx
document.querySelectorAll(".mdn-Menu-list-item")[6].querySelector('.mdn-Text').innerText =  'Teste-CRO'
```

#### 2️⃣ Rolando a página para baixo, encontre a seção de cards de “Nossos produtos e novidades”, faça as seguintes alterações no card circulado em amarelo
- Alterar o background do card “Fone fixo” para cor #fff;

- Alterar a cor dos ícones do card “Fone fixo” para cor #000;

Obs.: Preferível em CSS;

```

Essa parte não se encontra mais disponível na página principal da Claro

```

#### 3️⃣ Rolando a página para baixo, encontre a seção de cards de “Autoatendimento”, faça as seguintes alterações nos cards circulados em amarelo
 
- Altere as posições entre os cards “Recarga” e “Ativar chip pré-pago”, passando o card “Ativar chip pré-pago” para frente do card “Recarga”
```jsx
(() => {
const selfServiceList = document.querySelector('.cms-ShortcutGroup');
const selfServiceItens = [...selfServiceList.children];

selfServiceList.insertBefore(selfServiceItens[3], selfServiceItens[6].nextSibling)
})()
```

 

#### 4️⃣ Faça uma cópia do último card “Fone fixo”, repetindo todas as funcionalidades como link, click e formato. Em seguida adicione está copia na primeira posição, antes do card “Promoções Verão”



- Obs.: Essa tarefa deve ser feita necessariamente em Javascript, tanto a copia quanto as funcionalidades


```

Essa parte não se encontra mais disponível na página principal da Claro

```

### 5️⃣ Volte para o header da página: Clique na seção de Serviços Digitais e deixe apenas um link, remova todas os outros


- O link que deve criar será o “Claro Educação” e o seu direcionamento é para essa URL: “[https://www.claro.com.br/servicos/saude-e-bem-estar”](https://www.claro.com.br/servicos/saude-e-bem-estar%E2%80%9D)

- Obs.: Essa tarefa deve ser feita necessariamente em Javascript, tanto a copia quanto as

funcionalidades. Não pode deixar o link atual, precisa criar um do zero

  

```jsx
(() => {
const linksList = document.querySelectorAll(".mdn-Menu-list-item")[5].querySelector('.mdn-Menu-subMenu-list').querySelector(".mdn-LinkList");
const copiedItem = linksList.children[0].cloneNode(true);

linksList.innerHTML =  "";

copiedItem.querySelector('a').innerText =  "Claro Educação";
copiedItem.setAttribute("href", "https://www.claro.com.br/servicos/saude-e-bem-estar");

linksList.appendChild(copiedItem)
})()
```

  

#### 6️⃣ Volte para o header da página. Clique na seção de Combos e estilize no mesmo modelo dos cards que estão em “Contrate” (botão amarelo canto direito do header da página)

- Obs. Essa tarefa deve ser feita necessariamente em Javascript, tanto a copia quanto as funcionalidades.

```jsx
  (() => {
  const contrateListLinks = document.querySelectorAll('.mdn-Menu-list-item')[7]
    .querySelector('.cms-Menu-shortcut-list');
  const stylesContrateListLinks = window.getComputedStyle(contrateListLinks);

  const stylesFirstLink = window.getComputedStyle(contrateListLinks.children[0].firstChild);
  const stylesAnothersLinks = window.getComputedStyle(contrateListLinks.children[1].firstChild);

  const comboListLinks = document.querySelectorAll('.mdn-Menu-list-item')[0]
    .querySelector('.mdn-LinkList');

  const linkOne = comboListLinks.children[0];
  const secondLink = comboListLinks.children[1];

  for (const propriedade of stylesContrateListLinks) {  
    const valor = stylesContrateListLinks.getPropertyValue(propriedade);
    if (valor) {
      comboListLinks.style[propriedade] = valor;
    }
  }

  for (const propriedade of stylesFirstLink) {
    const valor = stylesFirstLink.getPropertyValue(propriedade);
    if (valor) {
      linkOne.style[propriedade] = valor;
    }
  }

  for (const propriedade of stylesAnothersLinks) {
    secondLink.style[propriedade] = stylesAnothersLinks.getPropertyValue(propriedade);
  }
})();
```
  
