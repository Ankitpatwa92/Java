# Java

#### How to change java version
```
sudo update-alternatives --config java
```
#### How to get thread dump?
```
* jps //To list all java processes

* jstack -l  97008<pid>  >thread.dump


```
Found one Java-level deadlock:
=============================
"Thread-1":
  waiting to lock monitor 0x000000000483a808 (object 0x00000000d614dbe8, a logic.Account1),
  which is held by "Thread-0"
"Thread-0":
  waiting to lock monitor 0x000000000483bbf8 (object 0x00000000d614f280, a logic.Account2),
  which is held by "Thread-1"

Java stack information for the threads listed above:
===================================================
"Thread-1":
	at logic.ReentracLockTest.lambda$1(ReentracLockTest.java:33)
	- waiting to lock <0x00000000d614dbe8> (a logic.Account1)
	- locked <0x00000000d614f280> (a logic.Account2)
	at logic.ReentracLockTest$$Lambda$2/1044036744.run(Unknown Source)
	at java.lang.Thread.run(Thread.java:748)
"Thread-0":
	at logic.ReentracLockTest.lambda$0(ReentracLockTest.java:21)
	- waiting to lock <0x00000000d614f280> (a logic.Account2)
	- locked <0x00000000d614dbe8> (a logic.Account1)
	at logic.ReentracLockTest$$Lambda$1/135721597.run(Unknown Source)
	at java.lang.Thread.run(Thread.java:748)

Found 1 deadlock.


```
```
