���л���: Linux
������̬�⣺dl z ssl crypto stdc++ pthread
��̬��(�������Я��): cossdk fuse curl jsoncpp

1������
cmake .
make

2�������ļ�cos_config.json(��Ҫ��cosfs������COS SDKʹ��)
����˵��:
"AppID":1251668577,
"SecretID":"AKIDWtTCBYjM5OwLB9CAwA1Qb2ThTSUjfGFO",
"SecretKey":"FZjRSu0mJ9YJijVXXY57MAdCl4uylaA7",
"Region":"sh",                    //����COS�����ϴ����ز�����URL����ò����й�
"SignExpiredTime":360,            //ǩ����ʱʱ�䣬��λ����
"CurlConnectTimeoutInms":10000,   //CURL���ӳ�ʱʱ�䣬��λ������
"CurlGlobalConnectTimeoutInms":360000, //CURL����ִ�����ʱ�䣬��λ������
"UploadSliceSize":1048576,        //��Ƭ��С����λ���ֽڣ���ѡ����512k,1M,2M,3M(��Ҫ����ɶ�Ӧ�ֽ���)
"IsUploadTakeSha":0,              //�ϴ��ļ�ʱ�Ƿ���ҪЯ��shaֵ
"DownloadDomainType":2,           //�����������ͣ�1: cdn, 2: cos, 3: innercos, 4: self domain
"SelfDomain":"",                  //�Զ�������
"UploadThreadPoolSize":5          //���ļ���Ƭ�ϴ��̳߳ش�С
"AsynThreadPoolSize":2            //�첽�ϴ������̳߳ش�С
"LogoutType":0                    //��ӡ�����0:�����,1:�������Ļ,2:��ӡsyslog
һ��ֻ��Ҫ�޸�����COS��Ϣ������
AppID��SecretID��SecretKey��Region��DownloadDomainType
3������
(1)����bucket������/mnt/mointpoint/
./cosfs bucket /mnt/mointpoint/ -o cfgfile=cos_config.json

(2)����bucket�µ�ĳ��Ŀ¼������/mnt/mointpoint/
./cosfs bucket:/folder /mnt/mointpoint/ -o cfgfile=cos_config.json

4��ж��
��Ҫ��װfuse(yum install fuse),����ִ��
fusermount -u /mnt/mointpoint/
�����ʾ�豸æ,�����˳�/mnt/mointpoint/,��������޷�ж��,��ִ��
umount -l /mnt/mointpoint/

��ע��
Ŀǰ֧�ֵĲ���(ֻ����ز���,д������ʱ��֧��)��
linux���cd, ls, ll, cat, more, cp
ϵͳ�ӿ�:  open(), read(), stat(), close(), lseek()
