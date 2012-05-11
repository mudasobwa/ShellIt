ShellIt
=======

* Create a java classpath to be used with “-D” param in shell script:
  JARS_ARR=( `find libs/ -name "*.jar"` ) && JARS=$(printf ":%s" "${JARS_ARR[@]}")