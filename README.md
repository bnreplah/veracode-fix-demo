# veracode-fix-demo

This repo houses a veracode fix demo script that alllows you to use veracode fix easier.


Run without any parameters to use the default results.json file
It will parse the results.json and look for found relative paths
You will be prompted which file you want to run fix on in a menu
You can select the file to attempt to apply a fix to, and then select the fix
When you are done, you can tell the program you don't want to continue and it will close
Each itteration, the program will ask if you want to attempt to apply a fix, if you say Y, or Yes, then it will take you to apply fixes
If you don't want to continue to apply fixes, respond to the prompt N or No when asked if you want to apply fixes
If you want to override the results.json and generate a new one, pass an artifact path for the static pipeline scanner to analyze
If the results.json is named differently or in a different location specify that after the --results parameter

Usage:
- Get Help:
  --help
- Run A Pipeline Scan First, then veracode Fix against results.json:
  --artifact app/target/verademo.war
- Run veracode Fix against results in specified file:
  --results app/results.json
- Run a Pipeline Scan First and output to specified file, then run veracode Fix against the results file specified
  --artifact app/target/verdemo.war --results app/results.json
[Experimental] - Package the artifact before scanning it with the pipeline scan
  --outdir ./ --source verademo/ --type directory --trust --package
[Experimental] - Package the artifact, run a pipeline scan against the artifact, and generate fix recomendations from the results
  --outdir ./ --source verademo/ --type directory --trust --results results.json --package
[Experimental] - Install the Veracode Cli
  --install-cli <additional_args>
- Turn on debug"
  --debug <additional_args>
[Experimental] - Install Veracode CLI
  --install-cli <additional_args>
[Experimental] - Force Install Veracode CLI
  --force-install <additional_args>
[Experimental] - Force Install Veracode CLI Locally
  --force-install-local 
[Experimental] - Force Update Veracode CLI 
  --force-update <additional_args>

> Common issue:
>  - If you see the `exclusion error: zip: not a valid zip file` you may need to clean and remove the old packaged artifact and repackage
