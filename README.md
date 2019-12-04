# edam_onto

# Possibly can use for phenotype catalog in place of maelstrom
    - currently demoed in `EDAM Browser` VM
    - nav to /home/administrator/edam-browser and run python start-[something or other about the standalone browser]
    - will load to http://[VM IP]:20080

# Customizing the ontology
    - make changes to edam_extended.biotools.min.json file in this repo. 
    - clone repo to `media` directory in the VM edam-ontology directory
    - mv edam_extended out of cloned repo and into parent directory (`media`)
    - make changes to `index.html` in `edam-browser` directory to effect change in launched portal.

# Possible design
    - each phenotype described in hierachy as expected, with URI being link to phenotype page created as part of an
    
    application (likey React) in which I believe the browser application could be embedded/encapsulated by. 
    
    This would further link to study/dataset/etc. description pages in dss.niagads or wherever else. 

# still to figure out
    - how to change text of root node to not be `EDAM` (not in edam_extended.json onto schema)

# Inclusion in node application
- clone edam-browser (or whatever the name is that holds the browser app files) into the root of nodejs (or wherever)
- import {PythonShell} from 'python-shell' (npm install beforehand)
- find directions for using Babel to compile for ES6 (wont have to do if using in react-app?)
	- be sure to include build script in package.json and call build in "start" script before running main app
- python-shell runs python3, so have to change start-edam-browser-whatever.py start script to reflect this
        import http.server
        import socketserver
        Handler = http.server.SimpleHTTPRequestHandler

        httpd = socketserver.TCPServer(("", PORT), Handler)

- run script and vis browser will be at localhost:20080/edam-browser
