# hackathon
package some;
import java.io.BufferedReader;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;
public class FileReader {
			public static File folder = new File("C:/Users/aashu/Desktop/hack");
		   static String csvFile = "";
		   private static String cust_id;
       public static void main(String[] args)
                              {
    	                   cust_id=args[0];
    	                   System.out.println("hello "+ cust_id);
							System.out.println("Reading files under the folder "+ folder.getAbsolutePath());
							listFilesForFolder(folder);

	                                              }
  public static void listFilesForFolder(final File folder) {
		  for (final File fileEntry : folder.listFiles()) {
		      if (fileEntry.isDirectory()) 
		      {
		    	 
		        // System.out.println("Reading files under the folder "+folder.getAbsolutePath());
		        listFilesForFolder(fileEntry);
		      } 
		      else 
		      {
		        if (fileEntry.isFile()&& fileEntry.getName().equals(cust_id)) 
		        {
		        	
		        	System.out.println(fileEntry.getName());
		        	
		        	csvFile=folder.getAbsolutePath()+ "\\" + fileEntry.getName();
		          System.out.println(csvFile);
		          BufferedReader br = null;
		          String line = "";
			      String cvsSplitBy = ",";

			        try {
			        	br=new BufferedReader(new java.io.FileReader(csvFile));
		              // br=new BufferedReader(new FileReader(csvFile));
			   
			            try {
							while ((line = br.readLine()) != null) {

							    // use comma as separator
							    String[] arr = line.split(cvsSplitBy);

							    System.out.println("name= " + arr[0] + " , age=" + arr[1] + " , salary "+ arr[2]);

							}
						} catch (IOException e) {
							// TODO Auto-generated catch block
							e.printStackTrace();
						}

			        } catch (FileNotFoundException e) {
			            e.printStackTrace();
			        } 
			        
		        	}
		       
		          //System.out.println("File= " + folder.getAbsolutePath()+ "\\" + fileEntry.getName());
		        	
		          //System.out.println(cust_id);
		          //if ((temp.substring(temp.lastIndexOf('.') + 1, temp.length()).toLowerCase()).equals("txt"))
		           // System.out.println("File= " + folder.getAbsolutePath()+ "\\" + fileEntry.getName());
		        }
		      
		    	
		      }
		      
		    }
		   
	       
		  
  }




-------------------------------

package some;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.File;
import java.io.FileNotFoundException;
import java.io.FileReader;
public class CsvContent {

	public static void main(String[] args) {
		

	        String csvFile = "C:/Users/aashu/Desktop/hack/file11.csv";
	        BufferedReader br = null;
	        String line = "";
	        String cvsSplitBy = ",";

	        try {
               br=new BufferedReader(new FileReader(csvFile));
	   
	            try {
					while ((line = br.readLine()) != null) {

					    // use comma as separator
					    String[] arr = line.split(cvsSplitBy);

					    System.out.println("name= " + arr[0] + " , age=" + arr[1] + " , salary "+ arr[2]);

					}
				} catch (IOException e) {
					// TODO Auto-generated catch block
					e.printStackTrace();
				}

	        } catch (FileNotFoundException e) {
	            e.printStackTrace();
	        } 
	        
	}
}




---------------------


https://www.mkyong.com/java/how-to-read-and-parse-csv-file-in-java/
https://www.mkyong.com/java/how-to-read-and-parse-csv-file-in-java/
