# Design Patterns笔记
![avatar](http://www.runoob.com/wp-content/uploads/2014/08/the-relationship-between-design-patterns.jpg)

# Design Patterns 六大原则
1、开闭原则（Open Close Principle）
2、里氏代换原则（Liskov Substitution Principle）
3、依赖倒转原则（Dependence Inversion Principle）
4、接口隔离原则（Interface Segregation Principle）
5、迪米特法则，又称最少知道原则（Demeter Principle）
6、合成复用原则（Composite Reuse Principle）
# Factory Pattern
![avatar](http://www.runoob.com/wp-content/uploads/2014/08/factory_pattern_uml_diagram.jpg)
# Abstract Factory Pattern
![avatar](http://www.runoob.com/wp-content/uploads/2014/08/abstractfactory_pattern_uml_diagram.jpg)
# Singleton Pattern
![avatar](http://www.runoob.com/wp-content/uploads/2014/08/singleton_pattern_uml_diagram.jpg)
> 懒汉式线程安全

```java
public class Singleton {
    private static Singleton instance;  
    private Singleton (){}  
    public static synchronized Singleton getInstance() {  
    if (instance == null) {  
        instance = new Singleton();  
    }  
    return instance;  
    }  
}
```
>double-checked locking

```java
public class Singleton {  
    private volatile static Singleton singleton;  
    private Singleton (){}  
    public static Singleton getSingleton() {  
    if (singleton == null) {  
        synchronized (Singleton.class) {  
        if (singleton == null) {  
            singleton = new Singleton();  
        }  
        }  
    }  
    return singleton;  
    }  
}  
```

> 登记式/静态内部类

```java
public class Singleton {  
    private static class SingletonHolder {  
    private static final Singleton INSTANCE = new Singleton();  
    }  
    private Singleton (){}  
    public static final Singleton getInstance() {  
    return SingletonHolder.INSTANCE;  
    }  
}   
```
# Builder Pattern
![avatar](http://www.runoob.com/wp-content/uploads/2014/08/builder_pattern_uml_diagram.jpg)
