ccd: Change current directory to subfolders

cd (fd --type d . | fzf)

Batch rename files in fish

for file in *.md
    mv -v -- "$file" (basename $file .md).txt 
end

-- postgres copy statement

\copy (select id from admin) to '/tmp/samsql/admin.csv' csv header;

feh command to move files to a folder on pressing enter
`feh --scale-down --auto-zoom -f removefiles.txt -A 'mv %F selected/%N'`

Random string generation

```js

function makeid(length) {
    var result           = '';
    var characters       = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';
    var charactersLength = characters.length;
    for ( var i = 0; i < length; i++ ) {
      result += characters.charAt(Math.floor(Math.random() * 
 charactersLength));
   }
   return result;
}
```
[credit](https://stackoverflow.com/a/1349426)


# Organize Imports

To automaitcally organize imports without using cli

```bash
npx organize-imports-cli tsconfig.json

prettier --write --single-quotes src

```

Use single quotes only if needed


# mysql dump to csv
`echo "select * from hotels_images" | mysql -u samyak -p hotel_images | sed 's/\t/,/g' > newdata.csv`

# add quotes around csv files
awk -F"'?,'?" -v OFS='","' '{$1=$1; gsub(/^.|$/,"\"")} 1' newdata.csv > hotels_images.csv
[credit](https://stackoverflow.com/a/36062929)

# Monolith cli
To download the page archive
`monolith -aIfMv`

# Get first n number of lines from a file

`sed -n -e '10,100p' input.txt > output.txt`

This will get lines from 10 to 100 of input.txt to output.txt

[credit](https://unix.stackexchange.com/a/138400)

# Youtube audio download with yt-dlp

```bash
yt-dlp --ignore-config -f "bestaudio/best" -ciw -o "%(title)s.%(ext)s" -v -
-extract-audio --audio-quality 0 --audio-format mp3 'https://www.youtube.com/watch?v=qCTMq7xvdXU'
```

# Aws dynamodb table items count
 aws dynamodb scan --table-name hotels --select "COUNT"

# Move n number of files
```
ls hotelImagesSplit/ | sort -n -k1.1,1.5 | head -n 10 | xargs -i mv hotelImagesSplit/{} split/
```

# Find duplicate urls from a file
cat links.txt | awk '/^\*/' | awk '_[$0]++'

# check for duplicate links


git diff | awk '/^\+\*/' | grep -Eo '(http|https)://[a-zA-Z0-9./?=_%:-]*' | grep -wof - test.txt

# find node_modules directory in current directory

fd --type directory -I -d 3 'node_modules'


