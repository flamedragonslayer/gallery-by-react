1.因为浏览器会默认自带margin和padding，这会导致div大小设置为100%时与浏览器产生白边间隔。因此，需要通过在style里设置 body{margin:0,padding:0}来消除白边，
解决问题。注意是body！

2.要在react里实现引用背景图片，只需在style里写上 backgroundImage:'url(...)'即可，不要忘了加引号！