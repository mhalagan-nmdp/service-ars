RESTful Calls
================================

Antigen Recognition Site (ARS)
------------------------
 --hml
	* HML file
	* Required parameter
 --output
	* Output directory
	* Required parameter
 --imgtdir
	* Location of where the BLAST IMGT database is located
	* Default location is /opt/html on the docker container
 --imgt
	* IMGT database version
	* Default is 3200
 --report
	* Binary flag for generating HTML validation report
	* default is 1

ARS Groups
------------------------
.. code-block:: shell

	./nextflow run nmdp-bioinformatics/flow-blast-hml -with-docker \
		nmdpbioinformatics/docker-blast-hml \
		--hml test_file.hml --outdir /path/to/output/dir
	
After running this command you should find a report and a validated file in the ouput directory you specified.

ARS Reduction
------------------------
.. code-block:: shell

	./nextflow run nmdp-bioinformatics/flow-blast-hml -with-docker \
		nmdpbioinformatics/docker-blast-hml \
		--hml test_file.hml --outdir /path/to/output/dir
	
After running this command you should find a report and a validated file in the ouput directory you specified.
