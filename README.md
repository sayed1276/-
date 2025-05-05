<!DOCTYPE html><html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>نتيجة الطالب</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f2f2f2;
      padding: 50px;
    }
    input, button {
      padding: 10px;
      margin: 10px;
      font-size: 16px;
    }
    .result {
      margin-top: 20px;
      font-size: 18px;
      color: green;
    }
  </style>
</head>
<body>
  <h1>الاستعلام عن النتيجة</h1>
  <input type="text" id="studentId" placeholder="أدخل رقم الجلوس">
  <button onclick="checkResult()">عرض النتيجة</button>
  <div id="result" class="result"></div>  <script>
    // بيانات الطالب
    const studentData = {
      "12345": {
        name: "السيد أحمد صلاح",
        arabic: 10,
        english: 10,
        total: 20
      }
    };

    function checkResult() {
      const id = document.getElementById("studentId").value;
      const resultDiv = document.getElementById("result");

      if (studentData[id]) {
        const student = studentData[id];
        resultDiv.innerHTML =
          `<p>الاسم: ${student.name}</p>
           <p>اللغة العربية: ${student.arabic}</p>
           <p>اللغة الإنجليزية: ${student.english}</p>
           <p>المجموع الكلي: ${student.total} من 20</p>`;
      } else {
        resultDiv.innerHTML = "رقم الجلوس غير موجود";
        resultDiv.style.color = "red";
      }
    }
  </script></body>
</html>
