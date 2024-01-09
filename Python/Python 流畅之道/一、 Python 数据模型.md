# 1. namedtuple 简介

- 自 python2.6 开始，namedtuple 就加入到 python 里，用以构建只有少数属性但是没有方法的对象：比如数据库条目

```python
import collections
# 使用 collections 模块中的 namedtuple 创建一个叫作 card 的类
# 该类有两个属性：rank，suit
Card = collections.namedtuple('Card', ['rank', 'suit'])
class FrenchDeck:
    # rank 表示牌面，从数字 2~10，再加上 JQKA
    ranks = [str(n) for n in range(2, 11)]+list('JQKA')
    # suit 表示花色，有 spades diamonds clubs hearts 四种
    suits = 'spades diamonds clubs hearts'.split（　）
    # _cards 属性被初始化为一幅完整的扑克牌，每张牌由 suit 和 rank 组成
    def __init__(self):
        self._cards = [Card(rank, suit) for suit in self.suits
                                        for rank in self.ranks]
    # len 方法返回这副牌的长度，即包含了多少张牌
    def __len__(self):
        return len(self._cards)
    # getitem 方法允许通过索引（position）来访问这副牌中特定位置的牌
    # getitem 方法使得该类的实例可以像普通的 python 序列一样被处理，可以使用切片和索引访问
    def __getitem__(self, position):
        return self._cards[position]
```

