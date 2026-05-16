# CialloVOL 1.2 - Memory Forensics Tool

基于 Volatility 3 的轻量化内存镜像分析平台，支持 Windows/Linux 完整内存镜像和 MiniDump 进程转储文件。

### CialloVOL1.2 最新最详细的使用演示见下方链接
- **CSDN**：https://blog.csdn.net/KivenMit/article/details/160565378?fromshare=blogdetail&sharetype=blogdetail&sharerId=160565378&sharerefer=PC&sharesource=KivenMit&sharefrom=from_link
- **微信公众号**： https://mp.weixin.qq.com/s/nOvH2iZ1JOXIcppJAJn5uQ
- ***演示视频***
-进程转储，高级采集及dmp的文件内容查看，进程扫描，文件扫描等功能演示
-https://github.com/KivenMit/CialloVOL/issues/1#issue-4460631606
-raw内存镜像的文件内容查看，进程扫描，文件扫描等功能演示
-https://github.com/KivenMit/CialloVOL/issues/2#issue-4460681756

### 如需获取完整版、技术支持或商务合作，请联系
 **微信**: `zjh19819621720`
### 若担心微信交易安全性，也可以进入下方平台链接走平台交易，售后保障是一样的
 **FreeBuf平台链接**：https://m-wiki.freebuf.com/clubsStore/detail?id=119

## 如果你喜欢本项目，请给一个star⭐吧~

## 售后
- 我们会持续更新这个工具以不断增强他的竞争力，一旦您购入完整版，我们将把每一次更新后的版本免费赠送给您--我们的授权文件是永久性的。
- 即使工具价格后续会随更新涨价，已购入前面版本的用户依旧可以免费获得后续版本。
- 我们会包下消费者一人的使用，即若用户更换电脑，或者环境出现预料外的变动，我们会为您免费发放新的授权文件。


## 使用
微信联系获取压缩包与授权文件后，双击即用。
无需额外手动配置，自带全套依赖！

注意：本工具已经打包好了vol3，且可以自动识别安装的vol
<img width="2550" height="1233" alt="2ee130be6f79a5cc65d6a121958d6b59" src="https://github.com/user-attachments/assets/a0461616-9ea4-43a5-a617-cb056e53b652" />


## ✨ v1.2 新特性
<img width="2550" height="1233" alt="ecab97a3b28dc3638ead78ccd2233eb4" src="https://github.com/user-attachments/assets/e5038e09-ed91-440b-98b3-d7c06c056c67" />
<img width="2550" height="1233" alt="57ce074b96a82e2dd74e0e398bf22a12" src="https://github.com/user-attachments/assets/431952e3-fdae-4e6e-8b51-65b551a647d1" />

### 🎨 全新加载体验
- **进度条**：`加载中~(∠・ω＜)⌒★` + 流光渐变动画
- **真实进度反馈**：精确显示 0-100% 进度，告别无限转圈
- **任务中断**：【停止加载】按钮，随时中止长时间任务
- **智能提示**：每个阶段显示具体操作（"正在解析进程信息..." / "正在写入文件..."）
<img width="2550" height="1233" alt="265c6bf30de9d36578e9e821eb074b5a" src="https://github.com/user-attachments/assets/d64c3940-832d-43e2-8564-fbca395dc11c" />

### 🔍 进程分析增强
- **单进程 DMP 自动识别**：上传 .dmp 文件自动提取真实 PID 并填充进程列表
- **完整镜像兼容**：自动运行 pslist 并填充进程分析下拉框
- **智能降级**：MiniDump 不支持的功能（句柄表/命令行）静默隐藏，不显示错误
- **友好错误提示**：Volatility 原始堆栈转为中文提示（"无法访问 Microsoft 符号服务器" 而非 Traceback）
- <img width="2550" height="1233" alt="895bc83737a651453dca4f97c4174bdd" src="https://github.com/user-attachments/assets/dd1677e5-242b-4887-8460-623af6661af8" />
<img width="2550" height="1233" alt="72407a6a31e130692a78e7492302e3aa" src="https://github.com/user-attachments/assets/90caff05-271c-47ab-92bb-042b05309d16" />

### 🌐 网络连接优化
- **MiniDump 支持**：从内存字符串提取该进程的网络连接
- **按时间排序**：一键查看最新建立的连接
- **进程关联**：点击 PID 直接跳转到进程分析页面
- **友好提示**：无数据时显示 "该进程 MiniDump 未发现网络连接（进程在转储时可能无活跃连接）"

### 🛠️ 文件提取优化
- **精确过滤**：修复 offset 匹配逻辑，确保只提取选中文件
- **进度反馈**：实时显示提取进度和文件数量
- **结果详情**：展示每个文件的大小和输出目录
- **文件可提取性分析**：自动检测哪些文件数据仍在内存中，哪些已被换页到磁盘，便于提取


### 🐛 核心修复
- **扫描失败弹窗**：过滤 Volatility 正常日志（"Updating caches" / "Downloading PDB"），只报告真实错误
- **进程分析兼容**：修复多进程完整镜像的进程列表加载和下拉框填充
- **字段格式统一**：MiniDump 和 Volatility 返回字段统一为大写（PID/PPID/ImageFileName）


## 特性

- **双模式分析**：自动识别完整内存镜像（使用 Volatility 3）和 MiniDump 文件（原生解析器）
- **MiniDump 支持**：无需 Volatility，直接解析 Windows 进程转储文件（.dmp）
- **内存采集**：内置进程内存转储功能，无需外部工具
- **文件内容查看**：支持 Hex Dump、ASCII、UTF-8 等多种格式查看内存镜像内容
- **文件导出**：灵活的文件导出功能，支持自定义文件名和后缀
- **Web 界面**：暗黑主题，支持拖拽上传，实时分析
- **扩展工具**：编码/加密、端口扫描、数据对比


## 核心功能

### 1. 镜像加载与文件查看

| 功能 | 说明 |
|------|------|
| 文件上传 | 支持 .raw, .vol, .vmem, .mem, .dmp 格式，拖拽或点击上传 |
| 文件信息 | 显示文件名、大小、路径、MD5、SHA256、修改时间 |
| **内容查看器** | 实时查看文件内容，支持偏移跳转和分页浏览 |
| 显示格式 | 自动检测、Hex Dump、ASCII、UTF-8、原始十六进制 |
| 分页导航 | 上一页/下一页按钮，自定义偏移和读取长度 |
| **文件导出** | 复制文件并自定义文件名和后缀（支持无后缀） |

**内容查看器特性**：
- 默认从偏移 0 开始读取 512 字节
- 支持最大 10MB 单次读取
- Hex Dump 格式类似 `hexdump -C`（地址 + 十六进制 + ASCII 对照）
- 实时显示读取进度（当前位置 / 文件总大小 / 百分比）

**文件导出特性**：
- 自动拆分原文件名为主干和后缀（如 `proc_4344.dmp` → `proc_4344` + `dmp`）
- 可修改主干和后缀，或清空后缀导出无后缀文件
- 仅复制文件，不修改内容
- 导出到 `output/exported/` 目录

### 2. 完整内存镜像分析（需 Volatility 3）

| 功能 | 说明 |
|------|------|
| 进程列表 (pslist) | 表格展示 PID、PPID、进程名、地址等 |
| 按时间排序 | 按进程创建时间从新到旧排序 |
| 网络连接 (netscan) | 展示本地/远程 IP、端口、协议、状态、建立时间 |
| 按时间排序 | 按连接建立时间从新到旧排序 |
| PID 跳转 | 点击网络连接的 PID 直接跳转到进程分析 |
| 文件扫描+提取 | filescan + dumpfiles，过滤空文件，确保完整性 |
| 导出 CSV | 所有表格数据均可导出 |

### 3. MiniDump 分析（无需 Volatility）

| 功能 | 说明 |
|------|------|
| 自动识别 | 上传 .dmp 文件后自动切换为 MiniDump 模式 |
| **真实 PID 提取** | 从 MiscInfo 流提取真实 PID，自动填充进程列表 |
| 进程信息 | 从模块列表推断进程名、线程数 |
| 文件路径扫描 | 从内存字符串提取文件路径（正则匹配） |
| 网络信息扫描 | 从内存字符串提取 IP:Port 地址 |
| 内存区域导出 | 导出所有内存区域为二进制文件 |
| 模块/线程/字符串 | 查看加载的 DLL、线程信息、内存字符串 |
| **智能降级** | 不支持的功能（句柄表/命令行）静默隐藏，不报错 |

**MiniDump 限制**：
- 仅包含单个进程的内存，无法获取系统级信息（完整进程列表、全局网络连接表）
- 扫描结果来自内存字符串匹配，可能包含历史数据或误报
- 适用于恶意软件分析、崩溃调试、单进程取证

### 4. 本机内存采集

| 功能 | 说明 |
|------|------|
| 权限检查 | 检测管理员权限和工具可用性 |
| 进程列表 | 显示当前运行的所有进程（PID、名称、状态、内存占用） |
| 进程转储 | 选择进程并转储内存（完整/堆+栈/摘要三种模式） |
| 自动加载 | 转储成功后自动加载到分析界面 |

**转储模式**：
- **完整内存**：包含进程的所有内存页（推荐）
- **堆+栈**：仅包含堆和栈数据
- **摘要**：最小化转储，仅基本信息

### 5. 进程深度分析

| 功能 | 说明 |
|------|------|
| 基本信息 | PID、进程名、路径、父进程、创建时间、线程数、句柄数 |
| 打开文件 | 进程打开的文件句柄列表 |
| DLL 模块 | 加载的动态链接库（基址、大小、路径） |
| 内存字符串 | 提取进程内存中的可读字符串 |
| 行为时间线 | 进程活动时间线（MiniDump 显示模块+线程） |
| 命令行参数 | 进程启动时的命令行 |
| **单个/批量分析** | 支持单进程完整分析或多进程批量分析 |

## 扩展功能

| 功能 | 说明 |
|------|------|
| JSON 提取 | 以 JSON 格式导出 Volatility 插件结果 |
| 编码/解码 | Base64、Hex、URL、Base32、ROT13 |
| 加密/解密 | AES-256-CBC 加密 |
| 端口扫描 | 多线程 TCP 端口扫描 |
| 数据对比 | 两份数据差异对比 |

## 使用场景

### 场景 1：分析完整内存镜像
1. 使用 FTK Imager、DumpIt、WinPmem 等工具采集完整物理内存
2. 上传 .raw/.vmem 文件
3. 自动运行 pslist 填充进程列表
4. 点击「扫描网络」查看所有网络连接
5. 点击网络连接的 PID 跳转到进程分析
6. 使用「按时间排序」查看最新进程/连接

### 场景 2：分析单进程 MiniDump
1. 使用任务管理器或 ProcDump 转储目标进程
2. 上传 .dmp 文件，自动识别为 MiniDump
3. 自动提取真实 PID 并填充进程列表
4. 查看该进程的模块、线程、内存字符串
5. 扫描网络连接（如果进程有活跃连接）
6. 不支持的功能（句柄表/命令行）自动隐藏

### 场景 3：本机实时取证
1. 切换到「内存采集」标签页
2. 查看当前运行的进程列表
3. 选择可疑进程，点击「转储进程」
4. 自动加载转储文件到分析界面
5. 立即分析进程行为和内存内容

## 技术细节

### 文件类型自动识别
- 上传时检测文件头（`MDMP` 签名 → MiniDump，否则 → 完整镜像）
- 后端 `current_file_state['is_minidump']` 标记文件类型
- 所有 API 根据文件类型自动切换分析器：
  - MiniDump → `MiniDumpAnalyzer`
  - 完整镜像 → `VolatilityHandler`

### 进程分析智能降级
- MiniDump 不支持的功能返回 `unsupported: true`
- 前端检测 `unsupported` 标记，静默隐藏对应区块
- 错误统计只计入真实失败（`!success && !unsupported`）
- 成功提示附加 `note` 字段（如 "来自 MiniDump（基本信息，无 PEB/环境变量）"）

### 错误信息友好化
- `VolatilityHandler._clean_error()` 将原始堆栈转为中文提示
- 模式匹配覆盖常见错误：
  - `Could not find a valid kernel` → "未找到有效的 Windows 内核结构"
  - `Unable to validate the Microsoft symbol` → "无法访问 Microsoft 符号服务器（PDB 缺失）"
  - `UnsatisfiedRequirement` → "插件缺少必要依赖（文件可能不是完整内存镜像）"

### 任务中断机制
- 全局 `currentAbortController` 管理当前任务
- 所有 fetch 请求添加 `signal` 参数
- 点击【停止加载】调用 `AbortController.abort()`
- 捕获 `AbortError` 静默返回，不弹错误框

### 进程管理优化
- Flask 运行时关闭 `debug` 模式和 `use_reloader`，避免重载器进程残留
- 所有 `MiniDumpAnalyzer` 实例使用后立即 `del`，释放内存
- 防止文件句柄未释放导致目录无法重命名的问题

## 更新日志

### v1.2 (2026-04-05)
- ✨ **全新加载体验**：进度条 + 真实进度反馈 + 任务中断按钮
- ✨ **进程分析增强**：单进程 DMP 自动提取 PID、完整镜像自动填充下拉框、智能降级
- ✨ **网络连接优化**：MiniDump 支持、按时间排序、PID 跳转、友好提示
- ✨ **文件提取优化**：精确 offset 匹配、进度反馈、结果详情
- 🐛 **核心修复**：扫描失败弹窗过滤、进程分析兼容、字段格式统一
- ⚡ **错误友好化**：Volatility 原始堆栈转为中文提示
- 📝 完善 README 文档，新增 v1.2 特性说明

### v1.0 (2026-04-04)
- ✨ 新增文件内容查看器（支持 Hex Dump、ASCII、UTF-8 等格式）
- ✨ 新增文件导出功能（自定义文件名和后缀）
- 🐛 修复 Flask debug 模式导致的进程残留问题
- 🐛 修复 MiniDumpAnalyzer 内存未释放导致的文件句柄占用
- ⚡ 优化内存管理，所有 MiniDumpAnalyzer 实例使用后立即释放
- 📝 完善 README 文档

## 许可证

MIT License
