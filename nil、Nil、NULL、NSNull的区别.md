#nil、Nil、NULL、NSNull的区别
nil：指向一个对象的空指针   
Nil：指向一个类的空指针   
NULL：指向其他类型（如：基本类型、C类型）的空指针   
NSNull：通常表示集合中的空值  

###nil
nil 是 ObjC 对象的字面空值，对应 id 类型的对象，或者使用 @interface 声明的 ObjC 对象。  
例如：
NSString *someString = nil;  
NSURL *someURL = nil;  
id someObject = nil;   
if (anotherObject == nil) // do something 

###Nil
　　Nil 是 ObjC 类类型的书面空值，对应 Class 类型对象。 
　　例如： 
　　Class someClass = Nil; 
　　Class anotherClass = [NSString class]; 
　　
　　
###NSNull
　　NSNull 是一个代表空值的类，是一个 ObjC 对象。实际上它只有一个单例方法：+[NSNull null]，一般用于表示集合中值为空的对象。
　　例如：
　　// 因为 nil 被用来用为集合结束的标志，所以 nil 不能存储在 Foundation 集合里。
　　NSArray *array = [NSArray arrayWithObjects:@"one", @"two", nil];
　　// 错误的使用
　　NSMutableDictionary *dict = [NSMutableDictionary dictionary];
　　[dict setObject:nil forKey:@"someKey"];
　　// 正确的使用
　　NSMutableDictionary *dict = [NSMutableDictionary dictionary];
　　[dict setObject:[NSNull null] forKey:@"someKey"];

