## I'm a Python!

### Reverse Engineering, 50pts

Flag:  easyctf{python\_3x3c\_exec\_3xec\_ex3c}

##### How to solve it:

All of the text in file is converted into a base 16 encryption. Which is called hexadecimal\(logic\). So copy all of what the text file contains and paste it into the hex to ascii online tool. If you did it right, you will get somthing like this:

![](/assets/Capture2.PNG)

What could this be? Lets look at the hints! "you will need Python on your computer". So after a quick google search, exec in Python executes the code that is within its parentheses. chr\(\), returns a string of whose ascii code is of that value.

So, all you have to do is save this to a variable in python, and loop it until you get the flag!

Hint: Break the exec code into multiple parts and save them into muliple variables, so you don't get an overflow error when you try to save it all to one variable.

Made by: Konstantin T

