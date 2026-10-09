# Useful RST commands 

## Linux

Merge all rst into single file:

```
find . -name "*.rst" -type f | sort -V | xargs -I{} sh -c 'echo "\n\n.. _$(echo {} | sed "s/[^a-zA-Z0-9_-]/_/g"):\n.. {}\n====================\n" >> merged.rst; cat "{}" >> merged.rst'
```

Strip all digits from all rst files:

```
find . -type f -name "*.rst" -exec bash -c 'mv "$0" "$(dirname "$0")/$(basename "$0" | sed -E "s/^[0-9]+_//")"' {} \;
```

Compress files via OPTIPNG
```
find . -type f -iname "*.PNG" -exec optipng -o7 {} +
```
