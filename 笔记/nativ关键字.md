```java
public class HelloJNI {
  //native 关键字告诉 JVM 调用的是该方法在外部定义
  private native void helloJNI();
  static{
    System.loadLibrary("helloJNI");//载入本地库
  }
  public static void main(String[] args) {
    HelloJNI jni = new HelloJNI();
    jni.helloJNI();
  }
}
```