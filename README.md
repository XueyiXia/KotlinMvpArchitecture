# android-mvp-architecture

kotlin 版本的 mvp 开发框架,适用于中小型项目，在以前开发的时候，很多时候都是用mvp 架构的方式去做，到后期发展都基本使用mvvm架构了！这段时间有空也就随手写了一个 mvp 架构，现在算是基本完成了！

## 先看项目的架构图
![image](https://user-images.githubusercontent.com/25949241/206661466-06902a35-bbe4-4869-976b-9f3a4eec024c.png)

基本上封装了基类，目前时间有限只是把mvp 架构思维设计出来

#1.定义了BasePresenter ，相信大家都比较熟悉这个基类做什么用的，这个是用来沟通view 和mode 的桥梁

![image](https://user-images.githubusercontent.com/25949241/206661870-04152818-e7ba-48f5-b37d-b53d6515375d.png)



#2.定义了BaseModel，这个负责存储、检索、操纵数据,网络请求存放的基类，解耦部分的数据耦合，通俗一些来说，就是你的网络请求放在这里面，通过接口回调到Presenter类，然后Presenter 再通知View，大概可以这样理解

![image](https://user-images.githubusercontent.com/25949241/206662878-1bd91984-a585-4c97-bc18-3c579a092a62.png)

#3.BaseView ，一个更新UI 的接口，作用等下会解释

![image](https://user-images.githubusercontent.com/25949241/206663089-a7086e90-e80c-497a-a0a5-b260ebde8c5f.png)


## BaseActivity 和 BaseFragment

定义两个base,这个做什么用？大概只能说统一管理所有的类吧！在基类中继承BaseView，当新建的类继承 BaseActivity 或者 BaseFragment可以刷新UI

![image](https://user-images.githubusercontent.com/25949241/206663993-d22fdfbf-ea51-41d6-ba50-a187be145252.png)


## 在项目中调用
继承BasePresenter和BaseModel ，分别创建自己的业务类和桥梁类，还有自己的Ui更新回调类

![image](https://user-images.githubusercontent.com/25949241/206664839-6daf953a-1271-4fc2-8812-a1a0e295e3cc.png)

详细的使用请看HomeFragment 类：

![image](https://user-images.githubusercontent.com/25949241/206665007-2d72ed35-e90a-48b6-9b73-e265311a3de5.png)


##How to use Add this to your build.gradle:

dependencies {

	implementation 'com.github.XueyiXia:android-mvp-architecture:v1.0.0' 
}


最后，代码是最好的老师，如果有兴趣，可以下载demo 看看，如果这个这个架构能帮助到你，请右上角点击个星星吧！！！Thanks you so much .........END
