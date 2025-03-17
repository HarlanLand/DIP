<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>แบบทดสอบ</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .exam-container {
            max-width: 500px;
            margin: auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
        }
        li {
            list-style: none;
            margin: 5px 0;
        }
        #feedback {
            color: red;
            margin-top: 10px;
        }
    </style>
</head>
<body>

<div class="exam-container">
    <h2 id="exam-header">แบบทดสอบ</h2>
    <h3 id="exam">คำถาม</h3>
    <ul>
        <li>
            <input type="radio" name="answer" class="answer" id="a">
            <label for="a" id="a-text"></label>
        </li>
        <li>
            <input type="radio" name="answer" class="answer" id="b">
            <label for="b" id="b-text"></label>
        </li>
        <li>
            <input type="radio" name="answer" class="answer" id="c">
            <label for="c" id="c-text"></label>
        </li>
        <li>
            <input type="radio" name="answer" class="answer" id="d">
            <label for="d" id="d-text"></label>
        </li>
    </ul>
    <button id="submit">ส่งคำตอบ</button>
    <p id="feedback"></p>
</div>

<script>
    // คำถามและคำตอบ
    const quizData = [
        {
            question: "1 + 1 = ?",
            a: "1",
            b: "2",
            c: "3",
            d: "4",
            correct: "b"
        },
        {
            question: "dip ย่อมาจากอะไร?",
            a: "Dumb in Public",
            b: "Department of Internet People",
            c: "Double Ice-cream Please",
            d: "Department Of Intellectual Property",
            correct: "d"
        },
        {
            question: "ข้อใดเป็นสินค้าที่มีสิ่งบ่งชี้ทางภูมิศาสตร์หรือGI",
            a: "ชามไก่ลำปาง",
            b: "ชามเขียวคว่ำเช้า",
            c: "ชามพลาสติก",
            d: "ชามขาวคว่ำค่ำ",
            correct: "a"
        },
        {
            question: "ข้อใดคือเครื่องหมายร่วม?",
            a: "ฮาลาล",
            b: "ธนาคารกรุงไทย",
            c: "M-150",
            d: "ตราช้างของปูนซีเมนต์ จำกัด (มหาชน)",
            correct: "d"
        }
    ];

    let currentQuestion = 0;

    const examEl = document.getElementById("exam");
    const aText = document.getElementById("a-text");
    const bText = document.getElementById("b-text");
    const cText = document.getElementById("c-text");
    const dText = document.getElementById("d-text");
    const submitBtn = document.getElementById("submit");
    const feedbackEl = document.getElementById("feedback");

    function loadQuestion() {
        const q = quizData[currentQuestion];
        examEl.innerText = q.question;
        aText.innerText = q.a;
        bText.innerText = q.b;
        cText.innerText = q.c;
        dText.innerText = q.d;
        feedbackEl.innerText = "";
    }

    function getSelected() {
        const answers = document.querySelectorAll(".answer");
        let selectedAnswer = null;
        answers.forEach((answer) => {
            if (answer.checked) {
                selectedAnswer = answer.id;
            }
        });
        return selectedAnswer;
    }

    function resetSelection() {
        document.querySelectorAll(".answer").forEach((answer) => answer.checked = false);
    }

    submitBtn.addEventListener("click", () => {
        const answer = getSelected();
        if (!answer) {
            feedbackEl.innerText = "กรุณาเลือกคำตอบก่อน!";
            return;
        }
        if (answer === quizData[currentQuestion].correct) {
            currentQuestion++;
            if (currentQuestion < quizData.length) {
                loadQuestion();
                resetSelection();
            } else {
                document.querySelector(".exam-container").innerHTML = "<h2>คุณทำแบบทดสอบเสร็จแล้ว!</h2>";
            }
        } else {
            feedbackEl.innerText = "ผิด! ลองอีกครั้ง";
        }
    });

    loadQuestion();
</script>

</body>
</html>
