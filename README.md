# Awsome-Shell
some shell script to use and learn from it

## -h example

```bash
#!/bin/bash

# Display usage information and examples
display_help() {
  echo "Usage: $0 fromExt toExt"
  echo
  echo "Renames all files with the specified fromExt extension to have the specified toExt extension"
  echo
  echo "Examples:"
  echo "  $0 \".ts\" \".cs\"  # Renames all .ts files to .cs files"
  echo "  $0 \".js\" \".ts\"  # Renames all .js files to .ts files"
  echo "  $0 \".txt\" \".md\"  # Renames all .txt files to .md files"
}

# Check if the correct number of arguments was provided
if [ "$#" -ne 2 ]; then
  echo "Error: Invalid number of arguments" >&2
  display_help
  exit 1
fi

# Check if the -h or --help option was provided
if [ "$1" = "-h" ] || [ "$1" = "--help" ]; then
  display_help
  exit 0
fi
```

## batch_rename

```bash
# Assign the arguments to variables
fromExt=$1
toExt=$2

# Rename the files
for file in *"$fromExt"; do mv "$file" "${file%$fromExt}$toExt"; done
```

