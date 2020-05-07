# Series Data Analyzing và Visualizing 
## Lời tựa
Trong công việc AI engineer, làm việc với data là một phần không thể tách rời với quy trình phát triển mô hình, cứ như đồng tiền phải đi liền với khúc ruột vậy *penguin emoticon*.  
Một câu hỏi đặt ra: Tôi làm vision thì sao phải xử lý data?????  
_ Câu trả lời ngắn: Bạn phải test model sau khi train chứ.  
_ Câu trả lời dài: Mỗi mô hình sau khi train xong đều cần được test performance trên tập test. Việc phân tích data do mô hình test xong ảnh hưởng rất nhiều tới cách ta giải quyết vấn đề.  
Cụ thể: Bạn có mô hình nhận dạng chó mèo, sau khi chạy xong bạn nhận được tỉ lệ phân loại trên tập test là 90%, bạn thấy performance quá tệ, bạn không làm gì nữa mà vứt luôn mô hình rồi tìm mô hình mới. Tuy nhiên, nếu bạn biết cách phân tích data, bạn sẽ lọc 10% ảnh bị sai ra thành các đặc tính, biểu diễn chúng trên các biểu đồ, ví dụ: bạn plot vài đặc tính của tập dữ liệu ra thành scatter plot, bạn phát hiện trong plot về số chiều dữ phân thành hai cụm khá rõ rệt là chiều bằng 1 và chiều bằng 3, bằng cách tính % đơn giản bạn biết được số ảnh trắng đen chiếm tới 5%, đầu bạn sáng lên "aha" và bạn đã có hướng đi tiếp theo cho mình.
Đấy là một ví dụ nhỏ về sự cần thiết của kỹ năng làm data. Mình luôn tâm đắc 1 câu nói rất nổi tiếng trong giới xử lý ảnh: "A picture is worth a thousand words"
## Phần 1: Làm việc với Pandas
**Series và DataFrame**
Trong pandas, Series và DataFrame là 2 đối tượng mà lập trình viên sẽ làm việc thường xuyên nhất.  
Series là đối tượng giúp ta làm việc với dữ liệu chiều. DataFrame sẽ làm việc với dữ liệu từ 2 chiều trở lên.  
Một vài ví dụ:  
```
obj = Series([4,5,6,6])
ww2_cas = Series([1000, 2000, 3000, 800], index=['USSR','Germany','China','Japan'])

data = {'City':['SF','LA','NYC'], 'Population':[837000,3880000,8400000]}
city_frame = DataFrame(data)
```
Tất cả code đã được cung cấp tại [github của mình](https://github.com/manaclan/Data-Analyze-And-Visualize), các bạn cứ lên đấy tải về nhé