 <!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mendespods</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #000;
      color: #fff;
    }
    header {
      background-color: #111;
      text-align: center;
      padding: 20px;
      font-size: 2rem;
      font-weight: bold;
      color: gold;
    }
    .products {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      padding: 20px;
    }
    .product {
      background: #1a1a1a;
      border: 2px solid gold;
      border-radius: 10px;
      padding: 15px;
      text-align: center;
      box-shadow: 0 0 10px rgba(255,215,0,0.3);
    }
    .product img {
      width: 100%;
      height: 200px;
      object-fit: cover;
      border-radius: 8px;
    }
    .product h3 {
      margin: 10px 0;
      color: gold;
    }
    .product p {
      margin: 5px 0;
    }
    .whatsapp-btn {
      display: inline-block;
      margin-top: 10px;
      padding: 10px 15px;
      background: #25d366;
      color: #fff;
      border-radius: 8px;
      text-decoration: none;
      font-weight: bold;
      transition: background 0.3s;
    }
    .whatsapp-btn:hover {
      background: #1ebe5c;
    }
    footer {
      background: #111;
      text-align: center;
      padding: 15px;
      margin-top: 20px;
      font-size: 0.9rem;
      color: #ccc;
    }
    /* Modal idade */
    #ageModal {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.9);
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      color: white;
      z-index: 9999;
    }
    #ageModal button {
      margin: 10px;
      padding: 10px 20px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      font-size: 1rem;
      font-weight: bold;
    }
    #enterBtn {
      background: #25d366;
      color: #fff;
    }
    #exitBtn {
      background: red;
      color: #fff;
    }
  </style>
</head>
<body>

  <div id="ageModal">
    <h2>Você tem 18 anos ou mais?</h2>
    <div>
      <button id="enterBtn">Sim</button>
      <button id="exitBtn">Não</button>
    </div>
  </div>

  <header>
    Mendespods 👑🔥
  </header>

  <main>
    <section class="products" id="products">
      <!-- Produtos -->
    </section>
  </main>

  <footer>
    © 2025 Mendespods - Todos os direitos reservados
  </footer>

  <script>
    // CONFIGURAÇÃO WHATSAPP
    const WHATSAPP_NUMBER = "5511983000691"; // teu número já adicionado
    
    // Produtos placeholder
    const products = [
      { name: "Produto 1", price: "R$ 100", img: "https://via.placeholder.com/300x200" },
      { name: "Produto 2", price: "R$ 120", img: "https://via.placeholder.com/300x200" },
      { name: "Produto 3", price: "R$ 90", img: "https://via.placeholder.com/300x200" },
      { name: "Produto 4", price: "R$ 110", img: "https://via.placeholder.com/300x200" },
      { name: "Produto 5", price: "R$ 150", img: "https://via.placeholder.com/300x200" },
      { name: "Produto 6", price: "R$ 200", img: "https://via.placeholder.com/300x200" },
      { name: "Produto 7", price: "R$ 75", img: "https://via.placeholder.com/300x200" },
      { name: "Produto 8", price: "R$ 80", img: "https://via.placeholder.com/300x200" },
      { name: "Produto 9", price: "R$ 95", img: "https://via.placeholder.com/300x200" },
      { name: "Produto 10", price: "R$ 130", img: "https://via.placeholder.com/300x200" },
      { name: "Produto 11", price: "R$ 140", img: "https://via.placeholder.com/300x200" },
      { name: "Produto 12", price: "R$ 160", img: "https://via.placeholder.com/300x200" },
    ];

    // Renderizar produtos
    const container = document.getElementById("products");
    products.forEach(p => {
      const div = document.createElement("div");
      div.classList.add("product");
      div.innerHTML = `
        <img src="${p.img}" alt="${p.name}">
        <h3>${p.name}</h3>
        <p>${p.price}</p>
        <a class="whatsapp-btn" target="_blank"
           href="https://wa.me/${WHATSAPP_NUMBER}?text=Salve,%20quero%20pedir%20${encodeURIComponent(p.name)}%20na%20Mendespods%20👊🔥">
           Pedir via WhatsApp
        </a>
      `;
      container.appendChild(div);
    });

    // Modal idade
    const ageModal = document.getElementById("ageModal");
    document.getElementById("enterBtn").onclick = () => { ageModal.style.display = "none"; };
    document.getElementById("exitBtn").onclick = () => { window.location.href = "https://www.google.com"; };
  </script>

</body>
</html>
