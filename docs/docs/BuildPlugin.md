
Steps to build, upload and run unit tests for plugin:
-----------------------------------------------------

  1. Create a virtual environment and install required libraries(dvp, pytest, pytest-html & pytest-cov) using script `virtualEnvSetup.sh`.
    
  ```bash
    cd <complete path of project directory till `couchbase-plugin` directory>
    ./test/virtualEnvSetup.sh <virtual enviornment name>
For example:
    cd /Users/<your-user-name>/Desktop/Plugins/OpenSourceCouchbase/couchbase-plugin
    ./test/virtualEnvSetup.sh "MyLocalEnv"
```
    
  2.  Run this command to activate the virtual environment created in step 1:
   ```bash
    . test/MyLocalEnv/bin/activate
   ```

  3.  Build the source code. It generates the build with name `artifacts.json`:
```bash
    dvp build
```
    
   4. Upload the `artifacts.json` ( generated in step 3 ) on Delphix Engine:
```bash
    dvp upload -e <Delphix_Engine_Name> -u <username> --password <password>
```
   5. Unit test run: Make sure to build the source code( using `dvp build` ) before running unit tests
  ```bash
     pytest test/
```

### <a id="run_unit_test_case"></a>Download plugin logs
#### Plugin Logs:
Download the plugin logs using below command:

```dvp download-logs -c plugin_config.yml -e <Delphix_Engine_Name> -u admin --password <password>```

#### Unit test logs: 
##### SummaryReport:
A report with name `Report.html` gets generated in `test` directory which contains the summary of test passed vs failed. If any test case fails then complete stack trace can be seen in that test case section.
##### Module wise coverage report:
There is a report folder `CodeCoverage`(can change the folder name in config file `pytest.ini`) generated in `test` directory, which contains html files. These files help in source code coverage visualization, in which we can see statements processed and missed in each module of source code.
