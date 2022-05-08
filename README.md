# Ansible-EmpireSuite
ansible roles to download and install empire (BC-Security),deathstar(byt3bl33der)  and starkiller (BC-Security)

**update** since the release of this play, the installer has been updated so it cannot be installed automatically anymore as there are yes or no prompts in the installation. this can probably be bypassed in ansible with some kind of "expects" statements but currently dont have time to fix this. Pr welcome

## Usage 
Some Ansible experience comes in handy if you want to remote deploy, create an inventory file and specify the roles you want,
an example playbook has been provided which will install empire,deathstar and starkiller on the localhost:
```ansible-playbook play.yml --ask-become-pass```


## Variables

| Role       	| variable       	| explanation                                                                                                                                             	|   	|   	|
|------------	|----------------	|---------------------------------------------------------------------------------------------------------------------------------------------------------	|---	|---	|
| Empire     	| new_path       	| in case you want to add empire to local path, currently unused due to a bug that prevents database connection to be made when calling empire from $PATH 	|   	|   	|
| Empire     	| install_dir    	| The installation dir you want empire to be installed to, defaults to /opt                                                                               	|   	|   	|
| Starkiller 	| starkiller_url 	| the url of the latest appimage of starkiller, defaults to <br>https://github.com/BC-SECURITY/Starkiller/releases/download/v1.5.1/starkiller-1.5.1.AppImage 
| Starkiller     	| install_dir    	| The installation dir you want starkiller to be installed to, defaults to /opt, starkiller's role also adds a symlink to /usr/bin for global access|
