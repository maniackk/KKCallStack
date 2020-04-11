## KKCallStack
Get call stack~


## 用途
程序中获取调用堆栈。  

## 用法
```
typedef NS_ENUM(NSUInteger, KKCallStackType) {
    KKCallStackTypeAll,     //全部线程
    KKCallStackTypeMain,    //主线程
    KKCallStackTypeCurrent  //当前线程
};


//获取所有线程的调用堆栈
NSString *callStack = [KKCallStack callStackWithType:KKCallStackTypeAll];

//获取主线程的调用堆栈
NSString *callStack = [KKCallStack callStackWithType:KKCallStackTypeMain];

//获取当前线程的调用堆栈
NSString *callStack = [KKCallStack callStackWithType:KKCallStackTypeCurrent];

```
## 注意 
在获取当前线程的调用堆栈，别人都是通过 [NSThread setName:xx(比如时间戳)] , 然后通过pthread_getname_np()。通过比对两者 name 一样，来关联NSThread 跟 pthread_t，而我直接用 [NSThread callStackSymbols] 获取当前线程的堆栈。😂😂




