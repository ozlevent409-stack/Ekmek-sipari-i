<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#111827">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-title" content="Ekmek Sipariş">
<title>Ekmek Sipariş Hesaplama</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Arial, sans-serif;
    background: #f3f4f6;
    color: #111827;
}

.container {
    max-width: 700px;
    margin: auto;
    padding: 16px;
}

h1 {
    text-align: center;
    font-size: 24px;
    margin-bottom: 20px;
}

.card {
    background: white;
    border-radius: 16px;
    padding: 16px;
    margin-bottom: 15px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.08);
}

.title {
    font-size: 19px;
    font-weight: bold;
    margin-bottom: 5px;
}

.info {
    color: #6b7280;
    font-size: 14px;
    margin-bottom: 15px;
}

.day-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
}

.input-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
}

label {
    display: block;
    font-size: 13px;
    color: #6b7280;
    margin-bottom: 6px;
}

input,
select {
    width: 100%;
    height: 48px;
    border: 1px solid #d1d5db;
    border-radius: 10px;
    padding: 0 12px;
    font-size: 17px;
    background: white;
}

.delivery {
    height: 48px;
    display: flex;
    align-items: center;
    font-size: 18px;
    font-weight: bold;
}

.calculate {
    width: 100%;
    height: 54px;
    border: none;
    border-radius: 12px;
    background: #111827;
    color: white;
    font-size: 17px;
    font-weight: bold;
    cursor: pointer;
    margin-bottom: 15px;
}

.calculate:active {
    transform: scale(0.98);
}

.result {
    border-top: 1px solid #e5e7eb;
    margin-top: 15px;
    padding-top: 15px;
}

.result-row {
    margin-bottom: 7px;
}

.value {
    font-size: 22px;
    font-weight: bold;
}

.order-title {
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 10px;
}

.order-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 14px 0;
    border-bottom: 1px solid #e5e7eb;
}

.order-row:last-child {
    border-bottom: none;
}

.order-amount {
    font-size: 21px;
    font-weight: bold;
}

.delivery-result {
    color: #6b7280;
    margin-top: 10px;
}

@media (max-width: 560px) {
    .input-grid {
        grid-template-columns: 1fr;
    }
}
</style>
</head>

<body>

<div class="container">

    <h1>🍞 Ekmek Sipariş Hesaplama</h1>

    <!-- SİPARİŞ GÜNÜ -->
    <div class="card">

        <div class="day-grid">

            <div>
                <label>Sipariş Günü</label>

                <select id="orderDay">
                    <option value="Salı">Salı</option>
                    <option value="Perşembe">Perşembe</option>
                    <option value="Cumartesi">Cumartesi</option>
                </select>
            </div>

            <div>
                <label>Sevkiyat Günü</label>

                <div id="deliveryDay" class="delivery">
                    Perşembe
                </div>
            </div>

        </div>

        <div class="info" style="margin-top:10px;">
            Salı → Perşembe &nbsp; | &nbsp;
            Perşembe → Cumartesi &nbsp; | &nbsp;
            Cumartesi → Salı
        </div>

    </div>


    <!-- 7'' EKMEK -->

    <div class="card">

        <div class="title">
            7’’ Tavukburger Ekmeği
        </div>

        <div class="info">
            1 poşet = 24 adet
        </div>

        <div class="input-grid">

            <div>
                <label>Kapanış (adet)</label>
                <input
                    id="closing7"
                    type="number"
                    min="0"
                    inputmode="numeric"
                >
            </div>

            <div>
                <label>Gelen (adet)</label>
                <input
                    id="incoming7"
                    type="number"
                    min="0"
                    inputmode="numeric"
                >
            </div>

            <div>
                <label>Kullanım (adet)</label>
                <input
                    id="usage7"
                    type="number"
                    min="0"
                    inputmode="numeric"
                >
            </div>

        </div>

        <div class="result">

            <div class="result-row">
                Kalan:
                <span id="remaining7" class="value">—</span>
                adet
            </div>

            <div class="result-row">
                Sipariş:
                <span id="bags7" class="value">—</span>
                poşet
            </div>

        </div>

    </div>


    <!-- 3.75 EKMEK -->

    <div class="card">

        <div class="title">
            3.75 Ekmek
        </div>

        <div class="info">
            1 poşet = 30 adet
        </div>

        <div class="input-grid">

            <div>
                <label>Kapanış (adet)</label>
                <input
                    id="closing375"
                    type="number"
                    min="0"
                    inputmode="numeric"
                >
            </div>

            <div>
                <label>Gelen (adet)</label>
                <input
                    id="incoming375"
                    type="number"
                    min="0"
                    inputmode="numeric"
                >
            </div>

            <div>
                <label>Kullanım (adet)</label>
                <input
                    id="usage375"
                    type="number"
                    min="0"
                    inputmode="numeric"
                >
            </div>

        </div>

        <div class="result">

            <div class="result-row">
                Kalan:
                <span id="remaining375" class="value">—</span>
                adet
            </div>

            <div class="result-row">
                Sipariş:
                <span id="bags375" class="value">—</span>
                poşet
            </div>

        </div>

    </div>


    <!-- HESAPLA -->

    <button class="calculate" onclick="calculateOrder()">
        HESAPLA
    </button>


    <!-- BÜYÜK SİPARİŞ LİSTESİ -->

    <div class="card">

        <div class="order-title">
            BÜYÜK SİPARİŞ LİSTESİ
        </div>

        <div id="orderList">
            Bilgileri girip HESAPLA'ya bas.
        </div>

    </div>

</div>


<script>

/* SEVKİYAT GÜNLERİ */

const deliveryDays = {

    "Salı": "Perşembe",

    "Perşembe": "Cumartesi",

    "Cumartesi": "Salı"

};


/* SEVKİYAT GÜNÜNÜ GÜNCELLE */

function updateDeliveryDay() {

    const orderDay =
        document.getElementById("orderDay").value;

    document.getElementById("deliveryDay").innerText =
        deliveryDays[orderDay];
}


/* SAYI AL */

function getNumber(id) {

    const value =
        Number(document.getElementById(id).value);

    return value || 0;
}


/* HESAPLAMA */

function calculateOrder() {

    /*
        7'' EKMEK

        Kapanış + Gelen - Kullanım = Kalan
    */

    const closing7 =
        getNumber("closing7");

    const incoming7 =
        getNumber("incoming7");

    const usage7 =
        getNumber("usage7");


    const remaining7 =
        closing7 + incoming7 - usage7;


    /*
        1 poşet = 24 adet

        14.49 → 14
        14.50 → 15
        15.49 → 15
        15.50 → 16
    */

    const bags7 =
        Math.max(
            0,
            Math.floor((remaining7 / 24) + 0.5)
        );


    /*
        3.75 EKMEK

        Kapanış + Gelen - Kullanım = Kalan
    */

    const closing375 =
        getNumber("closing375");

    const incoming375 =
        getNumber("incoming375");

    const usage375 =
        getNumber("usage375");


    const remaining375 =
        closing375 + incoming375 - usage375;


    /*
        1 poşet = 30 adet
    */

    const bags375 =
        Math.max(
            0,
            Math.floor((remaining375 / 30) + 0.5)
        );


    /* SONUÇLARI GÖSTER */

    document.getElementById("remaining7").innerText =
        remaining7;

    document.getElementById("bags7").innerText =
        bags7;


    document.getElementById("remaining375").innerText =
        remaining375;

    document.getElementById("bags375").innerText =
        bags375;


    /* SİPARİŞ GÜNÜ */

    const orderDay =
        document.getElementById("orderDay").value;


    const deliveryDay =
        deliveryDays[orderDay];


    /* BÜYÜK SİPARİŞ LİSTESİ */

    document.getElementById("orderList").innerHTML = `

        <div class="order-row">

            <span>
                7’’ Tavukburger Ekmeği
            </span>

            <span class="order-amount">
                ${bags7} poşet
            </span>

        </div>


        <div class="order-row">

            <span>
                3.75 Ekmek
            </span>

            <span class="order-amount">
                ${bags375} poşet
            </span>

        </div>


        <div class="delivery-result">

            Sevkiyat:
            <strong>${deliveryDay}</strong>

        </div>

    `;
}


/* GÜN DEĞİŞİNCE SEVKİYATI DEĞİŞTİR */

document
    .getElementById("orderDay")
    .addEventListener(
        "change",
        updateDeliveryDay
    );


/* BAŞLANGIÇ */

updateDeliveryDay();

</script>

</body>
</html>
