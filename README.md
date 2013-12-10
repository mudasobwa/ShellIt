ShellIt
=======

## Java Tricks

* Create a java classpath to be used with “-D” param in shell script:
 
  JARS_ARR=( \`find libs/ -name "*.jar"\` ) && JARS=$(printf ":%s" "${JARS_ARR[@]}")

## Ruby As Shell Utils

With options `-e`, `-n`, `-p`, perl can do what grep/awk/sed can, what about ruby?

Let's take the result of `ls -l` as input and process it with ruby

### grep with ruby
`\ls -l | ruby -ne 'print if /^d/'`

### awk with ruby
`\ls -l | ruby -ne 'puts split(/\s+/).last if /^d/'`

### sed with ruby
`\ls -l | ruby -pe 'gsub /.*\s+(\S+)$/, %q|\1|'`  
`\ls -l | ruby -pe 'gsub(/.*\s+(\S+)$/) {$1.capitalize}'`

— https://gist.github.com/ryenus/1518596
