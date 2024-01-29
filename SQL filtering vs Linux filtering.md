SQL filtering vs Linux filtering

Accessing SQL

    to access SQL from Linux you need to type in a command for the version of SQL that you want to use. For example if you want to access SQLite you can enter the command sqlite3 in the command line.

    after this any commands typed in the command line with be directed to SQL instead of Linux commands.

Differences between Linux and SQL filtering

    although both linux and SQL allow you to filter through data, there are some differences that affect which one you should choose.

Structure

    SQL offers a lot more structure than Linux, which is more free-form and not as tidy

    for example if you wanted to access a log of employees log-in attemps, SQL would have each record separated into columns. Linux would print the data as a line of text without this organization. As a result, selecting a specific column to analyze would be easier and more efficient in SQL

    in terms of structure, SQL provides results that are more easily readable and that can be adjusted more quickly than when using Linux.

Joining tables

    some security-related decisions require information from different tables. SQL allows the analyst to join multiple tables together when returning data. Linux doesn't have the same functionality; it doesn't allow data to be connected to other information on your computer. This is more restrictive for an analyst going through security logs.

Best uses

    As a security analyst it's important to understand when you can use which tool. Although SQL has a more organized structure and allows you to join tables, this doesn't mean that there aren't situatuions that would require you to filiter data in Linux.

    A lot of data used in cybersecurity will be stored in a database format that works with SQL. However, other logs might be in a format that is not compatible with SQL. For instance, if the data is stored in a text file, you cannot search through it with SQL. In those cases, it is useful to know how to filter in Linux.
