@keyframes appear {
        from {
            opacity: 0;
            transform: translateY(20px);
        }

        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    /* Адаптация телефона */

    @media (max-width: 600px) {

        body {
            padding: 25px 15px;
        }

        header {
            margin-bottom: 30px;
        }

        .shop {
            grid-template-columns: 1fr;
        }

        .product:hover {
            transform: translateY(-5px);
        }
    }
</style>
<header>
    <h1>MaxFlomShop</h1>
    <p>Добро пожаловать в наш магазин</p>
</header>

<main class="shop">

    <div class="product">
        <h2>Товар №1</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(1)">Купить</button>
    </div>

    <div class="product">
        <h2>Товар №2</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(2)">Купить</button>
    </div>

    <div class="product">
        <h2>Товар №3</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(3)">Купить</button>
    </div>

    <div class="product">
        <h2>Товар №4</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(4)">Купить</button>
    </div>

    <div class="product">
        <h2>Товар №5</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(5)">Купить</button>
    </div>

    <div class="product">
        <h2>Товар №6</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(6)">Купить</button>
    </div>

    <div class="product">
        <h2>Товар №7</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(7)">Купить</button>
    </div>

    <div class="product">
        <h2>Товар №8</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(8)">Купить</button>
    </div>

    <div class="product">
        <h2>Товар №9</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(9)">Купить</button>
    </div>

    <div class="product">
        <h2>Товар №10</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(10)">Купить</button>
    </div>

</main>

<div class="message" id="message"></div>

<script>
    function buy(number) {
        const message = document.getElementById("message");

        message.textContent =
            "🛒 Вы выбрали товар №" + number + " — 20 ₽";

        message.classList.add("show");

        setTimeout(() => {
            message.classList.remove("show");
        }, 2500);
    }
</script>
