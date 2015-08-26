# D3Json
通过swift的反射特性，把json数据转换为model对象,本类最主要是解决了其他一般json转换类不能转换自定义对象的问题
只有一个文件：D3Json.swfit
自定义类需要@objc(User) ,可以参照例子


# Usage
例子在D3Json的Project里面，写了两个测试，一个是json转单model，一个是转model的list
在playgroud里面也有两个例子

只需要一句代码：
var user:User = D3Json.jsonToModel(json, clazz: User.self)
就可以把json数据转换成User类

转成list对象:
var users = D3Json.jsonToModelList(jsonArr, clazz: User.self) as! Array<User>
就可以把json数据转换成Array<User>类

#Problem
 1. model属性基础类型需要初始化，自定义类型要用Optional类型
 2. 因为swift的反射reflect的缺陷，父类的属性暂不转换

#Requirements
- iOS 7.0+ / Mac OS X 10.9+
- Xcode 6.1


#Integration
##CocoaPods (iOS 8+, OS X 10.9+)

You can use Cocoapods to install D3Json adding it to your Podfile:

    platform :ios, '7.0'
    use_frameworks!
    
    pod 'D3Json’, '~> 1.1.0'
you need `import D3Json`


Note that it needs you to install CocoaPods 36 version, and requires your iOS deploy target >= 8.0:

    [sudo] gem install cocoapods -v '>=0.36'

##Manually
drag D3Json.swift to the project
