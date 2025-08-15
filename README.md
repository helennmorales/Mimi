# Mimi
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mimi Art - Inicio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
<meta http-equiv="Permissions-Policy" content="interest-cohort=(), upselling=(), compute-pressure=(), hid=(), serial=(), bluetooth=()">
<style>
    :root {
        --primary-color: #ff6b81;
        --secondary-color: #ff4757;
        --dark-color: #2c3e50;
        --light-bg: #ecf0f1;
        --white-bg: #ffffff;
        --text-color: #34495e;
    }

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: 'Poppins', sans-serif;
    }

    body {
        background: var(--light-bg);
        color: var(--text-color);
        line-height: 1.6;
    }

    h1 {
        text-align: center;
        padding: 30px 20px;
        background: var(--dark-color);
        color: var(--white-bg);
        font-size: clamp(2rem, 5vw, 3rem);
        letter-spacing: 2px;
    }

    .section {
        padding: 40px 20px;
        max-width: 1200px;
        margin: 0 auto;
    }

    .info-box {
        background: var(--white-bg);
        border-radius: 12px;
        padding: 30px;
        margin-bottom: 40px;
        box-shadow: 0 8px 25px rgba(0,0,0,0.08);
        text-align: center;
    }

    .info-box h2 {
        color: var(--primary-color);
        margin-bottom: 20px;
        font-size: 1.8rem;
    }

    .info-box p {
        margin-bottom: 12px;
        font-size: 1rem;
    }

    .phone-box {
        display: flex;
        justify-content: center;
        gap: 8px;
        margin-top: 15px;
        flex-wrap: wrap;
    }

    .phone-box div {
        background: var(--light-bg);
        padding: 12px 18px;
        border-radius: 8px;
        font-weight: 600;
        box-shadow: 0 4px 10px rgba(0,0,0,0.05);
        transition: transform 0.3s ease, background 0.3s ease;
    }

    .phone-box div:hover {
        background: var(--primary-color);
        color: var(--white-bg);
        cursor: pointer;
        transform: translateY(-3px);
    }

    .gallery-title {
        text-align: center;
        margin-bottom: 30px;
        color: var(--primary-color);
        font-size: 2rem;
    }

    .gallery {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
        gap: 20px;
    }

    .gallery-item {
        position: relative;
        cursor: pointer;
        border-radius: 15px;
        overflow: hidden;
        box-shadow: 0 6px 20px rgba(0,0,0,0.1);
        transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .gallery-item:hover {
        transform: scale(1.03);
        box-shadow: 0 10px 30px rgba(0,0,0,0.15);
    }

    .gallery-item img {
        width: 100%;
        height: 220px;
        object-fit: cover;
        display: block;
        transition: transform 0.3s ease;
    }

    /* Modal de compra */
    .modal {
        display: none;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0,0,0,0.7);
        justify-content: center;
        align-items: center;
        z-index: 2000;
    }

    .modal-content {
        background: var(--white-bg);
        padding: 25px;
        border-radius: 15px;
        width: 350px;
        max-width: 90%;
        text-align: center;
        position: relative;
        box-shadow: 0 8px 30px rgba(0,0,0,0.3);
        animation: fadeIn 0.3s ease-out;
    }

    .modal-content img {
        width: 100%;
        border-radius: 10px;
        margin-bottom: 15px;
    }

    .modal-content h3 {
        color: var(--dark-color);
        margin-bottom: 10px;
    }

    .modal-content label {
        display: block;
        margin-bottom: 10px;
        font-weight: 600;
    }

    .modal-content input {
        width: 70px;
        padding: 8px;
        text-align: center;
        border: 1px solid #ccc;
        border-radius: 5px;
        font-size: 1rem;
    }

    .modal-content button {
        background: var(--primary-color);
        color: white;
        border: none;
        padding: 12px 25px;
        border-radius: 8px;
        cursor: pointer;
        margin-top: 20px;
        transition: background 0.3s ease, transform 0.3s ease;
        font-weight: 600;
        text-transform: uppercase;
        letter-spacing: 1px;
    }

    .modal-content button:hover {
        background: var(--secondary-color);
        transform: scale(1.05);
    }

    .close-modal {
        position: absolute;
        top: 10px;
        right: 15px;
        font-size: 2rem;
        cursor: pointer;
        color: var(--text-color);
        transition: color 0.3s;
    }

    .close-modal:hover {
        color: var(--primary-color);
    }

    /* Botón comprar */
    #buyBtn {
        position: fixed;
        bottom: 30px;
        right: 30px;
        padding: 15px 25px;
        background: var(--primary-color);
        color: white;
        border: none;
        border-radius: 50px;
        cursor: pointer;
        font-weight: 700;
        box-shadow: 0 8px 20px rgba(0,0,0,0.2);
        transition: transform 0.3s ease, background 0.3s ease;
        z-index: 1000;
        text-transform: uppercase;
        letter-spacing: 1px;
    }

    #buyBtn:hover {
        background: var(--secondary-color);
        transform: scale(1.05);
    }

    footer {
        text-align: center;
        padding: 20px;
        background: var(--dark-color);
        color: var(--white-bg);
        margin-top: 40px;
        font-size: 0.9rem;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(-20px); }
        to { opacity: 1; transform: translateY(0); }
    }
</style>
</head>
<body>

<h1>Mimi Art 🎨✨</h1>

<div class="section">
    <div class="info-box">
        <h2>ℹ️ Información de Contacto</h2>
        <p>✉️ Correo: helen.morales2609@gmail.com</p>
        <p>📞 Teléfono:</p>
        <div class="phone-box">
            <div>+56</div><div>9</div><div>2163</div><div>7749</div>
        </div>
    </div>

    <h2 class="gallery-title">🖼️ Galería de Productos</h2>
    <div class="gallery" id="gallery"></div>
</div>

<footer>© 2025 Mimi Art | Todos los derechos reservados</footer>

<div class="modal" id="modal">
    <div class="modal-content">
        <span class="close-modal" onclick="closeModal()">×</span>
        <h3 id="modalName"></h3>
        <img id="modalImage" src="">
        <label>Cantidad: <input type="number" id="quantity" value="1" min="1"></label><br>
        <button onclick="addToCart()">🛒 Agregar al carrito</button>
    </div>
</div>

<button id="buyBtn" onclick="buyAll()">🛒 Comprar carrito</button>

<script>
const gallery = document.getElementById("gallery");
const modal = document.getElementById("modal");
const modalImage = document.getElementById("modalImage");
const modalName = document.getElementById("modalName");
let currentItem = null;
let cart = [];

const images = [
    {name:"Toppers 1", img:"https://i.imgur.com/dTRygAM.jpeg"},
    {name:"Cut 1", img:"https://i.imgur.com/8jPG42Y.jpeg"},
    {name:"Cut 2", img:"https://i.imgur.com/FyZH5ff.jpeg"},
    {name:"Toppers 2", img:"https://i.imgur.com/MHgXG8g.jpeg"},
    {name:"Producto Especial", img:"https://i.imgur.com/63oVYwr.jpeg"}
];

// Cargar galería
images.forEach(item=>{
    const div=document.createElement("div");
    div.className="gallery-item";
    const img=document.createElement("img");
    img.src=item.img;
    img.alt=item.name;
    img.onclick=()=>openModal(item);
    div.appendChild(img);
    gallery.appendChild(div);
});

function openModal(item){
    currentItem=item;
    modalImage.src=item.img;
    modalName.textContent=item.name;
    modal.style.display="flex";
}

function closeModal(){ modal.style.display="none"; }

function addToCart(){
    const qty=parseInt(document.getElementById("quantity").value);
    if(qty>0){
        const exists=cart.find(i=>i.name===currentItem.name);
        if(exists) exists.qty+=qty;
        else cart.push({...currentItem, qty});
        alert(`✅ ${currentItem.name} agregado al carrito (${qty})`);
    }
    closeModal();
}

function buyAll(){
    if(cart.length===0){
        alert("❌ No hay productos en el carrito");
        return;
    }
    let msg="Hola, quiero comprar:\n";
    cart.forEach(i=> msg+=`${i.qty} x ${i.name} (${i.img})\n`);
    
    // Obtiene el número de teléfono desde el HTML y elimina los espacios y el signo '+'
    const phoneElement = document.querySelector('.phone-box');
    const phone = phoneElement.textContent.replace(/\s/g, '').replace('+', '');
    
    // La URL correcta para WhatsApp. Esto reemplaza el protocolo 'whatsapp://'
    window.open(`https://wa.me/${phone}?text=${encodeURIComponent(msg)}`,"_blank");
    cart=[];
}
</script>

</body>
</html>
