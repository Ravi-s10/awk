# awk

# awk command usage
awk 'BEGIN { } { } END{ }' filename
# Example awk 'BEGIN {print "Start of the line"} {print $1} END {print "End of the line"}' file 
# Record and filed in awk  


Filed1  Filed2  Filed3
Mango   Dog     fish   - Record 1
Banana  Cat     shark  - Record 2
Orange  Rat     bear   - Record 3

# Deault Record seperator is newline and default filed seprator is space 
# print first filed
awk 'BEGIN {print "hello"} {print $1} END {print "Eod"} file

# How to use field seprator in awk
awk 'BEGIN {FS=","} {print $2} {print "EOD"}' filename

# How to create a awk script of command

awk --profile 'BEGIN {print "Start"} {print $2} END {print "bye"}' filename 

# Above command will genarte a awk file with above command



