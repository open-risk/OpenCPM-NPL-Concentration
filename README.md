## OpenCPM Demo (Model Server)

This Demo Model Server is a python/flask based server for exploring a simplified version of the Open Risk Models API.


### Getting started


#### Dependencies

The server is based on the python flask framework. It has the following additional dependencies

- pip install requests
- pip install json
- pip install numpy
- pip install pandas
- pip install rdflib
- pip install rdflib-jsonld

#### Install a model library

This demo is using a library of concentration risk measures. You can get a copy of the
latest version here https://github.com/open-risk/concentration_library

You only need to include the file concentration_library.py (for convenience we include it in this demo)

The model metadata are stored in one rdf file per model (HHI_Index.rdf etc)

#### Startup the model server:
   	
- Simply run the server script from the console (python model_server.py)
- The model server should startup on port http://127.0.0.1:5000/
- You can check the server is live by pointing your browser to the port (you will get an json-ld reply)
- or by using curl from the console (curl -v http://127.0.0.1:5000/)
  
  
#### Model Server API endpoints: 

The general structure of the simplified API is

- /
- /model_list
- /{model_name}

The model name endpoint responds to both GET / PUT http verbs. In the first instance
it returns model metadata. In the second instance it returns the model output

The model metadata are in JSON-LD format. This is human readable with any JSON editor