<!DOCTYPE html>
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
        }
        header {
            background-color: #f8f8f8;
            padding: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .header-left {
            display: flex;
            align-items: center;
        }
        .header-left span {
            margin-right: 10px;
        }
        .account-number {
            font-size: 24px;
            margin: 10px;
        }
        .tabs {
            display: flex;
            justify-content: space-around;
            background-color: #e8e8e8;
            padding: 10px;
        }
        .tab {
            padding: 10px 20px;
            border-radius: 20px;
            cursor: pointer;
        }
        .tab.active {
            background-color: #ff9800;
            color: white;
        }
        .transactions {
            padding: 20px;
        }
        .transaction {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
            border-bottom: 1px solid #e8e8e8;
        }
        .transaction:last-child {
            border-bottom: none;
        }
    </style>
</head>
<body>
    <header>
        <div class="header-left">
            <span>返回</span>
            <h1>明细查询</h1>
        </div>
        <div class="header-right">
            <span>电话</span>
            <span>筛选</span>
        </div>
    </header>
    <div class="account-number">
        6228 **** 9073
        <span style="float: right;">人民币 | 本币</span>
    </div>
    <div class="tabs">
        <div class="tab active">近一周</div>
        <div class="tab">近一月</div>
        <div class="tab">近三月</div>
    </div>
    <div class="transactions">
        <!-- 生成的交易记录 -->
        <div class="transaction">
            <div>
                <p>度小满（国美易…</p>
                <p>2024-08-27 08:24:51</p>
            </div>
            <div>
                <p>-4,726.67</p>
                <p>余额：762.23</p>
            </div>
        </div>
        <div class="transaction">
            <div>
                <p>网银在线（京东…</p>
                <p>2024-08-26 09:26:37</p>
            </div>
            <div>
                <p>-3,028.59</p>
                <p>余额：5,488.90</p>
            </div>
        </div>
        <!-- 更多交易记录 -->
        <div class="transaction">
            <div>
                <p>支付宝（购物…</p>
                <p>2024-08-25 15:43:21</p>
            </div>
            <div>
                <p>-123.45</p>
                <p>余额：6,365.45</p>
            </div>
        </div>
        <div class="transaction">
            <div>
                <p>微信支付（餐饮…</p>
                <p>2024-08-24 12:34:56</p>
            </div>
            <div>
                <p>-56.78</p>
                <p>余额：6,489.23</p>
            </div>
        </div>
        <div class="transaction">
            <div>
                <p>信用卡还款（招商银行…</p>
                <p>2024-08-23 09:01:12</p>
            </div>
            <div>
                <p>-1,000.00</p>
                <p>余额：6,546.01</p>
            </div>
        </div>
        <div class="transaction">
            <div>
                <p>水电费缴费…</p>
                <p>2024-08-22 10:11:22</p>
            </div>
            <div>
                <p>-234.56</p>
                <p>余额：7,546.01</p>
            </div>
        </div>
        <div class="transaction">
            <div>
                <p>工资收入…</p>
                <p>2024-08-21 14:23:11</p>
            </div>
            <div>
                <p>+4,500.00</p>
                <p>余额：7,780.57</p>
            </div>
        </div>
        <div class="transaction">
            <div>
                <p>房租支出…</p>
                <p>2024-08-20 16:34:21</p>
            </div>
            <div>
                <p>-1,200.00</p>
                <p>余额：3,280.57</p>
            </div>
        </div>
        <div class="transaction">
            <div>
                <p>话费充值…</p>
                <p>2024-08-19 18:45:32</p>
            </div>
            <div>
                <p>-50.00</p>
                <p>余额：4,480.57</p>
            </div>
        </div>
        <div class="transaction">
            <div>
                <p>理财产品赎回…</p>
                <p>2024-08-18 09:01:23</p>
            </div>
            <div>
                <p>+2,300.00</p>
                <p>余额：6,780.57</p>
            </div>
        </div>
        <div class="transaction">
            <div>
                <p>银行存款利息…</p>
                <p>2024-08-17 10:11:22</p>
            </div>
            <div>
                <p>+123.45</p>
                <p>余额：6,657.12</p>
            </div>
        </div>
        <!-- 更多交易记录 -->
    </div>
    <script>
        const tabs = document.querySelectorAll('.tab');
        const transactions = document.querySelectorAll('.transaction');

        function showTransactions(timePeriod) {
            transactions.forEach((transaction, i) => {
                let display = 'flex';

                // 根据时间周期过滤交易记录
                switch (timePeriod) {
                    case 'week':
                        if (i >= 7) display = 'none';
                        break;
                    case 'month':
                        if (i >= 30) display = 'none';
                        break;
                    case 'threeMonths':
                        if (i >= 90) display = 'none';
                        break;
                    default:
                        display = 'flex';
                }

                transaction.style.display = display;
            });
        }

        tabs.forEach((tab, index) => {
            tab.addEventListener('click', () => {
                // 清除所有tab的active类
                tabs.forEach(tab => tab.classList.remove('active'));
                // 添加active类到当前点击的tab
                tab.classList.add('active');

                let timePeriod;

                switch (index) {
                    case 0:
                        timePeriod = 'week';
                        break;
                    case 1:
                        timePeriod = 'month';
                        break;
                    case 2:
                        timePeriod = 'threeMonths';
                        break;
                    default:
                        timePeriod = 'all';
                }

                showTransactions(timePeriod);
            });
        });

        // 默认显示近一周的交易记录
        showTransactions('week');
    </script>
</body>
</html>
