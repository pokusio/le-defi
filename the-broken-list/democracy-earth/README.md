# Experimenting all repos talking about blockchain in democracy.earth org on Github

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

# following quickstart with docker
docker-compose up
curl -H "Content-type:application/json" --data '{"data" : "Some data to the first block"}' http://localhost:3001/mineBlock

```

* Result as expected : catastrophic, and to give you a hint, there is nodejs involved hgere... version four `4.6` (while `latest` is node:**fourteeen**) : 

```bash 
jbl@pc-alienware-jbl:~/coopcycle-web$ export OPS_HOME=~/hello.santiago
jbl@pc-alienware-jbl:~/coopcycle-web$ 
jbl@pc-alienware-jbl:~/coopcycle-web$ if [ -d ${OPS_HOME} ]; then 
>   sudo rm -fr ${OPS_HOME}
> fi;
jbl@pc-alienware-jbl:~/coopcycle-web$ 
jbl@pc-alienware-jbl:~/coopcycle-web$ # https://github.com/DemocracyEarth/blockchain/commit/6573d3ebdace5914e36457c14632d890bb03a14a  is latest commit on July, the 4th
jbl@pc-alienware-jbl:~/coopcycle-web$ export VERSION_UNDER_TEST=6573d3ebdace5914e36457c14632d890bb03a14a
jbl@pc-alienware-jbl:~/coopcycle-web$ 
jbl@pc-alienware-jbl:~/coopcycle-web$ git clone https://github.com/DemocracyEarth/blockchain ${OPS_HOME}
Cloning into '/home/jbl/hello.santiago'...
remote: Enumerating objects: 129, done.
remote: Total 129 (delta 0), reused 0 (delta 0), pack-reused 129
Receiving objects: 100% (129/129), 79.03 KiB | 0 bytes/s, done.
Resolving deltas: 100% (72/72), done.
jbl@pc-alienware-jbl:~/coopcycle-web$ 
jbl@pc-alienware-jbl:~/coopcycle-web$ cd ${OPS_HOME}
jbl@pc-alienware-jbl:~/hello.santiago$ docker-compose up
Creating network "hellosantiago_default" with the default driver
Building node1
Step 1/8 : FROM node:4.6
4.6: Pulling from library/node
386a066cd84a: Pull complete
75ea84187083: Pull complete
88b459c9f665: Pull complete
1e3ee139a577: Pull complete
f78ff7d0315b: Pull complete
f4ba677961ff: Pull complete
21db8c3555aa: Pull complete
Digest: sha256:a1cc6d576734c331643f9c4e0e7f572430e8baf9756dc24dab11d87b34bd202e
Status: Downloaded newer image for node:4.6
 ---> e834398209c1
Step 2/8 : RUN mkdir /naivechain
 ---> Running in 1ce7908843c5
Removing intermediate container 1ce7908843c5
 ---> c718f64fc76b
Step 3/8 : ADD package.json /naivechain/
 ---> c98eb64950a5
Step 4/8 : ADD main.js /naivechain/
ERROR: Service 'node1' failed to build: ADD failed: stat /var/lib/docker/tmp/docker-builder912311471/main.js: no such file or directory

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

# attmepting quickstart with docker 
# one thing I really don't like here : 
# the docker-ècompose is much too simple "to be true", especally it 
# lacks environement vairables, very bad sign for what is going to happen at runtime inside that box

docker-compose up
curl -H "Content-type:application/json" --data '{"data" : "Some data to the first block"}' http://localhost:3001/mineBlock

```


## Other tested repos 

* https://github.com/DemocracyEarth/sovereign


## Misc.


* https://github.com/pokusio/le-defi/raw/master/the-broken-list/democracy-earth/misc/embracing-innovation-in-government-colombia.pdf : there you will rad a whole lot of "data analysis", which obviously is supposed to look serious. Well, How serious/true can those data be, while I have those results on their "technology" ?


