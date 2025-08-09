<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>المتجر</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #fff;
            margin: 0;
            padding: 0;
            direction: rtl;
            text-align: center;
        }
        .container {
            max-width: 500px;
            margin: auto;
            padding: 15px;
        }
        img {
            width: 100%;
            border-radius: 8px;
        }
        h1 {
            font-size: 20px;
            margin: 10px 0;
        }
        .price {
            font-size: 18px;
            color: #d4af37;
            font-weight: bold;
        }
        .old-price {
            text-decoration: line-through;
            color: #777;
            margin-left: 10px;
        }
        .form-group {
            margin-top: 15px;
        }
        input {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
        }
        button {
            padding: 12px;
            background-color: #d4af37;
            color: white;
            font-size: 16px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 5px;
        }
        button:hover {
            background-color: #b8902d;
        }
        .nav-buttons {
            margin-top: 15px;
        }
    </style>
</head>
<body>
    <div class="container">
        <img id="product-img" alt="">
        <h1 id="product-name"></h1>
        <p>
            <span class="old-price" id="old-price"></span>
            <span class="price" id="new-price"></span>
        </p>
        <form>
            <div class="form-group">
                <input type="text" placeholder="الاسم الكامل" required>
            </div>
            <div class="form-group">
                <input type="tel" placeholder="رقم الهاتف" required>
            </div>
            <button type="submit">تأكيد الطلب - الدفع عند الاستلام</button>
        </form>

        <div class="nav-buttons">
            <button onclick="prevProduct()">السابق</button>
            <button onclick="nextProduct()">التالي</button>
        </div>
    </div>

    <script>
        // 🔹 قائمة المنتجات — عدّلها كما تريد
        let products = [
            {
                name: "ساعة يد فاخرة - Timora",
                oldPrice: "26,000 DZD",
                newPrice: "19,000 DZD",
                image: "https://via.placeholder.com/500x300?text=Timora+Watch"
            },
            {
                name: "نظارات شمسية رجالية",
                oldPrice: "8,000 DZD",
                newPrice: "5,500 DZD",
                image: "https://via.placeholder.com/500x300?text=Sunglasses"
            },
            {
                name: "حقيبة جلد طبيعية",
                oldPrice: "15,000 DZD",
                newPrice: "11,000 DZD",
                image: "https://via.placeholder.com/500x300?text=Leather+Bag"
            }
        ];

        let currentIndex = 0;

        function displayProduct(index) {
            document.getElementById("product-name").textContent = products[index].name;
            document.getElementById("old-price").textContent = products[index].oldPrice;
            document.getElementById("new-price").textContent = products[index].newPrice;
            document.getElementById("product-img").src = products[index].image;
            document.getElementById("product-img").alt = products[index].name;
        }

        function nextProduct() {
            currentIndex = (currentIndex + 1) % products.length;
            displayProduct(currentIndex);
        }

        function prevProduct() {
            currentIndex = (currentIndex - 1 + products.length) % products.length;
            displayProduct(currentIndex);
        }

        // عرض أول منتج عند تحميل الصفحة
        displayProduct(currentIndex);
    </script>
</body>
</html>
