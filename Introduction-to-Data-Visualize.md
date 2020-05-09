# Series Data Analyzing và Visualizing 
## Lời tựa
Trong công việc AI engineer, làm việc với data là một phần không thể tách rời với quy trình phát triển mô hình, cứ như đồng tiền phải đi liền với khúc ruột vậy \*penguin emoticon*.  
Một câu hỏi đặt ra: Tôi làm vision thì sao phải xử lý data?????  
_ Câu trả lời ngắn: Bạn phải test model sau khi train chứ.  
_ Câu trả lời dài: Mỗi mô hình sau khi train xong đều cần được test performance trên tập test. Việc phân tích data do mô hình test xong ảnh hưởng rất nhiều tới cách ta giải quyết vấn đề.  
Cụ thể: Bạn có mô hình nhận dạng chó mèo, sau khi chạy xong bạn nhận được tỉ lệ phân loại trên tập test là 90%, bạn thấy performance quá tệ, bạn không làm gì nữa mà vứt luôn mô hình rồi tìm mô hình mới. Tuy nhiên, nếu bạn biết cách phân tích data, bạn sẽ lọc 10% ảnh bị sai ra thành các đặc tính, biểu diễn chúng trên các biểu đồ, ví dụ: bạn plot vài đặc tính của tập dữ liệu ra thành scatter plot, bạn phát hiện trong plot về số chiều dữ phân thành hai cụm khá rõ rệt là chiều bằng 1 và chiều bằng 3, bằng cách tính % đơn giản bạn biết được số ảnh trắng đen chiếm tới 5%, đầu bạn sáng lên "aha" và bạn đã có hướng đi tiếp theo cho mình.
Đấy là một ví dụ nhỏ về sự cần thiết của kỹ năng làm data. Mình luôn tâm đắc 1 câu nói rất nổi tiếng trong giới xử lý ảnh: "A picture is worth a thousand words"
## Phần 1: Làm việc với Pandas
Ta bắt đầu series này với bạn - Nhà tư vấn phân tích và biểu diễn dữ liệu siêu hạng làm việc ở công ty Sao Hỏa đang trong bài giới thiệu về pandas cho các AI dev của công ty.  
"Mà khoan!" - Ai đó trong phòng lên tiếng  
"Tại sao lại là pandas? Trong khi đã có numpy array và dictionary?" - Người đó tiếp tục  
Bạn nhướng mài: "Không ai dùng 1 đoàn xe máy để xuất trái cây qua Tàu cả, họ dùng container!"  
Pandas không chỉ giúp chúng ta tiết kiệm thời gian suy nghĩ cách tổ chức và xử lý dữ liệu mà nó còn giúp ta tiết kiệm công sức vẽ plot với thư viện seaborn đi kèm.  
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
Một ứng dụng vô cùng hữu ích của pandas đó là load được dữ liệu từ những loại file phổ biến trong ngành Data như .xlsx, .csv, .json và xuất ngược lại những loại file này:
```
# Các file trong bài đều có thể tìm thấy trong gitlab ở cuối trang
dframe = pd.read_csv('cat.csv')

dframe.to_csv('abc.csv')

import sys
dframe.to_csv(sys.stdout)
```
Ngoài ra pandas còn cho phép ta làm việc với missing data trong dataset:
```
dframe = DataFrame([[1,2,3],[np.nan,5,6],[7,np.nan,9],[np.nan,np.nan,np.nan]])
# Ta có thể fill giá trị bị thiếu hoặc loại bỏ dòng có data missing
dframe.fillna(1)
dframe2.dropna(thresh=2)
```
Ok phần 1 tạm kết thúc ở đây, các bạn ngâm cứu kỹ hơn về phần này trong các notebook: Introduction-to-pandas, CSV-Reading, Data-Aligment-And-Rank-Sort, Indexing-And-Drop-Select-Entry, Summary-statistic-And-Missing-data-And-Level-Hierachy
Tất cả code đã được cung cấp tại [gitlab của mình](https://gitlab.com/vinh.ngo/Data-Analyze-And-Visualize), các bạn cứ lên đấy tải về nhé