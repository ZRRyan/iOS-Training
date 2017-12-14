
## UIImage的2种加载方式
### 方式一
有缓存（图片所占用的内存会一直停留在程序中）,name是图片的文件名
```
+ (UIImage *)imageNamed:(NSString *)name;
```

### 方式二
无缓存（图片所占用的内存会在一些特定操作后被清除）,path是图片的全路径
```
+ (UIImage *)imageWithContentsOfFile:(NSString *)path
- (id)initWithContentsOfFile:(NSString *)path;
```
