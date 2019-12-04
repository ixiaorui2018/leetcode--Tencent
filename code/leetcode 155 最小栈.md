# leetcode 155 最小栈
## edited by 王少锐
## c++



### 即实现栈操作，这里耍个小聪明，使用辅助栈!
```cpp
class MinStack {
public:
    stack<int> data;
    stack<int> minstack;
    /** initialize your data structure here. */
    MinStack() {
        
    }
    
    void push(int x) {
        data.push(x);
        if(minstack.empty() || x <= minstack.top()){
            minstack.push(x);
        }
    }
    
    void pop() {
        if(data.top() == minstack.top()){
            minstack.pop();
        }
        data.pop();
    }
    
    int top() {
        return data.top();
    }
    
    int getMin() {
        return minstack.top();
    }
};

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack* obj = new MinStack();
 * obj->push(x);
 * obj->pop();
 * int param_3 = obj->top();
 * int param_4 = obj->getMin();
 */

```
### 当然应该正式要这么写！不使用辅助栈！
### 以下这两种写法均来自评论区大佬，不是我自己写的，因为我赶时间哈哈哈！

#### 链表实现！
```java
class MinStack {
    List<Integer> list=new LinkedList<Integer>();
    int minNum=Integer.MAX_VALUE;
    /** initialize your data structure here. */
    public MinStack() {
        
    }  
    public void push(int x) {
        list.add(x);
        if(x<minNum){
            minNum=x;
        }
    }   
    public void pop() {
        if(minNum==list.get(list.size()-1)){
            minNum=Integer.MAX_VALUE;
            for(int i=0;i<list.size()-1;i++){
                if(list.get(i)<minNum){
                    minNum=list.get(i);
                }
            }
        }
        if(list.size()!=0){
            list.remove(list.size()-1);
        } 
    }
    
    public int top() {  
        return list.get(list.size()-1);
    }
    
    public int getMin() {
        return minNum;
    }
}


```

#### 数组写法！
```java
import java.util.EmptyStackException;
class MinStack {
        // 存储整个stack中的最小值
        private int min = Integer.MAX_VALUE;
        private int[] arrs = new int[10];
        private int index = 0;

        /**
         * initialize your data structure here.
         */
        public MinStack() {

        }

        public void checkGrowth() {
            if (index >= arrs.length - 1) {
                // 使用右移位运算符，每次扩容一半
                this.arrs = Arrays.copyOf(this.arrs, this.arrs.length + (this.arrs.length >> 1));
            }
        }

        public boolean isEmpty() {
            return this.index <= 0;
        }

        public void push(int x) {
            // 判断是否扩容
            checkGrowth();
            int min = this.min;
            if ( min > x) {
                this.min = x;
            }
            // 加入
            arrs[index] = x;
            index++;
        }

        public int pop() {
            // pop的时候先将下标指针-1, 然后找出此时栈中的最小值,赋值给this.min
            int top = top();
            this.index--;
            int min = Integer.MAX_VALUE;
            for (int i = 0; i < this.index; i++) {
                if (min > this.arrs[i]) {
                    min = this.arrs[i];
                }
            }
            this.min = min;
            return top;
        }

        public int top() {
            if (this.isEmpty()) {
                throw new EmptyStackException();
            }
            // 指针前移一位
            return this.arrs[this.index - 1];
        }

        public int getMin() {
            return this.min;
        }
}

```