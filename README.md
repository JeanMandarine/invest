# invest


et il me propose ça comme script pr aller chercher mon prix 

// Sélectionner la ligne du tableau
const row_8 = document.querySelector("tbody").rows[7];

// Sélectionner la sixième case de la huitième ligne du tableau
const cell_8_6 = row_8.cells[5];

// Récupérer le texte de la ligne de code 1013 du HTML de la page https://buff.163.com/goods/871803
fetch('https://buff.163.com/goods/871803')
  .then(response => response.text())
  .then(data => {
    const parser = new DOMParser();
    const htmlDoc = parser.parseFromString(data, 'text/html');
    const line_1013 = htmlDoc.querySelector("#data-options").getAttribute("data-options");

    // Coller le texte dans la sixième case de la huitième ligne du tableau
    cell_8_6.textContent = line_1013;
  })
  .catch(error => console.log(error));




ou bien ça

const valeur = document.querySelector('span[data-price]').getAttribute('data-price'); // récupère la valeur "14999"
const cell_8_6 = document.querySelector("tbody").rows[7].cells[5]; // sélectionne la sixième cellule de la huitième ligne
cell_8_6.textContent = valeur; // met à jour le contenu de la cellule avec la valeur récupérée




sachant que la ligne de code sur le site que je veux ressemble à ça 

<span class="custom-currency" data-price="14999" data-type="small" data-original-currency="CNY"  ></span>

et que je veux juste extraire le 14999 pour le coller dans mon tableau
mais ça marche pas wlh
