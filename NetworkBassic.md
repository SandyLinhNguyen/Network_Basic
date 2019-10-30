# 1.Mô hình TCP/IP 

![TCP_IP](/img/TCP_IP.png)


Bộ giao thức TCP/IP là một bộ các giao thức truyền thông cài đặt chồng giao thức mà internet và hầu hết các mạng máy tính thương mại đang chạy trên đó. Bộ giao thức này được đặt tên theo hai giao thức chính của nó là TCP (Transmission Control Protocol - Giao thức điều khiển truyền vận) và IP (Internet Protocol - Giao thức Internet).

## Layer 1. Network Access Layer

` Network Access Layer ` xác định chi tiết về về cách thức dữ liệu được gửi qua mạng, bởi các thiết bị phần cứng trực tiếp giao tiếp với môi trường mạng, chẳng hạn như cáp đồng trục, cáp quang hay dây đồng xoắn đôi. Các giao thức bao gồm trong Network Access Layer là Ethernet, Token Ring, FDDI, X.25, Frame Relay ...vv

## Layer 2. Internet Layer

` Internet Layer ` đóng gói dữ liệu vào các gói dữ liệu được biết đến dưới dạng các gói tin thông giao thức Internet Protocol, chứa địa chỉ nguồn và đích (địa chỉ logic hoặc địa chỉ IP) được sử dụng để chuyển tiếp các gói tin giữa các máy chủ và qua các mạng.

## Layer 3. Transport Layer


Mục đích của Transport Layer là cho phép các thiết bị trên máy chủ nguồn và đích đến trao đổi dữ liệu. Transport Layer sẽ xác định mức độ service và trạng thái của kết nối được sử dụng khi vận chuyển dữ liệu. Trong đó có giao thức chính trong lớp Transport là TCP (Transmission Control Protocol). Sử dụng TCP, các ứng dụng trên các máy chủ được nối mạng có thể tạo các "kết nối" với nhau, mà qua đó chúng có thể trao đổi dữ liệu hoặc các gói tin. Giao thức này đảm bảo chuyển giao dữ liệu tới nơi nhận một cách đáng tin cậy và đúng thứ tự.

## Layer 4. Application Layer

Các thực thể của lớp Application cung cấp các ứng dụng cho phép người dùng trao đổi dữ liệu ứng dụng qua mạng

Một số ứng dụng thường gặp của chồng giao thức TCP/IP: FTP (File Transfer Protocol), DNS



# 2. Các giao thức cơ bản 




## a, HTTP 

### HTTP là gì?
HTTP (HyperText Transfer Protocol - Giao thức truyền tải siêu văn bản) là một trong các giao thức chuẩn về mạng Internet, được dùng để liên hệ thông tin giữa Máy cung cấp dịch vụ (Web server) và Máy sử dụng dịch vụ (Web client), là giao thức Client/Server dùng cho World Wide Web – WWW

### Sơ đồ hoạt động của HTTP 

![HTTP](/img/HTTP.png)

HTTP cho phép giao tiếp giữa rất nhiều loại server/client với nhau, chủ yếu thông qua TCP/IP, tuy nhiên bất kỳ giao thức đáng tin cậy nào khác cũng có thể được dùng. Cổng giao tiếp chuẩn là 80, tuy nhiên có thể dùng bất kỳ cổng khác. Giao tiếp giữa client và server dựa vào một cặp request/response. Client khởi tạo HTTP request và nhận HTTP response từ server gửi về.

 

HTTP request bao gồm hai thành phần quan trọng là URL và Verb (phương thức), được gửi từ client. Ở phía ngược lại, server trả về HTTP response trong đó chứa Status code và Message body.
### HTTP request 

![http_request](/img/Screenshot%202019-05-28%20at%2011.09.55.png)

Bắt đầu của HTTP Request sẽ là dòng Request-Line bao gồm 3 thông tin đó là:METHOD, URI, VERSION.
 - Method : là phương thức mà HTTP request sử dụng, thường là GET cà POST.Ngoài ra còn có các phương thức khác :

| STT | Method |
|-----|--------|
|1|GET được sử dụng để lấy lại thông tin từ Server đã cung cấp bởi sử dụng một URI đã cung cấp. Các yêu cầu sử dụng GET nên chỉ nhận dữ liệu và nên không có ảnh hưởng gì tới dữ liệu.|
|2|HEAD tương tự như GET, nhưng nó truyền tải dòng trạng thái và khu vực Header.|
|3| POST một yêu cầu POST được sử dụng để gửi dữ liệu tới Server, ví dụ, thông tin khách hàng, file tải lên, …, bởi sử dụng các mẫu HTML.|
|4| PUT thay đổi tất cả các đại diện hiện tại của nguồn mục tiêu với nội dung được tải lên.|
|5|DELETE gỡ bỏ tất cả các đại diện hiện tại của nguồn mục tiêu bởi URI.|
|6|CONNECT thiết lập một tunnel tới Server được xác định bởi URI đã cung cấp.|
|7|OPTIONS miêu tả các chức năng giao tiếp cho nguồn mục tiêu.|
|8|TRACE trình bày một vòng lặp kiểm tra thông báo song song với path tới nguồn mục tiêu.|

- URI : là địa chỉ định danh của tài nguyên. Trong tường hợp này URI là / - tức request cho tài nguyên gốc, nếu request không yêu cầu một tài nguyên cụ thể, URI có thể là dấu *.
- HTTP version : là phiên bản HTTP đang sử dụng, ở đây là HTTP 1.1.

Tiếp theo là các trường request-header, cho phép client gửi thêm các thông tin bổ sung về thông điệp HTTP request và về chính client. Một số trường thông dụng như:
 - User-Agent: thông tin về user agent của người dùng.
 - Host: là địa chỉ destination. 
 - Connection là kiểu kết nối . 


### HTTP Response

![http_response](/img/Screenshot%202019-05-28%20at%2011.09.38.png)

Cấu trúc HTTP response gần giống với HTTP request, chỉ khác nhau là thay vì Request-Line, thì HTTP có response có Status-Line. Và giống như Request-Line, Status-Line cũng có ba phần như sau:

- HTTP-version: phiên bản HTTP cao nhất mà server hỗ trợ.
- Status-Code: mã kết quả trả về.
- Reason-Phrase: mô tả về Status-Code.

#### Status Code 
Status code là thông tin quan trọng server trả về cho client, cho biết kết quả xử lý request của server. Các loại status code thường gặp:

- 1xx: Informational Messages loại status code này được mô tả ở HTTP/1.1 và hoàn toàn mang tính chất tạm thời, client có thể bỏ qua chúng.

- 2xx: Successful: Server trả về status dạng này khi đã xử lý thành công request của client. Đối với GET request, dữ liệu trả về nằm trong message body. Phổ biến nhất là mã 200 OK. Ngoài ra còn có:

  - 202 Accepted: request từ client đã được chấp nhận nhưng có thể server không trả về kết quả cho client. Điều này hữu dụng trong trường hợp xử lý bất đồng bộ phía server: server thông báo cho client không phải tiếp tục chờ đợi cho tới khi quá trình xử lý trên server hoàn tất.
  - 204 No content: không có phần message body trong response.
  - 205 Reset content: tương tự như 204, nhưng mã trả về này yêu cầu client reset document view.
  - 206 Partial content: server chỉ gửi về một phần dữ liệu phụ thuộc và giá trị range header client gửi lên. Giá trị này được sử dụng bởi các tool hỗ trợ download như wget, IDM để phân mảnh dữ liệu thành nhiều phần nhằm tải về đồng thời hoặc hỗ trợ tiếp tục download khi bị ngắt giữa chừng.
- 3xx: Redirection
: server thông báo cho client phải thực hiện thêm action để hoàn thành request.

  - 301 Moved Permanently: resource đã được chuyển hoàn toàn tới địa chỉ trong trường Location của response.
  - 303 See Other: resource được chuyển tạm thời tới địa chỉ trong trường Location của response.
  - 304 Not Modified: resource không thay đổi từ lần cuối cùng client gửi request, và client nên sử dụng dữ liệu đã lưu trong bộ nhớ cache. Điều này được thực hiện bằng cách khi gửi request, client gửi đi trường ETag là định danh của phần dữ liệu đã request lần trước, server so sánh với trường ETag ứng với dữ liệu của nó để kiểu tra sự thay đổi.
 - 4xx: Client Error
   - 400 Bad Request: request không đúng định dạng, cú pháp.
   - 401 Unauthorized: client chưa xác thực.
   - 403 Forbidden: client không có quyền truy cập.
   - 404 Not Found: không tìm thấy resource.
   - 405 Method Not Allowed: phương thức (HTTP verb) không được server hỗ trợ.
 - 5xx: Server Error
: có lỗi xảy ra trong quá trình xử lý của server. Mã 500 Internal Server Error là phổ biến nhất.

   - 501 Not Implemented: server không hỗ trợ chức năng client yêu cầu.
   - 503 Service Unavailable: một thành phần xử lý trên server bị lỗi hoặc server bị quá tải.

## b, DHCP 
` DHCP ` là giao thức cấp phát ip một cách tự động cùng với các cấu hình liên quan như subnet mask và gateưay và cung cấp database trung tâm để theo dõi tất cả máy tính trong hệ thống mạng tránh việc trùng lặp ip như cài đặt ip thủ công.


## Mô hình làm việc của DHCP 
![DHCP](/img/DHCP.png)

Khi 1 thiết bị được bật và kết nối tới một mạng có máy chủ DHCP, thiết bị sẽ gửi yêu cầu tới máy chủ, và yêu cầu đó được gọi là yêu cầu DHCPDISCOVER.

Sau khi gói DISCOVER đến máy chủ DHCP, máy chủ sẽ tìm cách giữ lấy một địa chỉ IP mà thiết bị có thể sử dụng, và sau đó cung cấp cho client địa chỉ với một gói DHCPOFFER.

Sau khi cung cấp địa chỉ IP đã chọn, thiết bị sẽ phản hồi lại máy chủ DHCP với một gói DHCPREQUEST để chấp nhận yêu cầu, máy chủ sau đó sẽ gửi ACK để xác nhận thiết bị đã có địa chỉ IP cụ thể và xác định khoảng thời gian thiết bị có thể sử dụng địa chỉ đó trước khi nhận một địa chỉ mới.

## c, DNS 
` Domain Name System ` là hệ thống thiết lập tương ứng giữ địa chỉ ip và tên miền giúp người đọc dễ nhớ hơn là những chữ số IP .


### Mô hình hoạt động của DNS 
![Các bước truy vấn](/img/Cac_buoc_truy_van.png)

Giả sử máy tính muốn truy cập vào trang whitehat.vn 

Trước hết chương trình trên máy người sử dụng gửi yêu cầu tìm kiếm địa chỉ IP ứng với tên miền whitehat.vn tới máy chủ quản lý tên miền (name server) cục bộ thuộc mạng của nó.Máy chủ tên miền cục bộ này kiểm tra trong cơ sở dữ liệu của nó có chứa cơ sở dữ liệu chuyển đổi từ tên miền sang địa chỉ IP của tên miền mà người sử dụng yêu cầu không. Trong trường hợp máy chủ tên miền cục bộ có cơ sở dữ liệu này, nó sẽ gửi trả lại địa chỉ IP của máy có tên miền nói trên.Trong trường hợp máy chủ tên miền cục bộ không có cơ sở dữ liệu về tên miền này nó sẽ hỏi lên các máy chủ tên miền ở mức cao nhất ( máy chủ tên miền làm việc ở mức ROOT). Máy chủ tên miền ở mức ROOT này sẽ chỉ cho máy chủ tên miền cục bộ địa chỉ của máy chủ tên miền quản lý các tên miền có đuôi .VN.Máy chủ tên miền cục bộ gửi yêu cầu đến máy chủ quản lý tên miền có đuôi (.VN) tìm tên miền whitehat.vn. Máy chủ tên miền quản lý các tên miền.VN sẽ gửi lại địa chỉ của máy chủ quản lý tên miền whitehat.vnMáy chủ tên miền cục bộ sẽ hỏi máy chủ quản lý tên miền vnn.vn này địa chỉ IP của tên miền whitehat.vn. Do máy chủ quản lý tên miền vnn.vn có cơ sở dữ liệu về tên miền whitehat.vn nên địa chỉ IP của tên miền này sẽ được gửi trả lại cho máy chủ tên miền cục bộ. Máy chủ tên miền cục bộ chuyển thông tin tìm được đến máy của người sử dụng. Người sử dụng dùng địa chỉ IP này để kết nối đến server chứa trang web có địa chỉ whitehat.vn




## d, TCP - UDP 

| TCP | UDP |
|-----|-----|
| TCP có quá trình kiểm tra lỗi khi truyền tin nên độ tin cậy cao và không bị mất dữ liệu nhưng bị giới hạn thời gian chuyển gói tin vì khi bên chuyển nhận được xác nhận đã nhận gói tin thì mới tiếp tục chuyển tiếp | UDP không có quá trình kiểm tra lỗi khi truyền tin nên độ tin cậy là k có và không thể kiểm soát lỗi trong quá trình truyền tin nhưng bù lại được thời gian chuyển gói tin vì không cần xác nhận gói tin đã được nhận nên việc gửi gói tin theo UDP được gửi một cách liên tục |



## e, IP , ARP , ICMP 

#### IP:
` Internet protocol ` là giao hướng gói dữ liệu sử dụng bởi các máy chủ nguồn và đích để truyền dữ liệu liên mạng chuyển mạch gói 

### ARP  :
` ARP ` là phương thức phân giải địa chỉ động giữa địa chỉ lớp network và địa chỉ lớp datalink. Quá trình thực hiện bằng cách: một thiết bị IP trong mạng gửi một gói tin local broadcast đến toàn mạng yêu cầu thiết bị khác gửi trả lại địa chỉ phần cứng ( địa chỉ lớp datalink ) hay còn gọi là Mac Address của mình.



### ICMP : 

![ICMP](/img/Screenshot%202019-05-28%20at%2014.30.18.png)

` ICMP ` có nhiệm vụ là thông báo cho sender biết về việc gói tin , data gửi đi gặp vấn đề .

Gói tin ICMP thường bắt đầu với ba trường :
    
- TYPE: Định nghĩa thông báo đi sau.



Các kiểu TYPE cho ICMP :

| Type Field	| ICMP Message Type |
|-----------|-----------------|
| 0 | Echo Reply |
| 3 | Destination Unreachable |
| 4 | Source Quench |
| 5 | Redirect (Change o router)|
| 8 | Echo Request |
| 11 | Time Exceeded for a Datagram |
| 12 | Parameter Problem on a Datagram|
| 13 | Timestamp Request |
| 14 | Timestamp Reply |
| 15 | Information Request |
| 16 | Information Reply |
| 17 | Address Mask Request |
| 18 | Address Mask Reply |

- CODE: Cung cấp thông tin thêm về thông báo.
- CHECKSUM: Chưa checksum của thông báo.  


