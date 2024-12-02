<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>간단한 메모장</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f4f4f4;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        h1 {
            text-align: center;
        }
        textarea {
            width: 100%;
            height: 300px;
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 4px;
            resize: none;
        }
        .buttons {
            text-align: center;
            margin-top: 20px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            background-color: #4CAF50;
            color: white;
            cursor: pointer;
            border-radius: 4px;
            margin: 5px;
        }
        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>간단한 메모장</h1>
    <textarea id="memoArea" placeholder="메모를 작성하세요..."></textarea>
    <div class="buttons">
        <button onclick="saveMemo()">저장</button>
        <button onclick="loadMemo()">불러오기</button>
        <button onclick="clearMemo()">초기화</button>
    </div>
</div>

<script>
    // 메모 저장 기능
    function saveMemo() {
        const memo = document.getElementById('memoArea').value;
        localStorage.setItem('memo', memo);
        alert('메모가 저장되었습니다!');
    }

    // 메모 불러오기 기능
    function loadMemo() {
        const savedMemo = localStorage.getItem('memo');
        if (savedMemo) {
            document.getElementById('memoArea').value = savedMemo;
        } else {
            alert('저장된 메모가 없습니다.');
        }
    }

    // 메모 초기화 기능
    function clearMemo() {
        document.getElementById('memoArea').value = '';
        alert('메모가 초기화되었습니다.');
    }
</script>

<!-- Kommunicate 챗봇 스크립트 추가 -->
<script type="text/javascript">
    (function(d, m){
        var kommunicateSettings = 
            {"appId":"233b2479ea8ce27c062486acd486d90b0","popupWidget":true,"automaticChatOpenOnNavigation":true};
        var s = document.createElement("script"); s.type = "text/javascript"; s.async = true;
        s.src = "https://widget.kommunicate.io/v2/kommunicate.app";
        var h = document.getElementsByTagName("head")[0]; h.appendChild(s);
        window.kommunicate = m; m._globals = kommunicateSettings;
    })(document, window.kommunicate || {});
</script>

</body>
</html>
