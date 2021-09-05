
### حذف منوی گراب در هنگام روشن و ریستارت شدن سیستم

<!--
 

### توضیحات

احتمالا شما هم زمانی که فدورا رو نصب کردید با این مشکل مواجه شده اید که به محص روشن شدن سیستم منوی گراب برای شما لود میشود
خب ما در اینجا به حل این مشکل میپردازیم

### شروع کار


خب اول از همه ترمینال رو باز کنید


بعد این دستور رو بزنید


```bash

sudo grub2-editenv - set menu_auto_hide=1
sudo grub2-mkconfig -o /etc/grub2-efi.cfg

```

وبعد هم این دستور رو بزنید


‍‍‍
```bash

sudo grub2-mkconfig -o /etc/grub2-efi.cfg
sudo grub2-mkconfig -o /boot/grub2/grub.cfg

```



خب الان اگه سیستم رو روشن کنید بهتون منو رو نشون نمیده ولی اگه سیستم رو ریستارت کنید دوباره بهتون منو رو نشون میده


برای حل این مشکل هم این دستور رو بزنید



```bash

set -e
exec grub2-mkconfig -o /boot/grub2/grub.cfg "$@"

```

خب تمام شد 


[منبع](https://unix.stackexchange.com/questions/533244/hide-grub-menu-at-boot-on-fedora-30)


 -->


اگر دوباره موقع روشن کردن سیستم منو بالا اومد این کارهارو انجام دهید


‍‍‍
```bash

sudo dnf install grub2-breeze-theme

```


```bash

sudo gedit /etc/default/grub

or

sudo nano /etc/default/grub


```


این خط رو کامنت کنید


```bash

GRUB_TERMINAL_OUTPUT="console"

```

به این صورت 



```bash

#GRUB_TERMINAL_OUTPUT="console"

```


این خط رو هم اضافه کنید 

```bash

GRUB_THEME="/boot/grub2/themes/breeze/theme.txt"


```


وبعد این دستورات رو بزنید


‍‍‍```bash
sudo grub2-editenv - set menu_auto_hide=1
sudo grub2-mkconfig -o /etc/grub2-efi.cfg

sudo grub2-mkconfig -o /etc/grub2-efi.cfg
sudo grub2-mkconfig -o /boot/grub2/grub.cfg

```

