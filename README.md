# SetNulllWithStr
iOS 网络请求中的空类型字符串转换
-
将网络请求的返回的空数据所有`NSNull`类型转化成`@""`，利用递归的思想，查找`“<null>”`,替换为`@“”`
```OC
+(id)changeType:(id)myObj
{
    if ([myObj isKindOfClass:[NSDictionary class]])
    {
        return [self nullDic:myObj];
    }
    else if([myObj isKindOfClass:[NSArray class]])
    {
        return [self nullArr:myObj];
    }
    else if([myObj isKindOfClass:[NSString class]])
    {
        return [self stringToString:myObj];
    }
    else if([myObj isKindOfClass:[NSNull class]])
    {
        return [self nullToString];
    }
    else
    {
        return myObj;
    }
}
```
使用方法：
```OC
	NSDictionary *dic = (NSDictionary*)responseObject;
	NSDictionary *newDic = [NSDictionary changeType:dic];
```
觉得有用的话请给个star吧^_^
