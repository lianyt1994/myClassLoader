# myClassLoader
手写类加载器<br>
先继承`ClassLoader`，重写父类`findClass(String name)`方法，调用`parent.loadClass(name)`方法来看看有没有被父类加载，
如果有直接返回加载到的Class类对象，如果没有就通过`FileInputStream`或者`url.openStream()`来得到输入流，进而加载到内存，最后调用`defineClass(name, classData, 0,classData.length)`方法
把加载到内存的`byte[]`数组转变成Class类对象返回，加载结束。
