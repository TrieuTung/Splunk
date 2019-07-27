# Cài đặt và triển khai hệ thống Splunk 

1. Cài đặt hệ thống Splunk
 
   Splunk hỗ trợ một loạt các hệ điều hành bao gồm, Windows, Linux, FreeBSD, OSX, Solaris, AIX và nhiều hơn nữa. Bạn có thể tải xuống các phiên bản của Splunk từ trang web chính thức của họ hoặc sử dụng lệnh sau:

    |wget https://download.splunk.com/products/splunk/releases/7.1.1/linux/splunk-7.1.1-8f0ead9ec3db-linux-2.6-amd64.deb|
|---|

   Bạn có thể cài file đã download bằng lệnh sau:

    |dpkg -i splunk-7.1.1-8f0ead9ec3db-linux-2.6-amd64.deb|
|---|

   Sau khi cài đặt đặt thành công thì bạn sẽ thấy output như sau:

   `(Reading database ... 218552 files and directories currently installed.)
   Preparing to unpack splunk-7.1.1-8f0ead9ec3db-linux-2.6-amd64.deb ...
   Unpacking splunk (7.1.1) over (7.1.1) ...
   Setting up splunk (7.1.1) ...
   complete`

   Tiếp theo, bạn cần phải enable dịch vụ Splunk để bắt đầu trong boot time. Bạn cần phải chạy lệnh sau:








   




   



