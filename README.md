# Image CURLs

Simple bash script to download multiple image files that are indexed by number. Also supports the ability to download images through a list of urls stored in a file.

## Use Cases and Arguments

### Downloading from a Numbered URL

For example, we want to download images from `https://chpic.su/save/file/stickers/PeachAndGoma/PeachAndGoma_001/` to `010`. 

To do this, we would run the following command: 

`./imgcurls -u https://chpic.su/save/file/stickers/PeachAndGoma/PeachAndGoma_ -v / -s 1 -e 11 -l 3 -o output-dir/image- -p .png`

**Command line arguments**
```
-u      URL prefix (before number)
-v      URL suffix [optional]
-s      start number
-e      end number
-l      length/width of number (pad with 0s) [optional]
-o      output prefix (including directories relative to script)
-p      output suffix [optional]
```

### Downloading from a list of URLs

For example, we have a text file (`links.txt`) with a list of URLs.

To download all the URLs listed in the file, we would do the following:

`./imgcurls -j ./links.txt -o $DESKTOP/pictures/image- -p .webp -s 1`

**Command line arguments**
```
-j      file to read from
-o      output prefix (including directories relative to script)
-p      output suffix [optional]
-s      start for numbering [optional default=0]
```

## Troubleshooting

* Sometimes URLs can contain required trailing slashes; check for this
* Make sure files contain LF (\n) line endings instead of Windows-style CRLF (\r\n) or Mac CR (\r) line ending styles
