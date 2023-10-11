## Description

Ở cuộc thi này bạn sẽ được cung cấp hơn 600 bài viết về các bệnh thường gặp ở người, mỗi bài viết ứng với một loại bệnh lý khác nhau. Các bài viết này được đăng tải công khai trên website của bệnh viện Tâm Anh. Tất cả các câu hỏi trong các tập test đều dựa trên thông tin của các bài viết được cung cấp.

**Tải data tại đây:** Coming soon

## Files and Folders

- Thư mục `corpus`: chứa các bài viết về các loại bệnh. Mỗi loại bệnh ứng với một file text

- File `public_test.csv`: các câu hỏi trong tập public test

- File `sample_submission.csv`: mẫu submission cho tập public test

## Columns

Với file `public_test.csv`

- `id (string)`: Mã câu hỏi

- `question (string)`: Nội dung câu hỏi.

- `option_1 (string)`: Lựa chọn thứ nhất.

- `option_2 (string)`: Lựa chọn thứ hai.

- `option_3, option_4, option_5, option_6 (string | null)`: Các lựa chọn tiếp theo, nếu câu hỏi không có lựa chọn tương ứng, trường này nhận giá trị null.

Với file `sample_submission.csv`

- `id (string)`: Mã câu hỏi

- `answer (string)`: Xâu nhị phân câu trả lời theo mô tả trong đề bài
