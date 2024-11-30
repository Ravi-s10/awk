# awk

# awk command usage
awk 'BEGIN { } { } END{ }' filename
# BEGIN and END block are optional
# Example awk 'BEGIN {print "Start of the line"} {print $1} END {print "End of the line"}' file 
# Record and filed in awk  


# Filed1  Filed2  Filed3
# Mango   Dog     fish   - Record 1
# Banana  Cat     shark  - Record 2
# Orange  Rat     bear   - Record 3

# Deault Record seperator is newline and default filed seprator is space 
# print first filed
awk 'BEGIN {print "hello"} {print $1} END {print "Eod"} file

# How to use field seprator in awk
awk 'BEGIN {FS=","} {print $2} {print "EOD"}' filename

# How to create a awk script of command

awk --profile 'BEGIN {print "Start"} {print $2} END {print "bye"}' filename 

# Above command will genarte a awk file with above command

# Output field seprator in awk (OFS)

awk 'BEGIN {FS="," ; OFS="-"} {print $2} END {print "ok"} ' filename 
# Record Seprator in awk (RS)

file1- apple 12 av : mango 20 nav : baanan 25 av
file2 - Kapil,25,ok | ayush,28,ok | ravi,28,ok

# Comamnd
awk 'BEGIN {RS=":"} {print $1}' file1 
# Output
apple
mango
banana

# Command
awk 'BEGIN {RS="|"} {print $1} ' file2

# Output 
Kapi,25,ok
ayansh,28,ok
Ramehs,28,ok

# Command 
awk 'BEGIN {RS="|";FS=","} {print $2} ' file2
# Output
25
28
28







