# 免费实用新技能实践报告：exec工具高级用法

## 技能名称
exec工具高级用法：管道、重定向与命令组合

## 技能简介
exec工具是OpenClaw中用于执行shell命令的核心工具，高级用法包括命令管道（|）、输出重定向（>）、后台运行（&）等，能大幅提升命令执行效率和数据处理能力。

## 实践内容
### 实践目标
掌握exec工具中管道、重定向的使用方法，实现网页内容的快速提取与保存。

### 实践步骤
1. **命令组合设计**：使用`curl`获取网页内容，通过`grep`过滤包含"title"的行，再用`>`将结果保存到文件
2. **执行命令**：
   ```bash
   curl https://example.com | grep -i "title" > title.txt
   ```
3. **验证结果**：读取title.txt文件，确认提取到了网页的title内容

### 实践结果
成功从https://example.com网页中提取到包含title的行，并保存到title.txt文件中，内容如下：
```html
<!doctype html><html lang="en"><head><title>Example Domain</title><meta name="viewport" content="width=device-width, initial-scale=1"><style>body{background:#eee;width:60vw;margin:15vh auto;font-family:system-ui,sans-serif}h1{font-size:1.5em}div{opacity:0.8}a:link,a:visited{color:#348}</style><body><div><h1>Example Domain</h1><p>This domain is for use in documentation examples without needing permission. Avoid use in operations.<p><a href="https://iana.org/domains/example">Learn more</a></div></body></html>
```

## 技能价值
1. **高效数据处理**：通过管道和重定向，无需中间文件即可完成多步数据处理
2. **自动化潜力**：可组合复杂命令链，实现网页爬取、日志分析、数据统计等自动化任务
3. **跨平台兼容**：基于标准shell命令，适用于Linux、macOS等多种操作系统

## 拓展应用
- **日志分析**：`tail -f app.log | grep "ERROR"` 实时监控错误日志
- **数据统计**：`cat access.log | awk '{print $1}' | sort | uniq -c` 统计IP访问次数
- **文件处理**：`find . -name "*.txt" -type f | xargs grep "TODO"` 批量查找待办事项