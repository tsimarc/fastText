### 1
[First steps — pybind11 2.3.dev0 documentation](https://pybind11.readthedocs.io/en/master/basics.html)

```bash
source /home/qian/project/learn/learn-nlp/fasttext/venv/bin/activate
```
```
$ c++ -O3 -Wall -shared -std=c++11 -fPIC `python3 -m pybind11 --includes` pybind.cpp -o example`python3-config --extension-suffix`
```

头文件是由python模块pybind11输出的`python3 -m pybind11 --includes`

```bash
(venv) ➜  pybind git:(master) ✗ python3-config --extension-suffix
.cpython-35m-x86_64-linux-gnu.so
```

生成example.cpython-35m-x86_64-linux-gnu.so

```
>>> import example
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ImportError: /home/qian/project/learn/learn-nlp/fasttext/git_repo/exploratory/pybind/example.cpython-35m-x86_64-linux-gnu.so: undefined symbol: _Z3addii
```

### 2

按照教程中，把函数实现移到pybind文件中才正常。

```bash
(venv) ➜  pybind git:(master) ✗ python3 -m pybind11 --includes
-I/home/qian/project/learn/learn-nlp/fasttext/venv/include/python3.5m -I/home/qian/project/learn/learn-nlp/fasttext/venv/include/site/python3.5
```

加入vscode的项目设置中。
