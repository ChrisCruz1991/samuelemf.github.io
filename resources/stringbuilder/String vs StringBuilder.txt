
public class StringBuilderTestTime {

	public static void main(String[] args) {
		// This program show how efficient is StringBuilder over using String to concatenate.
		
		/* String Test*/
		String addHere = "";
		long startTime = System.nanoTime();
		//We add 250,000 a to the string called addHere.
		for (int i = 0; i < 250000; i++) 
			addHere += "a"; // <-- same as addHere = addHere + "a";

		long estimatedTime = System.nanoTime()-startTime;

		// 1 second is 1,000,000,000 nanoseconds
		// Here we print the time it took to print 250,000 'a' using normal concatenation.
		System.out.println("\t\t\tString\n__________________________________________________________________");
		System.out.println("It took " + estimatedTime + " nanoseconds or " +(estimatedTime/1000000000)+" seconds to concatenate 250,000 times using String.\n\n\n");

		/* StringBuilder Test */
		StringBuilder st = new StringBuilder();
		startTime = System.nanoTime();

		// We add the
		for (int i = 0; i < 250000; i++) 
			st.append("a"); // It can be a char, integer, double, float, and string.
		estimatedTime = System.nanoTime()-startTime;

		// 1 second is 1,000,000,000 nanoseconds
		// Here we print the time it took to print 250,000 'a' using StringBuilder
		System.out.println("\t\t\tStringBuilder\n__________________________________________________________________");
		System.out.println("It took " + estimatedTime + " nanoseconds or " +(estimatedTime/1000000000)+" seconds to concatenate 250,000 times using StringBuilder.");
		
		// To check that both strings are the same
		System.out.println(addHere.equals(st.toString())?"\n\nBoth of the strings are identical copies of each other.":"\n\nThe strings are not the same.");
		System.exit(0);
	}

}
