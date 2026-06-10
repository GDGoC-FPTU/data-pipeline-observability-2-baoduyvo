# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-BAODUY
**Name:** Vo Duy Bao
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | Agent trả lời chính xác, gợi ý đúng sản phẩm. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Agent bị đánh lừa bởi dữ liệu rác chứa giá trị ngoại lai. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent đã trả lời sai khi sử dụng Garbage Data vì tập dữ liệu rác không được kiểm duyệt, chứa các bản ghi không hợp lý như "Nuclear Reactor" với mức giá trị ngoại lai (outlier) lên tới 999999. Logic tìm kiếm của Agent chỉ đơn giản là tìm kiếm từ khoá và chọn sản phẩm có giá cao nhất. Do dữ liệu chưa được làm sạch, Agent đã chọn phải dữ liệu sai lệch và đưa ra gợi ý không chính xác. Việc thiếu kiểm soát chất lượng dữ liệu như trùng lặp (duplicate IDs), sai kiểu dữ liệu (wrong types) hay giá trị trống (null values) có thể làm gián đoạn hệ thống AI hoặc cung cấp thông tin rác cho người dùng.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Đồng ý.

Chất lượng của dữ liệu (Quality Data) đóng vai trò nền tảng và quan trọng hơn so với chất lượng của câu lệnh (Quality Prompt) trong hệ thống AI. Một câu lệnh tốt cũng không thể cứu vãn được nếu AI truy xuất từ một nguồn dữ liệu sai lệch. Dữ liệu sạch sẽ và chuẩn xác đảm bảo câu trả lời tin cậy và an toàn.
