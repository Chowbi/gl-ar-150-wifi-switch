# gl-ar-150-wifi-switch

mv /usr/bin/switchaction /usr/bin/switchaction.bak

vim /usr/bin/switchaction
> i  
> {copy content}  
> echap  
> :wq  

chmod +x switchaction

test !

/etc/init.d/initswitch restart

if fail / error :  
vim /etc/init.d/initswitch  
> replace   
>     /usr/bin/switchaction  
> by   
>     sh -e /usr/bin/switchaction  

vim /etc/rc.button/BTN_8  
> replace   
>     /usr/bin/switchaction  
> by   
>     sh -e /usr/bin/switchaction  

test !
