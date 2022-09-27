---
id: 0ppe5i8lqtc1e7jk9zjfar7
title: Mfast Data Analyst
desc: Mfast Data Analyst
updated: 1664147731697
created: 1663168170929
tags:
  - topic.data
  - cat.tut
---
# Mfast Data Analyst 2022-09-01

Đề bài vòng 1 cho vị trí data analyst ở mfast. [JD](https://mfast.talent.vn/job/senior-data-analyst-1515).

## Tóm tắt yêu cầu

Input: file data.xlsx, visitor_info.csv, challenge.pdf

`data.xlsx`: thông tin đơn hàng gồm mã định danh của khách, số lượng đơn hàng đã đặt và ngày đơn hàng được thực hiện
-	visitor_id: mã định danh của khách hàng
-	bảng dữ liệu đầu vào của đề bài ở dạng bảng pivot

`visitor_info.csv`: thông tin khách hàng
-	create_date: ngày ghi nhận lượt ghé thăm của khách hàng
-	visitor_id: mã định danh của khách hàng
-	gender: thông tin giới tính của khách
-	age: tuổi của khách
-	visitor_source: ghi nhận kênh tiếp cận mà khách đã dùng

`challenge.pdf`: mô tả tình huống và các yêu cầu
- A: lọc ra tập khách hàng thỏa mãn 2 điều kiện: 
    - tiếp cận với cty qua kênh cửa hàng
    - đã có thực hiện đơn hàng
	- từ tập khách hàng này, tính xem số khách nữ chiếm bao nhiêu %?
- B: làm 1 dashboard thể hiện được:
	- số lượng đơn hàng theo tuần, sự thay đổi của số lượng đơn hàng theo thời gian
	- dự báo số lượng đơn hàng tới cuối tháng
	- so sánh số lượng dự báo với số lượng do phòng kinh doanh đề xuất
- C: làm 1 dashboard thể hiện được:
    - tỉ lệ chuyển đổi, theo ngày. Nhằm đánh giá nhận định “khách nào có ghé vào thì cũng mua hàng hết”
    - tỉ lệ giữ chân khách hàng

## Hướng giải quyết

### Sơ chế, làm sạch dữ liệu

file data.xlsx:
- loại bỏ hàng header nội dung hướng dẫn
- chuyển đổi sang định dạng csv
- chuyển các dữ liệu bảng sang dạng unpivot [^1]

[^1]: [microsoft | Unpivot columns (Power Query)](https://support.microsoft.com/en-us/office/unpivot-columns-power-query-0f7bad4b-9ea1-49c1-9d95-f588221c7098)

file visitor_info.csv:
- Sửa lỗi chính tả trong cột visitor_source từ “Cừa hàng” thành “Cửa hàng”

Import 2 file dữ liệu csv trên vào Power BI để thực hiện việc làm báo cáo và minh họa dữ liệu.

### Data model

- fOrder: fact table, measure orders
    - visitor_id: data type: text
    - order_date: data type: date
    - order_quantity: data type: integer
- dVisitor: dimension table, depict customers
    - create_date: data type: date
    - visitor_id: data type: text
    - gender: data type: text
    - age: data type: integer
    - visitor_source: data type: text
- dDate: dimension table, depict dates

### Làm báo cáo và minh họa dữ liệu

## Related

- [microsoft | Unpivot columns (Power Query)](https://support.microsoft.com/en-us/office/unpivot-columns-power-query-0f7bad4b-9ea1-49c1-9d95-f588221c7098)
- [geeksforgeeks | Pivot and Unpivot in SQL](https://www.geeksforgeeks.org/pivot-and-unpivot-in-sql/)