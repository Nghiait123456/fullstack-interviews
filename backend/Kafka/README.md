# Câu hỏi phỏng vấn Microservice

![](./assets/microservices.png)

## Mục lục

[1. Khi nào sử dụng Kafka](#khi-nao-su-dung-kafka)
[2. Vì sao kafka có high throught output](#vi-sao-kafka-co-high-output-cao)
[3. Chi co mot topic va 1 partition, làm sao kafka vẫn đảm bảo hight throut-output](#chi-co-mot-topic-va-1-partition-lam-sao-kafka-van-dam-bao-hight-throut-output)
[4. Tool quan ly topic kafka](#tool-quan-ly-topic-kafka)
[5. Các mode sử dụng chính của kafka](#cac-mode-su-dung-chinh-cua-kafka)

output
afka

## Câu hỏi phỏng vấn cho Fresher

### 1. Khi nào sử dụng Kafka?

Kafka là một hệ thống xử lý dòng thông tin (stream processing system) mã nguồn mở được sử dụng để xử lý và lưu trữ các
luồng dữ liệu trực tiếp. Kafka có khả năng xử lý hàng tỉ tin nhắn mỗi ngày, đồng thời cho phép phân tán dữ liệu trên
nhiều máy chủ.

Kafka thường được sử dụng trong các ứng dụng liên quan đến Big Data, Internet of Things (IoT), và xử lý trực tuyến (
real-time processing). Các công ty và tổ chức có thể sử dụng Kafka để theo dõi các hoạt động của người dùng, xử lý các
bản ghi log, hoặc tích hợp các ứng dụng lớn với nhau.

Ngoài ra, Kafka còn được sử dụng để truyền tải thông tin giữa các hệ thống khác nhau và tối ưu hóa các kết nối giữa các
thành phần của hệ thống. Vì vậy, khi bạn cần xử lý một lượng lớn dữ liệu trực tuyến, Kafka có thể là một lựa chọn tốt.

==> chủ yếu là message bus theo event sourcing.

### Vì sao kafka có high throught output?

Kafka có high throughput (tốc độ xử lý dữ liệu cao) bởi vì nó được thiết kế để xử lý các luồng dữ liệu trực tuyến một
cách hiệu quả và phân tán. Sau đây là một số lí do giải thích cho high throughput của Kafka:

    Kiến trúc phân tán: Kafka được thiết kế để hoạt động trong một môi trường phân tán, có khả năng chia nhỏ dữ liệu thành nhiều phần và phân phối chúng trên nhiều máy chủ.

    Ghi dữ liệu tuần tự: Dữ liệu trong Kafka được ghi tuần tự trên đĩa, giúp tối ưu hóa việc đọc và ghi dữ liệu.

    In-memory cache: Kafka sử dụng một bộ đệm trong bộ nhớ cho các tin nhắn mới nhất, giúp tăng tốc độ đọc và ghi dữ liệu.

    Zero-copy data transfer: Kafka sử dụng kiểu giao tiếp zero-copy, giúp truyền dữ liệu nhanh hơn bằng cách tránh sao chép nhiều lần dữ liệu qua các bộ đệm.

    Khả năng scale-out: Kafka có khả năng mở rộng dễ dàng bằng cách thêm nhiều node vào hệ thống mà không ảnh hưởng đến hiệu suất.

    Kafka có thể có cơ chế chia tải cho partition và groupId, nến ngưỡng tải có thể rất cao.

Tóm lại, Kafka có high throughput bởi vì nó được thiết kế để xử lý các luồng dữ liệu trực tuyến một cách hiệu quả và
phân tán, cùng với một số tính năng tối ưu hóa khác để tăng tốc độ đọc và ghi dữ liệu


3. Chi co mot topic va 1 partition, làm sao kafka vẫn đảm bảo hight throut-output?

Một partition vẫn có thể có nhiều group-id support nó, nên nó vẫn có thể hoạt động với tải cao. </br>


4. Tool quan ly topic kafka?
   Có nhiều công cụ quản lý topic Kafka khác nhau mà bạn có thể sử dụng để vận hành, thêm sửa xóa topic. Dưới đây là một số công cụ phổ biến:

   Kafka Manager: Là một ứng dụng web mã nguồn mở được thiết kế để quản lý và giám sát Kafka clusters. Nó cung cấp các tính năng như tạo mới, chỉnh sửa và xóa topic, theo dõi thông tin về consumer group, kiểm tra trạng thái của broker, ...

   Confluent Control Center: Đây là một công cụ quản lý Kafka do Confluent cung cấp. Nó cho phép quản lý Kafka cluster của bạn, bao gồm các tính năng như tạo mới, chỉnh sửa và xóa topic, giám sát hiệu suất và sức mạnh của consumer group, ...

   Kafka Tool: Đây là một ứng dụng desktop được thiết kế để quản lý Kafka cluster từ xa. Nó cung cấp các tính năng như tạo mới, chỉnh sửa và xóa topic, theo dõi consumer group, xem trạng thái của broker, ...


Trên AWS có nhiều công cụ giúp quản lý Kafka, bao gồm:

    Amazon Managed Streaming for Apache Kafka (Amazon MSK): Đây là một dịch vụ quản lý Kafka được quản lý bởi AWS. Nó cung cấp các tính năng như tạo mới, chỉnh sửa và xóa topic, theo dõi hiệu suất, cân bằng tải tự động và hỗ trợ các tính năng an ninh.

    Amazon Kinesis Data Streams: Đây là một dịch vụ trực tuyến giúp lấy dữ liệu từ các nguồn khác nhau (ví dụ như các máy chủ web hoặc thiết bị IoT) và lưu trữ chúng trong các streams. Tương tự như Kafka, Kinesis cũng cung cấp các tính năng như tạo mới, chỉnh sửa và xóa stream, giám sát hiệu suất và cân bằng tải tự động.

    Confluent Cloud: Đây là một dịch vụ quản lý Kafka do Confluent cung cấp. Nó cho phép bạn triển khai và quản lý Kafka clusters trên AWS, bao gồm các tính năng như tạo mới, chỉnh sửa và xóa topic, giám sát hiệu suất, cân bằng tải tự động và hỗ trợ các tính năng an ninh.

Các công cụ này đều giúp bạn quản lý Kafka trên AWS, tuy nhiên mỗi công cụ có những ưu điểm và hạn chế riêng. Bạn nên xem xét tùy thuộc vào nhu cầu của mình để chọn công cụ phù hợp nhất.


