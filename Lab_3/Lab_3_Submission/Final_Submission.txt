if test -f "$1"; then
        echo "$1 exists."
else
        echo "$1 does not exists."
        exit
fi

i=0

while [[ $i -eq 0 ]]

do
echo "Enter a file you wish to execute: "
echo "count_lines, count_words, add_text, copy_and_exit"
read file
case $file in
        count_lines)
        echo "The number of lines in the file is: "
        wc -l $1
        ;;

        count_words)
        echo "These are the lines that Lorem, model, Ipsum and will are in: "
        echo "$(grep -n -w 'Lorem\| model\| Ipsum\| will' $1)"
        ;;

        add_text)
        echo "Input a sentence you would liek to add: "
        read input
        echo " $input" >> sample_text.txt
        ;;

        copy_and_exit)
        mkdir solution
        cp "sample_text.txt" solution
        i = 1
        ;;
        *)
        echo "Invalid input."
        ;;

esac
done
exit
