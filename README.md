<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ดีกันนะอ้วน</title>
    <link href="https://fonts.googleapis.com/css2?family=Prompt:wght@300;500&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Prompt', sans-serif;
            background-color: #ffe6ea; /* สีชมพูอ่อน */
            text-align: center;
            padding: 30px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 90vh;
        }
        .container {
            background-color: #fff0f3;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 8px 16px rgba(255, 182, 193, 0.3);
            max-width: 500px;
            width: 90%;
        }
        h1 {
            color: #d63384;
            font-size: 1.5em;
            line-height: 1.6;
        }
        p {
            color: #666;
            font-size: 1.1em;
        }
        .cute-img {
            width: 200px;
            height: auto;
            margin-bottom: 20px;
            border-radius: 15px;
        }
        .buttons {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }
        button {
            padding: 15px 30px;
            font-size: 1.2em;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-family: 'Prompt', sans-serif;
            transition: all 0.3s ease;
        }
        #noBtn {
            background-color: #dc3545; /* สีแดง */
            color: white;
        }
        #yesBtn {
            background-color: #198754; /* สีเขียว */
            color: white;
        }
        /* หน้าที่ 2 ซ่อนไว้ก่อน */
        #page2 {
            display: none;
        }
    </style>
</head>
<body>

    <div class="container" id="page1">
        <img src="https://media1.giphy.com/media/v1.Y2lkPTc5MGI3NjExYnB5OXBpYjJ6YjJ6YjJ6YjJ6YjJ6YjJ6YjJ6YjJ6YjJ6Ynd5ZSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/3oriO0OEd9QIDdllqo/giphy.gif" alt="Cute Bear Ngor" class="cute-img">
        
        <h1>เค้าขอโทษน๊าเค้าผิดไปแล้ว เค้ามาง้อแล้วขอโทษที่ทำให้งอนนะเค้าจะไม่ส่งผิดอีก เค้าตั้งใจมาง้องะ ขอโทษน๊าอ้วนดีกันนะคะ💐</h1>
        
        <div class="buttons">
            <button id="noBtn">ไม่</button>
            <button id="yesBtn">ได้</button>
        </div>
    </div>

    <div class="container" id="page2">
        <img src="https://media2.giphy.com/media/v1.Y2lkPTc5MGI3NjExYnB5OXBpYjJ6YjJ6YjJ6YjJ6YjJ6YjJ6YjJ6YjJ6YjJ6Ynd5ZSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/RetroG25k3lQY/giphy.gif" alt="Cute Bear Happy" class="cute-img">

        <h1>ขอบคุณนะคะที่ยอมให้อภัยเค้า น่ารักที่สุดเลยยย <br>พี่รักหนูที่สุดนะคะ พร้อมง้อตลอดเลย ❤️</h1>
    </div>


    <script>
        let noCount = 0;
        const noBtn = document.getElementById('noBtn');
        const yesBtn = document.getElementById('yesBtn');
        const page1 = document.getElementById('page1');
        const page2 = document.getElementById('page2');

        noBtn.addEventListener('click', function() {
            noCount++;
            
            // ขยายปุ่ม "ได้" ขึ้นเรื่อยๆ
            let currentSize = parseFloat(window.getComputedStyle(yesBtn).fontSize);
            let currentPadding = parseFloat(window.getComputedStyle(yesBtn).padding);
            yesBtn.style.fontSize = (currentSize * 1.2) + 'px';
            yesBtn.style.padding = (currentPadding * 1.1) + 'px';

            // ลดขนาดหรือทำให้ปุ่ม "ไม่" กดยากขึ้น
            if (noCount < 5) {
                noBtn.innerText = ["ไม่น้าาา", "ดีกันนะ", "ขอร้องล่ะ", "นะนะนะ"][noCount-1] || "ไม่";
                noBtn.style.transform = `scale(${1 - (noCount * 0.1)})`;
            }

            // เมื่อกดครบ 5 ครั้ง
            if (noCount >= 5) {
                noBtn.style.display = 'none'; // ซ่อนปุ่ม "ไม่"
                yesBtn.style.fontSize = '3em'; // ขยายปุ่ม "ได้" ให้ใหญ่มาก
                yesBtn.style.width = '100%';
                yesBtn.innerText = "ได้สิคะ! (กดเลย)";
            }
        });

        yesBtn.addEventListener('click', function() {
            // เปลี่ยนหน้า
            page1.style.display = 'none';
            page2.style.display = 'block';
        });
    </script>

</body>
</html>

