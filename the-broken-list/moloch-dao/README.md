# Just another one : Moloch "DAO" (Have become a Demon hunter...??)

Under test, here : 

* https://github.com/MolochVentures/moloch



## prepare my debian machine for a demon catch

* install `nodejs`, `npx` : 

```bash

curl -sL https://deb.nodesource.com/setup_14.x -o nodesource_setup.sh
sudo apt install -y nodejs
node --version
npm --version

sudo npm install -g npx

```

* zero releases in the project (too bad) : https://github.com/MolochVentures/moloch/releases
* bracnhes : the repo has many branches, all of them looking like feature branch, or test branch, nothing like a release
* so no chice but latest commit on `master` : https://github.com/MolochVentures/moloch/commit/7db370566a5d8c3bad3624700a4ca710c8cf35b4

## following https://github.com/MolochVentures/moloch#installation

```bash
export OPS_HOME=~/hello.moloch

cd ~ 

if [ -d ${OPS_HOME} ]; then 
  sudo rm -fr ${OPS_HOME}
fi;

# https://github.com/MolochVentures/moloch/commit/7db370566a5d8c3bad3624700a4ca710c8cf35b4  is latest commit on the 4th of July, 2020
export VERSION_UNDER_TEST=7db370566a5d8c3bad3624700a4ca710c8cf35b4

git clone https://github.com/MolochVentures/moloch ${OPS_HOME}

cd ${OPS_HOME}

git checkout ${VERSION_UNDER_TEST}

npm i


```

* Right, now, accordng to the docs, you have to cofigure stuff, before you can do anything with "moloch", quoting : 

> 
> 
> #### Deploying a new DAO
> 
> Follow this instructions to deploy a new DAO:
> 
> 1. Edit `buidler.config.js`, setting the values for `INFURA_API_KEY` and `MAINNET_PRIVATE_KEY`.
> 2. Edit `deployment-params.js`, setting your desired deployment parameters.
> 3. Run `npx buidler moloch-deploy --network mainnet`
> 4. Edit `buidler.config.js`, setting the address of the DAO in `networks.mainnet.deployedContracts.moloch`.
> 
> 


Alright, here we have to setup `INFURA_API_KEY` , and we do not need to go any further : 
* Moloch does nothing, unless you have an Ethereum Blockchain, and there it is even worse : on special, non open source, commercial Etheruem SAAS is required : https://infura.io 
* I have allready tackled the https://infura.io  case, it is complete "open source false flag",  see [my broken list entry on DEmocracy Earth](https://github.com/pokusio/le-defi/blob/master/the-broken-list/democracy-earth/README.md) and `Ctrl + F` into my article

Okay, so let's now just just the stuf until npm install, just for the sake of ethics (std out under there) : 



```bash
jbl@pc-alienware-jbl:~/hello.santiago$ npm --version
6.14.5
jbl@pc-alienware-jbl:~/hello.santiago$ sudo npm install -g npx
npm ERR! code EEXIST
npm ERR! syscall symlink
npm ERR! path ../lib/node_modules/npx/index.js
npm ERR! dest /usr/bin/npx
npm ERR! errno -17
npm ERR! EEXIST: file already exists, symlink '../lib/node_modules/npx/index.js' -> '/usr/bin/npx'
npm ERR! File exists: /usr/bin/npx
npm ERR! Remove the existing file and try again, or run npm
npm ERR! with --force to overwrite files recklessly.

npm ERR! A complete log of this run can be found in:
npm ERR!     /root/.npm/_logs/2020-07-04T15_27_23_328Z-debug.log
jbl@pc-alienware-jbl:~/hello.santiago$ npx --version
6.14.5
jbl@pc-alienware-jbl:~/hello.santiago$ 

```


One less demon in this world.




And time to go back to real projects.
