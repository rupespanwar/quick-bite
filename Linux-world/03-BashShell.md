# Intriduction
           echo $0
           cat /etc/shells
           bashshell $ vi demo.sh
```
  bashshell $ cat demo.sh
  #!/bin/bash
  mkdir -p dir1
  echo "some text" > dir1/file1.txt
  ls -l dir1
  cat dir1/file1.txt
```
-  bashshell $ chmod 700 demo.sh
-  bashshell $ ls
```
                demo.sh
                bashshell $ ./demo.sh
                total 8
                -rw-r--r--  1 rupeshpanwar  staff  10 Aug 19 06:55 file1.txt
                some text
```
- echo $PATH

# Shebang & comments
- bashshell $ which bash
       - /bin/bash
- #!/bin/bash
- comment #
<img width="371" alt="image" src="https://user-images.githubusercontent.com/75510135/129993572-9ef3dc6c-af16-45f7-9aa7-fcc2b221f548.png">
- set line number => :set nu
- to make it persistent => bashshell $ vi ~/.vimrc => set nu

# Running the script
        ./scriptname.sh
        chmod 700 scriptname
        bash scriptname
        python3 scriptname
        chmod +x scriptname
        source scriptname
        . scriptname

# variables
          os=linux
          distro="ms linux"
          age=30
          4you=true #not allowed
          server_name="Apache 2.4"
          to print => echo $age , echo $os
          echo "I' learning $os and I'm $age old"
          echo "the value of \$os is $os"
          my_distro="$os $distro"
          to search => set | grep distro
          # to unset the value of distro
          unset distro
          # Env vars
          echo $USER $HISTFILE $HOME $HISTSIZE
          # declare var
          declare -r logdir="/var/log"
          echo $logdir
          # script to print first few and last few lines
          bashshell $ vi headntail.sh
          bashshell $ cat headntail.sh
          #!/bin/bash
          filename="/etc/passwd"
          echo "Number of lines:"
          wc -l $filename
          echo "####################"V
          echo "first 5 lines:"
          head -n 5 $filename


          echo "$$$$$$$$$$$$$$$$$$$$$$$$"
          echo "last 7 lines:"
          tail -n 7 $filename
          
          # execute the above script
          bashshell $ chmod +x headntail.sh
          bashshell $ ./headntail.sh
          
# Getting User Input
          read name
          echo $name
          bashshell $ read -p "Enter IP address " ip
          Enter IP address 10.10.10.10
          bashshell $ echo $ip
          10.10.10.10
          ping -c 1 $ip
          # script to block ip
          vi block_ip.sh
          #!/bin/bash
          read -p "enter ip addr of domain to block : " ip
          iptables -I INPUT -s $ip -j DROP
          echo "packets from ip address $ip will be dropped"
          
          #set the exec mode 
          chmod +x block_ip.sh
          # execute the script
          ./block_ip.sh
          
          # enter password without showing on terminal
          read -s -p "enter the pwd: " pwd
          echo $pwd
          
          
### defining a variable: variable_name=value
### variable names should start with a letter or underscore and can contain letters, digits and underscore
          os="Kali Linux"
          version=10
 
### referencing the value of a variable (getting the variable value): $variable_name
          echo $os
          echo $version
 
### defining a read-only variable (constant)
          declare -r temperature=100
 
### removing (unsetting) a variable
          unset version
 
### listing all environment variables
          env
          printenv
 
### searching for an environment variable
          printenv PATH
          env | grep -i path
 
### creating new environment variables for the user: in ~/.bashrc add export MYVAR=”value” 
          export IP="80.0.0.1"
 
### changing the PATH
          export PATH=$PATH:~/scripts     # in ~/.bashrc
 
### getting user input
          read MY_VAR
          echo $MY_VAR
 
### displaying a message
          read -p "Enter the IP address: " ip
          ping -c 1 $ip
 

 
          
# Special Vars and Positional argument
<img width="715" alt="image" src="https://user-images.githubusercontent.com/75510135/129999093-5020af4f-b2aa-49fb-bd73-d18dd140595f.png">

```
        #!/bin/bash
        echo "\$0 is $0"
        echo "\$1 is $1"
        echo "\$2 is $2"
        echo "\$3 is $3"
        echo "\$* is $*"
        echo "\$# is $#"
```
    - Move to the script's direcotory and run it as: ./script_name.sh Ubuntu CentOS "Kali Linux" "Windows 10"

```
        #!/bin/bash
        echo "Displaying the contents of $1 ..."
        sleep 2
        cat $1
        echo 
        echo "Compressing $1 ..."
        sleep 2
        tar -cjvf "$1.tar.gz" $1
```
- Move to the script's directory and run it as: ./script_name.sh filename or: sudo ./script_name.sh /etc/passwd

```
        #!/bin/bash
        echo "Dropping packets from $1"
        iptables -I INPUT -s $1 -j DROP

        # Move to the script's directory and run it as: sudo ./script_name.sh IP_ADDRESS
```

# if , elseif , else statement
<img width="311" alt="image" src="https://user-images.githubusercontent.com/75510135/130001155-a2d6c279-aeb3-46f0-8a93-a08324f66d38.png">
```
# for all test conditions
$ man test
```

<img width="212" alt="image" src="https://user-images.githubusercontent.com/75510135/130001844-cd0c9792-6ce9-4a82-bc53-5fa138a12ce2.png">
<img width="242" alt="image" src="https://user-images.githubusercontent.com/75510135/130001882-8d4d9237-567c-4f62-9200-23ca07052d4b.png">
<img width="539" alt="image" src="https://user-images.githubusercontent.com/75510135/130002024-a519d77e-67a4-41ef-a1a7-31f00b395d3d.png">
<img width="532" alt="image" src="https://user-images.githubusercontent.com/75510135/130002222-710cb2f9-5bd9-493f-93a6-d985ecb65842.png">

<img width="242" alt="image" src="https://user-images.githubusercontent.com/75510135/130001882-8d4d9237-567c-4f62-9200-23ca07052d4b.png">

## testing condition for numbers
<img width="498" alt="image" src="https://user-images.githubusercontent.com/75510135/130002337-d4a8db4d-fef5-4cea-8804-5edc7158c134.png">
<img width="497" alt="image" src="https://user-images.githubusercontent.com/75510135/130002794-18b63483-6d5c-49ad-a659-b9b86022951b.png">

<img width="242" alt="image" src="https://user-images.githubusercontent.com/75510135/130001882-8d4d9237-567c-4f62-9200-23ca07052d4b.png">
## multiple conditions
<img width="545" alt="image" src="https://user-images.githubusercontent.com/75510135/130003029-d6883e3f-8e05-4743-ad89-63f81b1ab363.png">

# Coding - If...Elif...Else Statements
    # if [ some_condition_is_true ]
    # then
    #   //execute this code
    # elif [ some_other_condition_is_true ]
    # then
    #   //execute_this_code
    # else
    #   //execute_this_code
    # fi
    ## Examples:
``` 
        i=1
        if [[ $i -lt 10 ]]
        then
           echo "i is less than 10."
        fi
```
#################
```
        i=100
        if [[ $i -lt 10 ]]
        then
           echo "i is less than 10."
        else
           echo "i is greater than or equal to 10."
        fi
```
################
```
        i=10
        if [[ $i -lt 10 ]]
        then
           echo "i is less than 10."
        elif [[ $i -eq 10 ]]
        then
           echo "i is 10"
        else
           echo "i is greater than or equal to 10."
        fi
```
################
### TESTING CONDITIONS => man test ###
 
      ### For numbers (integers) ###
      # -eq   equal to
      # -ne   not equal to
      # -lt   less than
      # -le   less than or equal to
      # -gt   greater than
      # -ge   greater than or equal to
 
### For files:
      # -s    file exists and is not empty
      # -f    file exists and is not a directory
      # -d    directory exists
      # -x    file is executable by the user
      # -w    file is writable by the user
      # -r    file is readable by the user
 
### For Strings
      # =     the equality operator for strings if using single square brackets [ ]
      # ==    the equality operator for strings if using double square brackets [[ ]]
      # !=    the inequality operator for strings
      # -n $str   str is nonzero length
      # -z $str   str is zero length

      # &&  => the logical and operator
      # ||  => the logical or operator
# command substitution
```
        users="$(who)"
        u="`who`"
        ps -ef | grep bash
        output="$(ps -ef | grep bash)"
        date +%F
        date +%F_%H%M
        tar -czvf etc.tar.gz /etc/
        tar -czvf etc-$(date +%F_%H%M).tar.gz /etc/
```
# compare strings
```
        #!/bin/bash
        read -p "String1: " str1
        read -p "String2: " str2

        # if with single square brackets and single =
        if [ "$str1" = "$str2" ]	 

        then
                echo "The strings are equal."
        else
                echo "The strings are NOT equal."
        fi

        # if with double square brackets and ==
        if [[ $str1 == $str2 ]] 
        then
                echo "The strings are equal."
        else
                echo "The strings are not equal."
        fi

        if [[ "$str1" != "$str2" ]];then  
                echo "The strings are not equal."
        fi

```
- find a string example
<img width="500" alt="image" src="https://user-images.githubusercontent.com/75510135/130004769-e4812157-74e8-4137-a1df-80d6e85d2aa8.png">
- check the len of the string example

<img width="383" alt="image" src="https://user-images.githubusercontent.com/75510135/130004970-4e05f765-d9fd-47e8-9567-ceacdfaffbc1.png">
<img width="408" alt="image" src="https://user-images.githubusercontent.com/75510135/130005017-218fb99a-375e-400f-a810-fa4f6d5ad7d4.png">

# test network connection
```
           #!/bin/bash
           output="$(ping -c 3 $1)" 
           #echo "$output"

           if [[ $output == *"100% packet loss"* ]]
           then
                   echo "The network connection to $1 is not working."
           else
                   echo "The network connection to $1 is working"
           fi


           # Run the script as: ./script_name.sh 8.8.8.8
```

# For...loop
<img width="817" alt="image" src="https://user-images.githubusercontent.com/75510135/130008403-edcf141f-8277-4770-a4d4-2cbdfc272ad2.png">
<img width="354" alt="image" src="https://user-images.githubusercontent.com/75510135/130008593-263366b7-f5cb-4a49-b7a8-2dd87809e1a4.png">
<img width="502" alt="image" src="https://user-images.githubusercontent.com/75510135/130008653-d8df413f-206c-4487-8541-313d8a60ec4b.png">
<img width="350" alt="image" src="https://user-images.githubusercontent.com/75510135/130008698-05bda8f0-a888-424b-8ec6-1c5f2682942c.png">
<img width="329" alt="image" src="https://user-images.githubusercontent.com/75510135/130008733-348690e4-f31a-46bf-b609-886517e156c5.png">
<img width="541" alt="image" src="https://user-images.githubusercontent.com/75510135/130008836-f507f687-9671-415e-a1af-445ada211450.png">
<img width="499" alt="image" src="https://user-images.githubusercontent.com/75510135/130008971-298d75af-fdb4-4828-8de4-7f9973275d32.png">
<img width="347" alt="image" src="https://user-images.githubusercontent.com/75510135/130009124-577bf6c4-344c-446e-8e55-63d8c915e68e.png">

# while loop
<img width="807" alt="image" src="https://user-images.githubusercontent.com/75510135/130009188-27aaf15b-916a-418f-a136-ec6e9d9c4b55.png">
<img width="290" alt="image" src="https://user-images.githubusercontent.com/75510135/130009471-5d429193-7761-4b43-ad0b-e3ea434c3355.png">
<img width="519" alt="image" src="https://user-images.githubusercontent.com/75510135/130009638-c7c7629e-9d0e-446f-8518-e18b51eb8e2e.png">
<img width="481" alt="image" src="https://user-images.githubusercontent.com/75510135/130009849-d1298796-5eb1-45ca-a6f4-ea5aedeaad7d.png">
<img width="551" alt="image" src="https://user-images.githubusercontent.com/75510135/130010044-883d368c-018d-4b9b-99e6-98890ccbe7b7.png">
# Case statement
<img width="191" alt="image" src="https://user-images.githubusercontent.com/75510135/130010235-5de36829-0e31-4339-8364-8651b1848909.png">
<img width="489" alt="image" src="https://user-images.githubusercontent.com/75510135/130010950-fd0c7799-95c3-4a49-a465-1a1a62fb064e.png">

