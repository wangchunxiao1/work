<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>账单展示</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f8f8f8;
        }
        .container {
            max-width: 600px;
            margin: auto;
            padding: 20px;
            background-color: #fff;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            border-radius: 5px;
        }
        .bill {
            padding: 15px;
            border-bottom: 1px solid #ebebeb;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .bill:hover {
            background-color: #f5f5f5;
        }
        .bill h2 {
            color: #333;
            margin-bottom: 5px;
        }
        .bill p {
            color: #666;
            font-size: 14px;
        }
        .details {
            display: none;
            padding: 15px;
            border-top: 1px solid #ebebeb;
        }
        .details ul {
            list-style-type: none;
            padding-left: 0;
        }
        .details li {
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: #666;
            font-size: 14px;
            margin-bottom: 5px;
        }
        .details li:last-child {
            margin-bottom: 0;
        }
        .details h3 {
            color: #333;
            font-size: 16px;
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>账单列表</h1>

        <div class="bill" data-bill-id="1">
            <h2>账单 1</h2>
            <p>总金额: $100</p>
            <div class="details">
                <h3>账单详情</h3>
                <ul>
                    <li>项目 1: $50</li>
                    <li>项目 2: $25</li>
                    <li>项目 3: $25</li>
                </ul>
            </div>
        </div>

        <div class="bill" data-bill-id="2">
            <h2>账单 2</h2>
            <p>总金额: $150</p>
            <div class="details">
                <h3>账单详情</h3>
                <ul>
                    <li>项目 1: $75</li>
                    <li>项目 2: $50</li>
                    <li>项目 3: $25</li>
                </ul>
            </div>
        </div>
                <div class="bill" data-bill-id="3">
            <h2>账单 2</h2>
            <p>总金额: $150</p>
            <div class="details">
                <h3>账单详情</h3>
                <ul>
                    <li>项目 1: $75</li>
                    <li>项目 2: $50</li>
                    <li>项目 3: $25</li>
                </ul>
            </div>
        </div>
                <div class="bill" data-bill-id="4">
            <h2>账单 2</h2>
            <p>总金额: $150</p>
            <div class="details">
                <h3>账单详情</h3>
                <ul>
                    <li>项目 1: $75</li>
                    <li>项目 2: $50</li>
                    <li>项目 3: $25</li>
                </ul>
            </div>
        </div>
                <div class="bill" data-bill-id="5">
            <h2>账单 2</h2>
            <p>总金额: $150</p>
            <div class="details">
                <h3>账单详情</h3>
                <ul>
                    <li>项目 1: $75</li>
                    <li>项目 2: $50</li>
                    <li>项目 3: $25</li>
                </ul>
            </div>
        </div>
    </div>

    <script>
        function toggleDetails(billId) {
            const details = document.querySelector(`.bill[data-bill-id="${billId}"] .details`);
            if (details.style.display === 'none' || details.style.display === '') {
                details.style.display = 'block';
            } else {
                details.style.display = 'none';
            }
        }

        document.querySelectorAll('.bill').forEach(bill => {
            bill.addEventListener('click', () => {
                const billId = bill.getAttribute('data-bill-id');
                toggleDetails(billId);
            });
        });
    </script>
</body>
</html>
