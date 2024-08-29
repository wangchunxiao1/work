<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>明细查询</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }

        header {
            background-color: #f8f8f8;
            padding: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .back-button {
            font-size: 24px;
            cursor: pointer;
        }

        .header-right {
            display: flex;
            align-items: center;
        }

        .account-info {
            display: flex;
            justify-content: space-between;
            padding: 10px;
            background-color: #f0f0f0;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .time-selector {
            display: flex;
            justify-content: space-around;
            padding: 10px;
            background-color: #f0f0f0;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .time-button {
            padding: 10px 20px;
            border: none;
            border-radius: 20px;
            background-color: #f0f0f0;
            margin: 0 5px;
            cursor: pointer;
            transition: all 0.2s ease-in-out;
        }

        .time-button.active {
            background-color: orange;
            color: white;
        }

        .transactions {
            padding: 10px;
            background-color: #fff;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .transaction-item {
            display: flex;
            justify-content: space-between;
            padding: 10px;
            border-bottom: 1px solid #ddd;
            transition: all 0.2s ease-in-out;
        }

        .transaction-item:last-child {
            border-bottom: none;
        }

        .transaction-item:hover {
            background-color: #f0f0f0;
        }
    </style>
</head>
<body>
    <header>
        <div class="header-content">
            <div class="back-button">❮</div>
            <h1>明细查询</h1>
            <div class="header-right">
            </div>
        </div>
    </header>
    <main>
        <div class="account-info">
            <div class="account-number">6228 **** 9073</div>
            <div class="currency">人民币 | 本币</div>
        </div>
        <div class="time-selector">
            <button class="time-button" data-time="近一周">近一周</button>
            <button class="time-button" data-time="近一月">近一月</button>
            <button class="time-button" data-time="近三月">近三月</button>
            <button class="filter-button">筛选</button>
        </div>
        <div class="transactions">
            <!-- 交易数据将动态添加在这里 -->
        </div>
    </main>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const timeButtons = document.querySelectorAll('.time-button');
            const transactions = document.querySelector('.transactions');

            // 假数据
            const data = [
                { date: '2024-08-01 08:13:34', amount: -2181.90, type: '转支' },
                { date: '2024-07-31 15:04:14', amount: 2181.90, type: '转存' },
                { date: '2024-06-19 15:34:14', amount: -49400.00, type: '转支' },
                { date: '2024-06-19 15:04:14', amount: 49400.00, type: '转存' }
            ];

            function displayTransactions(time) {
                transactions.innerHTML = '';
                const filteredData = data.filter(item => {
                    const date = new Date(item.date);
                    const now = new Date();
                    const diff = now - date;
                    const daysDiff = Math.floor(diff / (1000 * 60 * 60 * 24));
                    return daysDiff <= time;
                });

                filteredData.forEach(item => {
                    const transactionItem = document.createElement('div');
                    transactionItem.className = 'transaction-item';
                    transactionItem.innerHTML = `
                        <div>${item.type}</div>
                        <div>${item.date}</div>
                        <div>${item.amount}</div>
                    `;
                    transactions.appendChild(transactionItem);
                });
            }

            timeButtons.forEach(button => {
                button.addEventListener('click', function() {
                    timeButtons.forEach(btn => btn.classList.remove('active'));
                    this.classList.add('active');
                    const time = this.getAttribute('data-time');
                    displayTransactions(time === '近一周' ? 7 : time === '近一月' ? 30 : 90);
                });
            });

            // 默认显示近三月的数据
            timeButtons[2].click();
        });
    </script>
</body>
</html>
