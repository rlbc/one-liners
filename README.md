# one-liners
My bioinformatics one liners.

## tsv to csv
`sed 's/\t/,/g' input_file > output_file`

`sed -i 's/\t/,/g' input_file` (inline)

## grep multiple entries
`grep 'word1\|word2' file`

## R change ENSGXYZ.X to ENSGXYZ
`sub('\\.[0-9]*$', '', item)`

## fasta files
(https://www.biostars.org/p/17680/)
Add something to the end of headers
`sed 's/>.*/&WHATEVERYOUWANT/' file.fa > outfile.fa`

Extract IDs
`grep -o -E "^>\w+" file.fasta | tr -d ">"`

Linearize sequence and extract IDs
`while read line;do if [ "${line:0:1}" == ">" ]; then echo -e "\n"$line; else echo $line | tr -d '\n' ; fi; done < input.fasta > output.fasta`
`grep -A1 'Q15049' output.fasta`
Alternative:
`awk '{if(NR==1) {print $0} else {if($0 ~ /^>/) {print "\n"$0} else {printf $0}}}' input.fasta > output.fasta`
