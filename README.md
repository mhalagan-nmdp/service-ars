# service-ars
RESTful Service for Antigen Recognition Site Reduction

### Build
[![Build Status](https://travis-ci.org/nmdp-bioinformatics/service-ars.svg?branch=master)](https://travis-ci.org/nmdp-bioinformatics/service-ars)

### Docker Image
[![](https://images.microbadger.com/badges/image/nmdpbioinformatics/docker-ars.svg)](http://microbadger.com/images/nmdpbioinformatics/docker-ars "Get your own image badge on microbadger.com")[![](https://images.microbadger.com/badges/version/nmdpbioinformatics/docker-ars.svg)](http://microbadger.com/images/nmdpbioinformatics/docker-ars "Get your own version badge on microbadger.com")

Further documentation is available at [service-ars.readthedocs.io](http://service-ars.readthedocs.io/en/stable/index.html)

## Using service-ars

```bash
    
    # Do ARS reduction on a typing #
    curl http://localhost:3000/api/v1/redux?typing=A*01:01?dbversion=3.20

    # Do ARS reduction on multiple subjects # 
    curl --header "Content-type: application/json" --request POST 
    --data '{"arsFile":"hla_nom_g.txt","dbversion":"3.20.0","arsType":"G",
    "Subjects":[{"SubjectID":1,"typing":["A*01:01+A*01:02","B*08:01+B*07:02","C*07:01+C*07:01"]},
    {"SubjectID":1,"typing":["A*01:01+A*01:02","B*08:01+B*07:02","C*07:01+C*07:01"]}]}' 
    http://localhost:3000/api/v1/reduxSubjects
    
    # Get all the ARS data #
    curl http://localhost:3000/api/v1/ars
    
    # Get all the ARS data for IMGTDB 3.20.0 #
    curl http://localhost:3000/api/v1/ars?dbversion=3.20.0
```

### Tools

ex. config.json
```bash
{  
   "arsFile":"hla_nom_g.txt",
   "dbversion":"3.20.0",
   "arsUrl":"http://localhost:3000",
   "macUrl":"http://devgenomicservices1.nmdp.org/mac",
   "arsType":"g"
}
```


#### Java
```bash
hml-typing-resolution

arguments:
   -a, --about  display about message [optional]
   -h, --help  display help message [optional]
   -i, --input-file [class java.io.File]  input file, default stdin [optional]
   -j, --json-file [class java.io.File]  json configuration file [required]
   -x, --xml  print output as xml [optional]
   -s, --json  print output as json [optional]
   -c, --csv  print output as csv [optional]

```


```bash
hml-typing-resolution -j config.json -x < inputFile.xml > outputFile.xml
hml-typing-resolution -j config.json -x -i inputFile.xml > outputFile.xml
hml-typing-resolution -j config.json -c -i inputFile.xml > outputFile.csv
hml-typing-resolution -j config.json -s -i inputFile.xml > outputFile.json
```

#### Perl
```bash
./ars-resolution [--config] [--verbos] [--help]
    -c/--config
    -v/--verbose
    -h/--help
```


```bash
ars-resolution -c config.json < testInput.csv > testOutput.csv
```


## Installing

```bash
./build.sh
```

### Required Software

 * JDK 1.7 or later, http://openjdk.java.net
 * Apache Maven 3.2.5 or later, http://maven.apache.org
 * Git, http://git.org
 * perl 5.18 or later, http://perl.org

### Perl Modules

 * YAML 
 * Plack 
 * Plack::Handler::Starman 
 * Template 
 * JSON 
 * Getopt::Long 
 * LWP::UserAgent 
 * Test::More Dancer


### Related Pages

 * [docker-ars](https://github.com/nmdp-bioinformatics/docker-ars)
 * [dockerhub](https://hub.docker.com/r/nmdpbioinformatics/docker-ars/)


