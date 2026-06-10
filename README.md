[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112915&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** baoduyvo@example.com
**Name:** Vo Duy Bao

---

## Mo ta

Bài lab này nhằm mục đích xây dựng một pipeline ETL tự động đơn giản và hiểu được tầm quan trọng của Data Observability đối với AI Agent. Em đã thực hiện các bước trích xuất dữ liệu từ JSON, kiểm tra tính hợp lệ, làm sạch, và ghi vào file CSV. Ngoài ra, em còn chạy thử nghiệm để thấy được dữ liệu rác ảnh hưởng như thế nào đến kết quả đầu ra của AI Agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Mo ta cach ban chay thi nghiem Clean vs Garbage data
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- **Extract**: Đọc thành công 5 dòng dữ liệu từ file `raw_data.json`.
- **Validate**: Đã giữ lại 3 dòng hợp lệ và loại bỏ 2 dòng bị lỗi (1 dòng có giá âm, 1 dòng trống category).
- **Transform & Load**: Áp dụng logic kinh doanh (tính giá sau giảm 10%, chuẩn hoá danh mục thành Title Case) và lưu thành công 3 dòng vào file `processed_data.csv`.
- **Stress Test**: Agent đưa ra kết quả chính xác khi sử dụng `processed_data.csv`, nhưng đã trả lời sai lệch hoàn toàn (gợi ý Nuclear Reactor với giá $999999) khi truy xuất trên tập dữ liệu rác, chứng minh dữ liệu tốt quan trọng hơn câu lệnh (Prompt).
