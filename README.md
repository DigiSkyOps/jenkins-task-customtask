# 插件名称 

customtask

# 功能说明

用于调用和执行工作脚本好命令行程序

# 参数说明

| 参数名称 | 类型 | 默认值 | 是否必须 | 含义 |
|---|---|---|---|---|
| type | string | auto | **非必须** | 执行命令类型，auto为自动判断, ant/python/cmdline等 |
| workdir | string | ${ws.dir} | **非必须** | 执行任务所在的工作路径 |
| command | string | 空 | **必须** | 所需执行的命令，当type为ant时，填写build.xml文件路径相对于workdir变量 |
| args | string | 空 | **非必须** | command执行所需参数 |
| failonerror | string | false | **非必须** | 当命令执行失败是否终止构建 |

# 配置使用样例

```yml
stages:
- name: customtask
  tasks:
    - task.id: customtask
      type: ant
      workdir: ${ws.dir}/.ci
      command: pkg.xml
      failonerror: true
```