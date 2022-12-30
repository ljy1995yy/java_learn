ArrayList<E>

- 可调整大小的数组实现
- <E>:是一种特殊的数据类型，泛型

ArrayList的构造

ArrayList的常用方法

索引越界会报错

- 添加（添加成功或失败会有返回值，成功true，失败false）

  - add 在末尾添加元素

  - add(int index,E element) 在指定位置（index）添加元素（element）

- 删除（索引越界会报错）

  - remove(object)  (返回成功或失败)
  - remove(int index)  (返回被删除的元素)

- 查

  - get（int index） 返回索引所在的元素
  - size（） 返回列表内元素的个数

- 改 

  - set（int index，E element） 修改执行索引出的元素，返回被修改的元素