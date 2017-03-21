# SetNulllWithStr

主要方法: 类型识别:将所有`NSNull`类型转化成@""
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
