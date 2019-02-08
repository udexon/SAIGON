## Bootstrapping Artificial Intelligence: Grounding and Metaprogramming
### SAIGON: Kotlin Examples


\[ [Table of Contents](https://github.com/udexon/SAIGON/blob/master/0_Table_of_Contents.md) \]

We begin with a motion detection Python program from PyImageResearch.

https://www.pyimagesearch.com/2015/05/25/basic-motion-detection-and-tracking-with-python-and-opencv/

The reason we are interested in an image processing program is that we believe this is the foundation of “grounding” in the philosophy of artificial intelligence, ie. how could computer know about itself and the external world? The quick and short answer is: it has to be based on sensors, and the most widely available sensor with the largest amount of input data has to be the camera. A thorough discussion of this issue would be the topic of multiple PhD theses!! 

https://en.wikipedia.org/wiki/Symbol_grounding_problem

The Python motion detection program gives a simple measure to detect if an external object is near to the camera -- by simply counting the number of white pixels of one contiguous region of moving objects: if the number of white pixels is large, then the object is near. We believe this also forms the fundamental mechanism in human reasoning. One of the areas of investigation in the SAIGON project is to construct a hierarchical framework of computer program functions, to mimic how human beings think, based on multiple primitive functions in a hierarchical structure. 
Although the Python program looks simple enough for any programmer with several months of experience, it would be nice if we can run the motion detection algorithm on an Android mobile phone. But here is where the nightmare begins. Android programs are MONSTERS!!

https://github.com/RedApparat/Fotoapparat

https://github.com/amanjeetsingh150/kotlin-android-examples

Firstly, it takes experience, lots of experience in fact, to identify Android open source projects that are actually working -- having to go through setting up the Android Studio for compiling and testing etc, which is non-trivial for programming “babies”. We have done the heavy lifting for you by identifying the Kotlin projects listed above.

Finally we look at the Stack Machine Metaprogramming (SMMP) part of SAIGON. Although the name SMMP sounds daunting, it is again actually quite straight forward. To illustrate, consider these questions: 

    Q: How would you write a program without learning the programming language? 
    A: Just copy it. 

    Q: How many lines of code do you need to modify to satisfy the requirements by a customer?
    A: As few as possible.

SMMP is simply an automatic way to do the above!! Wonderful, isn’t it?

Now wait, for those of you with slightly more programming experience, you might start to wonder if this is possible at all, having known the complexities of some of the fundamental problems in software engineering. So we will show you the magic.

Of the fundamental problems of software engineering, consider this: Is there a single computer programming language that can be used to represent and process ALL the different configuration files and source files in various formats and programming languages, typical in modern software projects?

It turns out that there is one, which predates all modern programming languages -- the Reverse Polish Notation of a stack machine. The historical development of RPN and stack machine is another interesting topic which could span multiple PhD theses. Suffice to say that, the design of stack machine predated modern electronic computers. The modern form of Reverse Polish Notation can however, in our humble opinion, be attributed to Edsger Dijkstra and Charlese H. Moore, the inventor of the Forth programming language.

Knowing the factionalism in the programming communities, I suspect the above paragraph would ignite “flame wars”, an old Usenet newsgroup term which may have largely been forgotten. However, we are always open to proposals if you think there is an alternative to replace RPN. In our case, we combine RPN with JSON to create SAIGON.  

(As an overseas Chinese, I would like the readers to consider the history of Qin Shihuang who united China and its writing system, as the cultural background of SAIGON.  西贡， 华夏南端也。西贡以外， 夷邦也。)

Just to recap an important point we made above: The most important application of the idea of database function for the purpose of learning a new programming language would be to treat the source code and configuration files of a project as database objects.

If we copy a project such as Fotoapparat without change, it may not seem relevant to have to treat the source files as database objects. However, even if we decide to change the value of one single variable in one of the thousands of files, we need database operations to accomplish this. 

Or you might argue, I can just edit a variable using a text editor. If you take this line of arguments, is it possible that your decision to modify a variable the results of graph database operations, which originates from your brain? 

As such, in order to create an “automatic” or “programmable” system that can modify variables of existing programs, we need graph database as well as stack machine functionalities, hence the name Stack Machine Artificial Intelligence Graph Object Notation.

Our strategy starts with comparing project files in Kotlin projects, from the examples mentioned above (shown again below). To be more specific, we use the Unix “diff -r” (recursive diff) to compare all files in in all subdirectories. Our hypothesis is that, similar projects would have project files that are similar. We may sort projects by arranging them in pairs which are most similar, to create a hierarchy of projects, from the simplest “Hello World” to the more complex Fotoapparat, or even more complex projects.

https://github.com/RedApparat/Fotoapparat

https://github.com/amanjeetsingh150/kotlin-android-examples

For example, we may compare MainActivity.kt in the project subdirectories. 

What we described above is simply a formalization of “learning by examples”. In order to manage the project files, we need a graph database system that is integrated with the Unix filesystem. Further, in order to model the objects in a file (tokens, variables, blocks etc.), we need a programming language capable of manipulating trees, specifically abstract syntax trees. There are many programming languages which are capable of manipulating trees. However, perhaps only LISP and RPN satisfy the homoiconic criterion, ie. the code can be represented as data in database record (i.e. SAIGON). In contrast to LISP, we have also demonstrated that RPN can be easily implemented in most programming languages in around 50 lines of PHP or JavaScript equivalent code, using the Inverse Shunting Yard Algorithm (ISYA), the inverse of the shunting yard algorithm proposed by Dijkstra (DSYA).

The following script counts the number of different lines (Unix diff) in MainActivity.kt from the basic KotlinTest (“Hello World”) project. It gives a good indication of projects in increasing complexity.

```
while read p; do
    echo `diff ./KotlinTest/app/src/main/java/com/developers/kotlintest/MainActivity.kt $p | wc` "$p"
done < $1
```
```
0 0 0 ./KotlinTest/app/src/main/java/com/developers/kotlintest/MainActivity.kt
4 8 80 ./CustomView/app/src/main/java/com/developers/customview/MainActivity.kt
8 15 195 ./UsingSpringAnimation/app/src/main/java/com/developers/usingspringanimation/MainActivity.kt
9 17 181 ./TimberExample/app/src/main/java/com/developers/timberexample/MainActivity.kt
10 31 318 ./IntentService/app/src/main/java/com/developers/intentservice/MainActivity.kt
12 28 315 ./ViewPager/app/src/main/java/com/developers/viewpager/MainActivity.kt
15 40 512 ./DataBinding/app/src/main/java/com/developers/databinding/MainActivity.kt
16 36 414 ./ObjectAnimator/app/src/main/java/com/developers/objectanimator/MainActivity.kt
17 48 661 ./RecyclerView/app/src/main/java/com/developers/recyclerview/MainActivity.kt
18 36 439 ./BroadcastReceiver/app/src/main/java/com/developers/broadcastreceiver/MainActivity.kt
21 55 643 ./SpekExample/app/src/main/java/com/developers/spekexample/MainActivity.kt
22 59 694 ./ValueAnimator/app/src/main/java/com/developers/valueanimator/MainActivity.kt
…. …. ….
71 231 2550 
72 231 2170 ./KotlinCoroutines/app/src/main/java/com/developers/kotlincoroutines/MainActivity.kt
73 208 2610 ./HandlerThread/app/src/main/java/com/developers/handlerthread/MainActivity.kt
87 262 2629 ./FormsWithRx/app/src/main/java/com/developers/formswithrx/MainActivity.kt
90 324 3486 ./CircularReveals/app/src/main/java/com/developers/circularreveals/MainActivity.kt
103 309 3568 ./MVVMSample/app/src/main/java/com/developers/mvvmsample/ui/MainActivity.kt
108 331 3763 ./MVPSample/app/src/main/java/com/developers/mvpsample/ui/main/MainActivity.kt
147 464 7087 ./GraphQL/app/src/main/java/com/developers/graphql/MainActivity.kt
163 680 6940 ./FingerprintAPI/app/src/main/java/com/example/jatinjha/fingerprintkotlin/MainActivity.kt
```


\[ [Table of Contents](https://github.com/udexon/SAIGON/blob/master/0_Table_of_Contents.md) \]
