# Threads

_How is this achieved?_

## First way: 

1. Create a class that implements a Runnable interface ( run() method )
2. Write the code inside the run method
3. Create an instance of this class and store it in a variable of type Runnable
4. Build an instance of the Thread class with the Runnable object we just created as parameter (in ints constructor)
5. Run the thread via the start() method built in the Thread class

In the first example program (ThreadsBall, first commit) we practice this technique. It is demonstrated how we can launch simultaneously 3 threads represented as balls and stop them indivually. This is out first glance of what a thread is. Next we will look at thread sync.

## Second way:

1. Create a class that extends Thread
2. Write the code inside the run method
3. Start the thread

We can achieve thread synchronization with the method join(). 
In the second example, ThreadSync, we showcase this functionality of syncing threads, it tourns out to be quite interesting...

## Third example, the bank application:

1. We build a very simple app to make transfers between accounts. We implement this with the thread techniques we learned before...
2. In the commit "corrupt bank" we can see that there was something else to learn as our threads are not been synched successfully leading to a problem in the total money in the bank. It is dissapearing.
3. In the commit "I hired an accountant" we solved the previous issue by locking the code to the threads, only allowing one at a time. This is achieved with a few lines of code using the Reentrantlock class.
4. The next concept we learned is a clever one that kind of reminds me of my adventures in Javascript with the asynchronous stuff...Th function await() is useful because it causes a thread to "pause" but unlocks the code so that when a certain condition allows the paused thread to be executed, it will. I see this as a, lets say, optimizing technique.
5. There is also another way around the functionality we described in the fourth step. It consists on using the syncronyzed word. It is simpler but not as powerful compared to the previous way so I will leave that one in the code.
