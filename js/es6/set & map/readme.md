# set
set对象，是一个集合的数据结构
set是一个类似于数据的结构，但是其成员没有重复项


1. add()添加值
2. delete()删除值
3. has()判断是否有值
4. clear()清空值
5. values()返回set里面的所有值，且返回的结构是具备迭代器属性的
6. keys() 返回set里面所有键，且返回的结构具有迭代器属性
7. entries() 返回set里面的所有键值对，且返回的对象具有迭代器属性

优雅的去除重复数组
let union = new Set([...a,...b])
let intersect = new Set([...a].filter(x=>b.has(x)))

# weakSet 
1. 成员只能是对象
2. weakSet这种数据结构不受垃圾回收机制的控制，只要weakSet里面的对象在weakSet的外部没有被引用，或者说在外部消失，那么weakSet中对象所占据的内存空间就是直接被释放（垃圾回收机制回收）

# map
map对象，是一种叫做字典的数据结构
