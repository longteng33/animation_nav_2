# animation_nav_2
用animation和js制作的动画菜单，从不同的方向进入会有不同的动画效果
https://longteng33.github.io/animation_nav_2  

1、首先通过js判断鼠标进入、离开的方向  
原理：  

建设鼠标进入的是一个正方形（长方形只需在此基础上乘以一个长款比即可）  
在鼠标的mouseenter事件发生时，获取 x=e.offsetX-ele.offsetWidth/2和y=e.offsetY-ele.offsetHeight/2  
Math.atan2(y,x)，得到弧度值  
Math.atan2(y,x)*(180/Math.PI)得到角度值  
(Math.round((Math.atan2(y,x)*(180/Math.PI)+180)/90)+3)%4，那么从上、右、下、左进入分别返回0、1、2、3  
鼠标离开也是同样的判断方法  
2、根据进入的方向不同，给节点不同的in-class及out-class，在不同的in-class和out-class中设置transform,animation  