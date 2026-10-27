# srcchain

**把每个检索片段追溯回它的原始文档与位置。**

`srcchain` —— 沿片段的元数据向上追溯，打印完整的来源路径与偏移量

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`srcchain.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install afungeltid-srcchain
```

装完直接用命令名调用：

```bash
srcchain --help
```

也可以不用安装，直接把 `srcchain.py` 拷走用——它只依赖标准库。

## 为什么需要它

来源链要能一路走到原始文件，中间断了的会被标出来

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 片段来源追踪 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python srcchain.py --file input.txt
python srcchain.py --text "示例内容"
python srcchain.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 计数按字面 token 统计，不做词形还原。
- 只报告分布，不判断该保留哪些。

## 跑测试

```bash
python test_srcchain.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/afungeltid/srcchain>

---

## 关于作者

afungeltid 做片段来源追踪相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://afungeltid.github.io>
- 仓库：<https://github.com/afungeltid/srcchain>

## 许可

MIT，见 [LICENSE](LICENSE)。
