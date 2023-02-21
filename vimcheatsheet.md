# Search lines and get the result list in a file
---

## Way to search
Here we don't want to use the ```:/...```, instead we are gonna use : 
```
:vimgrep /pattern/%
```

## Get a list of lines containing the pattern
Lines containing the pattern are now accessible in the quickfix list:
```
:copen
```

# Apply a command to lines containing a pattern
---

Here the mighty **general** command is the way to go :
```
:g/pattern/cmd
```

Ex : let's say I wanna delete all lines containing "#define":
```
:g/# define/d
```

**Note**: if I wanna use a shortcut as the cmd part, I can use the **norm** function:
```
:g/pattern/norm!J
```
will join to the line containing "pattern" whatever line follows it.

# Sort alphabetically
---
Simply use the ```:sort``` command on the selection.
sort can also take a regex as argument : lines containing the pattern will be sorted according to that pattern. Other will be sorted normally.

# Use groups in a search and replace
---
Groups are delimited by '''\(Here is my group\)''' and can be refered to using escaped integer starting at 1 (...).
So if I want to replace PREFIX_string_SUFIX by string I can use ''':s#PREFIX_\(\w*\)_SUFIX#\1#'''

