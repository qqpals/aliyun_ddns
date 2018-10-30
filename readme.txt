1. 脚本需要Python2.x运行

2.安装alidns python sdk

sudo pip2 install aliyun-python-sdk-alidns

3.准备以下数据

access_key_id：

access_Key_secret：

account_id：可以在你账户的 账号管理 >> 安全设置 中找到；

rc_record_id：你需要先将 i_dont_know_record_id = ‘no’ 设为yes，然后运行脚本，在返还的内容中找到RecordId，这个就是了。获取到RecordId后还需要把i_dont_know_record_id设为no！(通过check_records(dns_domain)返回的json数据中获得)

rc_domain：一级域名（你的域名）

rc_rr：请填写你的解析记录，对应的主机记录

rc_type：A，CNAME

rc_ttl：请填写解析有效生存时间TTL，单位：秒

4.设置定时任务
crontab -l
*/10 * * * * root /usr/bin/python2.7 /usr/local/shell/aliyun_ddns.py > /dev/null 1>/dev/null
