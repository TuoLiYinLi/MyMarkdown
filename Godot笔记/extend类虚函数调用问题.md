#踩坑记录 
### 总结
+ 子类中与父类同名的虚函数，不会覆盖父类的函数
+ 当引擎调用这个同名的虚函数时，会先调用一次父类的虚函数，再调用一次子类

### 举例
父类为A
```
# A.gd
extends Node2D
class_name A

func _ready():
	print("A ready")
	tt()
	print("A ready end")
	
	
func tt():
	print("A tt")
```
子类为B
```
extends A
class_name B

func _ready():
	print("B ready")
	print("B end")

func tt():
	print("B tt")
```
