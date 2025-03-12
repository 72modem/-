<!DOCTYPE html>
<html>
<head>
    <title>송금할 은행 선택</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; padding: 20px; }
        h2 { color: #333; }
        .bank-list { display: flex; flex-direction: column; align-items: center; }
        button { padding: 10px 20px; margin: 5px; font-size: 16px; cursor: pointer; }
    </style>
</head>
<body>
    <h2>송금할 은행을 선택하세요</h2>
    <div class="bank-list">
        <button onclick="sendMoney('nh')">농협</button>
        <button onclick="sendMoney('kb')">국민은행</button>
        <button onclick="sendMoney('woori')">우리은행</button>
        <button onclick="sendMoney('post')">우체국</button>
        <button onclick="sendMoney('kakao')">카카오뱅크</button>
        <button onclick="sendMoney('mg')">새마을금고</button>
    </div>

    <script>
        function sendMoney(bank) {
            let account = "74111052063094"; // 송금 받을 계좌
            let name = "전상욱"; // 예금주

            let url = "";

            if (bank === "nh") url = `https://banking.nonghyup.com/transfer?account=${account}&name=${name}`;
            else if (bank === "kb") url = `https://obank.kbstar.com/quics?page=C101590&account=${account}`;
            else if (bank === "woori") url = `https://spib.wooribank.com/pib/common/CusLogin.jsp?account=${account}`;
            else if (bank === "post") url = `https://www.epostbank.go.kr/transfer?account=${account}`;
            else if (bank === "kakao") url = `https://www.kakaobank.com/transfer?account=${account}`;
            else if (bank === "mg") url = `https://smart.mg.co.kr/transfer?account=${account}`;

            window.location.href = url;
        }
    </script>
</body>
</html>
# -
