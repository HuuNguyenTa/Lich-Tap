
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lịch Tập</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 800px;
            margin: 50px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 20px;
        }
        .timeline {
            position: relative;
            padding: 20px 0;
        }
        .timeline-item {
            margin-bottom: 20px;
            padding-left: 40px;
            position: relative;
        }
        .timeline-item::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 10px;
            height: 10px;
            background-color: #4CAF50;
            border-radius: 50%;
            z-index: 1;
        }
        .timeline-item::after {
            content: '';
            position: absolute;
            left: 5px;
            top: 10px;
            height: calc(100% - 10px);
            width: 2px;
            background-color: #4CAF50;
        }
        .timeline-item:last-child::after {
            display: none;
        }
        .day {
            font-weight: bold;
            color: #333;
            margin-bottom: 5px;
        }
        .content {
            color: #666;
            line-height: 1.5;
        }
        .rest-day .content {
            color: #000;
        }
        .tips {
            margin-top: 30px;
            text-align: center;
        }
        .tips h2 {
            color: #333;
        }
        .tips ul {
            list-style-type: none;
            padding: 0;
            color: #4CAF50;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>LỊCH TẬP</h1>
        <p style="text-align: center; font-style: italic;">Mỗi buổi ~45–60 phút</p>
        <div class="timeline" id="timeline">
            <!-- Timeline items will be dynamically added here -->
        </div>
        <div class="tips">
            <h2>TIPS:</h2>
            <ul>
                <li>Đừng bỏ bữa sáng.</li>
                <li>Uống đủ nước.</li>
                <li>Ngủ 7–8 tiếng – ngủ là lúc cơ bắp phát triển!</li>
                <li>Đừng nôn nóng: 4–6 tuần đầu thấy body gọn rõ.</li>
                <li>Ăn đủ protein/ngày.</li>
            </ul>
        </div>
    </div>

    <script>
        const timelineData = [
            {
                day: "MONDAY",
                content: [
                    "Warm-up: 5–10 phút (Jumping jack, xoay khớp)",
                    "Hít đất – 3 set x 15–20",
                    "Dumbbell Shoulder Press – 3 set x 12–15",
                    "Dumbbell Bench Press – 3 set x 12–15",
                    "Tricep kickback – 3 set x 15",
                    "Core: Plank – 2 set x 30s, Mountain climbers – 2 set x 1 phút",
                    "Cool down: Giãn cơ nhẹ"
                ]
            },
            {
                day: "TUESDAY",
                content: [
                    "Warm-up: 5–10 phút (Jumping jack, xoay khớp)",
                    "Bent-over row – 3 set x 15",
                    "Bicep curl – 3 set x 15",
                    "Lateral raise – 2 set x 15",
                    "Xô dày/kéo tạ – 2 set x 15",
                    "Superman/Deadlift nhẹ – 2 set x 15",
                    "Cool down"
                ]
            },
            {
                day: "WEDNESDAY",
                content: [
                    "Warm-up: Squat không tạ, nhảy nhẹ",
                    "Squat (có tạ) – 3 set x 10",
                    "Lunges – 2 set x 10 bước/chân",
                    "Deadlift nhẹ – 3 set x 15",
                    "Leg extension – 2 set x 15",
                    "Glute bridge – 2 set x 15",
                    "Core: Leg raise – 2 set x 15, Plank – 2 set x 30s",
                    "Cool down"
                ]
            },
            {
                day: "THURSDAY",
                content: ["Nghỉ hoặc Cardio nhẹ (Đi bộ 30p, đạp xe)"],
                isRest: true
            },
            {
                day: "FRIDAY",
                content: [
                    "Warm-up: 5–10 phút (Jumping jack, xoay khớp)",
                    "Hít đất – 2 set x 20",
                    "Bent-over row – 2 set x 15",
                    "Shoulder Press – 2 set x 15",
                    "Deadlift – 2 set x 15",
                    "Core: Plank – 2 set x 1 phút"
                ]
            },
            {
                day: "SATURDAY",
                content: ["Nghỉ hoặc Cardio nhẹ"],
                isRest: true
            },
            {
                day: "SUNDAY",
                content: ["Nghỉ hoặc Cardio nhẹ"],
                isRest: true
            }
        ];

        const timeline = document.getElementById('timeline');
        timelineData.forEach(item => {
            const div = document.createElement('div');
            div.className = `timeline-item ${item.isRest ? 'rest-day' : ''}`;
            div.innerHTML = `
                <div class="day">${item.day}</div>
                <div class="content">${item.content.map(line => `<p>${line}</p>`).join('')}</div>
            `;
            timeline.appendChild(div);
        });
    </script>
</body>
</html>
