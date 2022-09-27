---
id: xgmzg0tx4tp061j7gy2iyjd
title: Square và tham vọng về chén thánh của ngành thanh toán
desc: ''
updated: 1652915711689
created: 1652913535723
---
# Reading 2022-05-19

## Metadata

- Ref:: [Dentmakers](https://dentmakers.substack.com/p/square-va-tham-vong-ve-chen-thanh)
- Title:: Square và tham vọng về chén thánh của ngành thanh toán
- Author:: Dentmakers
- Year of publication:: 2022
- Category:: Blog
- Topic:: 
- Related:: 

## Notes from reading

### Overview

Square khởi đầu là một công ty B2B - làm cổng thanh toán cho merchants, nhưng sau đó lại có thể phát triển được một B2C product cực kỳ thành công là mobile wallet mang tên Cash App.

Với việc sở hữu cả hai đầu của một giao dịch từ merchant đến user, và gần đây là phi vụ mua về AfterPay một trong những công ty BNPL lớn nhất hiện nay, để làm cây cầu kết nối hai đầu này, Square trở thành một ứng cử viên nặng ký để có thể chạm đến chén thánh về payment tại Mỹ - A closed-loop payments network.

Chuỗi giá trị của giao dịch thanh toán qua thẻ debit/credit. Về cơ bản mỗi giao dịch dạng này để có sự tham gia của 4 key players chính. Merchant, Acquiring Bank, Card Scheme, Issuing Bank.

![chuoi-giao-dich-the](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fb5e4ab37-7bf2-40d4-838d-ddad31fa304f_1904x430.png){max-width: 300px, display: block, margin: 0 auto}

Khi người dùng thanh toán bằng thẻ, Starbucks sẽ phải chịu 3 lần phí. Tổng ba mức phí này đối với merchant tại Mỹ sẽ là khoảng 1.5-2.5% trên mỗi một giao dịch. Mức phí này thường được gọi chung là [merchant discount rate](https://www.adyen.com/blog/interchange-fees-explained) và merchant sẽ phải chịu toàn bộ. Tức là từ $100 bạn trả qua thẻ, Starbuck chỉ thực sự nhận về được khoảng $97.5
- Acquiring markup (processor fees). Phí này trả cho Acquiring Bank - tức ngân hàng chấp nhận thẻ. Ngân hàng này sẽ thay mặt merchant để nhận tiền từ ngân hàng của user, sau đó trả lại cho merchant. Giả sử máy POS để quẹt thẻ tại Starbucks là do Bank of America phát hành thì acquiring bank trong trường hợp này chính là Bank of America
- Card scheme fees (assessment fees). Phí này trả cho mạng lưới phát hành thẻ - tức Visa hoặc Master network. Visa và Master giống như một hệ thống điều hướng - routing giúp kết nối ngân hàng từ hai phía - merchant và user lại với nhau
- Interchange fees. Phí này trả cho ngân hàng phát hành ra thẻ của bạn - tức Citibank trong trường hợp này. Cashback mà người dùng thường nhận được khi quẹt thẻ chính là đến từ việc ngân hàng phát hành chia sẻ một phần Interchange fees này lại cho người dùng

### Business model

Mọi điện thoại trên thị trường, không chỉ iPhone, đều có một cổng kết nối tai nghe để nhận tín hiệu audio. Nói theo một cách khác thì nếu Square có thể biến dữ liệu đọc được từ thẻ tín dụng trở thành giống như dữ liệu output dạng audio thì họ có truyền những thông tin này vào iPhone thông qua khe cắm tai nghe. Không chỉ vậy, Apple audio software developer kit là một phần tiêu chuẩn trong thư viện của iPhone. Điều này có nghĩa rằng, bất cứ một developers nào cũng có thể code dựa trên thư viện mở này để tương tác với iPhone mà không cần phải xin phép bất cứ ai tại Apple.

Nhờ khéo léo sử dụng khe cắm tai nghe để “hack” luật của Apple về dock connector, team Square chỉ mất một tuần để tạo ra working prototype đầu tiên của máy đọc thẻ -Square Reader.

Về phía backend, Square tiếp tục việc “hack” của mình bằng một chiến lược rất thông minh. Square tạo một tài khoản merchant account để làm việc trực tiếp với acquiring bank. Tài khoản này đóng như một tài khoản tổng cho tất cả các merchant con sử dụng Square.

Hiểu đơn giản là những merchant đăng ký mới với Square sẽ không phải trải qua chu trình đăng ký phức tạp và tốn thời gian như khi trực tiếp đi tạo tài khoản merchant account với acquiring bank. Họ chỉ cần đăng ký cực kỳ nhanh một tài khoản Square và sẽ ngay lập tức nhận được một đầu đọc thẻ Square Reader để bắt đầu.

Toàn bộ chu trình này, Square như một trung gian đứng giữa các merchant nhỏ và acquiring bank. Giúp đơn giản hoá mọi thứ và tối ưu trải nghiệm cho những merchant nhỏ này, tuy nhiên vẫn tận dùng cơ sở hạ tầng sẵn có từ acquiring bank.

![payments-layer](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fe13ecc33-cc90-4f7a-a798-7d7bbc6c9ea5_1906x932.png){max-width: 300px, display: block, margin: 0 auto}

Những công ty đứng giữa merchant và acquiring bank như Square, Stripe, PayPal, Adyen được gọi chung là tầng lớp Payment Facilitators / Aggregators.

Square đóng vai trò là Payment Faciliator, đứng giữa Merchant và Acquiring bank. Square sẽ thu về một khoản phí cố định - merchant discount rate là khoảng 2.5-3% cent trên mỗi giao dịch tuỳ loại, từ merchant. Đây cũng chính là miếng bánh mà Square sau đó sẽ phải chia sẻ với các players còn lại trong chuỗi giá trị. Square sẽ giữ khoảng 1/3 của lượng phí này - tức 0.5-1% trên tổng giá trị của giao dịch dưới dạng acquiring markup. Phần còn lại được trả cho các players tiếp theo dưới dạng card scheme fees - cho Visa/Mastercard và interchange fees - cho ngân hàng phát hành thẻ.

Trong chuỗi giá trị của giao dịch thẻ, miếng bánh to nhất luôn thuộc về issuing side - tức bên phát hành ra thẻ cho người dùng. Nếu coi toàn bộ miếng bánh là 3 phần thì acquiring side - đầu merchant như Stripe, Square sẽ ăn được 1/3. 2/3 còn lại của miếng bánh sẽ thuộc về issuing side. Card scheme fee cho Visa/Mastercard là quá nhỏ nên về cơ bản có thể bỏ qua.

Về cơ bản, Square nắm giữ phần bánh phía đầu merchant, ngược lại Cash App nắm giữ phần bánh phía đầu người dùng. Cụ thể, Cash App đóng vai trò như một Issuing bank, phát hành thẻ cho người dùng, từ đó thu về interchange fee trên mỗi giao dịch.

Sẽ ra sao nếu Square cho phép người dùng Cash App dùng chính ứng dụng này để thanh toán tại những merchant sử dụng POS của Square? Điều này sẽ giúp Square gói trọn từ đầu đến cuối của giao dịch, loại bỏ toàn bộ Visa, Mastercard và những player khác. Từ đó, có thể thu về toàn bộ merchant discount rate mà không phải chia sẻ cho bất kỳ ai. Hệ sinh thái khép kín này, nơi một công ty sở hữu toàn bộ chuỗi giá trị được gọi là `a closed loop payment network`, vốn được coi là chén thánh của ngành thanh toán.

#### Pitch deck

![pitch](https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com%2Fpublic%2Fimages%2Fc28f647a-8b06-4024-b38c-4fe84d1bb4ad_1212x700.png){max-width: 300px, display: block, margin: 0 auto}

Tầng lớp merchant nhỏ này đang bị tính phí cao nhất nhất từ Acquirers, trong khi lại bị đối xử với trải nghiệm khách hàng tệ nhất. Square có thể mang đến một trải nghiệm đơn giản tiện lợi để phục vụ tầng lớp merchant đang bị “underserved’ này.

Không những vậy, tiềm năng lớn hơn cả của Square là việc mở rộng thị trường này đến những merchant trước đây chưa từng có cơ hội chấp nhận thẻ. Cụ thể, trước khi có Square, điều kiện để merchant có thể đăng ký tài khoản merchant account là phải có tối thiểu $10,000 doanh thu/năm. Quy định về doanh thu này, cùng với những thủ tục phức tạp để ứng tuyển, chi phí đắt đỏ để mua máy POS/phần mềm khiến một số lượng lớn merchant muốn chấp nhận thẻ đành từ bỏ ý định này.

Chi phí để sản xuất ra một chiếc Square reader chỉ là 97 cent - tức rẻ hơn 979 lần so với những thiết bị trên thị trường. Sự chênh lệch về giá đến một trời một vực này giúp Square có thể cho không nó cho merchant như một cách để acquire merchant với chi phí cực kỳ thấp.

Ngoài việc cho không phần cứng, Square cũng không tính phí thuê phần mềm hàng tháng hay bất cứ một khoản charge ngoài lề nào khác. Square cũng không yêu cầu merchant phải có mức doanh thu tối thiểu là $10,000 như quy định đăng ký merchant account truyền thống. Không những vậy, Square còn xây dựng thêm một phần mềm quản lý và analytics hoàn toàn miễn phí để giúp merchant theo các biến động về doanh số. Mức phí duy nhất mà merchant phải trả là mức cố định - 2.75% trên mỗi một giao dịch.