# github-extender
a github extender which will create the start and stop of the github cli actions for the repositories and will make it easier for the git actions. just a username and the number of the reporsitories to the user and it will make all the git clone clients for the user. 

```
#! /usr/bin/bash 
# Universitat Potsdam
# Author Gaurav Sablok
# date: 2024-1-23
# generating the html based style tags for the github
# generate the auto clone links for the github cli
# configured for both the linux client as well as the docker instances 
# implementing a indexed array to make the directory iteration faster
# generating the indexed array and a C loop for the faster git iteration
read -r -p "please provide the github number:" number
read -r -p "please provide the username:" username
echo "storing the variable number for an indexed array"
   for ((i=1; i<="${number}"; i++))
        do 
            echo "https://github.com/"${username}"?page="${i}"&tab=repositories" >> gitlinks.txt
        done
    echo "making the feed client code for the linux administration"
printf "%s\n" "thank you for using the git array indexing" 
echo "getting all the HTML dump for the gitlinks"
cat gitlinks.txt | while read line; \
    do 
        wget -F $line > $line.json.txt;
    done
echo "all the gitlinks for this username and the repository have been dumped"
echo "you can use the json shell based feed parser to get the git clone code"
for i in $(ls -l *.json.txt);
do 
    $(grep "itemprop" "${i}" | grep "href" | \
        cut -f 2 -d "=" | sed s/itemprop//g | sed s/\"//g);
do
  echo https://github.com/$i;
done
```
Gaurav Sablok \
Academic Staff Member \
Bioinformatics \
Institute for Biochemistry and Biology \
University of Potsdam \
Potsdam,Germany
