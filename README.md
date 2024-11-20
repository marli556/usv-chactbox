# usv-chactbox

Guide For AI Installation 

Something to know ahead of time is most things in this guide are referenced here. 

- We will be using Manual Installation since I found is much better for open AI since it is much more flexible when it comes to installing modules on 
  the AI Program I would highly recommend using this version of the AI project  

- In case you already have an installation for docker that is up and running with PrivateGPT I would only recommend just running these two commands. 
  First by running this command line ollama run llama3.1 as it is all that is needed to update to llama.  

And secondly the 

docker-compose --profile ollama-cuda up command within docker to create an image file to cuda generation Only use this if you have a Graphics card. 

 

Step 1: Installing Requirements  -  

You will need these installed on your computer before we get started on getting Ollama. 

 

PYENV 

- Windows Installation Steps 

- In Powershell run  

Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1" 

- Restart PowerShell 

- You should be able to check if it has been installed by running  

pyenv --version 

 

- Mac 

- On HomeBrew Run 

brew update 

brew install pyenv 

- Update the app once completed  

brew install pyenv --head 

 

Private GPT 

- Clone the PrivateGPT repository here through this command line 

git clone https://github.com/zylon-ai/private-gpt 

 

Python 3.11 
- Within the PrivateGPT Folder Python will need to be installed using PYENV through this command line 

pyenv install 3.11 

pyenv local 3.11 

- Run this command line after installing python. It will install pipx which is needed for Poetry Installation 

py -m pip install --user pipx 

 

Just In case this message comes up  

WARNING: The script pipx.exe is installed in `<USER folder>\AppData\Roaming\Python\Python3x\Scripts` which is not on PATH 

- Run the command prompt to that exact location and run this command 

.\pipx.exe ensurepath 

 

Poetry 
- Lastly to install Poetry run this command  

pipx install poetry 

Make 
- If you have windows and have chocolatey installed run this command line  

choco install make 

- On Mac if you have homebrew installed run this instead 

brew install make 

 

Step 2: Installing Ollama  

- You will need to download Ollama from its website here and run the program to install onto your computer. This will take up a bit of space from the 
  computer. 

- After installing the program go into the private gpt folder again and run this command 

ollama pull llama3.1 

- After this is done close the app either through a task manager or the ollama icon

- To open llama make sure you are in the privategpt directory and through command line ollama serve  

- Keep the command prompt running in the background and open a new one within the privategpt folder.   

- If this message pops up it is because ollama is still running in the background and needs to be shut 
  down.

- Create a makefile within the privategpt folder by creating a txt file and removing its extension at the 
  end of the filename. And then write this contained in it

- Run the command line:   
poetry install --extras "ui llms-llama-cpp embeddings-ollama vector-stores-qdrant embeddings-huggingface" 

- And finally after running the command line  

make run 

- It should be able to open up localhost:8001 and have the program up and running
- 
- Congrats privategpt should now be up and running any extra questions or troubleshooting you should be able to message me on teams and can possibly update the guide for any troubleshooting 
