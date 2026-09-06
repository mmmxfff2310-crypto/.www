header {
            padding-top: 45px;
        }

        .logo {
            letter-spacing: -2px;
        }

        .shop {
            grid-template-columns: repeat(2, 1fr);
            gap: 14px;
        }

        .product {
            min-height: 275px;
            padding: 18px 13px;
        }

        .product-icon {
            width: 68px;
            height: 68px;
            font-size: 37px;
        }

        .product h2 {
            font-size: 15px;
        }

        .price {
            font-size: 24px;
        }
    }

    @media (max-width: 430px) {

        .shop {
            grid-template-columns: 1fr;
        }

        .product {
            min-height: 260px;
        }
    }
</style>
<!-- Заголовок -->

<header>
    <h1 class="logo">Maximum Shop</h1>
    <p class="subtitle">Добро пожаловать в наш магазин</p>
</header>


<!-- Товары -->

<main class="shop">

    <div class="product">
        <div class="product-icon">🛍️</div>
        <h2>Товар №1</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(1)">
            🛒 Купить
        </button>
    </div>

    <div class="product">
        <div class="product-icon">🛍️</div>
        <h2>Товар №2</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(2)">
            🛒 Купить
        </button>
    </div>

    <div class="product">
        <div class="product-icon">🛍️</div>
        <h2>Товар №3</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(3)">
            🛒 Купить
        </button>
    </div>

    <div class="product">
        <div class="product-icon">🛍️</div>
        <h2>Товар №4</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(4)">
            🛒 Купить
        </button>
    </div>

    <div class="product">
        <div class="product-icon">🛍️</div>
        <h2>Товар №5</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(5)">
            🛒 Купить
        </button>
    </div>

    <div class="product">
        <div class="product-icon">🛍️</div>
        <h2>Товар №6</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(6)">
            🛒 Купить
        </button>
    </div>

    <div class="product">
        <div class="product-icon">🛍️</div>
        <h2>Товар №7</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(7)">
            🛒 Купить
        </button>
    </div>

    <div class="product">
        <div class="product-icon">🛍️</div>
        <h2>Товар №8</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(8)">
            🛒 Купить
        </button>
    </div>

    <div class="product">
        <div class="product-icon">🛍️</div>
        <h2>Товар №9</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(9)">
            🛒 Купить
        </button>
    </div>

    <div class="product">
        <div class="product-icon">🛍️</div>
        <h2>Товар №10</h2>
        <div class="price">20 ₽</div>
        <button class="buy-button" onclick="buy(10)">
            🛒 Купить
        </button>
    </div>

</main>


<!-- Уведомление -->

<div class="toast" id="toast">
    <div class="toast-icon">🛒</div>
    <div class="toast-text" id="toastText">
        Вы выбрали товар
    </div>
</div>


<script>

    function buy(number) {

        const toast = document.getElementById("toast");
        const text = document.getElementById("toastText");

        text.textContent =
            "Вы выбрали товар №" + number + " — 20 ₽";

        toast.classList.add("show");

        setTimeout(function() {
            toast.classList.remove("show");
        }, 2500);
    }

</script>
