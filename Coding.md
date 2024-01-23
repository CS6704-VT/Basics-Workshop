# Programming Languages

> "You may not get to choose what programming language you use for your project, but it may be the most important choice there is. Programmers have argued about which language is best for as long as there have been programmers. In my experience, it makes a lot less difference than most people think…" - [Greg Wilson](https://buildtogether.tech/tooling/#programming-language)

One of the first things you need to know to be a successful software engineer is a programming language. Developers should also be able to quickly learn new programming languages and transfer knowlede between languages, which can be [very difficult to do](http://nischalshrestha.me/docs/cross_language_interference.pdf). For example, the following code scripts to print the same `hello world!` message in various programming languages:

```js |{type:'script'}
    console.log( "hello world!" );
```

```python |{type:'script'}
    print("hello world!")
```

```ruby |{type:'script'}
    print 'hello world!'
```

```java |{type:'script'}
class HelloWorld {
    public static void main(String[] args) {
        System.out.println("hello world!");
    }
}
```

## Integrated Development Environments

Integrated Development Environments (IDEs) enable software engineers to complete various activities related to writing a computer program. IDEs often provide a variety of features to support software development, including syntax highlighting, autocomplete, static analysis tools, debugging functionality, refactoring, multiple language support, integrations with git, code searching, and more...

Originally, software engineers wrote program code using punch cards in languages such as FORTRAN. Before the modern coding editors and cloud-based IDES, software engineers wrote code using editors in the console or terminal. One example is vi, an open source terminal-based development environment referred to as "the programmer's editor". It is a common joke in software engineering communities that vi is difficult to exit out of...

## Advanced: Vi/Vim

Vi (which stands for visual) is a terminal based text editor created for the Unix operating system. An updated version, [vim](https://www.vim.org/) (Vi IMproved), was introduced with many additional features that are available in modern IDEs. Use your terminal to get acquainted on the basics of this code editor following the instructions below:

## 📝 Activity

1. Update and install the Vim editor, then type the `vi fizzbuzz.<ext>` command to create a source code file named fizzbuzz in the programming language of your choice. 
2. When you first open the editor, you are in _command_ mode. Press `i` to enter _insert_ mode.
3. In insert mode, you should be able to edit the text as normal. Write the code for the fizzbuzz program (see more details below).
4. Press the Esc key to exit insert mode and go back into command mode. Useful commands for navigation include `j/down`, `k/up`, `h/left`, and `l/right` to navigate the file, `x` to delete a character, `/<string>` or `?<string>` to search the text, `:set number` to display line numbers, and `:<number>` to navigate to a line of your program.
5. The vim command to quit is `:q`. Alternatively, `:wq` will save (write) and quit while `:q!` will quit without saving. Save the changes you made to the file.


> **Fizz Buzz**
> 
> Fizz buzz is a classic [children's game](https://en.wikipedia.org/wiki/Fizz_buzz) and [programming challenge](https://leetcode.com/problems/fizz-buzz/). Write a program that prints each number from 1 to 20. If the number is divisible by 3, print `Fizz` instead. If the number is divisible by 5, print `Buzz` instead. And if the number is divisible by 3 and 5, then print `FizzBuzz`. This is a simple activity to practice REPL programming, not an interview. You are not expected to come up with the most efficient solution. Your program must at least contain some type of loop structure, conditional statements, and print statements.


* Remember to save your file(s)! You will need them later to submit for this workshop.

## Pair Programming

Software engineering is rarely done alone, often requiring teams of software engineers working together to develop and maintain the same product. Pair programming, a common practice in development environments where two software engineers work on a programming task together at the same computer, is one example of a collaborative SE task.

![pair](resources/imgs/pair.png)

## 📝 Activity

For the following activity, find a partner in class (or virtually if you are not in class) with shared knowledge of a programming language. Each student must complete a designated part of the program below _on their own machine_, while the partner **_actively_** participates in the coding.

> **Roman Numerals**
> 
> Roman numerals are depicted by using seven different symbols: `I, V, X, L, C, D and M` to represent seven different numerical values: `1, 5, 10, 50, 100, 500, 1000` (For example, the most recent Super Bowl LVI was Super Bowl 56). Complete the following for this activity:
> * One student will be the driver while the other navigates to write a function that converts an [integer to a Roman Numeral](https://leetcode.com/problems/integer-to-roman/). 
> * Then, students should switch roles to develop a function that converts [Roman numerals to integers](https://leetcode.com/problems/roman-to-integer/). 
> 
> The driver must complete their portion of the program on their own machine. When driving, each partner should add method-level comments to describe what the function does, who wrote it, and which IDE or text editor was used to write the code. Create your method(s) in a file named `Roman.<ext>`. You are not expected to come up with the most efficient or correct solution---this is an activity to practice pair programming, not a job interview. Only the conversion methods are needed.

Each partner should save their own file for later.


## [**Version Control with Git** ⏭️ ](Git.md)
