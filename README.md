### Hi，我是 王宇轩 (Yuxuan Wang) 👋

做 AI 应用与数据工程的实践者。习惯把「论文里的方法」变成「能跑、能验、能交付」的东西。

- 🔬 **算法侧**：3DGS 稀疏视角重建、多视角一致性、消融实验设计
- 📊 **数据侧**：面板数据处理、空间计量、网络分析、批量数据管线
- 🔧 **工程侧**：Python / C 双线，交付级打包（PyQt + PyInstaller、bat 入口、自检脚本）
- 🎯 在意的事：**指标口径要对得上，失败能解释，交付能开箱即用**

---

### 精选项目

| 项目 | 做了什么 | 关键结果 |
|---|---|---|
| **[sparse-view-avatar](https://github.com/navisfint/3dgs-sparse-view-avatar)** | 3 视角重建可动画人体化身，SAS 表面锚定先验 + 时序正则 | PSNR **+15.3%** / SSIM **+33.9%** / LPIPS **−35.3%** vs vanilla 3DGS |
| **[spatial-network-analysis](https://github.com/navisfint/spatial-network-analysis)** | 改进障碍度模型 + 修正引力模型 + 社会网络分析工具集 | 拿已发表论文公开数值反查实现，**10 项指标逐位对上** |
| **[quant-auction-screener](https://github.com/navisfint/quant-auction-screener)** | 集合竞价选股引擎，六组条件全市场筛选 | 三源降级 + 采样架构，解决「9:20 数据只有一次机会」 |
| **[crypto-lab-c](https://github.com/navisfint/crypto-lab-c)** | AES-256-CBC / RSA-2048-OAEP / SHA-256 的 C 实现 | 833 行，含雪崩效应实测与篡改验证 |
| **[pdf-split-toolkit](https://github.com/navisfint/pdf-split-toolkit)** | 扫描件卷宗按目录自动拆分，带 GUI 与单文件 exe | 5 卷**119 个 PDF / 781 页**，首页页码吻合率 **100%** |
| **[wecom-workflow-automation](https://github.com/navisfint/wecom-workflow-automation)** | 外包业务全链路：订单/派单/结算建模 + 自动化巡检 | 规则落地为表格公式，脚本与公式同口径交叉校验 |
| **[algo-lab-python-c](https://github.com/navisfint/algo-lab-python-c)** | 六个经典算法的 Python / C 双实现 + 设计思想对比 | 实测：Python 用对算法**比 C 用错算法快 5 倍** |
| **[android-mic-roster](https://github.com/navisfint/android-mic-roster)** | 安卓端屏幕区域 OCR 名单工具，离线识别 + 悬浮窗 | Kotlin **2344 行**，三级文本清洗，未申请 INTERNET 权限 |

**更多：** [spot-on-manual-generator](https://github.com/navisfint/spot-on-manual-generator)（一份内容出多语言 PDF，内嵌市场二维码）·
[docx-eq-toolkit](https://github.com/navisfint/docx-eq-toolkit)（Word 公式段落转无框线两列表，不破坏 MathType 对象）·
[bar-light-game](https://github.com/navisfint/bar-light-game)（Arduino 拍击跑马灯，结果先抽后演，观众无法反推）

---

### 我在项目里反复做的事

**1. 先核对假设，再写代码**

PDF 拆分项目开工前，先解剖真实 PDF 的二进制结构逐页核验，结果发现需求描述里
**3 处与实际不符**（"手写页码"实际是打印体、部分页有两个数字、页码其实 100% 连续）。
技术路线因此从"高难度手写 OCR"变成"打印体 OCR + 规则引擎"，工期和风险大幅下降。

**2. 负收益先分清「机制无效」还是「注入错误」**

3DGS 项目里 SAS 模块最初是 −0.484 dB。常规做法是砍掉，但排查后发现是
SMPL 单位差了 1000 倍导致锚面塌缩——修复后变成 **+0.884 dB**。
**明显变差通常说明有东西被搞坏了，而不是这个方法没用。**

**3. 指标口径必须诚实**

同一 config 跨 batch 重跑，PSNR 会差 0.19~0.29 dB。所以所有对比强制同批次，
批次方差先量化出来，避免把噪声当成方法改进。不可比较的数字，不如不给。

**4. 交付物要能开箱即用**

单文件 exe、一键 .bat、自检与诊断脚本、失败时写明原因而不留白屏。
使用者不需要知道命令行是什么。

---

### 技术栈

```
语言      Python · C · JavaScript · VB.NET · SQL
AI/图形   PyTorch · 3D Gaussian Splatting · OpenCV · SMPL-X
数据      pandas · NumPy · SciPy · networkx · matplotlib
工程      PyQt · PyInstaller · OpenSSL · Git
```

---

<sub>📫 项目相关问题欢迎提 Issue，或通过 GitHub 联系。</sub>
