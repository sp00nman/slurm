## slurm-tips
> Collection of `slurm-tips` & best practices

###############################################################################################################
### WARNING: NONE OF THE COMMANDS HAVE BEEN TESTED YET AND MAY CAUSE SERIOUS HARM TO YOUR SYSTEM, USE WITH CARE. #
###############################################################################################################

* Usage of ENVIRONMENT VARIABLES in the context of job sumissions
* How to monitor peak memory of a job?


### Usage of ENVIRONMENT VARIABLES
+ [Online tutorial/explanation/introduciton](https://wiki.archlinux.org/index.php/Environment_variables)
+ "An environment variable is a named object that contains data used by one or more applications. In simple terms, it is a variable with a name and a value. The value of an environmental variable can for example be the location of all executable files in the file system, the default editor that should be used, or the system locale settings. Users new to Linux may often find this way of managing settings a bit unmanageable. However, environment variables provide a simple way to share configuration settings between multiple applications and processes in Linux."

Examples:

```
export NGS_GATK="/path/to/gatk/executables"
echo $NGS_GATK
```

Permanetly add environment variables to your shell:

```
echo "export NGS_GATK=\"/path/to/gatk/executables \" " >>~/.bashrc
```
Usefull environment variables:
 
```
echo $PATH
echo $TMPDIR
echo $PWD
echo $HOME
echo $USER
```
 
Default ```$TMPDIR``` which is set to /tmp can be quickly filled up depending on size; it's recommended to set TMPDIR to eg. /scratch/users/$USER/tmp

Certain modules set environment variables. ```module help module_name``` gives an overview of the environment variables set when loading the module.
 
 
 ### How to monitor peak memory of a job
+ ```acct --parsable --long``` check for MaxRSS 
