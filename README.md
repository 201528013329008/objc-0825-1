# objc-0825-1
NSString, char, NSData相互转化
1. NSString转化为UNICODE String：

(NSString*)fname ＝ @“Test”;

 

char fnameStr[10];

memcpy(fnameStr, [fname cStringUsingEncoding:NSUnicodeStringEncoding], 2*([fname length]));
2. NSString转化为char

(NSString*)fname ＝ @“Test”;

char fnameStr[10];

fnameStr =[fname UTF8String];

3. char -> NSData:

 方法一：

   char * postData = "TEST";

 

   NSData *data = [NSData dataWithBytes:postData length:strlen(postData)];

 方法二：

    转换为NSString： - (id)initWithUTF8String:(const char *)bytes
    然后用NSString的 - (NSData *)dataUsingEncoding:(NSStringEncoding)encoding

4. NSData ->char

  NSData returnData ；

  char* bu=[returnData bytes];

5. NSData->NSString

 

 NSString* aStr;

 aStr = ［NSString alloc] initWithData:aData encoding:NSASCIIStringEncoding];

6. NSString->NSData

 NSData* aData;

 aData = [aStr dataUsingEncoding: NSASCIIStringEncoding];
