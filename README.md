<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carrito de Compras</title>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f8f9fa;
            margin: 0;
            padding: 0;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            background-color: #0056b3;
            color: white;
        }

        .social-links {
            display: flex;
            align-items: center;
        }

        .social-links a {
            margin-right: 10px;
        }

        .product {
            border: 1px solid #ccc;
            padding: 20px;
            margin: 20px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .product:hover {
            transform: translateY(-5px);
        }

        .product img {
            max-width: 100px;
            display: block;
            margin: 0 auto;
        }

        button {
            background-color: #0056b3;
            color: white;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }

        button:hover {
            background-color: #004080;
        }

        .modal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0,0,0,0.4);
        }

        .modal-content {
            background-color: #fefefe;
            margin: 15% auto;
            padding: 20px;
            border: 1px solid #888;
            width: 80%;
            border-radius: 10px;
        }

        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }

        .close:hover, .close:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }

        .confirmation {
            display: none;
            text-align: center;
            margin: 20px;
        }

        #logo {
            max-width: 150px;
        }

        #company-name {
            font-size: 24px;
            font-weight: bold;
        }

        .social-links a img {
            max-width: 30px;
            margin-right: 10px;
        }

        #search-bar {
            display: flex;
            justify-content: center;
            align-items: center;
        }

        #search-input {
            padding: 5px;
            font-size: 16px;
        }

        #search-button {
            padding: 5px 10px;
            margin-left: 5px;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <header>
        <div>
            <img id="logo" src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d8/Ford_logo.svg/2560px-Ford_logo.svg.png" alt="Ford Logo">
        </div>
        <div id="company-name">Ford Motor Company</div>
        <div class="social-links">
            <a href="https://web.whatsapp.com/"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6b/WhatsApp.svg/1200px-WhatsApp.svg.png" alt="WhatsApp"></a>
            <a href="https://www.facebook.com/fordmx/"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ee/Logo_de_Facebook.png/220px-Logo_de_Facebook.png" alt="Facebook"></a>
            <a href="https://www.instagram.com/fordmx/"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Instagram_logo_2022.svg/1200px-Instagram_logo_2022.svg.png" alt="Instagram"></a>
        </div>
        <button id="view-cart">Ver Carrito</button>
    </header>

    <div id="search-bar">
        <input type="text" id="search-input" placeholder="Buscar productos...">
        <button id="search-button">Buscar</button>
    </div>

    <main class="container">
        <div class="row" id="product-list">
            <div class="col-md-6">
                <div class="product" data-name="Mustang GT">
                    <h2>Mustang GT</h2>
                    <img src="https://build.ford.com/dig/Ford/Mustang/2024/HD-TILE/Image%5B%7CFord%7CMustang%7C2024%7C1%7C1.%7C300A.P8C..PHY..88D.89W.~2WD00_BCMAB.AC--C.13R.COU.BSHEH.BYBBR.CJPAA.LTS.51W.64T.TA6.RWD.45D.99F.FS--A.HLLAD.58V.IDBAD.SY4.44X.GT.YZTAB.CLO.%5D/EXT/1/vehicle.png" alt="Mustang GT">
                    <p>Precio: $1,234,000</p>
                    <button class="add-to-cart" data-name="Mustang GT" data-price="1234000">Agregar al Carrito</button>
                </div>
            </div>
            <div class="col-md-6">
                <div class="product" data-name="Explorer">
                    <h2>Explorer</h2>
                    <img src="https://cdn-ds.com/chrome/2024-Ford-Explorer-Base-Arecibo-PR/seo/MzI0ODgwXk1lZGlhIEdhbGxlcnk/DqRJog7xp6ANe4HE8Ajg2jhlE2AdNqH8OY1mRnta87Ls3SdoBN7oLES34eAs0zbAP2K4rBo-EjUcSnk69zVUbeg_g1k5e3af1u7tm8PWepuae0NzJ-fsO5LnRLFFL4gcNE8U7wlSkA-qP2EHfkTpPpMiBP-EpxozLqkWObfH2dA/cc_2024FOS100071_01_1280_UM.jpg" alt="Explorer">
                    <p>Precio: $757,000</p>
                    <button class="add-to-cart" data-name="Explorer" data-price="757,000">Agregar al Carrito</button>
                </div>
            </div>
            <div class="col-md-6">
                <div class="product" data-name="F-150">
                    <h2>F-150</h2>
                    <img src="https://www.ford.mx/content/dam/Ford/website-assets/latam/mx/open-graph/2023/nameplate/f-150/ford-f150-2023-pickup-trabajo-precio-versiones-info-especificaciones.jpg" alt="F-150">
                    <p>Precio: $650,000</p>
                    <button class="add-to-cart" data-name="F-150" data-price="650000">Agregar al Carrito</button>
                </div>
            </div>
            <div class="col-md-6">
                <div class="product" data-name="Escape">
                    <h2>Escape</h2>
                    <img src="https://acroadtrip.blob.core.windows.net/catalogo-imagenes/s/RT_V_b3a219c40c9c4081941cc4007fced2c9.webp" alt="Escape">
                    <p>Precio: $540,000</p>
                    <button class="add-to-cart" data-name="Escape" data-price="540000">Agregar al Carrito</button>
                </div>
            </div>
           
            <div class="col-md-6">
                <div class="product" data-name="Ranger ford">
                    <h2>Ranger ford</h2>
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcThYqCMKyOI_GiJknfAfdOkf17ct7aIt0c7fg&s" alt="Ranger ford">
                    <p>Precio: $378,000</p>
                    <button class="add-to-cart" data-name="Ranger ford" data-price="378000">Agregar al Carrito</button>
                </div>
            </div>
            <div class="col-md-6">
                <div class="product" data-name="Edge">
                    <h2>Edge</h2>
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQc7XfsAUf-819p0pbaonVJoA4L0bzpssGsYA&s" alt="Edge">
                    <p>Precio: $740,000</p>
                    <button class="add-to-cart" data-name="Edge" data-price="740000">Agregar al Carrito</button>
                </div>
            </div>
         
            <div class="col-md-6">
                <div class="product" data-name="Mach-E">
                    <h2>Mach-E</h2>
                    <img src="https://acroadtrip.blob.core.windows.net/catalogo-imagenes/s/RT_V_9b48c45ff5df45fe9c49df0636f5c65f.jpg" alt="Mach-E">
                    <p>Precio: $850,000</p>
                    <button class="add-to-cart" data-name="Mach-E" data-price="850000">Agregar al Carrito</button>
                </div>
            </div>
          
            <div class="col-md-6">
                <div class="product" data-name="Expedition">
                    <h2>Expedition</h2>
                    <img src="https://acroadtrip.blob.core.windows.net/catalogo-imagenes/l/RT_V_36bc17aee05e4895a9358436277f3223.webp" alt="Expedition">
                    <p>Precio: $980,000</p>
                    <button class="add-to-cart" data-name="Expedition" data-price="980000">Agregar al Carrito</button>
                </div>
            </div>
            
            <div class="col-md-6">
                <div class="product" data-name="Mustang Shelby GT500">
                    <h2>Mustang Shelby GT500</h2>
                    <img src="https://platform.cstatic-images.com/xlarge/in/v2/stock_photos/29389cae-5d4c-45b0-b304-a9b8230ded50/39f70863-fc48-40dd-89bc-e2826a182e0a.png" alt="Mustang Shelby GT500">
                    <p>Precio: $2,300,000</p>
                    <button class="add-to-cart" data-name="Mustang Shelby GT500" data-price="2300000">Agregar al Carrito</button>
                </div>
            </div>
          
            <div class="col-md-6">
                <div class="product" data-name="Focus">
                    <h2>Focus</h2>
                    <img src="https://d19-a.sdn.cz/d_19/c_img_QN_E6/OIqkAH.jpeg?fl=exf|crr,1.33333,0|res,1024,768,1|wrm,/watermark/sauto.png,10,10|jpg,80,,1" alt="Focus">
                    <p>Precio: $350,000</p>
                    <button class="add-to-cart" data-name="Focus" data-price="350000">Agregar al Carrito</button>
                </div>
            </div>
       
            <div class="col-md-6">
                <div class="product" data-name="Ford Mustang Dark Horse 2024">
                    <h2>Ford Mustang Dark Horse 2024</h2>
                    <img src="https://build.ford.com/dig/Ford/Mustang/2024/HD-TILE/Image%5B%7CFord%7CMustang%7C2024%7C1%7C1.%7C600A.P8R..PK1..882.89A.576.BBHAU.13K.COU.BSHEH.BY1AB.BYBBR.BYPAC.858.LTS.64R.TBC.50C.RWD.67J.96D.45B.45T.990.19X.18Z.63V.FS--A.52B.GTDAC.91B.HLLAD.SSR.58X.17P.SY4.JCBAP.44E.MAC.YZTAB.%5D/EXT/1/vehicle.png" alt="Ford Mustang Dark Horse 2024">
                    <p>Precio: $3,500,000</p>
                    <button class="add-to-cart" data-name="Ford Mustang Dark Horse 2024" data-price="3500000">Agregar al Carrito</button>
                </div>
            </div>
       
            <div class="col-md-6">
                <div class="product" data-name="Mustang Fastback">
                    <h2>Mustang Fastback</h2>
                    <img src="https://build.ford.com/dig/Ford/Mustang/2024/HD-TILE/Image%5B%7CFord%7CMustang%7C2024%7C1%7C1.%7C300A.P8C..PHY..88D.89W.~2WD00_BCMAB.AC--C.13R.COU.BSHEH.BYBBR.CJPAA.LTS.51W.64T.TA6.RWD.45D.99F.FS--A.HLLAD.58V.IDBAD.SY4.44X.GT.YZTAB.CLO.%5D/EXT/1/vehicle.png" alt="Mustang Fastback">
                    <p>Precio: $2,800,000</p>
                    <button class="add-to-cart" data-name="Mustang Fastback" data-price="2800000">Agregar al Carrito</button>
                </div>
            </div>
        </div>
    </main>

    <div id="cart-modal" class="modal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <h2>Carrito de Compras</h2>
            <ul id="cart-items"></ul>
            <form id="checkout-form">
                <h3>Datos Personales</h3>
                <label for="name">Nombre:</label>
                <input type="text" id="name" name="name" required>
                <label for="address">Dirección:</label>
                <input type="text" id="address" name="address" required>
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>
                <button type="submit" class="btn btn-primary">Confirmar Compra</button>
            </form>
        </div>
    </div>

    <div id="confirmation-message" class="confirmation">
        <h2>Gracias por tu compra</h2>
        <p id="total-amount"></p>
    </div>

    <script>
        let cart = [];

        document.querySelectorAll('.add-to-cart').forEach(button => {
            button.addEventListener('click', () => {
                const name = button.getAttribute('data-name');
                const price = button.getAttribute('data-price');
                cart.push({name, price});
                alert(`${name} ha sido agregado al carrito`);
            });
        });

        document.getElementById('view-cart').addEventListener('click', () => {
            const modal = document.getElementById('cart-modal');
            const cartItems = document.getElementById('cart-items');
            cartItems.innerHTML = '';

            renderCart();

            modal.style.display = 'block';
        });

        function renderCart() {
            const cartItems = document.getElementById('cart-items');
            cartItems.innerHTML = '';

            cart.forEach((item, index) => {
                const li = document.createElement('li');
                li.textContent = `${item.name} - $${item.price}`;
                
                const removeBtn = document.createElement('button');
                removeBtn.textContent = 'Eliminar';
                removeBtn.classList.add('btn', 'btn-danger');
                removeBtn.addEventListener('click', () => {
                    cart.splice(index, 1);
                    renderCart();
                });

                li.appendChild(removeBtn);
                cartItems.appendChild(li);
            });
        }

        document.querySelector('.close').addEventListener('click', () => {
            document.getElementById('cart-modal').style.display = 'none';
        });

        document.getElementById('checkout-form').addEventListener('submit', (e) => {
            e.preventDefault();

            const name = document.getElementById('name').value;
            const address = document.getElementById('address').value;
            const email = document.getElementById('email').value;

            let total = 0;
            cart.forEach(item => {
                total += parseFloat(item.price);
            });

            const confirmationMessage = document.getElementById('confirmation-message');
            const totalAmount = document.getElementById('total-amount');
            totalAmount.textContent = `Tu total a pagar fue de $${total}`;

            document.getElementById('cart-modal').style.display = 'none';
            confirmationMessage.style.display = 'block';
        });

        document.getElementById('search-button').addEventListener('click', () => {
            const searchTerm = document.getElementById('search-input').value.toLowerCase();
            const products = document.querySelectorAll('.product');

            products.forEach(product => {
                const productName = product.getAttribute('data-name').toLowerCase();
                if (productName.includes(searchTerm)) {
                    product.style.display = 'block';
                } else {
                    product.style.display = 'none';
                }
            });
        });
    </script>
</body>
</html>

