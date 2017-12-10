#KVC（Key－Value Coding）
kVC,一个非正式协议，提供一种机制来简介的访问对象的属性；一个对象分别有一个value和一个key，并与之相对应；key对应的值可以是任意类型的对象。想要改变某些只读属性的值可以用该方法   
例如：  
```
Person *p = [[Person alloc] init];  
[p setValue:@"张三" forKey:@"name"]；   
[p valueForKey:@"name"];    
```
如果Person有另一个key， card，值为属性no 
```
[p setValue:@"123456" forKeyPath:@"card.no"];   
[p valueForKeyPath:@"card.no"];  相当于 [[p valueForKey:@"card"] valueForKey:@"no"]; 
```

#KVO（Key-Value Observing）
Key-Value Observing (KVO) 建立在 KVC 之上，它能够观察一个对象的 KVC key path 值的变化。举个例子，用代码观察一个 person 对象的 name 变化，

##1、添加观察
```
 [_person addObserver:self forKeyPath:@"name" options:0 context:nil];
```
##2、观察(当被观察的值发生变化时调用该方法)
```
- (void)observeValueForKeyPath:(NSString *)keyPath ofObject:(id)object change:(NSDictionary<NSString *,id> *)change context:(void *)context { 
      NSLog(@"%@", [_person valueForKey:@"name"]);    
    }
}
```

##3、移除观察
```
- (void)dealloc {
    [_person removeObserver:self forKeyPath:@"name"];
}
```
