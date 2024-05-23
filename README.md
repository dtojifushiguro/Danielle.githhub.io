<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine's Day Question</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: pink;
            margin: 0;
            text-align: center;
        }
        #question {
            font-size: 24px;
            margin-bottom: 20px;
        }
        button {
            padding: 10px 20px;
            font-size: 18px;
            margin: 5px;
            cursor: pointer;
        }
        #noButton {
            transition: font-size 0.3s;
        }
    </style>
</head>
<body>
    <div>
        <div id="question">Can you be my Valentine's Day?</div>
        <button onclick="handleYes()">Yes</button>
        <button id="noButton" onclick="handleNo()">No</button>
    </div>

    <script>
        let noButtonClickCount = 0;

        function handleYes() {
            document.body.innerHTML = '<h1>I love you</h1>';
        }

        function handleNo() {
            noButtonClickCount++;
            if (noButtonClickCount === 1) {
                document.getElementById('question').innerText = 'Are you sure?';
            } else {
                let noButton = document.getElementById('noButton');
                let newSize = 18 - noButtonClickCount * 2;
                noButton.style.fontSize = newSize + 'px';
                if (newSize <= 0) {
                    noButton.style.display = 'none';
                }
            }
        }
    </script>
</body>
</html>
