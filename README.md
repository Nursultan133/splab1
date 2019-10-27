#splab1

#VARIANT-6

cut -d '"' -f1,3 log.txt | cut -d ' ' -f4,8 | grep -v '-' | sort | sed -e 's/[[]//' | cut -d ':' -f1,4 | cut -c 1-11,15-100 | awk '{arr[$1]+=$2} END {for (i in arr) {print i,arr[i]}}'sort | uniq | sort -k 2 -n -r | head -5 | cut -d ' ' -f1,2 | awk '{ printf $1 | date  +'%Y-%m-%d' }'
