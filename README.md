
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>明细查询</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            background-color: #ffffff;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        h1 {
            text-align: center;
            margin-bottom: 20px;
        }
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        .header h2 {
            margin: 0;
        }
        .header button {
            background-color: #f0f0f0;
            border: none;
            padding: 10px 20px;
            border-radius: 20px;
            cursor: pointer;
        }
        .header button.active {
            background-color: #ff9800;
            color: #ffffff;
        }
        .transactions {
            list-style-type: none;
            padding: 0;
        }
        .transactions li {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
            border-bottom: 1px solid #e0e0e0;
        }
        .transactions li:last-child {
            border-bottom: none;
        }
        .transactions li .details {
            flex: 1;
        }
        .transactions li .amount {
            font-weight: bold;
            color: #ff0000;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>明细查询</h1>
        <div class="header">
            <h2>6228 **** 9073</h2>
            <button class="active">近一周</button>
            <button>近一月</button>
            <button>近三月</button>
            <button>筛选</button>
        </div>
        <ul class="transactions">
            <li>
                <div class="details">
                    <p>度小满（国美易…</p>
                    <p>2024-08-27 08:24:51</p>
                </div>
                <div class="amount">-4,726.67</div>
            </li>
            <li>
                <div class="details">
                    <p>网银在线（京东…</p>
                    <p>2024-08-26 09:26:37</p>
                </div>
                <div class="amount">-3,028.59</div>
            </li>
            <li>
                <div class="details">
                    <p>网银在线（苏银…</p>
                    <p>2024-08-24 01:29:42</p>
                </div>
                <div class="amount">-3,029.86</div>
            </li>
            <li>
                <div class="details">
                    <p>财付通（微信支…</p>
                    <p>2024-08-24 00:45:07</p>
                </div>
                <div class="amount">-1,500.00</div>
            </li>
        </ul>
    </div>
</body>
</html>
