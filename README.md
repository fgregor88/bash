# Navigation

## cd

Change directory. path can be absolute or relative
```Bash
cd /Users/filip/Code/
```

## ls

List the content of the current directory.
```Bash
ls
```
List content of parent directory.
```Bash
ls ..
```
List long output ```-l``` and hidden files ```-a```
```Bash
ls -la
```

## mkdir

# Streams and Piping

- Piping the result of ls -la to grep to do filtering
```Bash
ls -la | grep "config"
```
- Redirecting the output of the previous command to save the output to a file
```Bash
ls -la | grep "config" > output.log
```
