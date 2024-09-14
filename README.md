# Giới thiệu

Minh hoạ ví dụ chuyển đổi file sao kê từ định dạng PDF sang bảng tính. Nội dung chương trình thực tế được chia sẻ trong Khoá học Python Web Scraping [tại đây]([Khoá học Python Web Scraping - Thu thập mọi dữ liệu từ Internet | LEarn Anything](https://course.learn-anything.vn/courses/python-web-scraping-thu-thap-du-lieu-tu-internet/))



# # Cấu trúc thư mục

`README.md` chứa thông tin mô tả & hướng dẫn.

`/src`  chứa thông tin các file sao kê định dạng PDF được MTTQ Việt Nam chia sẻ.

`/output` chứa thông tin mẫu được chương trình trích xuất.



# Cấu trúc chương trình

Chương trình hoàn chỉnh để xử lý file sao kê PDF và trích xuất thông tin sao kê dạng bảng tính thành định dạng csv bao gồm các hàm chức năng chính sau:

- `sample_pages` cho phép trích xuất 3 mẫu trang PDF trong file thành hình ảnh gồm trang đầu, trang cuối và trang 2 giúp phân tích bố cục trang, kích thước cần áp dụng crop.

- `split` cho phép chia nhỏ file PDF lớn thành các phần khác nhau, mỗi phần là 1 batch (mẻ) bao gồm số trang giới hạn nhất định, ví dụ 100 trang. Việc này giúp việc xử lý từng phần tối ưu cho việc kiểm thử cũng như bảo vệ thành quả xử lý nếu không may xảy ra lỗi trong thời gian thực hiện.

- `crop` cho phép cắt lề các trang pdf giúp loại bỏ phần thông tin thừa trong trang không thuộc phạm vi bảng tính. Các thông tin mô tả ở trang đầu, thông tin ở footer (chân trang) từ trang thứ 2 đến trang kế trang cuối, phần header của bảng lặp lại ở các trang.

- `to_csv` cho phép trích xuất nội dung file PDF sang file csv, áp dụng với file PDF đã được crop.

- `to_text` cho phép chuyển đổi nội dung văn bản trong hình ảnh (file scan) thành văn bản.
