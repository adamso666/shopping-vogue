# shopping-vogue
C'est long
const productsContainer = document.getElementById("products");

const products = [
  {
    name: "Produit 1",
    price: 10.99,
    image: "product1.jpg"
  },
  {
    name: "Produit 2",
    price: 20.99,
    image: "product2.jpg"
  },
  {
    name: "Produit 3",
    price: 30.99,
    image: "product3.jpg"
  }
];

function displayProducts() {
  for (let i = 0; i < products.length; i++) {
    const product = products[i];
    const productElement = document.createElement("div");
    productElement.classList.add("product");

    const nameElement = document.createElement("h2");
    nameElement.innerText = product.name;

    const priceElement = document.createElement("p");
    priceElement.innerText = `$${product.price.toFixed(2)}`;

    const imageElement = document.createElement("img");
    imageElement.src = product.image;

    const buyButtonElement = document.createElement("button");
    buyButtonElement.innerText = "Acheter";
    buyButtonElement.addEventListener("click", () => {
      buyProduct(product);
    });

    productElement.appendChild(nameElement);
    productElement.appendChild(priceElement);
    productElement.appendChild(imageElement);
    productElement.appendChild(buyButtonElement);

    productsContainer.appendChild(productElement);
  }
}

function buyProduct(product) {
  alert(`Vous avez acheté ${product.name} pour $${product.price.toFixed(2)}`);
}

displayProducts();
