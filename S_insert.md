## Metaprogramming: Inserting New Code to Kotlin Program


\[ [Table of Contents](https://github.com/udexon/SAIGON/blob/master/0_Table_of_Contents.md) \]

```
 0   package com.developers.kotlintest 
 1    
 2   import android.support.v7.app.AppCompatActivity 
 3   import android.os.Bundle 
 4    
 5   class MainActivity : AppCompatActivity() { 
 6    
 7   override fun onCreate(savedInstanceState: Bundle?) { 
 8   super.onCreate(savedInstanceState) 
 9   setContentView(R.layout.activity_main) 
 10   } 
 11   }
 ```
Table 1

Source: https://github.com/amanjeetsingh150/kotlin-android-examples/blob/master/KotlinTest/app/src/main/java/com/developers/kotlintest/MainActivity.kt

Let us consider a seemingly trivial exercise: add `Log.i("test","test")` to the start of `onCreate()` in the program shown above. For human programmer, it would be almost trivial. But how can human programmer write a program to do so instead?

<pre>
0   package com.developers.kotlintest
1   
2   import android.support.v7.app.AppCompatActivity
3   import android.os.Bundle
4   <i>import android.util.Log</i>
5  
6   class MainActivity : AppCompatActivity() {
7  
8       override fun onCreate(savedInstanceState: Bundle?) {
9           <i>Log.i("test","test")</i>
10          super.onCreate(savedInstanceState)
11          setContentView(R.layout.activity_main)
12      }
13  }

</pre>
Table 2

Table 2 shows the output results. Line 4 is required for `import`. The `Log.i()` function is added at line 9.

```
 0    import java.io.File 
 1    import java.io.InputStream 
 2    
 3    // readinsert.jar f0 f1 L0 L1 L2 L3 L4 .... 
 4    // insert f1 line 0 to line L0 in f0 
 5    // insert f1 line 1 to line L1 in f0 
 6    // insert f1 line 2 to line L2 in f0 
 7    
 8    fun main(args: Array<String>) { 
 9    
 10   if (args.size == 0) { 
 11   println("Please provide a name as a command-line argument") 
 12   return 
 13   } 
 14   println("Input is: ${args[0]}") 
 15   println("Input is: ${args[1]}") 
 16   println("Lines   : ${args[2]} ${args[3]}") 
 17    
 18   // val inputStream: InputStream = File("o_diff_Main").inputStream() 
 19   val bufferedReader = File( args[0] ).bufferedReader() 
 20   val lineList = mutableListOf<String>() 
 21    
 22   bufferedReader.useLines { lines -> lines.forEach { lineList.add(it) } } 
 23   // lineList.forEach { println(">  " + it) } 
 24    
 25   val bufferedReader1 = File( args[1] ).bufferedReader() 
 26   val lineList1 = mutableListOf<String>() 
 27    
 28   bufferedReader1.useLines { lines -> lines.forEach { lineList1.add(it) } } 
 29    
 30   var j=0 
 31   for (i in lineList.indices) { 
 32   if (i==args[2].toInt() || i==args[3].toInt()) println("$i  " + lineList1[j++]) // println("$i  ") 
 33   println("$i  " + lineList[i]) 
 34   } 
 35    
 36    
 37   /*	for (i in lineList1.indices) { 
 38   println("$i  " + lineList1[i]) 
 39   } */ 
 40   } 
```
Table 3: Program A

Table 3 shows a Kotlin program to add the lines to produce the code shown in table 2.

```
 0   php saigon.php sl: 
 1   K/f1 fi: aswap: s: f1 bv: array: 
 2   8 ap: 4 ap: l bv: s: sbv: 
 3   K/MainActivity.kt  fi: 
 4   cx: s: L0 l: 1 - over: over: 12 swap: - 
 5   dup: l tbv: - L1 bnz: 
 6   l pbv: . f1 pbv:  esp: 
 7   L1 l: esp: i: esp: 
 8   L0 bnz: s:
```
Table 4: Program B

Table 4 shows a SAIGON (stack machine code) program implemented in PHP to perform the equivalent task in table 3. 


### Discussions

From the above seemingly trivial example, here is a serious questions:

- Is it possible to write a program to analyse Program A shown in table 3?

That would be a tall order.

It would be much easier to write a program to analyse Program B shown in table 4. This is where the homoiconic properties of stack machine / reverse Polish notation becomes significant.

SAIGON or reverse Polish notation (RPN a la Forth) is perhaps the most compact form of human readable code (although there are more exotic programming languages like “Brainfuck” -- I kid you not, it exists!!). The crucial feature here is homoiconicity: the program code can be parsed as data and analysed, vice versa. Any other programming language would be too complicated to be parsed.

SAIGON forces programmer to simplify program to stack machine minimal, hence easier to parse.

Without homoiconicity, it will be impossible to write a "self evaluating program", e.g. to accomplish the seemingly trivial task of inserting Logcat code to "Hello world" Kotlin example.




## Future Work

- Extend Fotoapparat, add SAIGON interface, then add OpenCV image processing capabilities.

This serves as the "grounding" for the SAIGON artificial intelligence module.

- Write SAIGON in Kotlin (by extension Java).

- Code and configuration files as SAIGON graph database objects

With the examples and discussions above, we are now better prepared to consider the following fundamental questions:

- Why would a programmer wants to insert a `Logcat()` function in a program?
- How could we simulate the programmer's decision to do so?
- How could be set up a system that can 'self evaluate' a program that involves camera and image processing?
- How can we make a program involoing camera and image processing 'self aware'?


\[ [Table of Contents](https://github.com/udexon/SAIGON/blob/master/0_Table_of_Contents.md) \]
