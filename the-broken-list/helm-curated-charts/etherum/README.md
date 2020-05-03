# Issue on repo

# Means to reproduce the bug

```bash 
jbl@poste-devops-jbl-16gbram:~$ helm version
version.BuildInfo{Version:"v3.2.0", GitCommit:"e11b7ce3b12db2941e90399e874513fbd24bcb71", GitTreeState:"clean", GoVersion:"go1.13.10"}
jbl@poste-devops-jbl-16gbram:~$ export KUBECONFIG=~/.petit.kube/.kube/config 
jbl@poste-devops-jbl-16gbram:~$ git clone git@github.com:helm/charts.git  helm-ethereum
Cloning into 'helm-ethereum'...
remote: Enumerating objects: 105973, done.
remote: Total 105973 (delta 0), reused 0 (delta 0), pack-reused 105973
Receiving objects: 100% (105973/105973), 28.94 MiB | 17.67 MiB/s, done.
Resolving deltas: 100% (79109/79109), done.
jbl@poste-devops-jbl-16gbram:~$ cd helm-ethereum/
jbl@poste-devops-jbl-16gbram:~/helm-ethereum$ cd stable/
jbl@poste-devops-jbl-16gbram:~/helm-ethereum/stable$ ls -allh |ether
bash: ether: command not found
jbl@poste-devops-jbl-16gbram:~/helm-ethereum/stable$ ls -allh |grep ether
drwxr-xr-x   5 jbl jbl 4.0K May  3 07:39 ethereum
jbl@poste-devops-jbl-16gbram:~/helm-ethereum/stable$ cd ethereum/
jbl@poste-devops-jbl-16gbram:~/helm-ethereum/stable/ethereum$ helm package .
Successfully packaged chart and saved it to: /home/jbl/helm-ethereum/stable/ethereum/ethereum-1.0.0.tgz
jbl@poste-devops-jbl-16gbram:~/helm-ethereum/stable/ethereum$ helm install /home/jbl/helm-ethereum/stable/ethereum/ethereum-1.0.0.tgz
Error: must either provide a name or specify --generate-name
jbl@poste-devops-jbl-16gbram:~/helm-ethereum/stable/ethereum$ helm install bleublancrouge /home/jbl/helm-ethereum/stable/ethereum/ethereum-1.0.0.tgz
Error: unable to build kubernetes objects from release manifest: unable to recognize "": no matches for kind "Deployment" in version "apps/v1beta2"
jbl@poste-devops-jbl-16gbram:~/helm-ethereum/stable/ethereum$ git remote -v
origin	git@github.com:helm/charts.git (fetch)
origin	git@github.com:helm/charts.git (push)
jbl@poste-devops-jbl-16gbram:~/helm-ethereum/stable/ethereum$ git tag -ln
jbl@poste-devops-jbl-16gbram:~/helm-ethereum/stable/ethereum$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/ambassador-helm3-support-crds
  remotes/origin/master
  remotes/origin/pr-template-note-deprecation-timeline
  remotes/origin/revert-10682-master
  remotes/origin/stable-incubator-deprecation-timeline
  remotes/origin/update-deprecation-timeline-covid-19
  remotes/origin/update-owners
jbl@poste-devops-jbl-16gbram:~/helm-ethereum/stable/ethereum$ git log --name-status HEAD^..HEAD
commit 6743d8e9b2c689644e7424dc60ceccbb2ac911d8
Author: Ben Klang <bklang@powerhrg.com>
Date:   Sat May 2 07:34:25 2020 -0400

    Remove broken attempt to mute logging of assets (#22197)
    
    These (commented) lines in `values.yaml` are the recommended ingress settings. It appears to be an attempt to reduce logging noise. Unfortunately it has the side effect of breaking image uploads & downloads from Nextcloud. This was documented in issue #16860, and specifically [this comment](https://github.com/helm/charts/issues/16860#issuecomment-538244349). I had the same issue as reported, and removing these lines made it so image uploads/downloads work as expected.
    
    Signed-off-by: Ben Klang <bklang@powerhrg.com>

M       stable/nextcloud/Chart.yaml
M       stable/nextcloud/values.yaml
jbl@poste-devops-jbl-16gbram:~/helm-ethereum/stable/ethereum$ date
Sun May  3 08:46:03 CEST 2020

```
