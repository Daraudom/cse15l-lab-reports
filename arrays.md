# Introduction to Arrays

<aside>
💡 Arrays are Zero-Indexed. When creating arrays, make sure that `[]` has no whitespace from the data type

</aside>

## Creating an Array Explicitly

`<data type>[] <field name> = { }` 

```java
public class Newsfeed {
  
  
  public Newsfeed(){
    
  }
  
  // Create getTopics() below:
  public String[] getTopics(){
    String[] topics = {"Opinion", "Tech", "Science", "Health"};
    return topics;
  }
    

  public static void main(String[] args){
    Newsfeed sampleFeed = new Newsfeed();
   
    String[] topics = sampleFeed.getTopics();
    System.out.println(topics); // prints out a memory address
    
  }
}
```

## Importing Arrays

`import java.util.Arrays` to access to the Array Classes and its static method

`Array.toStrings(<array>)`checks the content of the array

```java
// import the Arrays package here:
import java.util.Arrays;

public class Newsfeed {
  
  
  public Newsfeed(){
    
  }
    
  public String[] getTopics(){
    String[] topics = {"Opinion", "Tech", "Science", "Health"};
    return topics;
  }
  

  public static void main(String[] args){
    Newsfeed sampleFeed = new Newsfeed();
    String[] topics = sampleFeed.getTopics();
    System.out.println(Arrays.toString(topics));
  }
}
```

## Get Element by Index [ ]

```java
public class Newsfeed {
  
  String[] topics = {"Opinion", "Tech", "Science", "Health"};
  int[] views = {0, 0, 0, 0};

public String getTopTopic(){
    return topics[0];
  }
public void viewTopic(int topicIndex){
    views[topicIndex] += 1;
  }
```

## Getting Last Element by Indexing

```bash
array[array.length - 1]
```

## Creating an Empty Array

<aside>
💡 Empty arrays have to be initialized with a **fixed size.**

</aside>

```java
// Format for Creating Empty Arrays
String[] menuItems = new String[5];

// Assigning Values 1
menuItems[0] = "Veggie hot dog";
menuItems[1] = "Potato salad";
menuItems[2] = "Cornbread";
menuItems[3] = "Roasted broccoli";
menuItems[4] = "Coffee ice cream";

// Assigning Values 2
String[] menuItems = {"Veggie hot dog", "Potato salad", "Cornbread", "Roasted broccoli", "Coffee ice cream"};

// Replacing Values
menuItems[3] = "Baked cauliflower";

```

<aside>
💡 When using `new` to create an empty array, each element of the array is initialized with a specific value depending on what type the element is:

</aside>

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bf47b8a0-b440-4d74-b5ec-ac22ed43505d/Untitled.png)

For instance, consider the following code:

```java
String[] my_names = new String[5]; //will contain 5 nulls to begin with 
```

### Examples:

```java
import java.util.Arrays;

public class Newsfeed {
  
  String[] topics = {"Opinion", "Tech", "Science", "Health"};
  int[] views = {0, 0, 0, 0};
  String[] favoriteArticles;
  
  public Newsfeed(){
    // Initialize favoriteArticles here:
    this.favoriteArticles = new String[10];
  }
  
  public void setFavoriteArticle(int favoriteIndex, String newArticle){
    // Add newArticle to favoriteArticles:
    favoriteArticles[favoriteIndex] = newArticle;
    
  }
    
  public static void main(String[] args){
    Newsfeed sampleFeed = new Newsfeed();
    
    sampleFeed.setFavoriteArticle(2, "Humans: Exterminate Or Not?");
    sampleFeed.setFavoriteArticle(3, "Organic Eye Implants");
    sampleFeed.setFavoriteArticle(0, "Oil News");
    
    System.out.println(Arrays.toString(sampleFeed.favoriteArticles));
  }
}
```

## Length

```java
String[] topics = {"Opinion", "Tech", "Science", "Health"};
  int[] views = {0, 0, 0, 0};

public int getNumTopics(){
    return topics.length; // returns 4
  }
```

## String[] args

<aside>
💡 `args[]` is the parameter that contains the arguments we pass in from the terminal when we run the class file. It is customary to have it named like that.

</aside>

```java
import java.util.Arrays;

public class Newsfeed {
  // instance fields
  String[] topics;
  //constructor
  public Newsfeed(String[] initialTopics) {
		topics = initialTopics;
  }
  // main method
  public static void main(String[] args) {
		Newsfeed feed; // uninitialize class object
    if (args[0].equals("Human")) {
      
      //topics for a Human feed:
      String[] humanTopics = {"Politics", "Science", "Sports", "Love"};
			feed = new Newsfeed(humanTopics);
      
    } else if(args[0].equals("Robot")) { //first argument in the terminal
      
      //topics for a Robot feed:
      String[] robotTopics = {"Oil", "Parts", "Algorithms", "Love"};
      feed = new Newsfeed(robotTopics);
      
    } else {
      String[] genericTopics = {"Opinion", "Tech", "Science", "Health"};
      feed = new Newsfeed(genericTopics);
    }
        
    System.out.println("The topics in this feed are:");
    System.out.println(Arrays.toString(feed.topics));
  }
}
```

```bash
$ java Newsfeed Human <- that's the args[0]
The topics in this feed are:
[Politics, Science, Sports, Love]

```

## Review
