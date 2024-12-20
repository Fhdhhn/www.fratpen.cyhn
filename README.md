<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>شركة البناء</title>
    <script defer>
        const scrollInterval = 9000; // 3 ثوانٍ

        document.addEventListener("DOMContentLoaded", () => {
            const sliderContainer = document.querySelector('.box-container');
            let currentScrollPosition = 0;

            function autoScroll() {
                const scrollWidth = sliderContainer.scrollWidth;
                const containerWidth = sliderContainer.offsetWidth;

                if (currentScrollPosition + containerWidth < scrollWidth) {
                    currentScrollPosition += containerWidth;
                } else {
                    currentScrollPosition = 0;
                }

                sliderContainer.scrollTo({
                    left: currentScrollPosition,
                    behavior: 'smooth'
                });
            }

            setInterval(autoScroll, scrollInterval);
        });

        // وظيفة لتغيير اللغة عند الاختيار
        function changeLanguage(language) {
            const elements = document.querySelectorAll('[data-lang]');
            elements.forEach(element => {
                const langKey = element.getAttribute('data-lang');
                element.innerHTML = language[langKey] || element.innerHTML;
            });
        }

        // فتح وإغلاق الشريط الجانبي
        function toggleSidebar() {
            const sidebar = document.getElementById('sidebar');
            sidebar.classList.toggle('open');
        }
    </script>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            color: #333;
        }

        header {
            background-color: #FFFFFF;
            color: black;
            padding: 1px;
            text-align: left;
            padding-left: 20px;
        }

        h1 {
            color: #FFA500; /* تغيير لون اسم FIRATPEN إلى البرتقالي الفاتح */
        }

        nav ul {
            list-style: none;
            padding: 0;
            display: flex;
            justify-content: center;
            margin: 0;
        }

        nav ul li {
            margin: 0 15px;
        }

        nav ul li a {
            color: black;
            text-decoration: none;
            font-weight: bold;
        }

        section {
            padding: 10px;
            text-align: center;
        }

        .slider-container {
            overflow: hidden;
            width: 100%;
            margin: 20px auto;
            position: relative;
        }

        .box-container {
            display: flex;
            gap: 20px;
            overflow-x: auto;
            scroll-snap-type: x mandatory;
            padding-bottom: 10px;
        }

        .box-container::-webkit-scrollbar {
            display: none;
        }

        .box {
            min-width: 350px;
            height: 250px;
            background-color: #F8F8F8;
            border-radius: 30px;
            border: 0.5px solid #000;
            display: flex;
            align-items: center;
            justify-content: center;
            scroll-snap-align: center;
        }

        .box img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 20px;
        }

        footer {
            text-align: center;
            background-color: #FFFFFF;
            color: black;
            padding: 5px 0;
            margin-top: 20px;
        }

        /* تصميم ال""مربعات الأربعة */
        #buttons-section {
            margin-top: 10px;
            text-align: center;
        }

        .buttons-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px auto;
            max-width: 100%;
        }

        .buttons-container .button {
            width: 100px;
            height: 100px;
            border: 2px solid #FFA500;
            border-radius: 10px;
            overflow: hidden;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .buttons-container .button:hover {
            transform: scale(1.1);
        }

        .buttons-container .button img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 10px;
        }

        /* الشريط الجانبي */
        .sidebar {
            position: fixed;
            top: 0;
            right: -300px; /* بداية الشريط خارج الشاشة */
            width: 250px;
            height: 100%;
            background-color: #333;
            color: white;
            padding: 80px 15px;
            box-shadow: -2px 0 10px rgba(0, 0, 0, 0.2);
            transition: right 0.3s ease;
            z-index: 1000;
        }

        .sidebar a {
            display: block;
            color: white;
            text-decoration: none;
            padding: 15px 0;
            font-size: 18px;
            margin-bottom: 20px;
            border-bottom: 1px solid #444;
            transition: background-color 0.3s;
        }

        .sidebar a:hover {
            background-color: #575757;
        }

        .sidebar .close-btn {
            color: white;
            font-size: 30px;
            background: none;
            border: none;
            cursor: pointer;
            position: absolute;
            top: 20px;
            left: 10px;
        }

        /* عند فتح الشريط الجانبي */
        .sidebar.open {
            right: 0;
        }

        /* الأيقونة الثلاثية */
        .menu-icon {
            font-size: 30px;
            position: fixed;
            top: 20px;
            right: 20px;
            cursor: pointer;
            z-index: 1001;
        }
    </style>
</head>
<body>
    <header>
        <h1>FIRATPEN</h1>
        <nav>
            <ul>
                <li><a href="#slider-section" data-lang="home"></a></li>
            </ul>
        </nav>
    </header>

    <!-- أيقونة الشريط الجانبي -->
    <div class="menu-icon" onclick="toggleSidebar()">&#9776;</div>

    <!-- الشريط الجانبي -->
    <div class="sidebar" id="sidebar">
        <button class="close-btn" onclick="toggleSidebar()">×</button>
        <a href="contact.html">اتصل بنا</a>
        <a href="about.html">من نحن</a>
        <a href="services.html">خدماتنا</a>
        <a href="portfolio.html">أعمالنا</a>
    </div>

    <section id="slider-section">
        <div class="slider-container">
            <div class="box-container">
                <div class="box">
                    <img src="https://www.arabsharing.com/do.php?img=341384" alt="صورة 1">
                </div>
                <div class="box">
                    <img src="https://www.arabsharing.com/do.php?img=341389" alt="صورة 2">
                </div>
                <div class="box">
                    <img src="https://www.arabsharing.com/do.php?img=341390" alt="صورة 3">
                </div>
                <div class="box">
                    <img src="https://www.arabsharing.com/do.php?img=341391" alt="صورة 4">
                </div>
            </div>
        </div>
    </section>

    <!-- المربعات الأربعة -->
    <section id="buttons-section">
        <div class="buttons-container">
            <div class="button" onclick="window.location.href='ftpin.html'">
                <img src="https://www.arabsharing.com/do.php?img=341392" alt="صورة 1">
            </div>
            <div class="button" onclick="window.location.href='feto.html'">
                <img src="https://www.arabsharing.com/do.php?img=341399" alt="صورة 2">
            </div>
            <div class="button" onclick="window.location.href='page3.html'">
                <img src="https://via.placeholder.com/100" alt="صورة 3">
            </div>
            <div class="button" onclick="window.location.href='page4.html'">
                <img src="https://via.placeholder.com/100" alt="صورة 4">
            </div>
        </div>
    </section>

    <footer>
        <p data-lang="footer">Bu site, ihtiyacınız olan miktara göre ihtiyacınız olan pencere ve kapıları tasarlamak için oluşturulmuştur. Bize sabah 8'den akşam 6'ya kadar ulaşabilirsiniz</p>
    </footer>

    <script>
        const languageData = {
            arabic: {
                home: "الصفحة الرئيسية",
                contact: "اتصل بنا",
                footer: "حقوق الطبع والنشر &copy; 2024 شركة البناء"
            },
            english: {
                home: "Home",
                contact: "Contact Us",
                footer: "&copy; 2024 Construction Company"
            },
            turkish: {
                home: "Anasayfa",
                contact: "Bize Ulaşın",
                footer: "&copy; 2024 İnşaat Şirketi"
            }
        };
    </script>
</body>
</html>
