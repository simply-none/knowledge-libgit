# DecoratorPattern

💌**定义**：装饰者模式也叫包装器模式，在不改变对象本身的基础上，程序运行期间动态地给某个对象添加额外的职责，而不影响从这个类中派生的其他对象（改善继承的缺陷）。

💌**继承带来的问题**：
1. 父类和子类之间存在强耦合性，修改父类，子类也跟着改变
2. 白箱复用，父类内部细节对子类可见，破环封装性
3. 功能复用时，可能创建大量的子类

💌**特征**：
1. 装饰者对象与被装饰的对象拥有一致的接口，对于使用它的人来说是透明的，这种透明性可递归地嵌套任意多个装饰对象。
2. 将一个对象嵌入到另一个对象中，相当于这个对象被另一个对象包装起来，形成一条包装链，请求随着这条包装链传递到所有的对象，每个对象都有处理这条请求的机会。
3. 装饰函数：保存原先引用，并将该引用放入到新的该函数中执行，不过会带来以下问题：
   1. 增加了中间变量（保存原先引用的变量），在装饰链太长/装饰函数过多时，中间变量会越来越多
   2. 遇到了this被劫持的问题（比如改造document.getElementById函数）
4. AOP装饰函数：将行为依照职责分为粒度更细的函数，然后通过装饰将他们合并到一起，有利于松耦合、高复用
   1. 由于被before/after装饰后返回了新的函数，在原函数保存属性，新函数将会丢失
   2. 这种装饰方式叠加了作用域，装饰链过长，性能会受一些影响

💌**与其他模式的区别**：
1. 代理模式：访问本体不方便/不符合需要时，为该本体提供替代者。代理提供/拒绝访问本体已有的功能，或在访问前做一些额外的事情
2. 装饰者模式：为对象动态地加入一些新的行为