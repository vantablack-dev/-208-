import java.util.Arrays;
import java.util.Comparator;	
	
	/*52 
	Продемонструйте спадкування інтерфейсів Спортивний(методи тренуватися,змагатися) 
	та Олімпійський(приймати участь у відкритті та закритті Олімпіад). 
	Створіть відповідні класи Борець та Шахіст які імплементують ці інтерфейси. 
	Покажіть приклад поліморфізму на підставі інтерфейсів.
	*/
	
	

	/*54
	Створіть 3 різних реалізації інтерфейсу Comparator<String>. 
	Перша реалізація повинна допомагати сортувати  рядки по довжині, друга - по 3 символу, 
	третя- по кількості голосних букв англ. Алфавиту. 
	Продемонструйте використання усіх default-реалізацій методів цього інтерфейсу
	*/
	
	/*41
	Створіть код, у якому генеруються слідуючі типи виключень  ArrayIndexOutOfBoundsException, ArithmeticException, 
	NullPointerException, IndexOutOfBoundsException, Exception. 
	Продемонструйте відмінність між =checked=  та  =unchecked= виключеннями.
	*/
	
	
	/*
	42
	Продемонструйте у коді генерацію свого виключення AgeStudentException у конструкторі класу Student 
	при спробі створити об'єкт зі значенням віку помилковим.
	*/
	public class L2 {
		
		
		
	public static void main(String[] args) throws Exception {
		
		/*40
		Продемонструйте роботу 15 методів класу Arrays
		*/
		
		int[] numbers = {167, -2, 16, 99, 26, 92, 43, -234, 35, 80};
			
		//1
	       Arrays.sort(numbers);
	    //2   
	       System.out.println(Arrays.toString(numbers));
	       
	    //3
	       int [] numbersCopy = Arrays.copyOf(numbers, 4);
	       System.out.println(Arrays.toString(numbersCopy));
	    
	    //4
	       int [] numbersCopy2 = Arrays.copyOfRange(numbers, 2,4);
	       System.out.println(Arrays.toString(numbersCopy2));
	    
	    //5
	    int [] numbersCopy3 = Arrays.copyOf(numbers, numbers.length);
	    System.out.println(Arrays.equals(numbers, numbersCopy3));
	    
	    //6
	    int[][] numbers2 = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};

	    int[][] numbersCopy4 = Arrays.copyOf(numbers2, numbers2.length);
	    
	    System.out.println(Arrays.deepEquals(numbers2, numbersCopy4));
	    
	    //7
	    System.out.println(Arrays.deepToString(numbers2));
	    
	    //8
	    System.out.println(Arrays.binarySearch(numbers, 16));
	    
	    //9
	    int[] numbers9 = {1, 2, 3};
	    int[] numbers91 = {1, 2, 4};
	    //лексикографическое
	    System.out.println(Arrays.compare(numbers9, numbers91));
	    
	    //10
	    int[] num10 = new int[10];
	    Arrays.fill(num10, 10);
	    System.out.println(Arrays.toString(num10));
	    
	    //11
	    int[] numbers11 = {0, 1, 2, 3, 88, 5};
	    int[] numbers111 = {0, 1, 2, 4, 5};
	    System.out.println(Arrays.mismatch(numbers11, numbers111));
	    
	    
	    
	    
	    //Task 2
	    ChessPlayer cp1 = new ChessPlayer("Vasya",0,0,0);
	    cp1.compet();
	    cp1.print();
	    
	    //Task 3
	    String a = "eejeeeeeeeeee";
	    String b = "qwbrtyuiop";
	    
	    CompareStr comp = new CompareStr();
	    System.out.println(comp.compare3Letter(a, b));
	    System.out.println(comp.compareLength(a,b));
	    System.out.println(comp.compareVowelNumber(a, b));
	    
	    CompStr comp1 = new CompStr();
	    System.out.println(comp1.compare3Letter(a, b));
	    System.out.println(comp1.compare(a,b));
	    System.out.println(comp1.compareVowel(a, b));
	    
	    
	    //Task4
	    /*41
		Створіть код, у якому генеруються слідуючі типи виключень  ArrayIndexOutOfBoundsException, ArithmeticException, 
		NullPointerException, IndexOutOfBoundsException, Exception. 
		Продемонструйте відмінність між =checked=  та  =unchecked= виключеннями.
		*/
	    
	    int[] arrEx = {1,2,3};
	    //System.out.print(arrEx[3]);
	    
	    //System.out.print(10/5);
	    
	    //Object obj = null;
        //obj.hashCode();
	    
	    
	    for(int i = 0; i < 5; i++) {
	    	//System.out.print(arrEx[i]);
	    }
	    
	    
	    
	    //Task 5
	    Student S1 = new Student("Seryoza",14);
	    S1.print();
	    
	   
	    int[] arr1 = {1,2,3,4,5};
	    int[] arr2 = {6,7,8,9,10};
	    
	    
	}
	
		
	
		
	}
	
	/*52 
	Продемонструйте спадкування інтерфейсів Спортивний(методи тренуватися,змагатися) 
	та Олімпійський(приймати участь у відкритті та закритті Олімпіад). 
	Створіть відповідні класи Борець та Шахіст які імплементують ці інтерфейси. 
	Покажіть приклад поліморфізму на підставі інтерфейсів.
	*/
	
	interface Sportyvny{
		 
	    void train();
	    void compet();
	}
	
	interface Olympiyskiy extends Sportyvny{
		 
	    void takePartInOpening();
	    void takePartInClosing();
	}
	class ChessPlayer implements Olympiyskiy{
	  
	    String name;
	    int power;
	    int experience;
	    int respect;
	  
	    ChessPlayer(String name, int power, int experience, int respect){
	          
	        this.name = name;
	        this.power = power;
	        this.experience = experience;
	        this.respect = respect;
	    }
	      
	    public void print() {
	      
	        System.out.printf("%s: %s, %s, %s \n", name, power, experience, respect);
	    }

		
		public void takePartInOpening() {
			respect += 20;
			
		}

		
		public void takePartInClosing() {
			respect += 30;
			
		}

		
		public void train() {
			power += 10;
			
		}

		
		public void compet() {
			experience += 10;
			
		}
		
	}
	
	/*54
	Створіть 3 різних реалізації інтерфейсу Comparator<String>. 
	Перша реалізація повинна допомагати сортувати  рядки по довжині, друга - по 3 символу, 
	третя- по кількості голосних букв англ. Алфавиту. 
	Продемонструйте використання усіх default-реалізацій методів цього інтерфейсу
	*/
	
	interface Comparator1 {
		 
	    default int compareLength(String a, String b) {
	    	if(a.length()<b.length()) return -1;
	    	else if (a.length()>b.length()) return 1;
	    	else return 0;
	    }
	    
	    default int compare3Letter(String strA, String strB) {
	    	char a = strA.charAt(3);
	    	char b = strB.charAt(3);
	    	
	    	if(a<b) return -1;
	    	else if (a>b) return 1;
	    	else return 0;
	    }
	    
	    default int compareVowelNumber(String strA, String strB) {
	    	char[] Vowel = {'A','a','E','e','O','o','U','u','Y','y','I','i',};
	    	int counterInStrA = 0;
	    	int counterInStrB = 0;
	    	
	    	for(int i = 0; i < strA.length(); i++) {
	    		for(int j = 0; j < 12; j++) {
	    			if(strA.charAt(i) == Vowel[j])counterInStrA++;
	    		}
	    	}
	    	
	    	for(int i = 0; i < strB.length(); i++) {
	    		for(int j = 0; j < 12; j++) {
	    			if(strB.charAt(i) == Vowel[j])counterInStrB++;
	    		}
	    	}
	    	
	    	
	    	if(counterInStrA<counterInStrB) return -1;
	    	else if (counterInStrA>counterInStrB) return 1;
	    	else return 0;
	    }
	}
	
	class CompareStr implements Comparator1{};
	
	class CompStr implements Comparator<String>{
		
		public int compare(String o1, String o2) {
			return (o1.length()-o2.length());
		}
		
		public int compare3Letter(String strA, String strB) {
	    	strA = strA.substring(2, 3);
	    	strB = strB.substring(2, 3);
	    	return strA.compareTo(strB);
	    }
		
		public int compareVowel(String o1, String o2) {
			char[] Vowel = {'A','a','E','e','O','o','U','u','Y','y','I','i',};
	    	int counterInStrA = 0;
	    	int counterInStrB = 0;
	    	
	    	for(int i = 0; i < o1.length(); i++) {
	    		for(int j = 0; j < 12; j++) {
	    			if(o1.charAt(i) == Vowel[j])counterInStrA++;
	    		}
	    	}
	    	
	    	for(int i = 0; i < o2.length(); i++) {
	    		for(int j = 0; j < 12; j++) {
	    			if(o2.charAt(i) == Vowel[j])counterInStrB++;
	    		}
	    	}
			return (counterInStrA-counterInStrB);
		}
		
		
		
		
		
	}
	
	//Task 5
	//Продемонструйте у коді генерацію свого виключення AgeStudentException у конструкторі класу Student 
	//при спробі створити об'єкт зі значенням віку помилковим.
	
	class AgeStudentException extends Exception{
		 public AgeStudentException ()
	     {
	         super("Помилковий вік");
	     }
	}
	
	class Student {
		String name;
		int age;
		
			Student(String name, int age) throws AgeStudentException{
				try
				{
				     if(age<15)
				     {
				          throw new AgeStudentException();
				     }
				}
				catch(AgeStudentException ex)
				{
				      System.out.print("Ви впевнені що вам "+age+"років?\n");
				}
		        this.name = name;
		        this.age = age;
		    }
		
		
		
		public void print() {
	        System.out.printf("Name: %s Age:%s\n", name, age);
	    }
	}
	
	
	
