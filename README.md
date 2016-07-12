# PinYin2HanziPython
- `__future__　`
	- `print_function`
	- `unicode_literals`
- `sys.path.append('..')`
- `with as`
- `pinyin_list.py`


## 源码分析
- Pinyin2Hanzi
	- interface.py 定义两个抽象类 AbstractHmmParams AbstractDagParams。
	- implement.py interface.py 中两个抽象类的实现。
		- DefaultDagParams
			- `__init__`
				- 得到当前文件的目录。
				- 读取 JSON 文件。
				- get_phrase
					- 传入一个 pinyin_list，输出对应的 6 个字或词。
		- DefaultHmmParams
	- priorityset.py
		- class PrioritySet
			- `__init__`
				- 获取 capacity，得到一个 []。
			- put
				- 预言 path 一定是 list。
		- Item
			- `__init__`
			- 
- example
- 疑问
	[x] priorityset.py 为什么会出现多个 capacity？