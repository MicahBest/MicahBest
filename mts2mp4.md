# Convert `.MTS` Files to `.mp4`

The following Bash script converts all `.MTS` files in the current directory to `.mp4` format using `ffmpeg`. If the `.mp4` version of a file already exists, the script will skip the conversion for that file.

## Script

```bash
for FILE in *.MTS; do 
    if [ ! -f "${FILE%%.MTS}.mp4" ]; then 
        ffmpeg -i "$FILE" -threads 4 -f mp4 "${FILE%%.MTS}.mp4"
    fi
done
```

