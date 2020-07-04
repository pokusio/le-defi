# Experimenting all repos talking about blockchain in democracy.earth org on Github (and another one)

> 
> Note : All tests were run on a `Debian Stretch` machine, 2 Gb of RAM 12 CPUs threads
> 

* A funny, [demonic detail about Democracy Earth main product, "`sovereign`"](https://github.com/pokusio/le-defi/blob/master/the-broken-list/moloch-dao/README.md#funny-little-detail-the-devil-is-found-into-details) will perhaps make you share my today's opinion, that "`sovereign`" is mainly a fork built on top of Moloch, which a very, very money-interested organization (A "Venture"...)


If you are curious to see and hear Mr. Santiago Siri Talking about great ideas, in 2016, before checking how much of these great ideas, he and his party have turned into acts since 2016, just watch : 

https://www.youtube.com/watch?v=UajbQTHnTfM


Very personal, from me, To Santiago :

> 
> Let me remind you a little joke you startyed your talk with, involving De Gaulle and François Hollande : 
> 
> (De Gaulle talking to Hollande) : "The only way you can fix this country, is if you abolish the month of May
> 

Well, Santiago, before you consider "fixing" Frace, let's see about your own argentinian git repos, shall we ?  

And when finished with your repos, then we can talk about your ideas. 

## https://github.com/DemocracyEarth/blockchain

Let's take care of that one, seems to be the closest from being "a full blockchain"

* first thing (bad sing) : As of July, the 4th, of 2020, there is not even one release on that repo. 
* second thing (even worse) : There is only one banch, `master`. This shows there is zero collaboration happening on this repo. 
* So i'll just use latest commit on `master`
* third thing : there is zero documentation except the README's in the repo. Ok, we have a clear scope to amke sure we miss zero information
* fourth thing (as of the 4th of July 2020) :  
  * in the README itself, you find the link of another project, https://github.com/lhartikk/naivechain 
  * Oh, and if you look at https://github.com/lhartikk/naivechain, you will see that https://github.com/DemocracyEarth/blockchain was just a fork of that project. 
  * Oh, and if you look at https://github.com/lhartikk/naivechain, you will see that it had zero commits since.. 4years.
  * Oh, and on https://github.com/DemocracyEarth/blockchain you have only 35 commits, and nothing since 3 years
  * so lets sum it up : https://github.com/DemocracyEarth/blockchain is a copy of a project that has died 4 yaers ago (so won't ever come back to life), and the amount of addintional work on top of it, by Mr. Santiago Siri's team is close to zero (35 commits)

Fine, now just testing for the ethics, but given those first datas, well you and me have an idea of what is no doubt going to come out of tests results.

```bash
export OPS_HOME=~/hello.santiago

cd ~ 

if [ -d ${OPS_HOME} ]; then 
  sudo rm -fr ${OPS_HOME}
fi;

# https://github.com/DemocracyEarth/blockchain/commit/6573d3ebdace5914e36457c14632d890bb03a14a  is latest commit on July, the 4th
export VERSION_UNDER_TEST=6573d3ebdace5914e36457c14632d890bb03a14a

git clone https://github.com/DemocracyEarth/blockchain ${OPS_HOME}

cd ${OPS_HOME}

git checkout ${VERSION_UNDER_TEST}


# following quickstart with docker
docker-compose up
curl -H "Content-type:application/json" --data '{"data" : "Some data to the first block"}' http://localhost:3001/mineBlock

```

* Result as expected : catastrophic, and to give you a hint, there is nodejs involved hgere... version four `4.6` (while `latest` is node:**fourteeen**) : 

```bash 
jbl@pc-alienware-jbl:~/hello.santiago$ export OPS_HOME=~/hello.santiago
jbl@pc-alienware-jbl:~/hello.santiago$ 
jbl@pc-alienware-jbl:~/hello.santiago$ cd ~ 
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ if [ -d ${OPS_HOME} ]; then 
>   sudo rm -fr ${OPS_HOME}
> fi;
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ # https://github.com/DemocracyEarth/blockchain/commit/6573d3ebdace5914e36457c14632d890bb03a14a  is latest commit on July, the 4th
jbl@pc-alienware-jbl:~$ export VERSION_UNDER_TEST=6573d3ebdace5914e36457c14632d890bb03a14a
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ git clone https://github.com/DemocracyEarth/blockchain ${OPS_HOME}
Cloning into '/home/jbl/hello.santiago'...
remote: Enumerating objects: 129, done.
remote: Total 129 (delta 0), reused 0 (delta 0), pack-reused 129
Receiving objects: 100% (129/129), 79.03 KiB | 0 bytes/s, done.
Resolving deltas: 100% (72/72), done.
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ cd ${OPS_HOME}
jbl@pc-alienware-jbl:~/hello.santiago$ 
jbl@pc-alienware-jbl:~/hello.santiago$ git checkout ${VERSION_UNDER_TEST}
Note: checking out '6573d3ebdace5914e36457c14632d890bb03a14a'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b <new-branch-name>

HEAD is now at 6573d3e... valid
jbl@pc-alienware-jbl:~/hello.santiago$ docker-compose up
Building node1
Step 1/8 : FROM node:4.6
 ---> e834398209c1
Step 2/8 : RUN mkdir /naivechain
 ---> Using cache
 ---> c718f64fc76b
Step 3/8 : ADD package.json /naivechain/
 ---> Using cache
 ---> c98eb64950a5
Step 4/8 : ADD main.js /naivechain/
ERROR: Service 'node1' failed to build: ADD failed: stat /var/lib/docker/tmp/docker-builder228511337/main.js: no such file or directory
jbl@pc-alienware-jbl:~/hello.santiago$ 
```

Let's move to next 

## https://github.com/DemocracyEarth/sovereign

Now let's take care their "main" one (supposed to bring, how did they call it , "Liquid", democracy...?)

As of the 4th of July 2020 : 
* first thing : the last commits are from sdays ago (recent), there are 35 releases, and the latest is `0.8.0`, also being very recent ( [from a few days ago](https://github.com/DemocracyEarth/sovereign/commit/c3e7a536b268081e78ca1e8e2e27a5de6d4d1f49) ). Much better here, that for the "naive blockchain" 
* Santiago Siri happens to be one of the active commiters. He commits, let's not assume to xhat, he commits, but he seems to put some energy into it.
* second thing (collaboration) : 
  * There are many branches, aside `master`. This does not prove how good the collaboration happens on this repo, but it looks "normal" here. 
  * Also one good sign : there are 145 pull requests, with more than 6percent of them merged, good sign of collaboration too : https://github.com/DemocracyEarth/sovereign/pulls
* So i'll use latest release `` for this test.
* third thing : While https://democracy.earth/ there is zero documentation available except the README's in the repo. Ok, we have a clear scope to amke sure we miss zero information, but let's have a close look at those README's : 
  * https://github.com/DemocracyEarth/sovereign/tree/master/README.md : here we find instructions on how to build frm source, and run the thing. But only using meteor, nothing about how to run it with docker / compose / k8S. Honestly, I don't like that, at all : all software have, today, to prove they can be containerized (and run properluy as such). I do not like that, because ther eis a DOckerfile in the repo, so how much would it take to tell us to justy `docker-compose up` ? Right, I'll test the `Dockerfile` and other container related resources i find in the repo.
  * https://github.com/DemocracyEarth/sovereign/tree/master/docs :  pretty much nothing usueful there to run the app in a container world. Don't like that either.
  * The two live demo links give us total failures (not even one thing appearing on screen), see [this](https://github.com/pokusio/le-defi/raw/master/the-broken-list/democracy-earth/misc/DEMOCRACY_EARTH_2020-07-04%2015-05-46.png) , and [that](https://github.com/pokusio/le-defi/raw/master/the-broken-list/democracy-earth/misc/MOLOCH_DEMOCRACY_EARTH_2020-07-04%2015-04-37.png) screenshots . Very bad omen : They do not even monitor those demos, while it is the first thing to do so that you can prove your boss you have control on what the company publishes (if the work is shit, at least you arez aware of that, and can discuss on how to improve, and when a demo fails, inform the audience, at least ! )


```bash
export OPS_HOME=~/hello.santiago

cd ~

if [ -d ${OPS_HOME} ]; then 
  sudo rm -fr ${OPS_HOME}
fi;

# https://github.com/DemocracyEarth/sovereign/releases/tag/0.8.0  is latest release on July, the 4th of 2020
export VERSION_UNDER_TEST=0.8.0

git clone https://github.com/DemocracyEarth/sovereign ${OPS_HOME}

cd ${OPS_HOME}

git checkout ${VERSION_UNDER_TEST}

# attmepting quickstart with docker 
# one thing I really don't like here : 
# the docker-ècompose is much too simple "to be true", especally it 
# lacks environement vairables, very bad sign for what is going to happen at runtime inside that box

docker-compose up


```

Results : 
* Lamentably fails : and I did that from a release, not any commit. So there, for a release product, it just simply does not work at all, plus it fails so quickly, showing there is zero work done to operate this software nin a container workd (that is, in the real world at all) : 

```bash 
jbl@pc-alienware-jbl:~/hello.santiago$ export OPS_HOME=~/hello.santiago
jbl@pc-alienware-jbl:~/hello.santiago$ 
jbl@pc-alienware-jbl:~/hello.santiago$ cd ~
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ if [ -d ${OPS_HOME} ]; then 
>   sudo rm -fr ${OPS_HOME}
> fi;
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ # https://github.com/DemocracyEarth/sovereign/releases/tag/0.8.0  is latest release on July, the 4th of 2020
jbl@pc-alienware-jbl:~$ export VERSION_UNDER_TEST=0.8.0
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ git clone https://github.com/DemocracyEarth/sovereign ${OPS_HOME}
Cloning into '/home/jbl/hello.santiago'...
remote: Enumerating objects: 429, done.
remote: Counting objects: 100% (429/429), done.
remote: Compressing objects: 100% (297/297), done.
remote: Total 41543 (delta 238), reused 289 (delta 125), pack-reused 41114
Receiving objects: 100% (41543/41543), 146.94 MiB | 21.50 MiB/s, done.
Resolving deltas: 100% (24476/24476), done.
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ cd ${OPS_HOME}
jbl@pc-alienware-jbl:~/hello.santiago$ 
jbl@pc-alienware-jbl:~/hello.santiago$ git checkout ${VERSION_UNDER_TEST}
Note: checking out '0.8.0'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b <new-branch-name>

HEAD is now at c3e7a536... Merge pull request #512 from DemocracyEarth/dating
jbl@pc-alienware-jbl:~/hello.santiago$ docker-compose up
Building sovereign
Step 1/11 : FROM ubuntu
latest: Pulling from library/ubuntu
a4a2a29f9ba4: Pull complete
127c9761dcba: Pull complete
d13bf203e905: Pull complete
4039240d2e0b: Pull complete
Digest: sha256:35c4a2c15539c6c1e4e5fa4e554dac323ad0107d8eb5c582d6ff386b383b7dce
Status: Downloaded newer image for ubuntu:latest
 ---> 74435f89ab78
Step 2/11 : RUN apt-get update &&     apt-get install -qqy     apt-transport-https     build-essential     python     curl     git
 ---> Running in d51e0a290fc2
Get:1 http://archive.ubuntu.com/ubuntu focal InRelease [265 kB]
Get:2 http://security.ubuntu.com/ubuntu focal-security InRelease [107 kB]
Get:3 http://archive.ubuntu.com/ubuntu focal-updates InRelease [107 kB]
Get:4 http://archive.ubuntu.com/ubuntu focal-backports InRelease [98.3 kB]
Get:5 http://security.ubuntu.com/ubuntu focal-security/restricted amd64 Packages [33.4 kB]
Get:6 http://security.ubuntu.com/ubuntu focal-security/multiverse amd64 Packages [1077 B]
Get:7 http://security.ubuntu.com/ubuntu focal-security/main amd64 Packages [160 kB]
Get:8 http://security.ubuntu.com/ubuntu focal-security/universe amd64 Packages [44.2 kB]
Get:9 http://archive.ubuntu.com/ubuntu focal/multiverse amd64 Packages [177 kB]
Get:10 http://archive.ubuntu.com/ubuntu focal/main amd64 Packages [1275 kB]
Get:11 http://archive.ubuntu.com/ubuntu focal/universe amd64 Packages [11.3 MB]
Get:12 http://archive.ubuntu.com/ubuntu focal/restricted amd64 Packages [33.4 kB]
Get:13 http://archive.ubuntu.com/ubuntu focal-updates/restricted amd64 Packages [33.4 kB]
Get:14 http://archive.ubuntu.com/ubuntu focal-updates/multiverse amd64 Packages [1077 B]
Get:15 http://archive.ubuntu.com/ubuntu focal-updates/main amd64 Packages [301 kB]
Get:16 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 Packages [155 kB]
Get:17 http://archive.ubuntu.com/ubuntu focal-backports/universe amd64 Packages [2900 B]
Fetched 14.1 MB in 1s (12.4 MB/s)
Reading package lists...
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package liblocale-gettext-perl.
(Reading database ... 4122 files and directories currently installed.)
Preparing to unpack .../00-liblocale-gettext-perl_1.07-4_amd64.deb ...
Unpacking liblocale-gettext-perl (1.07-4) ...

# [...][Stripped out Skipped a lot of docker build stdout here]

Setting up libkrb5-26-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Setting up gcc-9 (9.3.0-10ubuntu2) ...
Setting up libstdc++-9-dev:amd64 (9.3.0-10ubuntu2) ...
Setting up libfile-fcntllock-perl (0.22-3build4) ...
Setting up libalgorithm-diff-perl (1.19.03-2) ...
Setting up libheimntlm0-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Setting up gcc (4:9.3.0-1ubuntu2) ...
Setting up dpkg-dev (1.19.7ubuntu3) ...
Setting up liberror-perl (0.17029-1) ...
Setting up libgssapi3-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Setting up g++-9 (9.3.0-10ubuntu2) ...
Setting up g++ (4:9.3.0-1ubuntu2) ...
update-alternatives: using /usr/bin/g++ to provide /usr/bin/c++ (c++) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/man1/c++.1.gz because associated file /usr/share/man/man1/g++.1.gz (of link group c++) doesn't exist
Setting up build-essential (12.8ubuntu1) ...
Setting up libalgorithm-diff-xs-perl (0.04-6) ...
Setting up libalgorithm-merge-perl (0.08-3) ...
Setting up libldap-2.4-2:amd64 (2.4.49+dfsg-2ubuntu1.2) ...
Setting up libcurl3-gnutls:amd64 (7.68.0-1ubuntu2.1) ...
Setting up dirmngr (2.2.19-3ubuntu2) ...
Setting up git (1:2.25.1-1ubuntu3) ...
Setting up libcurl4:amd64 (7.68.0-1ubuntu2.1) ...
Setting up curl (7.68.0-1ubuntu2.1) ...
Setting up gpg-wks-client (2.2.19-3ubuntu2) ...
Setting up gnupg (2.2.19-3ubuntu2) ...
Processing triggers for libc-bin (2.31-0ubuntu9) ...
Processing triggers for ca-certificates (20190110ubuntu1.1) ...
Updating certificates in /etc/ssl/certs...
0 added, 0 removed; done.
Running hooks in /etc/ca-certificates/update.d...
done.
Removing intermediate container d51e0a290fc2
 ---> 367b5b0ee29f
Step 3/11 : RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -
 ---> Running in aae3a65d2e3f

================================================================================
================================================================================

                              DEPRECATION WARNING                            

  Node.js 8.x LTS Carbon is no longer actively supported!

  You will not receive security or critical stability updates for this version.

  You should migrate to a supported version of Node.js as soon as possible.
  Use the installation script that corresponds to the version of Node.js you
  wish to install. e.g.

   * https://deb.nodesource.com/setup_10.x — Node.js 10 LTS "Dubnium"
   * https://deb.nodesource.com/setup_12.x — Node.js 12 LTS "Erbium" (recommended)
   * https://deb.nodesource.com/setup_14.x — Node.js 14 LTS "Fermium"

  Please see https://github.com/nodejs/Release for details about which
  version may be appropriate for you.

  The NodeSource Node.js distributions repository contains
  information both about supported versions of Node.js and supported Linux
  distributions. To learn more about usage, see the repository:
    https://github.com/nodesource/distributions

================================================================================
================================================================================

Continuing in 20 seconds ...


## Installing the NodeSource Node.js 8.x LTS Carbon repo...


## Populating apt-get cache...

+ apt-get update
Hit:1 http://security.ubuntu.com/ubuntu focal-security InRelease
Hit:2 http://archive.ubuntu.com/ubuntu focal InRelease
Hit:3 http://archive.ubuntu.com/ubuntu focal-updates InRelease
Hit:4 http://archive.ubuntu.com/ubuntu focal-backports InRelease
Reading package lists...

## Installing packages required for setup: lsb-release...

+ apt-get install -y lsb-release > /dev/null 2>&1

## Confirming "focal" is supported...

+ curl -sLf -o /dev/null 'https://deb.nodesource.com/node_8.x/dists/focal/Release'

## Your distribution, identified as "focal", is not currently supported, please contact NodeSource at https://github.com/nodesource/distributions/issues if you think this is incorrect or would like your distribution to be considered for support

ERROR: Service 'sovereign' failed to build: The command '/bin/sh -c curl -sL https://deb.nodesource.com/setup_8.x | bash -' returned a non-zero code: 1
jbl@pc-alienware-jbl:~/hello.santiago$ 

```

* (bad point here) during docker build process, we have stpout showing project is using nodejs version... Eight `8.x` (very much outdated, nodejs tells it to us explicitly, not me) How is the software going to behave, while we bump to more recent nodejs , e.g. `node:12.x` ? (the docker build stdout quote below)

```bash
Step 3/11 : RUN curl -sL https://deb.nodesource.com/setup_8.x | bash -
 ---> Running in aae3a65d2e3f

================================================================================
================================================================================

                              DEPRECATION WARNING                            

  Node.js 8.x LTS Carbon is no longer actively supported!

  You will not receive security or critical stability updates for this version.

  You should migrate to a supported version of Node.js as soon as possible.
  Use the installation script that corresponds to the version of Node.js you
  wish to install. e.g.

   * https://deb.nodesource.com/setup_10.x — Node.js 10 LTS "Dubnium"
   * https://deb.nodesource.com/setup_12.x — Node.js 12 LTS "Erbium" (recommended)
   * https://deb.nodesource.com/setup_14.x — Node.js 14 LTS "Fermium"

  Please see https://github.com/nodejs/Release for details about which
  version may be appropriate for you.

  The NodeSource Node.js distributions repository contains
  information both about supported versions of Node.js and supported Linux
  distributions. To learn more about usage, see the repository:
    https://github.com/nodesource/distributions

================================================================================
================================================================================
```

But let's give it a second chance (the last chance) : 
* lets run it "bare metal", that is out of any container, and just running the developers command, following the instructions given in the root [README.md](https://github.com/DemocracyEarth/sovereign/blob/master/README.md) : 

```bash
export OPS_HOME=~/hello.santiago

cd ~

if [ -d ${OPS_HOME} ]; then 
  sudo rm -fr ${OPS_HOME}
fi;

# https://github.com/DemocracyEarth/sovereign/releases/tag/0.8.0  is latest release on July, the 4th of 2020
export VERSION_UNDER_TEST=0.8.0

git clone https://github.com/DemocracyEarth/sovereign ${OPS_HOME}

cd ${OPS_HOME}

git checkout ${VERSION_UNDER_TEST}

# so folowing top readme instructions

# On Linux & MacOS, load a terminal and type:
# (installing meteor framework)
curl https://install.meteor.com/ | sh

# install dependencies
# if you have npm installed, type:
# npm install 

# I did not install npm, to make sure I have only ONE unque npm on the system :  to avoid probable bugs and interferences

# if you only have meteor, type:
# meteor npm install
# I added sudo, or some golobal npm installations are going to fail
meteor npm install

```
* Ok, now we need to configure the so called "sovereign" software form "Democracy Earth", and now I quote the doc : 

> 
> 4. **Configure**
> 
>     * On `/config/development/settings.json` you can configure Sovereign for your organization's governance needs.
>         * Make sure you configure the keys on `private.web3` to connect to an Ethereum node ([Infura](https://infura.io) API keys are supported).
>         * For production, you can use `/config/production/settings.json` file and run `$ meteor --settings=config/production/settings.json` in the console.
>     * Seed DAO settings can be found on `/private/dao.json` which consists of an array of DAOs to be read from the blockchain and persisted in the server DB. 
>         * [MolochDAO](https://molochdao.com) and others are included by default.
>     * Make sure `ROOT_URL` on `settings.json` is properly set to the domain that will be serving the application. 
>         * We recommend the use of `https` **always** when deployed on a server.
>     * On `/public/templates/` different template style folders are available. 
>         * The file `templateName.json` can be configured and a css design can be found on `/public/templates/name/css` folder.
> 

So let's sum it up : 

* The software cannot run without an Ethereum full blcockchain, and that blockchain is NOT provided by "democracy.earth" org.
* I have worked on etehreum, and I there is no one in this world who could ever point to me one repo, anywhere from which you can deploy a full Ethereum infrastructutre on premises (fully private and off internet, just a private network) : 
  * And I have a strong opinion as of today, and until I am proved wrong, that Ethereum is a typical "open source false flag" : it does all it can, to make you believe it is open source, while in the end, you will have to pay a company operating something theyu call ethereum, and you don't have a clue chwhat is actually is 
  * indeed, you can see how I worked on the subject, and directly challenged people, abotu that, here : https://github.com/pokusio/le-defi/tree/master/the-broken-list/helm-curated-charts/etherum
* Now it is a very bad sign, that this project has Etehreum as a dependency , because of what I just said. And guess what Mr. Santiago Siri suggests you, if you do not have a private Etehereum ? : 
  * He usggests you to use an Ethereum SAAS, called https://infura.io/product  : there you will have to pay, and You do not have a clue wwhat actually is there. **How much of sovereignty is that ???**
  * Worse, and my guess, cause I have a looot of experience with that kind of profile : I bet no one at Democracy Earth know how to deploy a fully private, off the internet, `Ethereum` Blockchain (Or proove me wrong, and open an issue on this repo, with references)
  * And even worse : You can confirm yoruself, that the suggested thrid party "https://infura.io" does not publish any open source way to deploy an ethereum blockchain : https://github.com/search?q=infura.io will give you only "clients" or gadgets like that, nothing like a full Ethereum infrastructure. **Infura.io is not open soure at all!** . So you do not know what runs over there in their servers, and who accesses the data : you cannot make sure of anything there.
  
  
Now, the test results, up until meteor npm install : 

```bash 
jbl@pc-alienware-jbl:~/hello.santiago$ export OPS_HOME=~/hello.santiago
jbl@pc-alienware-jbl:~/hello.santiago$ 
jbl@pc-alienware-jbl:~/hello.santiago$ cd ~
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ if [ -d ${OPS_HOME} ]; then 
>   sudo rm -fr ${OPS_HOME}
> fi;
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ # https://github.com/DemocracyEarth/sovereign/releases/tag/0.8.0  is latest release on July, the 4th of 2020
jbl@pc-alienware-jbl:~$ export VERSION_UNDER_TEST=0.8.0
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ git clone https://github.com/DemocracyEarth/sovereign ${OPS_HOME}
Cloning into '/home/jbl/hello.santiago'...
remote: Enumerating objects: 429, done.
remote: Counting objects: 100% (429/429), done.
remote: Compressing objects: 100% (297/297), done.
remote: Total 41543 (delta 238), reused 289 (delta 125), pack-reused 41114
Receiving objects: 100% (41543/41543), 146.94 MiB | 24.66 MiB/s, done.
Resolving deltas: 100% (24476/24476), done.
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ cd ${OPS_HOME}
jbl@pc-alienware-jbl:~/hello.santiago$ 
jbl@pc-alienware-jbl:~/hello.santiago$ git checkout ${VERSION_UNDER_TEST}
Note: checking out '0.8.0'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b <new-branch-name>

HEAD is now at c3e7a536... Merge pull request #512 from DemocracyEarth/dating
jbl@pc-alienware-jbl:~/hello.santiago$ curl https://install.meteor.com/ | sh
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  7915    0  7915    0     0  19245      0 --:--:-- --:--:-- --:--:-- 19211
Downloading Meteor distribution
######################################################################## 100.0%

Meteor 1.10.2 has been installed in your home directory (~/.meteor).
Writing a launcher script to /usr/local/bin/meteor for your convenience.
This may prompt for your password.

To get started fast:

  $ meteor create ~/my_cool_app
  $ cd ~/my_cool_app
  $ meteor

Or see the docs at:

  docs.meteor.com

Deploy and host your app with Galaxy:

  www.meteor.com/hosting

jbl@pc-alienware-jbl:~/hello.santiago$ meteor npm install

> keccak@2.1.0 install /home/jbl/hello.santiago/node_modules/ethereumjs-tx/node_modules/keccak
> npm run rebuild || echo "Keccak bindings compilation fail. Pure JS implementation will be used."


> keccak@2.1.0 rebuild /home/jbl/hello.santiago/node_modules/ethereumjs-tx/node_modules/keccak
> node-gyp rebuild

make: Entering directory '/home/jbl/hello.santiago/node_modules/ethereumjs-tx/node_modules/keccak/build'
  CXX(target) Release/obj.target/keccak/src/addon.o
  CC(target) Release/obj.target/keccak/src/libkeccak-64/KeccakSpongeWidth1600.o
  CC(target) Release/obj.target/keccak/src/libkeccak-64/KeccakP-1600-opt64.o
  SOLINK_MODULE(target) Release/obj.target/keccak.node
  COPY Release/keccak.node
make: Leaving directory '/home/jbl/hello.santiago/node_modules/ethereumjs-tx/node_modules/keccak/build'

> keccak@1.4.0 install /home/jbl/hello.santiago/node_modules/keccak
> npm run rebuild || echo "Keccak bindings compilation fail. Pure JS implementation will be used."


> keccak@1.4.0 rebuild /home/jbl/hello.santiago/node_modules/keccak
> node-gyp rebuild

make: Entering directory '/home/jbl/hello.santiago/node_modules/keccak/build'
  CXX(target) Release/obj.target/keccak/src/addon.o
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::Initialize(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:37:47: error: no matching function for call to ‘v8::Value::IntegerValue()’
     unsigned int rate = info[0]->IntegerValue();
                                               ^
In file included from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/node.h:63:0,
                 from ../src/addon.cc:1:
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2705:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2705:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc:38:51: error: no matching function for call to ‘v8::Value::IntegerValue()’
     unsigned int capacity = info[1]->IntegerValue();
                                                   ^
In file included from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/node.h:63:0,
                 from ../src/addon.cc:1:
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2705:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2705:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::AbsorbLastFewBits(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:56:48: error: no matching function for call to ‘v8::Value::IntegerValue()’
     unsigned char bits = info[0]->IntegerValue();
                                                ^
In file included from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/node.h:63:0,
                 from ../src/addon.cc:1:
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2705:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2705:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::Squeeze(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:64:43: error: no matching function for call to ‘v8::Value::IntegerValue()’
     size_t length = info[0]->IntegerValue();
                                           ^
In file included from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/node.h:63:0,
                 from ../src/addon.cc:1:
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2705:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2705:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::Copy(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:75:82: error: no matching function for call to ‘v8::Value::ToObject()’
     KeccakWrapper* to = Nan::ObjectWrap::Unwrap<KeccakWrapper>(info[0]->ToObject());
                                                                                  ^
In file included from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/node.h:63:0,
                 from ../src/addon.cc:1:
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2672:44: note: candidate: v8::MaybeLocal<v8::Object> v8::Value::ToObject(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT MaybeLocal<Object> ToObject(
                                            ^~~~~~~~
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2672:44: note:   candidate expects 1 argument, 0 provided
In file included from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8-internal.h:14:0,
                 from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:27,
                 from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/node.h:63,
                 from ../src/addon.cc:1:
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2686:31: note: candidate: v8::Local<v8::Object> v8::Value::ToObject(v8::Isolate*) const
                 Local<Object> ToObject(Isolate* isolate) const);
                               ^
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8config.h:328:3: note: in definition of macro ‘V8_DEPRECATED’
   declarator __attribute__((deprecated(message)))
   ^~~~~~~~~~
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2686:31: note:   candidate expects 1 argument, 0 provided
                 Local<Object> ToObject(Isolate* isolate) const);
                               ^
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8config.h:328:3: note: in definition of macro ‘V8_DEPRECATED’
   declarator __attribute__((deprecated(message)))
   ^~~~~~~~~~
keccak.target.mk:129: recipe for target 'Release/obj.target/keccak/src/addon.o' failed
make: *** [Release/obj.target/keccak/src/addon.o] Error 1
make: Leaving directory '/home/jbl/hello.santiago/node_modules/keccak/build'
gyp ERR! build error 
gyp ERR! stack Error: `make` failed with exit code: 2
gyp ERR! stack     at ChildProcess.onExit (/home/jbl/.meteor/packages/meteor-tool/.1.10.2.121ry7f.gueme++os.linux.x86_64+web.browser+web.browser.legacy+web.cordova/mt-os.linux.x86_64/dev_bundle/lib/node_modules/npm/node_modules/node-gyp/lib/build.js:194:23)
gyp ERR! stack     at ChildProcess.emit (events.js:311:20)
gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:275:12)
gyp ERR! System Linux 4.9.0-7-amd64
gyp ERR! command "/home/jbl/.meteor/packages/meteor-tool/.1.10.2.121ry7f.gueme++os.linux.x86_64+web.browser+web.browser.legacy+web.cordova/mt-os.linux.x86_64/dev_bundle/bin/node" "/home/jbl/.meteor/packages/meteor-tool/.1.10.2.121ry7f.gueme++os.linux.x86_64+web.browser+web.browser.legacy+web.cordova/mt-os.linux.x86_64/dev_bundle/lib/node_modules/npm/node_modules/node-gyp/bin/node-gyp.js" "rebuild"
gyp ERR! cwd /home/jbl/hello.santiago/node_modules/keccak
gyp ERR! node -v v12.16.1
gyp ERR! node-gyp -v v5.0.7
gyp ERR! not ok 
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! keccak@1.4.0 rebuild: `node-gyp rebuild`
npm ERR! Exit status 1
npm ERR! 
npm ERR! Failed at the keccak@1.4.0 rebuild script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.
npm WARN Local package.json exists, but node_modules missing, did you mean to install?

npm ERR! A complete log of this run can be found in:
npm ERR!     /home/jbl/.npm/_logs/2020-07-04T14_21_02_055Z-debug.log
Keccak bindings compilation fail. Pure JS implementation will be used.

> secp256k1@3.5.0 install /home/jbl/hello.santiago/node_modules/secp256k1
> npm run rebuild || echo "Secp256k1 bindings compilation fail. Pure JS implementation will be used."


> secp256k1@3.5.0 rebuild /home/jbl/hello.santiago/node_modules/secp256k1
> node-gyp rebuild

make: Entering directory '/home/jbl/hello.santiago/node_modules/secp256k1/build'
  CXX(target) Release/obj.target/secp256k1/src/addon.o
  CXX(target) Release/obj.target/secp256k1/src/privatekey.o
In file included from ../src/privatekey.cc:8:0:
../src/privatekey.cc: In function ‘Nan::NAN_METHOD_RETURN_TYPE privateKeyExport(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/util.h:14:38: error: no matching function for call to ‘v8::Value::BooleanValue()’
     compressed = value->BooleanValue() ? v_true : v_false;                     \
                                      ^
../src/privatekey.cc:36:3: note: in expansion of macro ‘UPDATE_COMPRESSED_VALUE’
   UPDATE_COMPRESSED_VALUE(compressed, info[1], 1, 0);
   ^~~~~~~~~~~~~~~~~~~~~~~
In file included from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/node.h:63:0,
                 from ../src/privatekey.cc:1:
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2699:8: note: candidate: bool v8::Value::BooleanValue(v8::Isolate*) const
   bool BooleanValue(Isolate* isolate) const;
        ^~~~~~~~~~~~
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2699:8: note:   candidate expects 1 argument, 0 provided
In file included from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8-internal.h:14:0,
                 from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:27,
                 from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/node.h:63,
                 from ../src/privatekey.cc:1:
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2702:51: note: candidate: v8::Maybe<bool> v8::Value::BooleanValue(v8::Local<v8::Context>) const
                 V8_WARN_UNUSED_RESULT Maybe<bool> BooleanValue(
                                                   ^
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8config.h:328:3: note: in definition of macro ‘V8_DEPRECATED’
   declarator __attribute__((deprecated(message)))
   ^~~~~~~~~~
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2702:51: note:   candidate expects 1 argument, 0 provided
                 V8_WARN_UNUSED_RESULT Maybe<bool> BooleanValue(
                                                   ^
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8config.h:328:3: note: in definition of macro ‘V8_DEPRECATED’
   declarator __attribute__((deprecated(message)))
   ^~~~~~~~~~
../src/privatekey.cc: In function ‘Nan::NAN_METHOD_RETURN_TYPE privateKeyNegate(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/privatekey.cc:73:61: warning: ignoring return value of ‘int secp256k1_ec_privkey_negate(const secp256k1_context*, unsigned char*)’, declared with attribute warn_unused_result [-Wunused-result]
   secp256k1_ec_privkey_negate(secp256k1ctx, &private_key[0]);
                                                             ^
secp256k1.target.mk:159: recipe for target 'Release/obj.target/secp256k1/src/privatekey.o' failed
make: *** [Release/obj.target/secp256k1/src/privatekey.o] Error 1
make: Leaving directory '/home/jbl/hello.santiago/node_modules/secp256k1/build'
gyp ERR! build error 
gyp ERR! stack Error: `make` failed with exit code: 2
gyp ERR! stack     at ChildProcess.onExit (/home/jbl/.meteor/packages/meteor-tool/.1.10.2.121ry7f.gueme++os.linux.x86_64+web.browser+web.browser.legacy+web.cordova/mt-os.linux.x86_64/dev_bundle/lib/node_modules/npm/node_modules/node-gyp/lib/build.js:194:23)
gyp ERR! stack     at ChildProcess.emit (events.js:311:20)
gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:275:12)
gyp ERR! System Linux 4.9.0-7-amd64
gyp ERR! command "/home/jbl/.meteor/packages/meteor-tool/.1.10.2.121ry7f.gueme++os.linux.x86_64+web.browser+web.browser.legacy+web.cordova/mt-os.linux.x86_64/dev_bundle/bin/node" "/home/jbl/.meteor/packages/meteor-tool/.1.10.2.121ry7f.gueme++os.linux.x86_64+web.browser+web.browser.legacy+web.cordova/mt-os.linux.x86_64/dev_bundle/lib/node_modules/npm/node_modules/node-gyp/bin/node-gyp.js" "rebuild"
gyp ERR! cwd /home/jbl/hello.santiago/node_modules/secp256k1
gyp ERR! node -v v12.16.1
gyp ERR! node-gyp -v v5.0.7
gyp ERR! not ok 
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! secp256k1@3.5.0 rebuild: `node-gyp rebuild`
npm ERR! Exit status 1
npm ERR! 
npm ERR! Failed at the secp256k1@3.5.0 rebuild script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.
npm WARN Local package.json exists, but node_modules missing, did you mean to install?

npm ERR! A complete log of this run can be found in:
npm ERR!     /home/jbl/.npm/_logs/2020-07-04T14_21_04_022Z-debug.log
Secp256k1 bindings compilation fail. Pure JS implementation will be used.

> tiny-secp256k1@1.1.3 install /home/jbl/hello.santiago/node_modules/tiny-secp256k1
> npm run build || echo "secp256k1 bindings compilation fail. Pure JS implementation will be used."


> tiny-secp256k1@1.1.3 build /home/jbl/hello.santiago/node_modules/tiny-secp256k1
> node-gyp rebuild

make: Entering directory '/home/jbl/hello.santiago/node_modules/tiny-secp256k1/build'
  CXX(target) Release/obj.target/secp256k1/native/addon.o
../native/addon.cpp: In function ‘Nan::NAN_METHOD_RETURN_TYPE ecdsaVerify(Nan::NAN_METHOD_ARGS_TYPE)’:
../native/addon.cpp:320:58: warning: ‘v8::Maybe<bool> v8::Value::BooleanValue(v8::Local<v8::Context>) const’ is deprecated: BooleanValue can never throw. Use Isolate version. [-Wdeprecated-declarations]
   strict = info[3]->BooleanValue(Nan::GetCurrentContext()).FromJust();
                                                          ^
In file included from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8-internal.h:14:0,
                 from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:27,
                 from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/node.h:63,
                 from ../../nan/nan.h:54,
                 from ../native/addon.cpp:4:
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2702:51: note: declared here
                 V8_WARN_UNUSED_RESULT Maybe<bool> BooleanValue(
                                                   ^
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8config.h:328:3: note: in definition of macro ‘V8_DEPRECATED’
   declarator __attribute__((deprecated(message)))
   ^~~~~~~~~~
../native/addon.cpp: In instantiation of ‘unsigned int {anonymous}::assumeCompression(const I&, const A&) [with long unsigned int index = 2ul; I = Nan::FunctionCallbackInfo<v8::Value>; A = v8::Local<v8::Object>]’:
../native/addon.cpp:142:50:   required from here
../native/addon.cpp:80:21: warning: comparison between signed and unsigned integer expressions [-Wsign-compare]
   if (info.Length() <= index) return __isPointCompressed(p) ? SECP256K1_EC_COMPRESSED : SECP256K1_EC_UNCOMPRESSED;
                      
../native/addon.cpp:82:62: warning: ‘v8::Maybe<bool> v8::Value::BooleanValue(v8::Local<v8::Context>) const’ is deprecated: BooleanValue can never throw. Use Isolate version. [-Wdeprecated-declarations]
   return info[index]->BooleanValue(Nan::GetCurrentContext()).FromJust() ? SECP256K1_EC_COMPRESSED : SECP256K1_EC_UNCOMPRESSED;
                                                               
In file included from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8-internal.h:14:0,
                 from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:27,
                 from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/node.h:63,
                 from ../../nan/nan.h:54,
                 from ../native/addon.cpp:4:
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2702:51: note: declared here
                 V8_WARN_UNUSED_RESULT Maybe<bool> BooleanValue(
                                                   ^
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8config.h:328:3: note: in definition of macro ‘V8_DEPRECATED’
   declarator __attribute__((deprecated(message)))
   ^~~~~~~~~~
../native/addon.cpp: In instantiation of ‘unsigned int {anonymous}::assumeCompression(const I&, const A&) [with long unsigned int index = 1ul; I = Nan::FunctionCallbackInfo<v8::Value>; A = v8::Local<v8::Object>]’:
../native/addon.cpp:174:49:   required from here
../native/addon.cpp:80:21: warning: comparison between signed and unsigned integer expressions [-Wsign-compare]
   if (info.Length() <= index) return __isPointCompressed(p) ? SECP256K1_EC_COMPRESSED : SECP256K1_EC_UNCOMPRESSED;
                      
../native/addon.cpp:82:62: warning: ‘v8::Maybe<bool> v8::Value::BooleanValue(v8::Local<v8::Context>) const’ is deprecated: BooleanValue can never throw. Use Isolate version. [-Wdeprecated-declarations]
   return info[index]->BooleanValue(Nan::GetCurrentContext()).FromJust() ? SECP256K1_EC_COMPRESSED : SECP256K1_EC_UNCOMPRESSED;
                                                               
In file included from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8-internal.h:14:0,
                 from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:27,
                 from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/node.h:63,
                 from ../../nan/nan.h:54,
                 from ../native/addon.cpp:4:
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2702:51: note: declared here
                 V8_WARN_UNUSED_RESULT Maybe<bool> BooleanValue(
                                                   ^
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8config.h:328:3: note: in definition of macro ‘V8_DEPRECATED’
   declarator __attribute__((deprecated(message)))
   ^~~~~~~~~~
../native/addon.cpp: In instantiation of ‘unsigned int {anonymous}::assumeCompression(const I&) [with long unsigned int index = 1ul; I = Nan::FunctionCallbackInfo<v8::Value>]’:
../native/addon.cpp:189:46:   required from here
../native/addon.cpp:87:21: warning: comparison between signed and unsigned integer expressions [-Wsign-compare]
   if (info.Length() <= index) return SECP256K1_EC_COMPRESSED;
                      
../native/addon.cpp:89:62: warning: ‘v8::Maybe<bool> v8::Value::BooleanValue(v8::Local<v8::Context>) const’ is deprecated: BooleanValue can never throw. Use Isolate version. [-Wdeprecated-declarations]
   return info[index]->BooleanValue(Nan::GetCurrentContext()).FromJust() ? SECP256K1_EC_COMPRESSED : SECP256K1_EC_UNCOMPRESSED;
                                                               
In file included from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8-internal.h:14:0,
                 from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:27,
                 from /home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/node.h:63,
                 from ../../nan/nan.h:54,
                 from ../native/addon.cpp:4:
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8.h:2702:51: note: declared here
                 V8_WARN_UNUSED_RESULT Maybe<bool> BooleanValue(
                                                   ^
/home/jbl/.meteor/packages/meteor-tool/1.10.2/mt-os.linux.x86_64/dev_bundle/include/node/v8config.h:328:3: note: in definition of macro ‘V8_DEPRECATED’
   declarator __attribute__((deprecated(message)))
   ^~~~~~~~~~
../native/addon.cpp: In function ‘Nan::NAN_METHOD_RETURN_TYPE eccPrivateSub(Nan::NAN_METHOD_ARGS_TYPE)’:
../native/addon.cpp:240:53: warning: ignoring return value of ‘int secp256k1_ec_privkey_negate(const secp256k1_context*, unsigned char*)’, declared with attribute warn_unused_result [-Wunused-result]
  secp256k1_ec_privkey_negate(context, tweak_negated); // returns 1 always
                                                     ^
  CC(target) Release/obj.target/secp256k1/native/secp256k1/src/secp256k1.o
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ec_pubkey_parse’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘pubkey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:154:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(pubkey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘input’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:156:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(input != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ec_pubkey_serialize’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘output’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:175:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(output != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘outputlen’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:171:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(outputlen != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘pubkey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:177:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(pubkey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ecdsa_signature_parse_der’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘sig’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:216:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(sig != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘input’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:217:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(input != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ecdsa_signature_parse_compact’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘sig’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:234:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(sig != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘input64’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:235:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(input64 != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ecdsa_signature_serialize_der’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘output’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:253:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(output != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘outputlen’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:254:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(outputlen != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘sig’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:255:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(sig != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ecdsa_signature_serialize_compact’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘output64’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:265:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(output64 != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘sig’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:266:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(sig != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ecdsa_signature_normalize’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘sigin’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:279:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(sigin != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ecdsa_verify’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘sig’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:300:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(sig != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘msg32’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:299:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(msg32 != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘pubkey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:301:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(pubkey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ecdsa_sign’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘signature’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:353:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(signature != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘msg32’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:352:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(msg32 != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘seckey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:354:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(seckey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ec_seckey_verify’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘seckey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:396:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(seckey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ec_pubkey_create’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘pubkey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:411:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(pubkey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘seckey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:414:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(seckey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ec_privkey_negate’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘seckey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:430:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(seckey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ec_pubkey_negate’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘pubkey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:443:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(pubkey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ec_privkey_tweak_add’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘seckey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:460:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(seckey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘tweak’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:461:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(tweak != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ec_pubkey_tweak_add’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘pubkey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:484:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(pubkey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘tweak’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:485:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(tweak != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ec_privkey_tweak_mul’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘seckey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:507:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(seckey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘tweak’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:508:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(tweak != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ec_pubkey_tweak_mul’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘pubkey’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:530:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(pubkey != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘tweak’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:531:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(tweak != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c: In function ‘secp256k1_ec_pubkey_combine’:
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘pubnonce’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:559:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(pubnonce != NULL);
     ^~~~~~~~~
../native/secp256k1/src/secp256k1.c:22:8: warning: nonnull argument ‘pubnonces’ compared to NULL [-Wnonnull-compare]
     if (EXPECT(!(cond), 0)) { \
        ^
../native/secp256k1/src/secp256k1.c:562:5: note: in expansion of macro ‘ARG_CHECK’
     ARG_CHECK(pubnonces != NULL);
     ^~~~~~~~~
  SOLINK_MODULE(target) Release/obj.target/secp256k1.node
  COPY Release/secp256k1.node
make: Leaving directory '/home/jbl/hello.santiago/node_modules/tiny-secp256k1/build'

> @web3-js/websocket@1.0.30 install /home/jbl/hello.santiago/node_modules/@web3-js/websocket
> (node-gyp rebuild 2> builderror.log) || (exit 0)

make: Entering directory '/home/jbl/hello.santiago/node_modules/@web3-js/websocket/build'
  CXX(target) Release/obj.target/bufferutil/src/bufferutil.o
bufferutil.target.mk:112: recipe for target 'Release/obj.target/bufferutil/src/bufferutil.o' failed
make: Leaving directory '/home/jbl/hello.santiago/node_modules/@web3-js/websocket/build'

> bcrypt@3.0.8 install /home/jbl/hello.santiago/node_modules/bcrypt
> node-pre-gyp install --fallback-to-build

node-pre-gyp WARN Using request for node-pre-gyp https download 
[bcrypt] Success: "/home/jbl/hello.santiago/node_modules/bcrypt/lib/binding/bcrypt_lib.node" is installed via remote

> fibers@4.0.2 install /home/jbl/hello.santiago/node_modules/fibers
> node build.js || nodejs build.js

`linux-x64-72-glibc` exists; testing
Binary is fine; exiting

> phantomjs-prebuilt@2.1.16 install /home/jbl/hello.santiago/node_modules/phantomjs-prebuilt
> node install.js

PhantomJS not found on PATH
Downloading https://github.com/Medium/phantomjs/releases/download/v2.1.1/phantomjs-2.1.1-linux-x86_64.tar.bz2
Saving to /tmp/phantomjs/phantomjs-2.1.1-linux-x86_64.tar.bz2
Receiving...
  [=====================================---] 94%
Received 22866K total.
Extracting tar contents (via spawned process)
Removing /home/jbl/hello.santiago/node_modules/phantomjs-prebuilt/lib/phantom
Copying extracted folder /tmp/phantomjs/phantomjs-2.1.1-linux-x86_64.tar.bz2-extract-1593872470541/phantomjs-2.1.1-linux-x86_64 -> /home/jbl/hello.santiago/node_modules/phantomjs-prebuilt/lib/phantom
Writing location.js file
Done. Phantomjs binary available at /home/jbl/hello.santiago/node_modules/phantomjs-prebuilt/lib/phantom/bin/phantomjs

> core-js@2.6.11 postinstall /home/jbl/hello.santiago/node_modules/core-js
> node -e "try{require('./postinstall')}catch(e){}"

Thank you for using core-js ( https://github.com/zloirock/core-js ) for polyfilling JavaScript standard library!

The project needs your help! Please consider supporting of core-js on Open Collective or Patreon: 
> https://opencollective.com/core-js 
> https://www.patreon.com/zloirock 

Also, the author of core-js ( https://github.com/zloirock ) is looking for a good job -)


> @web3-js/scrypt-shim@0.1.0 postinstall /home/jbl/hello.santiago/node_modules/@web3-js/scrypt-shim
> node ./scripts/postinstall.js


> web3@1.2.6 postinstall /home/jbl/hello.santiago/node_modules/web3
> node angular-patch.js


> Sovereign.app@ postinstall /home/jbl/hello.santiago
> opencollective-postinstall || exit 0

Thank you for using Sovereign.app!
If you rely on this package, please consider supporting our open collective:
> https://opencollective.com/DemocracyEarth/donate

added 1067 packages from 875 contributors and audited 1062 packages in 37.297s

1 package is looking for funding
  run `npm fund` for details

found 33 vulnerabilities (25 low, 8 high)
  run `npm audit fix` to fix them, or `npm audit` for details
jbl@pc-alienware-jbl:~/hello.santiago$ meteor npm install
^C.................] | preinstall:Sovereign.app: info lifecycle Sovereign.app@~preinstall: Sovereign.app@
meteor npm install^C
jbl@pc-alienware-jbl:~/hello.santiago$ sudo meteor npm install
root, this is your first time using Meteor!
Installing a Meteor distribution in your home directory.
Downloading Meteor distribution
######################################################################## 100.0%
npm WARN lifecycle Sovereign.app@~postinstall: cannot run in wd Sovereign.app@ opencollective-postinstall || exit 0 (wd=/home/jbl/hello.santiago)
npm WARN ajv-keywords@2.1.1 requires a peer of ajv@^5.0.0 but none is installed. You must install peer dependencies yourself.
npm WARN eslint-config-airbnb@11.2.0 requires a peer of eslint@^3.6.0 but none is installed. You must install peer dependencies yourself.
npm WARN eslint-config-airbnb-base@7.2.0 requires a peer of eslint@^3.6.0 but none is installed. You must install peer dependencies yourself.
npm WARN eslint-plugin-import@1.16.0 requires a peer of eslint@2.x - 3.x but none is installed. You must install peer dependencies yourself.
npm WARN eslint-plugin-jsx-a11y@2.2.3 requires a peer of eslint@^2.10.2 || 3.x but none is installed. You must install peer dependencies yourself.
npm WARN eslint-plugin-react@6.10.3 requires a peer of eslint@^2.0.0 || ^3.0.0 but none is installed. You must install peer dependencies yourself.

removed 6 packages and audited 1056 packages in 5.08s

1 package is looking for funding
  run `npm fund` for details

found 33 vulnerabilities (25 low, 8 high)
  run `npm audit fix` to fix them, or `npm audit` for details
jbl@pc-alienware-jbl:~/hello.santiago$ 

```

Well, all in all, what I am wondering, is if Mr. Siri works with root user, in everyday dev life... Pretty uncommon.


## Other tested repos 

* TODO


## Misc.


* https://github.com/pokusio/le-defi/raw/master/the-broken-list/democracy-earth/misc/embracing-innovation-in-government-colombia.pdf : there you will rad a whole lot of "data analysis", which obviously is supposed to look serious. Well, How serious/true can those data be, while I have those results on their "technology" ?


# Conclusion

I think the main problem found here is the depedency to the "open source false flag" project `Ethereum` here : 

Democracy Earth makes you dependent on third party that are pure commercial players, zero open source, to run this applicaton called Soverereign.

So I have as conclusion, one question, and one piece of advice to my only question is : 

* How much Sovereignity is that ?
* I (my personal opinion engaged here, only mine) give the Argentinian great people, the advice to not ever trust what **Democracy Earth** and **PartidoDeLared** propose you to use as software, because they had 4 years, to make something decent, since 2016's talk and great political declarations of Mr. Santiago Siri. And after 4 years, they did not inform you at all, of all those informations I gav eyou here in 5 hours of work, (One Day).

I also have today, 4th of July, 2020 : 

* sent an email to the Democracy Earth Team to give them a chance to change this catastrpophic situation with their project : 

![my email](https://github.com/Jean-Baptiste-Lasselle/for-fellow-developers/raw/master/docuementation/impr.ecrans/democracy-earth/MAIL_TO_DEMOCRACY_EARTH_2020-07-04%2016-35-31.png)

* and opened an issue on the Democracy Earth "Sovereign" project:  https://github.com/DemocracyEarth/sovereign/issues/514

Now, Mr. Siri, we can talk again about your little joke about France, when you are ready to answer this question.

Or when you can prove you know how to deploy a full Ethereum Blockchain, from pure open source code.

Finally, let me give you a real quote, from De Gaulle : 

> 
> Des chercheurs qui cherchent, on en trouve, des chercheurs qui trouvent, on en cherche.
> 

Regards.

