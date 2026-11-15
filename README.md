<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Listino Prezzi</title>
    <!-- Script ufficiale Telegram Web App -->
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            background-color: var(--tg-theme-bg-color, #ffffff);
            color: var(--tg-theme-text-color, #000000);
            margin: 0;
            padding: 16px;
            padding-bottom: 40px;
        }
        h1 {
            font-size: 22px;
            margin-bottom: 6px;
            text-align: center;
        }
        .subtitle {
            font-size: 13px;
            color: var(--tg-theme-hint-color, #888888);
            text-align: center;
            margin-bottom: 20px;
        }
        .card {
            background-color: var(--tg-theme-secondary-bg-color, #f4f4f5);
            padding: 16px;
            border-radius: 14px;
            margin-bottom: 14px;
        }
        .product-title {
            margin: 0 0 12px 0;
            font-size: 18px;
            font-weight: 700;
            letter-spacing: 0.5px;
        }
        .tier-list {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }
        .tier {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 14px;
            background-color: var(--tg-theme-bg-color, #ffffff);
            border-radius: 10px;
            border: none;
            width: 100%;
            cursor: pointer;
            text-align: left;
            box-sizing: border-box;
            transition: opacity 0.2s;
        }
        .tier:active {
            opacity: 0.7;
        }
        .qty {
            font-size: 15px;
            font-weight: 500;
            color: var(--tg-theme-text-color, #000000);
        }
        .price {
            font-weight: 700;
            font-size: 16px;
            color: var(--tg-theme-button-color, #2481cc);
        }
    </style>
</head>
<body>

    <h1>📋 Listino Prezzi</h1>
    <div class="subtitle">Ticca un'offerta per ordinare</div>

    <!-- Prodotto 1 -->
    <div class="card">
        <h2 class="product-title">DRY SIFT</h2>
        <div class="tier-list">
            <button class="tier" onclick="ordina('DRY SIFT', '100g', '400 €')">
                <span class="qty">100g</span>
                <span class="price">400 €</span>
            </button>
            <button class="tier" onclick="ordina('DRY SIFT', '500g', '1.500 €')">
                <span class="qty">500g</span>
                <span class="price">1.500 €</span>
            </button>
            <button class="tier" onclick="ordina('DRY SIFT', '1kg', '2.500 €')">
                <span class="qty">1kg</span>
                <span class="price">2.500 €</span>
            </button>
        </div>
    </div>

    <!-- Prodotto 2 -->
    <div class="card">
        <h2 class="product-title">PLASMA STATIC</h2>
        <div class="tier-list">
            <button class="tier" onclick="ordina('PLASMA STATIC', '100g', '450 €')">
                <span class="qty">100g</span>
                <span class="price">450 €</span>
            </button>
            <button class="tier" onclick="ordina('PLASMA STATIC', '500g', '1.700 €')">
                <span class="qty">500g</span>
                <span class="price">1.700 €</span>
            </button>
            <button class="tier" onclick="ordina('PLASMA STATIC', '1kg', '2.700 €')">
                <span class="qty">1kg</span>
                <span class="price">2.700 €</span>
            </button>
        </div>
    </div>

    <!-- Prodotto 3 -->
    <div class="card">
        <h2 class="product-title">BUBBLE HASH</h2>
        <div class="tier-list">
            <button class="tier" onclick="ordina('BUBBLE HASH', '100g', '450 €')">
                <span class="qty">100g</span>
                <span class="price">450 €</span>
            </button>
            <button class="tier" onclick="ordina('BUBBLE HASH', '500g', '1.700 €')">
                <span class="qty">500g</span>
                <span class="price">1.700 €</span>
            </button>
            <button class="tier" onclick="ordina('BUBBLE HASH', '1kg', '2.700 €')">
                <span class="qty">1kg</span>
                <span class="price">2.700 €</span>
            </button>
        </div>
    </div>

    <!-- Prodotto 4 -->
    <div class="card">
        <h2 class="product-title">PIATELLA</h2>
        <div class="tier-list">
            <button class="tier" onclick="ordina('PIATELLA', '100g', '500 €')">
                <span class="qty">100g</span>
                <span class="price">500 €</span>
            </button>
            <button class="tier" onclick="ordina('PIATELLA', '500g', '1.900 €')">
                <span class="qty">500g</span>
                <span class="price">1.900 €</span>
            </button>
            <button class="tier" onclick="ordina('PIATELLA', '1kg', '3.000 €')">
                <span class="qty">1kg</span>
                <span class="price">3.000 €</span>
            </button>
        </div>
    </div>

    <!-- Prodotto 5 -->
    <div class="card">
        <h2 class="product-title">VAPE LIVE ROSIN</h2>
        <div class="tier-list">
            <button class="tier" onclick="ordina('VAPE LIVE ROSIN', '10 pz', '150 €')">
                <span class="qty">10 pz</span>
                <span class="price">150 €</span>
            </button>
            <button class="tier" onclick="ordina('VAPE LIVE ROSIN', '50 pz', '700 €')">
                <span class="qty">50 pz</span>
                <span class="price">700 €</span>
            </button>
            <button class="tier" onclick="ordina('VAPE LIVE ROSIN', '100 pz', '1.300 €')">
                <span class="qty">100 pz</span>
                <span class="price">1.300 €</span>
            </button>
        </div>
    </div>

    <script>
        const tg = window.Telegram.WebApp;
        tg.ready();
        tg.expand();

        function ordina(prodotto, quantita, prezzo) {
            const messaggio = `Ciao! Vorrei ordinare:\n📦 *${prodotto}*\n⚖️ Quantità: ${quantita}\n💰 Prezzo: ${prezzo}`;
            const url = `https://t.me/crazyd5b?text=${encodeURIComponent(messaggio)}`;
            tg.openTelegramLink(url);
        }
    </script>
</body>
</html>
