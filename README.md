WTRequestCenter
===============

方便缓存的请求库
无需任何import和配置，目前实现了基础需求
如果有其他需要请在issue 上提出，谢谢！


使用方法 Usage
===============
#### 注意：GET默认是缓存请求，POST不提供缓存请求，详情请看Wiki
### GET 请求 
```objective-c
[WTRequestCenter getWithURL:url
                 parameters:parameters
          completionHandler:^(NSURLResponse *response, NSData *data, NSError *error) {
              id obj = [NSJSONSerialization JSONObjectWithData:data options:NSJSONReadingMutableContainers error:&jsonError];
              NSLog(@"result:%@",obj);
              }
```
              
### POST 请求
```objective-c
[WTRequestCenter postWithURL:url
                  parameters:parameters 
           completionHandler:^(NSURLResponse *response, NSData *data, NSError *error) {
                     id obj = [NSJSONSerialization JSONObjectWithData:data options:NSJSONReadingMutableContainers error:&jsonError];
              NSLog(@"result:%@",obj);
               }
```


### 取消所有请求 
```objective-c
[WTRequestCenter cancelAllRequest];
```


### WTDataSaver
WTDataSaver 是个文件存取类，用于自定的方式把数据存取到本地

#### 保存数据  name只需要传文件名就可以了，无需传路径
```objective-c
+(void)saveData:(NSData*)data
       withName:(NSString*)name
     completion:(void(^)())completion;
```

#### 读取数据 name只需要传文件名就可以了，无需传路径
```objective-c
+(void)dataWithName:(NSString*)name
         completion:(void(^)(NSData*data))completion;
```

还有一些更加便捷的方法，查看wiki吧


Requirement   需要
===============
Only need iOS 5.0 and later,no more import and Configuration!
仅仅需要iOS5 ！ 不需要其他任何import和配置


## Communication  沟通
- 如果你**发现bug**,打开右侧的问题
- 如果你**想做出贡献**，提交一个推（pull）的请求
- 如果你**有功能需求**，打开问题

##  UIKit+WTRequestCenter
这里面提供了许多UIKit的扩展方法
- UIImageView的图片缓存
- UIImage的播放gif+图片缓存
- UIButton的图片缓存
- UIColor的快速创建


