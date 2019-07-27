# Cài đặt và triển khai hệ thống Splunk 

1. Cài đặt hệ thống Splunk
 
   Splunk hỗ trợ một loạt các hệ điều hành bao gồm, Windows, Linux, FreeBSD, OSX, Solaris, AIX và nhiều hơn nữa. Bạn có thể tải xuống các phiên bản của Splunk từ trang web chính thức của họ hoặc sử dụng lệnh sau:

    |wget https://download.splunk.com/products/splunk/releases/7.1.1/linux/splunk-7.1.1-8f0ead9ec3db-linux-2.6-amd64.deb|
|---|

   Bạn có thể cài file đã download bằng lệnh sau:

    |dpkg -i splunk-7.1.1-8f0ead9ec3db-linux-2.6-amd64.deb|
|---|

   Sau khi cài đặt đặt thành công thì bạn sẽ thấy output như sau:

         (Reading database ... 218552 files and directories currently installed.)
         Preparing to unpack splunk-7.1.1-8f0ead9ec3db-linux-2.6-amd64.deb ...
         Unpacking splunk (7.1.1) over (7.1.1) ...
         Setting up splunk (7.1.1) ...
         complete

   Tiếp theo, bạn cần phải enable dịch vụ Splunk để bắt đầu trong boot time. Bạn cần phải chạy lệnh sau:

    |sudo /opt/splunk/bin/splunk enable boot-start|
|---|

   Ở đây bạn phải đồng ý với the License Agreement và cung cấp mật khẩu cho admin như sau:

       Splunk Software License Agreement 04.24.2018
       Do you agree with this license? [y/n]: y
       This appears to be your first time running this version of Splunk.
       An Admin password must be set before installation proceeds.
       Password must contain at least:
                  * 8 total printable ASCII character(s).
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









   




   



