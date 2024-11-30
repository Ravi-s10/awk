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
file2 - Kapi,25,ok | ayansh,28,ok | Ramesh,28,ok

# Comamnd
awk 'BEGIN {RS=":"} {print $1}' file1 
# Output
# apple
# mango
# banana

# Command
awk 'BEGIN {RS="|"} {print $1} ' file2

# Output 
# Kapi,25,ok
# ayansh,28,ok
# Ramehs,28,ok

# Command 
awk 'BEGIN {RS="|";FS=","} {print $2} ' file2
# Output
# 25
# 28
# 28

# Output Field seprator (ORS)

# Command 
awk 'BEGIN {FS=",";RS="|";OFS="+";ORS="#"} {print $1,$2}' file2

# Output 
Kapi+25# ayansh+28# Ramesh+28#

# Getting No of filed in each line (NF)

# Example
# Filed1  Filed2  Filed3
# Mango   Dog     fish   monkey - Record 1
# Banana  Cat     shark  python snake gorilla - Record 2
# Orange  Rat     - Record 3

# Command
awk '{print NF}' file

# Output
# 4
# 6
# 2

# No of record (NR)

# Command  taking example of above file

awk '{print NR }' file
 # Output 
# 1
# 2
# 3

# Regular Expressions in awk

# TO print a matching line

awk '/string/ {print $1}' file

# Match anything f.n . means sigle charcter
awk '/f.n/ {print $2}' file
awk '/$a/ {print $1}' file
awk '/Done$/ {print $4}' data
# Complete comamnd
awk '$0 ~ /fan/ {print $2}' file # $0 mean whole file and $1 means first filed
awk '$0 !~ /Done$/ {print $3} ' file

awk '/[A]ll/ {print $2}' file
awk '/^[A]ll/ ' file - nagation


# Arithmetic operation using awk
# Adding number of multiple fileds
awk  --profile 'BEGIN {ORS=" "} {sum+=$1;sum2+=$2;sum3+=$3;sum4+=4;sum5+=$5} END {print sum5 ;print sum4 ;print sum3;print sum2 ;print sum }' number.txt

# calculate average
 awk '{sum=sum+$1;count++ } END {print sum/count}' nuber2
