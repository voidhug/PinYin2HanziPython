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
	- dag.py
		- 生成 pinyin_list_len 个 PrioritySet，去 DagParams 中根据 pinyin_list，按照 0 —— pinyin_list_len 的顺序，得到相应的汉字及其概率，然后将汉字和概率放到对应的 PrioritySet 中。
		
- example
- 疑问
	- [x] priorityset.py 为什么会出现多个 capacity？
	- [] heapq.heappush(self.data, [score, Item(score, path)]) heapq 是根据谁来排序的？