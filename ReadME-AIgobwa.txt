Things that need to be changed

When staring out in powershell-
1) go to github and fork teh TemplateCalculator2050 to your github repo
2) once that is done download the files to your machine
3) open powershell and run the 'Push-Location' then add the path of the downloaded TemplateCalculator2050 file
4) open powershell and run as administrator then run the function Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine then click Y to accept,
Run it again then click A, close powershell then open powershell normally.
5) Run the .\scripts\convert_spreadsheet.ps1 path\to\spreadsheet with the directory to the TemplateCalculator2050.

############################################
When making the changes to the tables, ensure to highlight from WebOutputs!C31:N68 and save it at the top left column name to be outputs_summary_table
The same should be done for the control sheet where you highlight for the different sectors and highlight as follows Control!B70:C81 to output.lever.group1

Runtime = 6hrs 55min minimum
##############################
The errors that we encountered as pointed by DR. Chris were as follows
The existence of "INDEX(0,foo,bar)" and  "@0" are the main cause of the _xlfn.SINGLE errors. When the INDEX formula has the first value as 0 then the whole formula 
breaks and as such causes the _xlfn.SINGLE error to appear.

####
Running the debug file, run the Set-ExecutionPolicy - Unrestricted in the powershell where the unrestrictions help in running the debugger, it may require that you always hit run wuth each iteration

#############################
DEPLOYMENT

Once acquired the server from the facility working on ensure that the server has a public IP (starts with 156 for strath, a private one is 192) the next step is to ensure that the domain name and
the server have been linked.
Afterwrds in the IP given install the necessary files such as the build-essentials for ubuntu and docker, as well as apache2
Also install caddy (https://caddyserver.com/docs/install) install the stable release as indicated