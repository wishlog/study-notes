# study-notes
personal notes

# Programming course
https://hackr.io/

# Devop related
https://github.com/kamranahmedse/developer-roadmap
Graphical presentaiton of programming stuffs on the market divided by frontend, backend, devops

# Microservice explained
http://microservices.io/patterns/monolithic.html

# List of crypto related works
https://github.com/cmahon/awesome-cryptocurrency

# Another awesome devops
https://github.com/AcalephStorage/awesome-devops

# Awesome docker with cheatsheet
https://github.com/veggiemonk/awesome-docker

# video for full docker
https://github.com/machzqcq/docker-for-all

# udemy devops course
https://www.udemy.com/topic/devops/

# coursera bcp course
https://www.coursera.org/specializations/gcp-architecture

# Example go through dokku use case
https://glebbahmutov.com/blog/running-multiple-applications-in-dokku/#setting-up-continuous-deployment

# micro services explained, cloud foundry:
http://microservices.io/patterns/monolithic.html

# bash notes:
https://github.com/jlevy/the-art-of-command-line#meta

Understand that care is needed when variables and filenames include whitespace. Surround your Bash variables with quotes, e.g. "$FOO". Prefer the -0 or -print0 options to enable null characters to delimit filenames, e.g. locate -0 pattern | xargs -0 ls -al or find / -print0 -type d | xargs -0 ls -al. To iterate on filenames containing whitespace in a for loop, set your IFS to be a newline only using IFS=$'\n'.

Use xargs (or parallel). It's very powerful. Note you can control how many items execute per line (-L) as well as parallelism (-P). If you're not sure if it'll do the right thing, use xargs echo first. Also, -I{} is handy. Examples:


      find . -name '*.py' | xargs grep some_function
      cat hosts | xargs -I{} ssh root@{} hostname

Variable expression
In Bash, note there are lots of kinds of variable expansion. Checking a variable exists: ${name:?error message}. For example, if a Bash script requires a single argument, just write input_file=${1:?usage: $0 input_file}. Using a default value if a variable is empty: ${name:-default}. If you want to have an additional (optional) parameter added to the previous example, you can use something like output_file=${2:-logfile}. If $2 is omitted and thus empty, output_file will be set to logfile. Arithmetic expansion: i=$(( (i + 1) % 5 )). Sequences: {1..10}. Trimming of strings: ${var%suffix} and ${var#prefix}. For example if var=foo.pdf, then echo ${var%.pdf}.txt prints foo.txt.

Brace expansion using {...} can reduce having to re-type similar text and automate combinations of items. This is helpful in examples like mv foo.{txt,pdf} some-dir (which moves both files), cp somefile{,.bak} (which expands to cp somefile somefile.bak) or mkdir -p test-{a,b,c}/subtest-{1,2,3} (which expands all possible combinations and creates a directory tree). Brace expansion is performed before any other expansion.

The order of expansions is: brace expansion; tilde expansion, parameter and variable expansion, arithmetic expansion, and command substitution (done in a left-to-right fashion); word splitting; and filename expansion. (For example, a range like {1..20} cannot be expressed with variables using {$a..$b}. Use seq or a for loop instead, e.g., seq $a $b or for((i=a; i<=b; i++)); do ... ; done.)

Process substitution
      diff /etc/hosts <(ssh somehost cat /etc/hosts)

In Bash, redirect both standard output and standard error via: some-command >logfile 2>&1 or some-command &>logfile. Often, to ensure a command does not leave an open file handle to standard input, tying it to the terminal you are in, it is also good practice to add </dev/null.

For a simple web server for all files in the current directory (and subdirs), available to anyone on your network, use: python -m SimpleHTTPServer 7777 (for port 7777 and Python 2) and python -m http.server 7777 (for port 7777 and Python 3).
