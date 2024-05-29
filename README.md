package jdbcprogram1;

public class multithreading implements Runnable{
	
	String name;
	multithreading(String name1){
		name=name1;
	}
	
	@Override
	public void run() {
		for(int i=1;i<=10;i++)
		// TODO Auto-generated method stub
			
		{		
			try {
				Thread.sleep(1000);
			} catch (InterruptedException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
		
		System.out.println(name+":"+i);
	}
		
	}

	public static void main(String[] args) {
	// TODO Auto-generated method stub

	multithreading m1=new multithreading("thread1");
	multithreading m2=new multithreading("thread2");
	
	Thread t1=new Thread(m1);
	Thread t2=new Thread(m2);
	
	t1.start();
	
	
	try {
		t1.join();
	} catch (InterruptedException e) {
		// TODO Auto-generated catch block
		e.printStackTrace();
	}
		
	t2.start();
	
	try {
		t2.join();
	} catch (InterruptedException e) {
		// TODO Auto-generated catch block
		e.printStackTrace();
	}
	
	}
	}

//Java thread join method can be used to paused the current thread execution until unless the 
//specified thread is dead.
