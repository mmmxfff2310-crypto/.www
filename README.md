<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>MaxFlomShop</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      min-height: 100vh;
      font-family: Arial, sans-serif;
      color: white;
      background:
        radial-gradient(circle at 50% 0%, #006eff 0%, transparent 35%),
        linear-gradient(135deg, #020617, #001b52, #000b25);
      overflow-x: hidden;
    }

    /* Фоновое свечение */
    body::before {
      content: "";
      position: fixed;
      inset: 0;
      pointer-events: none;
      background-image:
        radial-gradient(#00bfff 1px, transparent 1px);
      background-size: 35px 35px;
      opacity: 0.12;
    }

    /* Шапка */

    header {
      text-align: center;
      padding: 60px 20px 40px;
      position: relative;
      z-index: 1;
    }

    .logo {
      font-size: clamp(40px, 8vw, 75px);
      font-weight: 900;
      letter-spacing: 3px;

      color: white;

      text-shadow:
        0 0 5px #00d9ff,
        0 0 15px #00aaff,
        0 0 30px #0077ff,
        0 0 60px #0055ff;

      animation: neon 2s ease-in-out infinite alternate;
    }

    @keyframes neon {
      from {
        text-shadow:
          0 0 5px #00d9ff,
          0 0 15px #00aaff,
          0 0 30px #0077ff;
      }

      to {
        text-shadow:
          0 0 10px white,
          0 0 25px #00d9ff,
          0 0 50px #0077ff,
          0 0 80px #0055ff;
      }
    }

    .subtitle {
      margin-top: 15px;
      color: #aeeaff;
      font-size: 18px;
    }

    /* Товары */

    .products {
      width: 92%;
      max-width: 1100px;
      margin: 0 auto;

      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 25px;

      position: relative;
      z-index: 1;
    }

    .product {
      padding: 28px;

      border-radius: 20px;

      background: rgba(0, 25, 80, 0.75);

      border: 1px solid rgba(0, 190, 255, 0.7);

      box-shadow:
        0 0 15px rgba(0, 150, 255, 0.35),
        inset 0 0 20px rgba(0, 150, 255, 0.08);

      backdrop-filter: blur(10px);

      transition:
        transform 0.3s ease,
        box-shadow 0.3s ease;
    }

    .product:hover {
      transform: translateY(-8px);

      box-shadow:
        0 0 20px #008cff,
        0 0 45px rgba(0, 120, 255, 0.5);
    }

    .product h2 {
      font-size: 26px;
      margin-bottom: 15px;
    }

    .description {
      color: #b8dcff;
      line-height: 1.5;
      margin-bottom: 20px;
    }

    .price {
      color: #00d9ff;
      font-size: 30px;
      font-weight: bold;

      margin-bottom: 20px;

      text-shadow:
        0 0 10px #008cff;
    }

    /* Кнопка */

    .buy {
      width: 100%;
      padding: 15px;

      border: none;
      border-radius: 12px;

      color: white;

      font-size: 18px;
      font-weight: bold;

      cursor: pointer;

      background:
        linear-gradient(
          90deg,
          #006eff,
          #00c8ff
        );

      box-shadow:
        0 0 15px rgba(0, 170, 255, 0.7);

      transition: 0.25s;
    }

    .buy:hover {
      transform: scale(1.04);

      box-shadow:
        0 0 20px #00c8ff,
        0 0 40px #006eff;
    }

    .buy:active {
      transform: scale(0.97);
    }

    /* Окно загрузки */

    .payment {
      position: fixed;
      inset: 0;

      display: flex;
      justify-content: center;
      align-items: center;

      background: rgba(0, 5, 30, 0.88);

      backdrop-filter: blur(10px);

      opacity: 0;
      visibility: hidden;

      transition:
        opacity 0.5s ease,
        visibility 0.5s ease;

      z-index: 9999;
    }

    .payment.active {
      opacity: 1;
      visibility: visible;
    }

    .payment-box {
      width: 90%;
      max-width: 430px;

      padding: 40px 30px;

      text-align: center;

      border-radius: 25px;

      background: rgba(0, 25, 75, 0.95);

      border: 1px solid #00bfff;

      box-shadow:
        0 0 25px #008cff,
        0 0 70px rgba(0, 100, 255, 0.5);

      transform: scale(0.8);

      transition:
        transform 0.5s ease;
    }

    .payment.active .payment-box {
      transform: scale(1);
    }

    .payment-box h2 {
      color: #00d9ff;

      font-size: 26px;

      margin-bottom: 15px;

      text-shadow:
        0 0 15px #008cff;
    }

    .payment-box p {
      color: #b9ddff;
    }

    /* Крутилка */

    .spinner {
      width: 65px;
      height: 65px;

      margin: 0 auto 25px;

      border-radius: 50%;

      border: 5px solid rgba(255,255,255,0.15);

      border-top-color: #00d9ff;

      animation:
        spin 1s linear infinite;

      box-shadow:
        0 0 20px #008cff;
    }

    @keyframes spin {
      to {
        transform: rotate(360deg);
      }
    }

    /* Прогресс */

    .progress {
      width: 100%;
      height: 7px;

      margin-top: 25px;

      background: rgba(255,255,255,0.15);

      border-radius: 10px;

      overflow: hidden;
    }

    .progress-bar {
      width: 0%;
      height: 100%;

      background: #00d9ff;

      box-shadow:
        0 0 15px #00c8ff;

      animation:
        progress 5s linear forwards;
    }

    @keyframes progress {
      from {
        width: 0%;
      }

      to {
        width: 100%;
      }
    }

    .counter {
      margin-top: 15px;
      color: #8edcff;
    }

    /* Подвал */

    footer {
      text-align: center;

      margin-top: 50px;
      padding: 25px;

      color: #7fb3df;
    }

    /* Телефон */

    @media (max-width: 800px) {
      .products {
        grid-template-columns: 1fr;
      }

      .logo {
        font-size: 42px;
      }
    }
  </style>
</head>

<body>

  <!-- ШАПКА -->

  <header>

    <div class="logo">
      MaxFlomShop
    </div>

    <div class="subtitle">
      Добро пожаловать в наш неоновый магазин ⚡
    </div>

  </header>


  <!-- ТОВАРЫ -->

  <main class="products">

    <!-- Товар 1 -->

    <div class="product">

      <h2>Товар №1</h2>

      <div class="description">
        Описание первого товара
      </div>

      <div class="price">
        20 ₽
      </div>

      <button
        class="buy"
        onclick="startPayment('https://mmmxfff2310-crypto.github.io/MaxFlomShopoffic/')">

        Оплатить

      </button>

    </div>


    <!-- Товар 2 -->

    <div class="product">

      <h2>Товар №2</h2>

      <div class="description">
        Описание второго товара
      </div>

      <div class="price">
        20 ₽
      </div>

      <button
        class="buy"
        onclick="startPayment('https://mmmxfff2310-crypto.github.io/MaxFlomShopoffic/')">

        Оплатить

      </button>

    </div>


    <!-- Товар 3 -->

    <div class="product">

      <h2>Товар №3</h2>

      <div class="description">
        Описание третьего товара
      </div>

      <div class="price">
        20 ₽
      </div>

      <button
        class="buy"
        onclick="startPayment('https://mmmxfff2310-crypto.github.io/MaxFlomShopoffic/')">

        Оплатить

      </button>

    </div>


    <!-- Товар 4 -->

    <div class="product">

      <h2>Товар №4</h2>

      <div class="description">
        Описание четвёртого товара
      </div>

      <div class="price">
        20 ₽
      </div>

      <button
        class="buy"
        onclick="startPayment('https://mmmxfff2310-crypto.github.io/MaxFlomShopoffic/')">

        Оплатить

      </button>

    </div>


    <!-- Товар 5 -->

    <div class="product">

      <h2>Товар №5</h2>

      <div class="description">
        Описание пятого товара
      </div>

      <div class="price">
        20 ₽
      </div>

      <button
        class="buy"
        onclick="startPayment('https://mmmxfff2310-crypto.github.io/MaxFlomShopoffic/')">

        Оплатить

      </button>

    </div>


    <!-- Товар 6 -->

    <div class="product">

      <h2>Товар №6</h2>

      <div class="description">
        Описание шестого товара
      </div>

      <div class="price">
        20 ₽
      </div>

      <button
        class="buy"
        onclick="startPayment('https://mmmxfff2310-crypto.github.io/MaxFlomShopoffic/')">

        Оплатить

      </button>

    </div>

  </main>


  <!-- ОКНО ЗАГРУЗКИ -->

  <div
    class="payment"
    id="payment">

    <div class="payment-box">

      <div class="spinner"></div>

      <h2>
        Загрузка платежа...
      </h2>

      <p>
        Подготавливаем платёж
      </p>

      <div class="progress">

        <div class="progress-bar"></div>

      </div>

      <div
        class="counter"
        id="counter">

        Осталось 5 секунд

      </div>

    </div>

  </div>


  <!-- ПОДВАЛ -->

  <footer>
    © 2026 MaxFlomShop
  </footer>


  <!-- JAVASCRIPT -->

  <script>

    function startPayment(paymentLink) {

      const payment =
        document.getElementById("payment");

      const counter =
        document.getElementById("counter");

      payment.classList.add("active");

      let seconds = 5;

      counter.textContent =
        "Осталось " + seconds + " секунд";

      const timer =
        setInterval(function () {

          seconds--;

          if (seconds > 0) {

            counter.textContent =
              "Осталось " + seconds + " секунд";

          } else {

            clearInterval(timer);

            counter.textContent =
              "Переходим к оплате...";

            setTimeout(function () {

              window.location.href =
                paymentLink;

            }, 300);

          }

        }, 1000);

    }

  </script>

</body>
</html>
