### اتوماتیک استارت شدن زمپ در اوبونتو

در این مقاله به  نحوه اتواتیک شدن زمپ میپردازیم


### شروع


اول از همه کد زیر را در ترمینال وارد کنید و وارد صفحه شوید

```bash

sudo gedit /etc/systemd/system/xampp.service
&
sudo subl /etc/systemd/system/xampp.service


```


بعد هم این دستورات در فایل قرار دهید

```bash
[Unit]
Description=XAMPP

[Service]
ExecStart=/opt/lampp/lampp start
ExecStop=/opt/lampp/lampp stop
Type=forking

[Install]
WantedBy=multi-user.target
```



و بعد هم این دستور رو وارد کنید


```bash

sudo systemctl enable xampp.service
sudo systemctl status xampp.service

```

 __اتمام__

