# one-liners
My bioinformatics one liners.

## tsv to csv
`sed 's/\t/,/g' input_file > output_file`

`sed -i 's/\t/,/g' input_file` (inline)

## grep multiple entries
`grep 'word1\|word2' file`
