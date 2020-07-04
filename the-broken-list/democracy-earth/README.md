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

# https://github.com/DemocracyEarth/blockchain/commit/6573d3ebdace5914e36457c14632d890bb03a14a  is latest commit on July, the 4th
export VERSION_UNDER_TEST=6573d3ebdace5914e36457c14632d890bb03a14a

git clone https://github.com/DemocracyEarth/blockchain ${OPS_HOME}

cd ${OPS_HOME}

# following quickstart with docker
docker-compose up
curl -H "Content-type:application/json" --data '{"data" : "Some data to the first block"}' http://localhost:3001/mineBlock

```



