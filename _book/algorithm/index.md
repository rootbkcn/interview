# 目录

<a href="#algorithm-1">★★★ 冒泡排序</a>

<a href="#algorithm-2">★★ 选择排序</a>

<a href="#algorithm-3">★★ 插入排序</a>

<a href="#algorithm-4">★★ 希尔排序</a>

<a href="#algorithm-5">★★ 归并排序</a>

<a href="#algorithm-6">★★★ 快速排序</a>

<a href="#algorithm-7">★★ 堆排序</a>

<a href="#algorithm-8">★★★ 斐波那契数列</a>

<a href="#algorithm-9">★★ 汉诺塔问题</a>

<a href="#algorithm-10">★★ 合并两个有序数组</a>

<a href="#algorithm-11">★★ 数组中重复的数字</a>

<a href="#algorithm-12">★★ 两个数组的交集</a>

<a href="#algorithm-13">★★ 旋转数组</a>

<a href="#algorithm-14">★★ 两数之和</a>

<a href="#algorithm-15">★★ 爬台阶的实现思路</a>


# 高频算法面试真题

### <p id="algorithm-1">★★★ 冒泡排序</p>

> 从开始位置两两比较，持续n轮

- #### 基础版
```javascript
function bubbleSort (arr) {
  // 执行第 i + 1 轮
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length - 1; j++) {
      // 前一个与后一个两两比较
      if (arr[j] > arr[j + 1]) {
        // 交换两个变量值
        let tmp = arr[j]
        arr[j] = arr[j + 1]
        arr[j + 1] = tmp
      }
    }
  }
}
```
- #### 改进版
```javascript
function bubbleSort (arr) {
  // 冒泡每次处理个最大/最小值, i 代表每次最大值的位置
  for (let i = arr.length - 1; i > 0; i--) {
    for (let j = 0; j < i; j++) {
      if (arr[j] > arr[j + 1]) {
        // 交换两个变量值
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]]
      }
    }
  }
}
```

### <p id="algorithm-2">★★ 选择排序</p>

> 每次选出最大/最小值 持续n轮

- #### 基础版

```javascript
function selectSort (arr) {
  // 每次的最小值的索引
  for (let i = 0, len_i = arr.length; i < len_i; i++) {
    // 每轮最小值索引
    let index = i

    for (let j = i, len_j = arr.length; j < len_j; j++) {
      if (arr[index] > arr[j]) {
        // 最小值变化
        index = j
      }
    }
    // 把最小值放到第 i 的索引
    [arr[i], arr[index]] = [arr[index], arr[i]]
  }
}
```

- #### 改进版

```javascript
function selectSort (arr) {
  // 排出 lenth - 1 个最小值即可
  for (let i = 0, len_i = arr.length - 1; i < len_i; i++) {
    let index = i
    for (let j = i + 1, len_j = arr.length; j < len_j; j++) {
      if (arr[index] > arr[j]) {
        index = j
      }
    }
    // 判断最小索引是否改变
    if (index !== i) {
      [arr[i], arr[index]] = [arr[index], arr[i]]
    }
  }
}
```

### <p id="algorithm-3">★★ 插入排序</p>

> 默认一个已排好序的数组 递增的往这个数组内插入元素

- #### 版本一

```javascript
function insertSort (arr) {
  // 将要插入的索引
  for (let i = 1, len_i = arr.length; i < len_i; i++) {
    let cur = i
    // 插入到已经排好序的序列中
    while (cur > 0 && arr[cur] < arr[cur - 1]) {
      [arr[cur], arr[cur - 1]] = [arr[cur - 1], arr[cur]]
      cur--
    }
  }
}
```

- #### 版本二

```javascript
function insertSort (arr) {
  // 将要插入的索引
  for (let i = 1, len = arr.length; i < len; i++) {
    let tmp = arr[i]

    // 插入到已经排好序的序列中
    for (let j = i - 1; j >= 0 && arr[j] > tmp; j--) {
      arr[j + 1] = arr[j]
    }
    arr[j + 1] = tmp
  }
}
```

### <p id="algorithm-4">★★ 希尔排序</p>

> 增量式的**`插入排序`** 正常的插入排序间隔为1 希尔排序默认设置间隔大于1 然后递减为1

```javascript
function shellSort (arr) {
  let len = arr.length
  let step = 1
  let dis = 3
  // 设置最大间隔
  while (step < len / dis) {
    step = step * dis + 1
  }
	
  // 间隔递减
  for (; step > 0; step = Math.floor(step / dis)) {
    // 单个间隔的插入排序
    for (let i = step; i < len; i++) {
      let tmp = arr[i]
      let j = i - step

      while (j >= 0 && arr[j] > tmp) {
        arr[j + step] = arr[j]
        j -= step
      }
      arr[j + step] = tmp
    }
  }
}
```

### <p id="algorithm-5">★★ 归并排序</p>

> 排序之前将数组拆分为两部分排序 然后将排好序的两个部分进行合并排序

```javascript
function mergeSort (arr) {
  if (arr.length <= 1) return ;
  let left = 0,
  let right = arr.length - 1,
  let mid = parseInt((left + right) * 0.5)

  sort(arr, left, mid)
  sort(arr, mid + 1, right)
  merge(arr, left, mid, right)
}
function sort (arr, left, right) {
  // 分解为一个元素
  if (left >= right) return ;
  let mid = parseInt((left + right) * 0.5)

  sort(arr, left, mid)
  sort(arr, mid + 1, right)
  merge(arr, left, mid, right)
}
function merge (arr, left, mid, right) {
  // 合并的[left, mid] [mid + 1, right] 部分 都已经排好序
  let i = left
  let j = mid + 1
  let tmp = []

  // 依次插入连个数组的元素
  while (i <= mid && j <= right) {
    // 这里的等于保证了排序算法稳定性(即两个相等的数排序后的位置不会改变)
    if (arr[i] <= arr[j]) {
      tmp.push(arr[i])
      i++
    } else {
      tmp.push(arr[j++])
    }
  }
  // 处理剩余的左边/右边元素
  while (i <= mid) tmp.push(arr[i++])
  while (j <= right) tmp.push(arr[j++])
  for (let i = 0, len = tmp.length; i < len; i++) {
    arr[left + i] = tmp[i]
  }
}
```


### <p id="algorithm-6">★★★ 快速排序</p>

> 排序之前将数组拆按照指定指定基点拆分为两部分 一部分小于等于基点 一部分大于基点

- #### 版本一

```javascript
function quickSort (arr) {
  if (arr.length <= 1) return ;
  let left = 0
  let right = arr.length - 1

  sort(arr, left, right)
}
function sort (arr, left, right) {
  if (left >= right) return ;
  let baseValue = arr[left]
  let start = left
  let end = right
  while (start < end) {
    // 找到右边小于基点的值的索引
    while (start < end && arr[end] >= baseValue) end--
    // 找到左边大于基点的值的索引
    while (start < end && arr[start] <= baseValue) start++
    if (start < end) {
      [arr[start], arr[end]] = [arr[end], arr[start]]
    }
  }
  [arr[left], arr[start]] = [arr[start], arr[left]]
  sort(arr, left, start - 1)
  sort(arr, start + 1, right)
}
```

- #### 版本二

```javascript
function quickSort(arr) {
  if (arr.length <= 1) return ;
  let left = 0
  let right = arr.length - 1

  sort(arr, left, right)
}
function sort (arr, left, right) {
  if (left >= right) return ;
  let baseValue = arr[left]
  let leftArr = []
  let rightArr = []

  for (let i = left; i <= right; i++) {
    if (arr[i] <= baseValue) {
      leftArr.push(arr[i])
    } else {
      rightArr.push(arr[i])
    }
  }
  let mid = left + leftArr.length - 1
  for (let i = 0, len = leftArr.length; i < len; i++) {
    arr[left + i] = leftArr[i]
  }
  for (let i = 0, len = rightArr.length; i < len; i++) {
    arr[mid + i + 1] = rightArr[i]
  }
  [arr[left], arr[mid]] = [arr[mid], arr[left]]
  sort(arr, left, mid - 1)
  sort(arr, mid + 1, right)
}
```

### <p id="algorithm-7">★★ 堆排序</p>

> 将数组看作为一个堆结构 其中 index = 0 为根节点 
>
> index 指向的节点的子节点有 2\*index + 1    2\*index + 2     0 -> 1, 2    1 -> 3, 4    2 -> 5, 6...
>
> 实际的操作就是对这个堆进行调整    堆这个数据结构可以去了解一下
>
> 参考 https://www.cnblogs.com/chengxiao/p/6129630.html

```javascript
// 堆排序
function heapSort (arr) {
  // 从最后一个非叶子节点开始  构建大顶堆   即每次找出最大的一个数
  for (let i = Math.floor(arr.length * 0.5 - 1); i >= 0; i--) {
    adjustHeap(arr, i, arr.length)
  }
  // 将最大的一个节点放在末尾 等于排好序了 在对剩下的元素构建大顶堆
  for (j = arr.length - 1; j > 0; j--) {
    [arr[0], arr[j]] = [arr[j], arr[0]]
    // 大部分都不需要调整了 所以直接从根节点开始
    adjustHeap(arr, 0, j)
  }
}
// 调整堆
function adjustHeap (arr, i, len) {
  // k = 2 * k + 1 是在交换两个节点时会导致原来的堆结构混乱，需要重新调整子节点
  let cnt = 0
  for (let k = 2 * i + 1; k < len; k = 2 * k + 1) {
    // 找出左子节点与右子节点中最大的节点
    if (k + 1 < len && arr[k] < arr[k + 1]) k++
    // 判断是否与子节点进行交换
    if (arr[k] > arr[i]) {
      [arr[k], arr[i]] = [arr[i], arr[k]]
      // 交换完成后要对下一级节点进行重新调整
      i = k
    } else {
      break ;
    }
  }
}
```


### <p id="algorithm-8">★★★ 斐波那契数列</p>

> 斐波那契数列 0 1 1 2 3 5 8 13 ... 第 n 项为第 n-1 与 第 n-2 项的和 首项为0 第二项为1

- #### 使用循环

```javascript
function fibonacci (n) {
  if (n <= 2) return n - 1
  let n1 = 0, n2 = 1

  for (let i = 2; i < n; i++) {
    [n1, n2] = [n2, n1 + n2]
  }
  return n2
}
```

- #### 使用递归

> 消耗内存空间较大

```javascript
function fibonacci (n) {
  return n <= 2 ? n - 1 : Fibonacci(n - 1) + Fibonacci(n - 2)
}

// 设置缓存
let cache = {}
function fibonacci (n) {
  if (n <= 0) return 0
  if (n <= 2) return n - 1
  if (cache[n]) return cache[n] 
  
  return cache[n] = Fibonacci(n - 1) + Fibonacci(n - 2)
}
```

### <p id="algorithm-9">★★ 汉诺塔问题</p>

> 汉诺塔规则参照 https://baike.baidu.com/item/%E6%B1%89%E8%AF%BA%E5%A1%94/3468295

- #### 递归解决

```javascript
// 三根柱子分别为 A B C  A 为初始位置
function hanoi (n, current = 'A', temp = 'B', target = 'C') {
  if (n <= 0) return 0
  let sum = 1

  sum += hanoi(n - 1, current, target, temp)
  console.log(current + ' ---> ' + target)
  sum += hanoi(n - 1, temp, target, current)
  return sum
}
```

### <p id="algorithm-10">★★ 合并两个有序数组</p>

> 直接参照归并排序的合并 merge方法

```javascript
function mergeArr (arr1, arr2) {
  let result = []
  // p1 与 p2 分别为 arr1 与 arr2 的索引
  let p1 = p2 = 0
  let len1 = arr1.length
  let len2 = arr2.length

  while (p1 < len1 && p2 < len2) {
    arr1[p1] <= arr2[p2] ? result.push(arr1[p1++]) : result.push(arr2[p2++])
  }
  while (p1 < len1) result.push(arr1[p1++])
  while (p2 < len2) result.push(arr2[p2++])
  return result
}
```

- #### API版

```javascript
function mergeArr (arr1, arr2) {
  // sort 自定义排序规则
  return (arr1.concat(arr2)).sort((a, b) => a - b)
}
```

### <p id="algorithm-11">★★ 数组中重复的数字</p>

> 数组去重  可以参考 https://segmentfault.com/a/1190000016418021

- #### 简易版

```javascript
function noRepeat (arr) {
  return [...new Set(arr)]
}
```

- #### 循环版

```javascript
function noRepeat (arr) {
  let result = []

  // 第 n+1 个不重复的元素
  for (let i = 0, len_i = arr.length; i < len_i; i++) {
    let isNoRepeat = true
    for (let j = 0, len_j = result.length; j < len_j; j++) {
      // 若数组中只有基本数据类型可以直接用 === 判断
      isNoRepeat = !isEqual(arr[i], result[j])
      if (!isNoRepeat) break;
    }
    if (isNoRepeat) result.push(arr[i])
  }
  return result;
}

// 用到的方法
function isEqual (obj1, obj2) {
  // 判断类型是否相同
  let type = getType(obj1)
  if (type !== getType(obj2)) return false;
  // 判断基本数据类型值
  if (typeof obj1 !== 'object') return obj1 === obj2;
  // 判断地址
  if (obj1 === obj2) return true;

  // 判断值是否相同
  switch (type) {
    // 对象
    case '[object Object]':
      // 取得可遍历属性
      let keys1 = Object.keys(obj1)
      let keys2 = Object.keys(obj2)
      if (keys1.length !== keys.length) return false
      // 长度相等
      for (let i = 0, len = keys1.length; i < len; i++) {
        let key = keys1[i]
        if (!isEqual(obj1[key], obj2[key])) return false;
      }
      break;
    // Map
    case '[object Map]':
    // Set
    case '[object Set]':
      // 转为数组
      obj1 = Array.from(obj1)
      obj2 = Array.from(obj2)
    // 数组
    case '[object Array]':
      if (obj1.length !== obj2.length) return false;
      for (let i = 0, len = obj1.length; i < len; i++) {
        if (!isEqual(obj1[i], obj2[i])) return false;
      }
      break;
    // ...
    default: break;
  }
  return true;
}
function getType (obj) {
  // 可以判断数组 Map Set数据类型
  return Object.prototype.toString.call(obj)
}
```

- #### 标记版

```javascript
function noRepeat (arr) {
  let result = []
  // 使用标记  使用 Map 可以判定多种数据类型
  // 这里也可以使用 WeakMap 弱引用  具体自己去查资料 js WeakMap类型
  const flag = new Map()

  for (let i = 0, len = arr.length; i < len; i++) {
    // 初步判定
    if (!flag.has(arr[i])) {
      let isNoRepeat = true
      // 基本数据类型直接插入
      // 引用数据类型
      if (typeof arr[i] === 'object') {
        for (let j = 0, len_j = result.length; j < len_j; j++) {
          isNoRepeat = !isEqual(arr[i], result[j])
          if (!isNoRepeat) break;
        }
      }
      // 没有重复
      if (isNoRepeat) {
        result.push(arr[i])
        flag.set(arr[i], true)
      }
    }
  }
  return result
}
```

### <p id="algorithm-12">★★ 两个数组的交集</p>

> 交集就是相同的部分  没有说是两个集合 所以最终的交集需要保留索引不同的相同的元素

- #### 基础版

```javascript
function intersection (arr1, arr2) {
  let flag = {}
  let result = []

  for (let i = 0, len_i = arr1.length; i < len_i; i++) {
    let item = arr1[i]
    // 搜索有没有    使用 indexOf 或 includes 也没问题
    for (let j = 0, len_j = arr2.length; j < len_j; j++) {
      // 判断相等建议使用之前封装的 isEqual 方法
      // isEqual(arr1[i], arr2[i])
      if (item === arr2[j] && !flag[j]) {
        result.push(item)
        flag[j] = true
        break;
      }
    }
  }
  return result
}
```

- #### Map标记版

```javascript
// 缺陷 若元素值有引用数据类型可能会出错
function intersection (arr1, arr2) {
  let map = new Map()
  let result = []

  for (let i = 0, len = arr1.length; i < len; i++) {
    let item = arr1[i]
    if (map.has(item)) map.set(item, map.get(item) + 1)
    else map.set(item, 1)
  }
  for (let i = 0, len = arr2.length; i < len ;i++) {
    let item = arr2[i]
    if (map.has(item)) {
      result.push(item)
      map.set(item, map.get(item) - 1)
    }
  }
  return result
}
```

- #### API版本

```javascript
// 更适合求两个集合的交集
function intersection (arr1, arr2) {
  // return noRepeat(arr1).filter(v => arr2.includes(v))
  return [...new Set(arr1)].filter(v => arr2.includes(v))
}
```

### <p id="algorithm-13">★★ 旋转数组</p>

> 倒序？ 或者 把数组往右旋转k步，要求不返回新的数组，直接改变原数组？

- #### 倒序

```javascript
function reverse (arr) {
  let len = arr.length

  for (let i = 0, mid = parseInt(len * 0.5); i < mid; i++) {
    [arr[i], arr[len - i - 1]] = [arr[len - i - 1], arr[i]]
  }
  return arr
}
```

- #### 旋转k步

```javascript
function rotateArr (arr, k) {
  let len = arr.length
  let tmp = [...arr]

  if (k < 0) k = (k % len) + len
  for (let i = 0; i < len; i++) {
    let index = (i + k) % len
    arr[index] = tmp[i]
  }
  return arr
}
```

### <p id="algorithm-14">★★ 两数之和</p>

> 给定一个整数数组`nums` 和一个目标值`target`，请你在该数组中找出和为目标值的那**两个**整数，并返回他们的数组下标。
>
> 你可以假设每种输入只会对应一个答案。但是，你不能重复利用这个数组中同样的元素。
>
> 示例    nums = [2, 7, 11, 15]    target  = 9    则结果返回 [0, 1] 即是2 和 7的下标

```javascript
function twoSum (arr, target) {
  let map = new Map()

  for (let i = 0, len = arr.length; i < len; i++) {
    let diff = target - arr[i]
    if (map.has(diff)) {
      return [map.get(diff), i]
    }
    map.set(arr[i], i)
  }
  return 'not found'
}
```

### <p id="algorithm-15">★★ 爬台阶的实现思路</p>

> 假设你正在爬楼梯。需要 n 阶你才能到达楼顶。
>
> 每次你可以爬 1 或 2 个台阶。你有多少种不同的方法可以爬到楼顶呢？
>
> 注意：给定 n 是一个正整数。
>
> 示例    n = 2  --->  2    两种方法 1阶 + 1阶    2阶

- #### 实现思路

```javascript
// 首先题目要求枚举出所有爬楼梯的台阶 而且可以一次只爬一个台阶(不管怎么爬最后都能只爬一步到达楼顶)
// 这是可以给出一个基本思路  爬一次(1或2) -> 爬剩余的台阶  终止条件是剩余台阶数为0
function climb (n) {
  if (n === 0) return 1  // 这里返回一次 代表可以爬到楼顶的一种方法
  climb(n - 1)  // 爬1阶后爬剩余的台阶
  if (n - 2 >= 0) {
  	climb(n - 2)  // 爬2阶后爬剩余的台阶 这时候要判断剩余台阶数是不是大于等于2      
  }
}

// 改进一下  终止条件设为 n <= 2
function climb (n) {
  if (n <= 0) return 0    // 直接终止
  if (n <= 2) return n    // 剩余1阶有一种解法 2阶有两种解法
  
  return climb(n - 1) + climb(n - 2)
}

// 此时可以发现climb(n - 1)内部又调用了climb(n - 2) 而 climb(n)也调用了climb(n - 2)
// 不妨保存一下计算结果
let cache = {}
function climb (n) {
  if (n <= 0) return 0    // 直接终止
  if (n <= 2) return n    // 剩余1阶有一种解法 2阶有两种解法
  if (cache[n]) return cache[n]
      
  return cache[n] = climb(n - 1) + climb(n - 2)
}
// 大功告成
```