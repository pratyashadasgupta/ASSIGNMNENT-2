# ASSIGNMNENT-2

Q1
package assignment2;

import java.util.ArrayList;

public class ReplaceElement {
	public static void main(String[]args) {
		ArrayList<Integer> list = new ArrayList<Integer>();
		
		list.add(1);
		list.add(2);
		list.add(3);
		list.add(4);
		list.add(5);
		
		System.out.println("Original list:- "+ list);
		int a=6;
		list.set(1, a);
		
		System.out.println("After replacing:- " + list);
	}
}

  
Q2
  
package movies.java;

public class Movie {
	
	private String name;
	private Integer year;
	private Double rating;
	
	public Movie() {
		
	}
	
	public Movie(String name, Integer year , Double rating) {
		super();
		this.name = name;
		this.year = year;
		this.rating = rating;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public Integer getYear() {
		return year;
	}

	public void setYear(Integer year) {
		this.year = year;
	}

	public Double getRating() {
		return rating;
	}

	public void setRating(Double rating) {
		this.rating = rating;
	}
	
	
    @Override
	public String toString() {
		return "Movie [name=" + name + ", year=" + year + ", rating=" + rating + "]";
	}
}
  
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

public class MovieSort {
	public static void main(String[] args) {
		ArrayList<Movie> movie = new ArrayList<Movie>();
		movie.add(new Movie("Gangubai Kathiawadi",2022,9.3));
		movie.add(new Movie("Iron Man",2010,7.8));
		movie.add(new Movie("Kuch Kuch Hota Hai",1997,6.6));
		
		System.out.println(movie);
		
		System.out.println("Year wise sorting:-");
		Collections.sort(movie, new Comparator<Movie>(){
			
			public int compare(Movie o1 , Movie o2) {
				return (o1.getYear() - o2.getYear());
			}
		});
		for(Movie m:movie) {
			System.out.println(m.getName()+" "+m.getRating()+" "+m.getYear());
		}
		
 
        System.out.println("Rating wise sorting:-");
		Collections.sort(movie, new Comparator<Movie>(){
			
			public int compare(Movie o1 , Movie o2) {
				return (int) (o1.getRating() - o2.getRating());
			}
		});
        for(Movie m:movie) {
 			System.out.println(m.getName()+" "+m.getRating()+" "+m.getYear());
 		}
        
        
        System.out.println("Name wise sorting:-"); 
        Collections.sort(movie, new Comparator<Movie>(){

			@Override
			public int compare(Movie o1, Movie o2) {
				// TODO Auto-generated method stub
				return o1.getName().compareTo(o2.getName());
			}
		});
        for(Movie m:movie) {
 			System.out.println(m.getName()+" "+m.getRating()+" "+m.getYear());
 		}
    }
}
  
  
Q3
  
package assignment2;

import java.util.HashMap;
import java.util.Set;

public class HashMapDemo {
	
	public static void main(String[] args) {
		
		HashMap<String,Integer> hm = new HashMap<String,Integer>();
		
		hm.put("Red",3);
		hm.put("Blue",1);
		hm.put("Green",2);
		
		Set ks = hm.keySet();
		
		System.out.println(ks);
	}
}
  
  
Q4
  
import java.util.HashMap;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
import java.util.Map;
import java.util.Map.Entry;


public class Sort {
	public static void main(String[] args) {
		HashMap<String,Integer> hm = new HashMap<String,Integer>();
		hm.put("Red",3);
		hm.put("Blue",1);
		hm.put("Green",2);
		
	    List<Map.Entry<String,Integer>> list = new ArrayList<>(hm.entrySet());
	    Collections.sort(list, new Comparator<Map.Entry<String, Integer>>(){

			@Override
			public int compare(Map.Entry<String,Integer> o1, Map.Entry<String,Integer> o2) {
				// TODO Auto-generated method stub
				return (o1.getValue()-o2.getValue());
			}
	    });
	    
	    for(Map.Entry<String,Integer> o:list) {
	        System.out.println(o.getKey()+" ");
	    }
	}

}

