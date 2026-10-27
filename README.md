# promptrisk

**扫描提示词里的高风险模式。**

`promptrisk` —— 检测歧义指令、隐含假设与可能导致越界的表述

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`promptrisk.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install pboelpaes2-promptrisk
```

装完直接用命令名调用：

```bash
promptrisk --help
```

也可以不用安装，直接把 `promptrisk.py` 拷走用——它只依赖标准库。

## 为什么需要它

风险要分级，不同等级给不同处置建议

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 提示词风险扫描 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python promptrisk.py --file input.txt
python promptrisk.py --text "示例内容"
python promptrisk.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 相似度按字符与词估算，不等于向量相似度。
- 不联网，不做语义检索。

## 跑测试

```bash
python test_promptrisk.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/pboelpaes2/promptrisk>

---

## 关于作者

pboelpaes2 做提示词风险扫描相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://pboelpaes2.github.io>
- 仓库：<https://github.com/pboelpaes2/promptrisk>

## 许可

MIT，见 [LICENSE](LICENSE)。
