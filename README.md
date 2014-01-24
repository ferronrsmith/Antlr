#Antlr Experiments
**Goal:** To learn how to process formal languages using the Java library Antrl

## Setup and install
On linux and Mac systems copy the `antlr-4.0-complete.jar` file to your `/usr/local/lib` directory. *Alternatively*: download it from <http://www.antlr.org/download.html>.

Once you have the jar in your usr directory add the following to your `.bash_profile`

    export CLASSPATH=".:/usr/local/lib/antlr-4.0-complete.jar:$CLASSPATH"

To test if installed properly from the command line run:

    java -jar /usr/local/lib/antlr-4.0-complete.jar

You should get some sort of help doc:

    ANTLR Parser Generator  Version 4.0
    -o ___              specify output directory where all output is generated
    -lib ___            specify location of grammars, tokens files
    ...

It would be wise to create the aliases:

    alias antlr='java -jar /usr/local/lib/antlr-4.0-complete.jar'
    alias grun='java org.antlr.v4.runtime.misc.TestRig'

You may see else where `antlr4` being used instead of `antlr`, I have only used version 4 so I leave that off. The second one will be used for testing on from the command line.

If you are on windows you are on your own. But basically you need to let Java know where you have the libary installed. for more info go to: <http://www.antlr.org/>.

##CSV (Comma Seperated Value)

In this exercise we are going to read in a csv file into a Java map. The grammar is defined in `CSV/CSV.g4` the listeners are the code required to load in the file are in `CSV/LoadCSV.java`.

To run enter the followng commands:

    cd CSV/
    antlr CSV.g4
    javac CSV*.java LoadCSV.java
    java LoadCSV test.csv

After enter that last command you should the following output:

    [{Details=Mid Bonus, Month=June, Amount="$2,000"}, {Details=, Month=January, Amount="""zippo"""}, {Details=Total Bonuses, Month="", Amount="$5,000"}]

Success!

## JSON to XML

    cd CSV/
    antlr4 JSON.g4
    javac JSON*.java
    java JSON2XML t.json

