###类图

####可见性
|符号|字段图标|方法图标|含义
|---|---|---|---|
|-|![](/assets/images/private-field.png)|![](/assets/images/private-method.png)|私有|
|#|![](/assets/images/protected-field.png)|![](/assets/images/protected-method.png)|保护|
|~|![](/assets/images/package-private-field.png)|![](/assets/images/package-private-method.png)|包/命名空间 私有|
|+|![](/assets/images/public-field.png)|![](/assets/images/public-method.png)|公开|

**示例代码**

```
@startuml
class Dummy {
-field1
#field2
~method1()
+method2()
}
@enduml
```

结果如下
![](/assets/images/class-diagram-access-demo.webp)
