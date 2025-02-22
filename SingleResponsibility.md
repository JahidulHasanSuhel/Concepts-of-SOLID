# Single-Responsibility Principle
## What is SRP?

This principle states that a class/method/interface **should only have one responsibility**. For example:
```
public class Book {
    // Properties
    private String name;
    private String author;
    private String text;

    // Constructor

    /*
    * Methods relate to the book properties
     */

    // Replace a word in text
    public String replaceWordInText(String word, String replacementWord){
        return text.replaceAll(word, replacementWord);
    }

    // Check if a word is in text
    public boolean isWordInText(String word){
        return text.contains(word);
    }

    /*
    * Method unrelated to the book, it is just output
     */

    // Print text to console
    public void printTextToConsole(){
        System.out.println(text);
    }

    // Getters and setters
}
```
The `Book` class should only handle the book properties, but, it violates the SRP because it has **two responsibilities: managing the book properties and printing the text to the console**. The `printTextToConsole` method should be in a different class, for example, in a `BookPrinter` class:
```
public class BookPrinter {
    /*
     * Method unrelated to the book, it is just output
     */

    // Print the book text to console
    public void printTextToConsole(Book book){
        System.out.println(book.getText());
    }
}
```
- [source code.](https://github.com/JahidulHasanSuhel/SOLID-Principles/tree/main/SingleResposibility)
## **`Goal`**: 
This principle aims to separate behaviours so that if bugs arise as a result of your change, it won’t affect other unrelated behaviours.
