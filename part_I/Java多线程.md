---
layout: default

---

# 多线程：

## Java创建多线程的几种方式：

- ## 继承Thread类，重写run()方法

  ```
  public class Demo1 extends Thread{
      
      //重写的是父类Thread的run()
      public void run() {
          System.out.println(getName()+"is running...");
      }
      
      
      public static void main(String[] args) {
          Demo1 demo1 = new Demo1();
          Demo1 demo2 = new Demo1();
          demo1.start();
          demo2.start();
      }
  }
  ```

- ## 实现Runnable接口，重写run()

  ```
  public class Demo2 implements Runnable{
  
      //重写的是Runnable接口的run()
      public void run() {
              System.out.println("implements Runnable is running");
      }
      
      public static void main(String[] args) {
          Thread thread1 = new Thread(new Demo2());
          Thread thread2 = new Thread(new Demo2());
          thread1.start();
          thread2.start();
      }
  
  }
  ```

- ## 匿名内部类的方式

  ```
  public class Demo3 {
      public static void main(String[] args) {
          //方式1：相当于继承了Thread类，作为子类重写run()实现
          new Thread() {
              public void run() {
                  System.out.println("匿名内部类创建线程方式1...");
              };
          }.start();
          
          
          
          //方式2:实现Runnable,Runnable作为匿名内部类
          new Thread(new Runnable() {
              public void run() {
                  System.out.println("匿名内部类创建线程方式2...");
              }
          } ).start();
      }
  }
  ```

- ## 带返回值的线程(实现implements Callable <返回值类型>)

  ```
  public class Demo5 implements Callable<String>{
  
      public String call() throws Exception {
          System.out.println("正在执行新建线程任务");
          Thread.sleep(2000);
          return "新建线程睡了2s后返回执行结果";
      }
  
      public static void main(String[] args) throws InterruptedException, ExecutionException {
          Demo5 d = new Demo5();
          /*    call()只是线程任务,对线程任务进行封装
              class FutureTask<V> implements RunnableFuture<V>
              interface RunnableFuture<V> extends Runnable, Future<V>
          */
          FutureTask<String> task = new FutureTask<>(d);
          Thread t = new Thread(task);
          t.start();
          System.out.println("提前完成任务...");
          //获取任务执行后返回的结果
          String result = task.get();
          System.out.println("线程执行结果为"+result);
      }
      
  }	
  ```

- ## 定时器(java.util.Timer)

  ```
  public class Demo6 {
      public static void main(String[] args) {
          Timer timer = new Timer();
          timer.schedule(new TimerTask() {
              @Override
              public void run() {
                  System.out.println("定时任务延迟0(即立刻执行),每隔1000ms执行一次");
              }
          }, 0, 1000);
      }
      
  }
  ```

  

- ## 线程池的实现(java.util.concurrent.Executor接口)

  ```
  public class Demo7 {
      public static void main(String[] args) {
          //创建带有5个线程的线程池
          //返回的实际上是ExecutorService,而ExecutorService是Executor的子接口
          Executor threadPool = Executors.newFixedThreadPool(5);
          for(int i = 0 ;i < 10 ; i++) {
              threadPool.execute(new Runnable() {
                  public void run() {
                      System.out.println(Thread.currentThread().getName()+" is running");
                  }
              });
          }
          
      }
  }
  ```

  

- ## Lambda表达式的实现(parallelStream)

  ```
  
  public class Demo8 {
      public static void main(String[] args) {
          List<Integer> list = Arrays.asList(1,2,3,4,5,6);
          Demo8 demo = new Demo8();
          int result = demo.add(list);
          System.out.println("计算后的结果为"+result);
      }
      
      public int add(List<Integer> list) {
          //若Lambda是串行执行,则应顺序打印
          list.parallelStream().forEach(System.out :: println);
          //Lambda有stream和parallelSteam(并行)
          return list.parallelStream().mapToInt(i -> i).sum();
      }
  }
  ```

  

[back](../)

