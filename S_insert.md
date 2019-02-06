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
Table 3

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
Table 4

| Line        | Code          
| -------------:|:-------------|
| 0 | php saigon.php sl: |
 | 1 | K/f1 fi: aswap: s: f1 bv: array: |
 | 2 | 8 ap: 4 ap: l bv: s: sbv: |
 | 3 | K/MainActivity.kt  fi: |
 | 4 | cx: s: L0 l: 1 - over: over: 12 swap: - |
 | 5 | dup: l tbv: - L1 bnz: |
 | 6 | l pbv: . f1 pbv:  esp: |
 | 7 | L1 l: esp: i: esp: |
 | 8 | L0 bnz: s: |
 | 9 |  |

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
