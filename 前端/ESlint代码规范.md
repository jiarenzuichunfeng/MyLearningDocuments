# ESlint代码规范

* 代码规范

  * 一套写代码的约定规则
  * JavaScriptStandard Style https://standardjs.com/rules-zhcn.html

* 修改

  * 手动修正

    * 根据错误一项一项手动修改

  * 自动修正

    * 基于vscode插件ESlint高亮错误，并通过配置自动帮我们修复错误

    * 在vscode设置文件中添加

      ```json
        //自动修改ESlint错误
        "editor.codeActionsOnSave": {
          "source.fixAll": true
        },
        // 保存不格式化
        "editor.formatOnSave": false
      ```

      