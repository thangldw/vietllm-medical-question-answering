# Description

https://challenge.kalapa.vn/portal/vietnamese-medical-question-answering/overview

## Problem statement

OCR là một trong những bài toán kinh điển trong lĩnh vực thị giác máy tính. Tuy đã được nghiên cứu trong nhiều năm nhưng việc OCR chữ viết tay, đặc biệt là với tiếng Việt còn gặp nhiều khó khăn.

Trong bài toán này, các đội thi sẽ xây dựng một model OCR **light-weight** giải quyết bài toán OCR chữ viết tay tiếng Việt với ngữ liệu là địa chỉ Việt Nam.

## Input & Output

### Input

Ảnh thô chứa một dòng chữ viết tay địa chỉ tiếng Việt

### Output

Đoạn text chứa trong ảnh đầu vào

### Examples

**Input image**

![](https://challenge.kalapa.vn/_nuxt/example_data_handwritten.05ae5a71.png)

**Label**: _Thôn 1 Ea Ktur Cư Kuin Đắk Lắk_

# Evaluation

## Stage 1

Tại stage 1, giải pháp của các đội thi được đánh giá dựa trên độ đo _edit distance (Levenshtein distance)_. Cụ thể, với mỗi test case, điểm mà đội thi nhận được sẽ được tính như sau:

- Giả sử kết quả của đội thi là `output`, nhãn đúng là `label`

- Nếu kết quả đưa ra chính xác tuyệt đối (output == label, edit distance bằng 0) thì điểm đạt được là 1.

- Ngược lại, điểm cho test case được tính theo công thức
    
    score=max(0,1−1.5dn)score = max(0, 1 - \frac{1.5 ^ d}{n})score=max(0,1−n1.5d​)
    
    với _d_ là edit distance giữa xâu output và xâu label, _n_ là độ dài xâu label
    

Điểm của mỗi đội là **điểm trung bình** trên tất cả các test case, đội nào đạt điểm cao hơn sẽ có thứ hạng cao hơn

Nếu có nhiều đội bằng điểm nhau, thời gian inference model sẽ được xét đến. Chi tiết về giới hạn tài nguyên và thời gian inference được nêu rõ trong phần **Limitation**

Stage 1 của cuộc thi diễn ra trong 2 giai đoạn:

- **Public test:** Các đội thi chỉ submit file CSV kết quả như mô tả. Score public test sẽ chỉ có tính chất tham khảo.

- **Private test:** Các đội thi nộp lại source code, BTC sẽ trực tiếp inference model của các đội trên server đã công bố. Thứ hạng cuối cùng của các đội sẽ được xét dựa trên private test.

Tham khảo thêm về edit distance tại: [https://en.wikipedia.org/wiki/Levenshtein_distance](https://en.wikipedia.org/wiki/Levenshtein_distance)

## Stage 2

__________Coming soon__________

# Limitation

- Model size: ≤ 50MB

- Thời gian inference: 2s

- Môi trường inference không có kết nối internet

- Cấu hình máy inference:
    
    - CPU: Intel(R) Core(TM) i9-10900K CPU @ 3.70GHz
    
    - RAM: 64GB

- Dữ liệu: Các đội không được sử dụng các bộ dataset khác ngoài cuộc thi, trừ các bộ dataset tự sinh

- Pre-trained model: Chỉ được sử dụng các pre-trained model được công khai và được huấn luyện cho các mục đích chung. Không được phép sử dụng các pret-rained model huấn luyện cho các bài toán OCR nói chung.
