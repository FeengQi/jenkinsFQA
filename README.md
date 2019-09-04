- 在项目中使用jenkins自动构建时，发生了提交一个分支的代码，其他分支也会构建的问题。
  - 经过排查，是有个配置遗漏了，在Build Triggers中
  ![](https://github.com/FeengQi/jenkinsFQA/blob/master/img/20190904195257.png)
  中‘Advanced’可以配置，但是，其中的‘Filter branches by name’有问题，在jenkins的issue中有人提出。于是该用‘Filter branches by regex’
  Source Branch Regex	 项为空，表示全部分支，但是在Target Branch Regex中选出要执行的分支，我们的分支为dev，于是这样配置 `.*dev$`
  ![](https://github.com/FeengQi/jenkinsFQA/blob/master/img/20190904195936.png)
