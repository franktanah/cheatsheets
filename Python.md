# Python

## Data Structures

### Lists

my_list = ["Test", "Something", "Else", "Lorem", "Ipsum"]

my_list.append("More Stuff")

my_list.remove("Something")

##### find 
my_list = ["Test", "Something", "Else", "Lorem", "Ipsum"]

my_list.index("Else") --> result 2

##### Get the last item / pop

last = my_list.pop

##### More functions

my_list.sort()

my_list[:2] --> ['Test', 'Something']

my_list[2:] --> ['Else', 'Lorem', 'Ipsum']


### Dicts

sample_dict={"apples":"28", "oranges":"12"}

sample_dict.keys() --> ['apples', 'oranges']

sample_dict.values() --> ['28', '12']

sample_dict.has_key("22") --> False