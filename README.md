# Go-Sport
<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Go Sport</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background-color: #000;
            color: #fff;
            line-height: 1.6;
            height: 100vh;
            display: flex;
            flex-direction: column;
        }

        header {
            background: rgba(0, 0, 0, 0.8);
            color: #fff;
            text-align: center;
            padding: 40px;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.7);
        }

        header h1 {
            font-size: 60px;
            letter-spacing: 4px;
            text-transform: uppercase;
            color: #f39c12;
            text-shadow: 3px 3px 10px rgba(0, 0, 0, 0.7);
            margin-bottom: 20px;
        }

        header nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            gap: 30px;
        }

        header nav a {
            color: #fff;
            text-decoration: none;
            font-size: 18px;
            text-transform: uppercase;
            padding: 10px 20px;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        header nav a:hover {
            background-color: #f39c12;
            transform: scale(1.1);
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.6);
        }

        .container {
            width: 90%;
            margin: 30px auto;
        }

        .section-title {
            font-size: 28px;
            text-align: center;
            color: #fff;
            margin-bottom: 20px;
            text-transform: uppercase;
            border-bottom: 2px solid #fff;
            padding-bottom: 10px;
        }

        .hidden {
            display: none;
            opacity: 0;
            transition: opacity 0.5s ease-out;
        }

        .container > div:not(.hidden) {
            display: block;
            opacity: 1;
            transition: opacity 0.5s ease-in;
        }

        .match-card, .news-card {
            display: flex;
            background-color: rgba(255, 255, 255, 0.1);
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.4);
            transition: transform 0.3s ease;
        }

        .match-card:hover, .news-card:hover {
            transform: scale(1.05);
        }

        .match-card img, .news-card img {
            width: 100px;
            height: 100px;
            border-radius: 10px;
            margin-right: 20px;
        }

        .match-details, .news-details {
            flex-grow: 1;
        }

        .match-details h3, .news-details h3 {
            font-size: 22px;
            color: #fff;
        }

        .match-details p, .news-details p {
            font-size: 16px;
            color: #bbb;
        }

        .match-time {
            color: #e74c3c;
            font-size: 18px;
            font-weight: bold;
            text-align: right;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            background-color: #333;
            border-radius: 10px;
            overflow: hidden;
        }

        th, td {
            padding: 12px;
            text-align: center;
            border: 1px solid #444;
            color: #fff;
        }

        th {
            background-color: #f39c12;
            font-weight: bold;
        }

        tbody tr:hover {
            background-color: #444;
        }

        .dropdown {
            text-align: center;
            margin: 20px 0;
        }

        .dropdown select {
            font-size: 18px;
            padding: 10px;
            border-radius: 5px;
            border: 1px solid #ccc;
            cursor: pointer;
        }

        footer {
            background: rgba(0, 0, 0, 0.8);
            color: #fff;
            padding: 15px;
            text-align: center;
        }

        @media (max-width: 768px) {
            header nav ul {
                flex-direction: column;
            }

            header nav a {
                margin-bottom: 10px;
            }

            .match-card, .news-card {
                flex-direction: column;
                align-items: center;
            }

            .match-details, .news-details {
                text-align: center;
                padding-left: 0;
            }

            .match-time {
                text-align: center;
            }
        }
    </style>
</head>
<body>

    <header>
        <h1>Go Sport</h1>
        <nav>
            <ul>
                <li><a href="javascript:void(0)" onclick="showSection('matches')">المباريات</a></li>
                <li><a href="javascript:void(0)" onclick="showSection('news')">الأخبار</a></li>
                <li><a href="javascript:void(0)" onclick="showSection('leagues')">الدوريات</a></li>
            </ul>
        </nav>
    </header>

    <div class="container">
        <!-- قسم المباريات -->
        <div id="matches" class="hidden">
            <div class="section-title">مباريات اليوم</div>
            <div class="match-card">
                <img src="https://upload.wikimedia.org/wikipedia/commons/a/a7/Zamalek_Sports_Club_logo.svg" alt="الزمالك">
                <div class="match-details">
                    <h3>الزمالك VS الأهلي</h3>
                    <p>التاريخ: 30 ديسمبر 2024</p>
                    <p>الساعة: 8:00 مساءً</p>
                    <p>المكان: استاد القاهرة الدولي</p>
                </div>
                <div class="match-time">8:00 مساءً</div>
            </div>

            <div class="match-card">
                <img src="https://upload.wikimedia.org/wikipedia/commons/1/1e/Pyramids_FC_logo.png" alt="بيراميدز">
                <div class="match-details">
                    <h3>بيراميدز VS الاتحاد السكندري</h3>
                    <p>التاريخ: 1 يناير 2025</p>
                    <p>الساعة: 6:30 مساءً</p>
                    <p>المكان: ملعب الدفاع الجوي</p>
                </div>
                <div class="match-time">6:30 مساءً</div>
            </div>
        </div>

        <!-- قسم الأخبار -->
        <div id="news" class="hidden">
            <div class="section-title">أحدث الأخبار الرياضية</div>
            <div class="news-card">
                <img src="https://upload.wikimedia.org/wikipedia/commons/a/a7/Zamalek_Sports_Club_logo.svg" alt="الزمالك">
                <div class="news-details">
                    <h3>الزمالك يتأهل إلى نصف نهائي دوري أبطال أفريقيا</h3>
                    <p>الزمالك يفوز على الترجي 2-1 في مباراة مثيرة.</p>
                </div>
            </div>

            <div class="news-card">
                <img src="https://upload.wikimedia.org/wikipedia/commons/1/1e/Pyramids_FC_logo.png" alt="بيراميدز">
                <div class="news-details">
                    <h3>بيراميدز يواجه الأهلي في نهائي كأس مصر</h3>
                    <p>بيراميدز يلتقي بالأهلي في نهائي كأس مصر، المباراة منتظرة بشدة.</p>
                </div>
            </div>
        </div>

        <!-- قسم الدوريات -->
        <div id="leagues" class="hidden">
            <div class="dropdown">
                <label for="league-selector">اختر الدوري: </label>
                <select id="league-selector" onchange="showLeagueTable(this.value)">
                    <option value="english">الدوري الإنجليزي</option>
                    <option value="egyptian">الدوري المصري</option>
                    <option value="spanish">الدوري الإسباني</option>
                    <option value="german">الدوري الألماني</option>
                    <option value="italian">الدوري الإيطالي</option>
                    <option value="french">الدوري الفرنسي</option>
                </select>
            </div>

            <!-- جداول الدوري -->
            <div id="english" class="hidden">
                <h2>الدوري الإنجليزي الممتاز</h2>
                <table>
                    <thead>
                        <tr>
                            <th>المركز</th>
                            <th>الفريق</th>
                            <th>النقاط</th>
                            <th>الأهداف</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>1</td>
                            <td>مانشستر سيتي</td>
                            <td>42</td>
                            <td>55</td>
                        </tr>
                        <tr>
                            <td>2</td>
                            <td>ليفربول</td>
                            <td>40</td>
                            <td>48</td>
                        </tr>
                        <tr>
                            <td>3</td>
                            <td>آرسنال</td>
                            <td>39</td>
                            <td>50</td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <div id="egyptian" class="hidden">
                <h2>الدوري المصري الممتاز</h2>
                <table>
                    <thead>
                        <tr>
                            <th>المركز</th>
                            <th>الفريق</th>
                            <th>النقاط</th>
                            <th>الأهداف</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>1</td>
                            <td>الأهلي</td>
                            <td>42</td>
                            <td>48</td>
                        </tr>
                        <tr>
                            <td>2</td>
                            <td>الزمالك</td>
                            <td>40</td>
                            <td>45</td>
                        </tr>
                        <tr>
                            <td>3</td>
                            <td>بيراميدز</td>
                            <td>39</td>
                            <td>43</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2024 Go Sport. جميع الحقوق محفوظة.</p>
    </footer>

    <script>
        function showSection(section) {
            var sections = document.querySelectorAll('.container > div');
            sections.forEach(function (div) {
                div.classList.add('hidden');
            });
            document.getElementById(section).classList.remove('hidden');
        }

        function showLeagueTable(league) {
            var leagues = document.querySelectorAll('[id$="english"], [id$="egyptian"], [id$="spanish"], [id$="german"], [id$="italian"], [id$="french"]');
            leagues.forEach(function (div) {
                div.classList.add('hidden');
            });
            document.getElementById(league).classList.remove('hidden');
        }
    </script>
</body>
</html>

