# ShipNames
Enter a file of characters' names and get their ship names!
//Make a file with a list of characters, change "FileNameGoesHere" to the name of that file, and hit run. If you don't want it to randomly generate the names, and instead match the characters and leave a space for you to write it yourself, change "boolean randomize = true;" to boolean randomize = false;" :)

import java.text.*;

import java.util.ArrayList;

import java.util.Arrays;

import java.util.Scanner;

import java.util.TreeMap;

import java.util.TreeSet;

import java.math.*;

import static java.lang.System.*;

import java.io.File;

public class ShipNames

{
	public void run() throws Exception
	{
		//Scanner file = new Scanner(System.in);
		Scanner file = new Scanner(new File("FileNameGoesHere"));
		TreeSet<String> set = new TreeSet<String>();
		boolean randomize = true;
		while(file.hasNext()) {
			String a = file.next();
			if(a.equals("0")) {
				break;
			}
			set.add(a);
		}
		ArrayList<String> l = new ArrayList<String>();
		for(String z:set) {
			l.add(z);
		}
		if(randomize==false) {
			for(int x=0;x<l.size();x++) {
				for(int y=x+1;y<l.size();y++) {
					System.out.println(l.get(x) + "/" + l.get(y) + ":");
				}
				System.out.println();
			}
		}
		else {
			for(int x=0;x<l.size();x++) {
				for(int y=x+1;y<l.size();y++) {
					System.out.print(l.get(x) + "/" + l.get(y) + ":");
					System.out.println(" " + l.get(x).substring(0,l.get(x).length()/2) + l.get(y).substring(l.get(x).length()/2));
				}
				System.out.println();
			}
		}
		
	}
	
	public static void main(String[] args) throws Exception
	{
		new ShipNames().run();
	}	
}

