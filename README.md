# gradle-git-hook-demo

本项目展示了通过 git hook 来校验代码仓库提交信息的规范。  
实现方式为在做`git commit`操作时，会检查`commit message`的内容，如果不符合格式，会阻断提交过程。 

操作步骤：
1. 拷贝 `gradle\git-hooks` 文件夹到项目目录下。位置和本项目保持一致。
2. 在`build.gradle`中添加
```
apply from: "${rootProject.projectDir}/gradle/git-hooks/git-hooks.gradle"
```
3. 在执行完 `./gradlew build ` 后，规范门禁会起作用。

注：相关规则配置在`gradle/git-hooks/prepare-commit-msg`中。 修改配置后，在`./gradlew build `执行后方能生效。
注：执行`./gradlew build `会覆盖原有hook文件的内容，如果需要，请提前备份。