# Useful RST commands 

## Linux

Merge all rst into single file:

```
find . -name "*.rst" -type f | sort -V | xargs -I{} sh -c 'echo "\n\n.. _$(echo {} | sed "s/[^a-zA-Z0-9_-]/_/g"):\n.. {}\n====================\n" >> merged.rst; cat "{}" >> merged.rst'
