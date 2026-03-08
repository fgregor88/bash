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
List content of some path.
```Bash
ls Users/filip/Code/
```
List long output ```-l``` and hidden files ```-a```
```Bash
ls -la
```

## mkdir

Make directory.
```Bash
mkdir new_directory
```
Can also nest directories.
```Bash
mkdir new_directory/sub_directory/sub_sub_directory
```
Flag ```-p``` doesn't throw error if the directory already exists.
```Bash
mkdir new_directory
mkdir - p new_directory/sub_directory
```

# Streams and Piping

Pipes the result of ```ls -la``` to ```grep``` to do filtering
```Bash
ls -la | grep "config"
```
Redirecting the output of the previous command to save the output to a file
```Bash
ls -la | grep "config" > output.log
```
## Standard input, output, error_output
- 0 - standard input
- 1 - standard output
- 2 - error output

Example script ```example_script.sh```
```Bash
echo "hello"
echo1 "error"
```
We can redirect the normal output of the script to a ```output.log``` file and the error message to a different ```error.log``` file.
```Bash
./example_script.sh > output.log 2> erro.log
```
Shorthand to redirect both output and error stream to a file.
```Bash
./example_script.sh &> combined.log
```
