# ComfyUI-FileDownloader
### 功能

这个节点可以在ComfyUI工作流中直接使用，下载的文件路径可以传递给其他需要文件输入的节点。

### 特性说明

1.重试机制：

支持配置重试次数

使用指数退避策略

智能判断HTTP错误类型（4xx错误不重试）

2.网络稳定性：

支持大文件流式下载

处理超时和连接错误

支持重定向

3.文件名处理：

从URL路径提取

从Content-Disposition头提取

根据内容类型生成扩展名

使用哈希值避免冲突

4.进度跟踪：

显示下载进度

详细的日志输出

5.错误处理：

验证URL格式

检查空文件

清理不完整文件

6.记录功能：

保存下载历史到JSON文件

便于调试和跟踪

### 安装与使用

1.安装：

将文件 download_from_url.py，放在ComfyUI的 custom_nodes 目录下，重启comfyui

2.使用方法：

a.在ComfyUI中搜索节点 "下载文件从URL" 或 "DownloadFromURL"

b.输入要下载的URL地址

*可选参数：

max_retries: 最大重试次数（默认3次）

retry_delay: 重试延迟（默认2秒，使用指数退避）

timeout: 超时时间（默认30秒）

filename_override: 自定义文件名（可选）

*节点输出：

输出下载文件的完整路径（字符串类型），文件保存在ComfyUI的临时目录中
