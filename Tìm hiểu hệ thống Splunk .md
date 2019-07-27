# Tìm hiểu hệ thống Splunk 
1. Giới thiệu tổng quan về Splunk

  - Giới thiệu công cụ giám sát an ninh mạng Splunk

      Splunk là một phần mềm giám sát mạng dựa trên sức mạnh của việc phân tích Log. Splunk thực hiện các công việc tìm kiếm, giám sát và phân tích các dữ liệu lớn được sinh ra từ các ứng dụng, các hệ thống và các thiết bị hạ tầng mạng. Nó có thể thao tác tốt với nhiều loại dịnh dạng dữ liệu khác nhau (Syslog, csv, apache-log, access_combined…). Splunk được xây dựng dựa trên nền tảng Lucene and MongoDB với một giao diện web hết sức trực quan.

  - Chính sách bản quyền: Splunk cung cấp 2 bộ miễn phí và trả phí cho người dùng

      Sản phẩm trả phí: Có tất cả các chức năng và không hạn chế kích thước dữ liệu.

      Sản phầm miễn phí: Hạn chế một số chức năng, hạn chế khối lượng dữ liệu mỗi ngày là 500MB. Bao gồm các chức năng: Data indexing, real-time search, statistics and report output.

  - Tính năng định dạng log

      Splunk hỗ trợ hầu như tất cả các loại log của hệ thống, thiết bị hạ tầng mạng, phần mềm, Firewall, IDS/IPS, Log Event, Register của các máy trạm…

  - Các hình thức thu thập dữ liệu
  
       Splunk có thể thực hiện việc thu thập log từ rất nhiều nguồn khác nhau. 

            From a file or folder (including compressed files) on the server
            Through UDP and TCP connections from Splunk Servers in the distributed Splunk model
            From Event Logs, Windows Registry ...

       Splunk cũng kết hợp rất tốt với các công cụ thu thập log khác để tăng hiệu năng của hệ thống. 

       Update data: Splunk cập nhật dữ liệu liên tục khi có thay đổi trong thời gian thực. Giúp cho việc phát hiện và cảnh báo chính xác trong thời gian thực.

       Data indexing: Splunk được xây dựng trên Lucence, có thể đánh chỉ mục dữ liệu với một khối lượng dữ liệu rất lớn trong một khoảng thời gian ngắn. Giúp việc tìm kiếm diễn ra nhanh chóng và thuận tiện.

       Finding information: Splunk làm việc rất tốt với dữ liệu lớn và cập nhật liên tục. Nó cung cấp cơ chế tìm kiếm với một “Splunk Language” cực kỳ thông minh bao gồm các từ khóa, các hàm và cấu trúc tìm kiếm giúp người sử dụng có thể truy xuất mọi thứ, theo rất nhiều tiêu chí từ tập dữ liệu rất lớn. Những nhà quản trị mạng cao cấp và chuyên nghiệp thường gọi Splunk với cái tên “Splunk toàn năng” hay “Splunk as Google for Log files” để nói lên sức mạnh của Splunk.

       Network security monitoring and warnings: Splunk cung cấp cho người dùng một cơ chế cảnh báo dựa trên việc tìm kiếm các thông tin do chính người sử dụng đặt ra. Khi có vấn đề liên quan tới hệ thống phù hợp với các tiêu chí mà người dùng đã đặt ra thì hệ thống sẽ cảnh báo ngay tới người dùng (cảnh bảo trực tiếp qua giao diện, giử Email).

       Troubleshooting: Splunk còn cung cấp một cơ chế tự động khắc phục với các vấn đề xảy ra bằng việc cấu hình để tự động chạy các file Script mà người dùng tự tạo (Ví dụ như: Chặn IP, đòng Port …) khi có các cảnh báo xảy ra.

       Information display: Splunk cung cấp một cơ chế hiển thị trực quan giúp người sử dụng có thể dễ dàng hình dung về tình trạng của hệ thống, đưa ra các đánh giá về hệ thống. Splunk còn từ động kết xuất ra các báo cáo với nhiều loại định dạng một cách chuyên nghiệp.

       Lưu ý: Splunk mạnh về khả năng phân tích và cảnh báo tuy nhiên nó lại không mạnh và không đảm bảo về việc thu thập và truyền tải log. Cụ thể là nó chưa có cơ chế bảo mật trên đường truyền, không phù hợp với những hệ thống đòi hỏi bảo mật cao. Để phát huy hết được sức mạnh của Splunk cần có thời gian tìm hiểu và sử dụng. Splunk chưa có cơ chế giúp tự động phát hiện ra các tấn công hay các vấn đề từ bên ngoài. Những điều này phụ thuộc vào kinh nghiệm sử dụng và vốn hiểu biết về bảo mật của người quản trị. Đề triển khai được một hệ thống sử dụng Splunk hiệu quả chúng ta cũng cần có một hệ thống riêng, đây cũng là một trở ngại không nhỏ với các hệ thống có quy mô trung bình và nhỏ. 

2. Cài đặt hệ thống Splunk
 
   Splunk hỗ trợ một loạt các hệ điều hành bao gồm, Windows, Linux, FreeBSD, OSX, Solaris, AIX và nhiều hơn nữa. Bạn có thể tải xuống các phiên bản của Splunk từ trang web chính thức của họ hoặc sử dụng lệnh sau:

       wget https://download.splunk.com/products/splunk/releases/7.1.1/linux/splunk-7.1.1-8f0ead9ec3db-linux-2.6-amd64.deb

   Bạn có thể cài file đã download bằng lệnh sau:

       dpkg -i splunk-7.1.1-8f0ead9ec3db-linux-2.6-amd64.deb

   Sau khi cài đặt đặt thành công thì bạn sẽ thấy output như sau:

       (Reading database ... 218552 files and directories currently installed.)
       Preparing to unpack splunk-7.1.1-8f0ead9ec3db-linux-2.6-amd64.deb ...
       Unpacking splunk (7.1.1) over (7.1.1) ...
       Setting up splunk (7.1.1) ...
       complete

   Tiếp theo, bạn cần phải enable dịch vụ Splunk để bắt đầu trong boot time. Bạn cần phải chạy lệnh sau:

       sudo /opt/splunk/bin/splunk enable boot-start

   Ở đây bạn phải đồng ý với the License Agreement và cung cấp mật khẩu cho admin như sau:

       Splunk Software License Agreement 04.24.2018
       Do you agree with this license? [y/n]: y
       This appears to be your first time running this version of Splunk.
       An Admin password must be set before installation proceeds.
       Password must contain at least:
       *8 total printable ASCII character(s).
       Please enter a new password: 
       Please confirm new password: 
       Copying '/opt/splunk/etc/openldap/ldap.conf.default' to '/opt/splunk/etc/openldap/ldap.conf'.
       Generating RSA private key, 2048 bit long modulus
       ..................+++
       ..............................................................................+++
       e is 65537 (0x10001)
       writing RSA key
       Generating RSA private key, 2048 bit long modulus
       .............+++
       ...................................+++
       e is 65537 (0x10001)
       writing RSA key
       Moving '/opt/splunk/share/splunk/search_mrsparkle/modules.new' to '/opt/splunk/share/splunk/search_mrsparkle/modules'.
       Adding system startup for /etc/init.d/splunk ...
        /etc/rc0.d/K20splunk -> ../init.d/splunk
        /etc/rc1.d/K20splunk -> ../init.d/splunk
        /etc/rc6.d/K20splunk -> ../init.d/splunk
        /etc/rc2.d/S20splunk -> ../init.d/splunk
        /etc/rc3.d/S20splunk -> ../init.d/splunk
        /etc/rc4.d/S20splunk -> ../init.d/splunk
        /etc/rc5.d/S20splunk -> ../init.d/splunk
       Init script installed at /etc/init.d/splunk.
       Init script is configured to run at boot.

   Bật dịch vụ Splunk bằng câu lệnh sau:

       sudo service splunk start

   Bây giờ hệ thống của bạn đang chạy và lắng nghe trên port:8000. Bạn có thể vào hệ thống của bạn trên web với đường dẫn sau: http://your_server_ip:8000/ (User là admin và Pass là mật khẩu bạn đã tạo bên trên).
   









   




   



