Filter content in Linux

filtering for information

filtering is selecting data that match a certain condition. For example, if you had a virus in you system that only affected the .txt files, you could use filtering to find these files quickly. Filtering allows you to search based on specific criteria, such as file extensions or a string of text.

grep:
    The grep command searches a specified file and returns all lines in the file containing a specified string. The grep command commonly takes two arguments: a specific string to search for and a specific file to search through.

    For example, entering: grep OS updates.txt returns all lines containing os in the updates.txt file. In this example, os is teh specified string to search for, and updates.txt is the specific file to search through.

Piping
    The pipe command is accessed using the pipe character (|). piping sends the standard output of one command as standard input to another command for further processing. As a reminder, standard output is the information returned by the OS through the shell, and standard input is information received by the os via the command line.

    The pipe character (|) is located in various places on the keyboard. On many keyboards, it's located on the same key as the backslash character (\). On some keyboards, the | can look different and have a small space through the middle of the line. If you cant find the pipe, search online for its locations on your particular keyboard.

    when used with grep the pip can help you find directories and files containing a specific word in thei names. For example, ls /home/analyst/reports | grep users , returns the file and diractory names in the reports dir that contains users. Before the pipe, ls indicates to list the names of the files and dirs in reports . then it sends this output to the command after the pipe. In this case, grep users returns all of the file or directory names containing users from the input it received.

    note: piping is a general form of redirection in linux and can be used for multiple tasks other than filtering. you can think of piping as a general tool that you can use whenever you want the output of one command to become the input of another command.

find
    the find command searches for dirs and files that meet specified criteria. There's a wide range of criteria that can be specified with find. For example you can search for files and dir that:

        contain a specific string in the name

        are a certain size, or 

        were last modified within a certain time frame

    when using find, the first arg after find indicates where to start searching. For example, entering find /home/analyst/projects searchs for everything starting at the projects dir.

    after the first arg, you need to indicate your criteria for the search. If you dont indlufe a specific search criteria with you second argument, your search will likely return a lot of directories and files.

    specifying criteria involes options. Options modify the behavior of a command and commonly being with a hyphen (-).

-name and -inname
    one key criteria analysts might use with find is to fin file or dir names that contain a specific string. The specific string you're searching for must be entered in quotes after the -name or -inname options. The difference between these two options is that -name is case-sensitive, and -inname is not.

    For example, you might want to find all files in the projects directory that contain the word “log” in the file name. To do this, you’d enter find /home/analyst/projects -name "*log*". You could also enter find /home/analyst/projects -iname "*log*".

    In these examples, the output would be all files in the projects directory that contain log surrounded by zero or more characters. The "*log*" portion of the command is the search criteria that indicates to search for the string “log”. When -name is the option, files with names that include Log or LOG, for example, wouldn’t be returned because this option is case-sensitive. However, they would be returned when -iname is the option.

    Note: An asterisk (*) is used as a wildcard to represent zero or more unknown characters.

-mtime
    Security analysts might also use find to find files or directories last modified within a certain time frame. The -mtime option can be used for this search. For example, entering find /home/analyst/projects -mtime -3 returns all files and directories in the projects directory that have been modified within the past three days.

    The -mtime option search is based on days, so entering -mtime +1 indicates all files or directories last modified more than one day ago, and entering -mtime -1 indicates all files or directories last modified less than one day ago. 

    Note: The option -mmin can be used instead of -mtime if you want to base the search on minutes rather than days.

Key takeaways
    Filtering for information using Linux commands is an important skill for security analysts so that they can customize data to fit their needs. Three key Linux commands for this are grep, piping (|), and find. These commands can be used to navigate and filter for information in the file system.
