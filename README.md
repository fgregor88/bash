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
# File Operations

## cp - Copy files/directories
```Bash
cp file.txt file_copy.txt
cp file.txt /path/to/destination/
cp -r directory/ directory_copy/  # -r for recursive (directories)
```
## mv - Move or rename files
```Bash
mv old_name.txt new_name.txt
mv file.txt /path/to/new/location/
mv file.txt /path/to/new/location/new_name.txt  # move AND rename
```

## rm - Remove files/directories
```Bash
rm file.txt
rm -r directory/  # -r for recursive (required for directories)
rm -f file.txt   # -f for force (no confirmation)
```

## cat - Read file contents
```Bash
cat file.txt
cat file1.txt file2.txt  # concatenate multiple files
```

## touch - Create empty files or update time stamp
```Bash
touch new_file.txt
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

## Here string & here doc

### Here string
Provides a string directly as the input to a command that normally takes a file.
```Bash
python3 <<< 'print("hello world")'
```

### Here doc
EOF stands for "end of file" but is completely arbitrary, it can be any token it just has to match the end token.
```Bash
python3 << EOF
heredoc>print("hello w2orld")
heredoc>print(2+)
heredoc>for i in range(10:
heredoc>  print(i)
heredoc>EOF
```
