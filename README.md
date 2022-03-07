# Eytion++
![](eppp.png)
# Introduce
Eytion++ is developed by PowerAgnelXD based on the original project Eytion, \
which can be regarded as an enhanced version of Eytion, \
and has some more practical functions than Eytion

# License
This project uses the MIT open source license

# Install
You can get the latest compilation through the "action" above the project

# Build
After you download the source code package of this project, go to the inside of the downloaded folder\
after setting the working directory of the console to that directory, \
You can get the compilation by the following command:
```
cmake --build build
```

# Grammar
[Grammar introduce](grammar.txt)

# Example
> HelloWorld
```go
out "hello world!";
```
> Variable
```go
var a="hello ";
var b="world";
out a+b;
a="helloworld!";
out a;
var c:string = "yes"; #You can also write that
out c;
```
> Constant
```go
const c="constant";
out c;
c="hello" # will error
```
> List
```go
var a=[1,2,3,4];
out a[0];
a[1] = 45;
out a[1];
```
> Delete
```go
var a=[1,2,3,4];
delete a;
var b="string";
delete b;
```
> If--elif-else
```go
var a=input();
if (a=="hello")
    out "hello! my friend!";
elif (a=="good bye"){
    out "good bye!!!";
}
else{
    out "well done!";
}
```
> Repeat
```go
var a=["a","cb","fgh","err"];
var index = 0;
repeat(len(a)){
    out a[index];
    index=index+1;
}
```
> While
```go
var a=[1,6,2,5];
var index = 0;
while(index < len(a)){
    out str(a[index]) + "\n";
    index = ++index;
}
```
> For_each
```go
var str_list = ["hello!", "Eytion", "plusplus"];
for_each(var s: str_list){
    out "content: " + s + "\n";
}
```
> Break
```go
var a=[1,6,2,5];
var index = 0;
var in = input();
while(index < len(a)){
    if(index == 2 && in == "yes") break;
    out str(a[index]) + "\n";
    index=index+1;
}
```
> Special keywords/built-in functions
```go
# typeof
var a=typeof("hello");
out a; # output: __STRING__

# input
var b=input();
var c=input("input: ");
out b;
out c;

# len
var list = [1,2,3,4,5];
out len(list);

# type conversion
var i=input() # type: __STRING__
if(int(i) == 12)
    out "yes!";
```

# Config File
Typically, the format of Epp's configuration file is: ". ecfg"\
Now, this section will introduce you to the configuration system in EppCli Generally speaking, the default name of EPP's configuration file is ***common.ecfg*** it should be in the folder: \
`resource\config\` \
Here are the names of several configuration items and their purposes:
|name|purpose|value|
|:--:|:--:|:--:|
|cli-exittip|Used to prompt you whether to exit when exiting eppcli|true/false|
|cli-nameshow|Display the word eppcli under the cursor of eppcli: "EppCli"|true/false|
|cli-workspace|Displays the current working path|true/false|
|cli-errorhighlight|Whether to highlight errors in EPP (not for errors in eppcli)|true/false|
|debug-echoast|Output AST of running program|true/false|
|debug-echotokeng|Output TokenGroup of running program|true/false|

When you modify the configuration file and need to re apply and load it, you should enter the following code in eppcli:
```bash
redcfg
```