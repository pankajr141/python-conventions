python-conventions
==================

Module focus on forcing some python conventions to the programm. Its can be used to make your programm better.

#### Installation

```shell
pip install conventions
```

### Current Features
* Automatically ad getter and setter 
* Convert function name to lower_case (seprated by _)
* Convert variable name to lower_case (seprated by _)
* Convert variable starting with const_ to UPPERCASE
* Convert class name to form CapitalizedWords example(MyClassName)

### Usage

Add following line to top of your file
```shell
from conventions.conventions import __metaclass__
```

For debugging

```shell
from conventions.conventions import __metaclass__
__metaclass__.debug = True
```

### Example
```shell
from conventions.conventions import __metaclass__
__metaclass__.debug = True


class MyCLass_newDefine():
    myVar = 5
    COnsT_DIV = 'ADDD'
    MULTIPLY = 'ssss'
    MyVARIBALE = 'sss'

    def __init__(self):
        self.mynextvariable = 4

    def add_this_FUNCTION(self):
        print 'add_this_FUNCTION called'

    def addNewFunction(self):
        print 'addNewFunction called'

print MyCLass_newDefine.__dict__
obj = MyCLass_newDefine()
obj.mynextvariable = 5
#print obj.myvar                     # Gives Error
print obj.get_my_var()
obj.set_my_var(100)
print obj.get_my_var()
# Myclass.get_myvar()
obj.add_this_function()
#obj.add_this_FUNCTION()              # Gives error
```

Output
```shell
################## Modification Block ###################
class name changed # MyCLass_newDefine -> MyClassNewDefine
added getter function # get_my_varibale
added setter function # set_my_varibale
var/func name changed # MyVARIBALE -> my_varibale
var/func name changed # MULTIPLY -> MULTIPLY
var/func name changed # COnsT_DIV -> CONST_DIV
added getter function # get_my_var
added setter function # set_my_var
var/func name changed # myVar -> my_var
var/func name changed # add_this_FUNCTION -> add_this_function
var/func name changed # addNewFunction -> add_new_function
#########################################################
{'get_my_var': <function get_my_var at 0x024FACF0>, '__module__': '__main__', 'get_my_varibale': <function get_my_varibale at 0x024FABF0>, 'my_var': 5, 'add_new_function': <function addNewFunction at 0x024FAB70>, '__doc__': None, '__dict__': <attribute '__dict__' of 'MyClassNewDefine' objects>, '__weakref__': <attribute '__weakref__' of 'MyClassNewDefine' objects>, 'CONST_DIV': 'ADDD', 'set_my_var': <function set_my_var at 0x024FAD30>, 'MULTIPLY': 'ssss', 'add_this_function': <function add_this_FUNCTION at 0x024FAB30>, 'my_varibale': 'sss', 'set_my_varibale': <function set_my_varibale at 0x024FAC30>, '__init__': <function __init__ at 0x024FAAF0>}
5
100
add_this_FUNCTION called
```

