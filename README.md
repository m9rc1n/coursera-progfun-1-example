# Assignment description

## Part 1: Obtain the Project Files

[Download the example.zip](http://spark-public.s3.amazonaws.com/progfun/assignments/example.zip) handout archive file and extract it somewhere on your machine.

## Part 2: Using the Scala REPL

During this class we will always launch the Scala REPL (the interactive Scala console) through sbt. This way you don’t need to install the Scala distribution on your machine, having sbt is enough. (In case you prefer to have the `scala` command available on your machine, you can download the Scala distribution from the [scala-lang.org website](http://www.scala-lang.org/downloads).)

Open the [Sbt Tutorial](../wiki/view?page=SbtTutorial) page and follow the first steps until “Running the Scala Interpreter”. Note that sbt can only be started inside a project directory, so first navigate to the project directory that you created in Part 1.

Enter a few Scala expressions to make sure everything is working as expected.

## Part 3: Opening the Project in Eclipse

To work on the source code of the project, you have to import it into eclipse. Follow the description on the [Eclipse Tutorial](../wiki/view?page=EclipseTutorial) page and take a first look at the source code. In the folder `src/main/scala`, open the package `example` and double-click the file `Lists.scala`. There are two methods in this file that need to be implemented (`sum` and `max`).

When working on an assignment, <span class="bigwarn">it is important that you don't change any existing method, class or object names or types</span>. Doing so will prevent our automated grading tools from working and you have a <span class="bigwarn">high risk of not obtaining any points</span> for your solution.

## Part 4: Running your Code

Once you start writing some code, you might want to run your code on a few examples to see if it works correctly. We present two possibilities to run the methods you implemented.

### Using the Scala REPL

In the sbt console, start the Scala REPL by typing `console`.

```
> console
[info] Starting scala interpreter...

scala>
```

The classes of the assignment are available inside the REPL, so you can for instance import all the methods from object `Lists`:

```
scala> import example.Lists._
import example.Lists._

scala> max(List(1,3,2))
res1: Int = 3
```

### Using a Main Object

Another way to run your code is to create a new `Main` object that can be executed by the Java Virtual Machine.

1.  In eclipse, right-click on the package `example` in `src/main/scala` and select “New” - “Scala Object”
2.  Use `Main` as the object name (any other name would also work)
3.  Confirm by clicking “Finish”

In order to make the object executable it has to extend the type `App`. Change the object definition to the following:

```
object Main extends App {
  println(Lists.max(List(1,3,2)))
}
```

Now the `Main` object can be executed. In order to do so in eclipse:

1.  Right-click on the file `Main.scala`
2.  Select “Run As” - “Scala Application”

You can also run the `Main` object in the sbt console by simply using the command `run`.

## Part 5: Writing Tests

Throughout the assignments of this course we will require you to write unit tests for the code that you write. Unit tests are the preferred way to test your code because unlike REPL commands, unit tests are saved and can be re-executed as often as required. This is a great way to make sure that nothing breaks when you have go back later to change some code that you wrote earlier on.

We will be using the ScalaTest testing framework to write our unit tests. In eclipse, navigate to the folder `src/test/scala` and open the file `ListsSuite.scala` in package `example`. This file contains a step-by-step tutorial to learn how to write and execute ScalaTest unit tests.
