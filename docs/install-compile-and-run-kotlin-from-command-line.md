[kotlin/install-compile-and-run-kotlin-from-command-line](http://www.codexpedia.com/kotlin/install-compile-and-run-kotlin-from-command-line/)

# Install, compile and run Kotlin from command line

**Prerequsite**: Kotlin runs on jvm, which means [java runtime](http://www.codexpedia.com/java/java-environment-set-up-guide/) is required to run it.

Install [sdkman](http://sdkman.io/) from command line if it is not installed yet.

```
curl -s https://get.sdkman.io | bash
```

**Install Kotlin using the command sdk from the command line.**

```
sdk install kotlin
```

**Create a new file hello.kt**

```
fun main(args: Array<String>) {
       println("Hello World!")
   }
```

**Compile the Kotlin code using the kotlin compiler.**

```
kotlinc hello.kt -include-runtime -d hello.jar
```

**Run the Kotlin code on jvm using the java command.**

```
java -jar hello.jar
```

**Create shortcut for compiling and running Kotlin program**

Find out the Kotlin binary executables

```
which kotlin
```

Add the following to the `~/.bash_profile` file, replace the bin path with yours using vim editor `vim ~/.bash_profile`

```
export PATH=$PATH:/Users/yourmacosusername/.sdkman/candidates/kotlin/current/bin/
   function kotlinr() {
     echo Compiling, please wait...
     kotlinc $1 -include-runtime -d out.jar
     java -jar out.jar
   }
```

Apply the updates in the `~/.bash_profile` file.

```
source ~/.bash_profile
```

Now you can compile and run your Kotlin programs at at the same time like this:

```
kotlinr hello.kt
```

**Other Resources**:

[https://en.wikipedia.org/wiki/Kotlin_(programming_language)](https://en.wikipedia.org/wiki/Kotlin_(programming_language))

[http://kotlinlang.org/docs/tutorials/command-line.html](http://kotlinlang.org/docs/tutorials/command-line.html)

[https://android-developers.googleblog.com/2017/05/android-announces-support-for-kotlin.html](https://android-developers.googleblog.com/2017/05/android-announces-support-for-kotlin.html)
