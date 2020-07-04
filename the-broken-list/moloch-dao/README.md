# Just another one : Moloch "DAO" (Have become a Demon hunter...??)

Under test, here : 

* https://github.com/MolochVentures/moloch



## prepare my debian machine for a demon catch

* install `nodejs`, `npx`, `make` : 

```bash
# make
sudo apt-get install -y build-essential
# nodejs
curl -sL https://deb.nodesource.com/setup_14.x -o nodesource_setup.sh
sudo apt install -y nodejs
node --version
npm --version
# will fire up an eror, cause npx is brought with nodejs package
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
jbl@pc-alienware-jbl:~$ export OPS_HOME=~/hello.moloch
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ cd ~ 
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ if [ -d ${OPS_HOME} ]; then 
>   sudo rm -fr ${OPS_HOME}
> fi;
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ # https://github.com/MolochVentures/moloch/commit/7db370566a5d8c3bad3624700a4ca710c8cf35b4  is latest commit on the 4th of July, 2020
jbl@pc-alienware-jbl:~$ export VERSION_UNDER_TEST=7db370566a5d8c3bad3624700a4ca710c8cf35b4
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ git clone https://github.com/MolochVentures/moloch ${OPS_HOME}
Cloning into '/home/jbl/hello.moloch'...
remote: Enumerating objects: 2950, done.
remote: Total 2950 (delta 0), reused 0 (delta 0), pack-reused 2950
Receiving objects: 100% (2950/2950), 1.46 MiB | 0 bytes/s, done.
Resolving deltas: 100% (1977/1977), done.
jbl@pc-alienware-jbl:~$ 
jbl@pc-alienware-jbl:~$ cd ${OPS_HOME}
jbl@pc-alienware-jbl:~/hello.moloch$ git checkout ${VERSION_UNDER_TEST}
Note: checking out '7db370566a5d8c3bad3624700a4ca710c8cf35b4'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b <new-branch-name>

HEAD is now at 7db3705... Fix sol versions
jbl@pc-alienware-jbl:~/hello.moloch$ 
jbl@pc-alienware-jbl:~/hello.moloch$ npm i

> keccak@1.4.0 install /home/jbl/hello.moloch/node_modules/ganache-cli/node_modules/keccak
> npm run rebuild || echo "Keccak bindings compilation fail. Pure JS implementation will be used."


> keccak@1.4.0 rebuild /home/jbl/hello.moloch/node_modules/ganache-cli/node_modules/keccak
> node-gyp rebuild

make: Entering directory '/home/jbl/hello.moloch/node_modules/ganache-cli/node_modules/keccak/build'
  CXX(target) Release/obj.target/keccak/src/addon.o
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::Initialize(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:37:47: error: no matching function for call to ‘v8::Value::IntegerValue()’
     unsigned int rate = info[0]->IntegerValue();
                                               ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc:38:51: error: no matching function for call to ‘v8::Value::IntegerValue()’
     unsigned int capacity = info[1]->IntegerValue();
                                                   ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::AbsorbLastFewBits(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:56:48: error: no matching function for call to ‘v8::Value::IntegerValue()’
     unsigned char bits = info[0]->IntegerValue();
                                                ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::Squeeze(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:64:43: error: no matching function for call to ‘v8::Value::IntegerValue()’
     size_t length = info[0]->IntegerValue();
                                           ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::Copy(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:75:82: error: no matching function for call to ‘v8::Value::ToObject()’
     KeccakWrapper* to = Nan::ObjectWrap::Unwrap<KeccakWrapper>(info[0]->ToObject());
                                                                                  ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2818:44: note: candidate: v8::MaybeLocal<v8::Object> v8::Value::ToObject(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT MaybeLocal<Object> ToObject(
                                            ^~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2818:44: note:   candidate expects 1 argument, 0 provided
keccak.target.mk:129: recipe for target 'Release/obj.target/keccak/src/addon.o' failed
make: *** [Release/obj.target/keccak/src/addon.o] Error 1
make: Leaving directory '/home/jbl/hello.moloch/node_modules/ganache-cli/node_modules/keccak/build'
gyp ERR! build error 
gyp ERR! stack Error: `make` failed with exit code: 2
gyp ERR! stack     at ChildProcess.onExit (/usr/lib/node_modules/npm/node_modules/node-gyp/lib/build.js:194:23)
gyp ERR! stack     at ChildProcess.emit (events.js:314:20)
gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:276:12)
gyp ERR! System Linux 4.9.0-7-amd64
gyp ERR! command "/usr/bin/node" "/usr/lib/node_modules/npm/node_modules/node-gyp/bin/node-gyp.js" "rebuild"
gyp ERR! cwd /home/jbl/hello.moloch/node_modules/ganache-cli/node_modules/keccak
gyp ERR! node -v v14.5.0
gyp ERR! node-gyp -v v5.1.0
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
npm ERR!     /home/jbl/.npm/_logs/2020-07-04T15_30_42_544Z-debug.log
Keccak bindings compilation fail. Pure JS implementation will be used.

> secp256k1@3.7.1 install /home/jbl/hello.moloch/node_modules/ganache-cli/node_modules/secp256k1
> npm run rebuild || echo "Secp256k1 bindings compilation fail. Pure JS implementation will be used."


> secp256k1@3.7.1 rebuild /home/jbl/hello.moloch/node_modules/ganache-cli/node_modules/secp256k1
> node-gyp rebuild

make: Entering directory '/home/jbl/hello.moloch/node_modules/ganache-cli/node_modules/secp256k1/build'
  CXX(target) Release/obj.target/secp256k1/src/addon.o
  CXX(target) Release/obj.target/secp256k1/src/privatekey.o
../src/privatekey.cc: In function ‘Nan::NAN_METHOD_RETURN_TYPE privateKeyNegate(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/privatekey.cc:73:61: warning: ignoring return value of ‘int secp256k1_ec_privkey_negate(const secp256k1_context*, unsigned char*)’, declared with attribute warn_unused_result [-Wunused-result]
   secp256k1_ec_privkey_negate(secp256k1ctx, &private_key[0]);
                                                             ^
  CXX(target) Release/obj.target/secp256k1/src/publickey.o
  CXX(target) Release/obj.target/secp256k1/src/signature.o
  CXX(target) Release/obj.target/secp256k1/src/ecdsa.o
  CXX(target) Release/obj.target/secp256k1/src/ecdh.o
  CC(target) Release/obj.target/secp256k1/src/secp256k1-src/src/secp256k1.o
  CC(target) Release/obj.target/secp256k1/src/secp256k1-src/contrib/lax_der_parsing.o
  CC(target) Release/obj.target/secp256k1/src/secp256k1-src/contrib/lax_der_privatekey_parsing.o
  SOLINK_MODULE(target) Release/obj.target/secp256k1.node
  COPY Release/secp256k1.node
make: Leaving directory '/home/jbl/hello.moloch/node_modules/ganache-cli/node_modules/secp256k1/build'

> keccak@1.4.0 install /home/jbl/hello.moloch/node_modules/ethereumjs-block/node_modules/ethereumjs-util/node_modules/keccak
> npm run rebuild || echo "Keccak bindings compilation fail. Pure JS implementation will be used."


> keccak@1.4.0 rebuild /home/jbl/hello.moloch/node_modules/ethereumjs-block/node_modules/ethereumjs-util/node_modules/keccak
> node-gyp rebuild

make: Entering directory '/home/jbl/hello.moloch/node_modules/ethereumjs-block/node_modules/ethereumjs-util/node_modules/keccak/build'
  CXX(target) Release/obj.target/keccak/src/addon.o
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::Initialize(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:37:47: error: no matching function for call to ‘v8::Value::IntegerValue()’
     unsigned int rate = info[0]->IntegerValue();
                                               ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc:38:51: error: no matching function for call to ‘v8::Value::IntegerValue()’
     unsigned int capacity = info[1]->IntegerValue();
                                                   ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::AbsorbLastFewBits(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:56:48: error: no matching function for call to ‘v8::Value::IntegerValue()’
     unsigned char bits = info[0]->IntegerValue();
                                                ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::Squeeze(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:64:43: error: no matching function for call to ‘v8::Value::IntegerValue()’
     size_t length = info[0]->IntegerValue();
                                           ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::Copy(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:75:82: error: no matching function for call to ‘v8::Value::ToObject()’
     KeccakWrapper* to = Nan::ObjectWrap::Unwrap<KeccakWrapper>(info[0]->ToObject());
                                                                                  ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2818:44: note: candidate: v8::MaybeLocal<v8::Object> v8::Value::ToObject(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT MaybeLocal<Object> ToObject(
                                            ^~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2818:44: note:   candidate expects 1 argument, 0 provided
keccak.target.mk:129: recipe for target 'Release/obj.target/keccak/src/addon.o' failed
make: *** [Release/obj.target/keccak/src/addon.o] Error 1
make: Leaving directory '/home/jbl/hello.moloch/node_modules/ethereumjs-block/node_modules/ethereumjs-util/node_modules/keccak/build'
gyp ERR! build error 
gyp ERR! stack Error: `make` failed with exit code: 2
gyp ERR! stack     at ChildProcess.onExit (/usr/lib/node_modules/npm/node_modules/node-gyp/lib/build.js:194:23)
gyp ERR! stack     at ChildProcess.emit (events.js:314:20)
gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:276:12)
gyp ERR! System Linux 4.9.0-7-amd64
gyp ERR! command "/usr/bin/node" "/usr/lib/node_modules/npm/node_modules/node-gyp/bin/node-gyp.js" "rebuild"
gyp ERR! cwd /home/jbl/hello.moloch/node_modules/ethereumjs-block/node_modules/ethereumjs-util/node_modules/keccak
gyp ERR! node -v v14.5.0
gyp ERR! node-gyp -v v5.1.0
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
npm ERR!     /home/jbl/.npm/_logs/2020-07-04T15_30_50_903Z-debug.log
Keccak bindings compilation fail. Pure JS implementation will be used.

> keccak@2.1.0 install /home/jbl/hello.moloch/node_modules/ethereumjs-block/node_modules/keccak
> npm run rebuild || echo "Keccak bindings compilation fail. Pure JS implementation will be used."


> keccak@2.1.0 rebuild /home/jbl/hello.moloch/node_modules/ethereumjs-block/node_modules/keccak
> node-gyp rebuild

make: Entering directory '/home/jbl/hello.moloch/node_modules/ethereumjs-block/node_modules/keccak/build'
  CXX(target) Release/obj.target/keccak/src/addon.o
  CC(target) Release/obj.target/keccak/src/libkeccak-64/KeccakSpongeWidth1600.o
  CC(target) Release/obj.target/keccak/src/libkeccak-64/KeccakP-1600-opt64.o
  SOLINK_MODULE(target) Release/obj.target/keccak.node
  COPY Release/keccak.node
make: Leaving directory '/home/jbl/hello.moloch/node_modules/ethereumjs-block/node_modules/keccak/build'

> keccak@2.0.0 install /home/jbl/hello.moloch/node_modules/ethereumjs-util/node_modules/keccak
> npm run rebuild || echo "Keccak bindings compilation fail. Pure JS implementation will be used."


> keccak@2.0.0 rebuild /home/jbl/hello.moloch/node_modules/ethereumjs-util/node_modules/keccak
> node-gyp rebuild

make: Entering directory '/home/jbl/hello.moloch/node_modules/ethereumjs-util/node_modules/keccak/build'
  CXX(target) Release/obj.target/keccak/src/addon.o
  CC(target) Release/obj.target/keccak/src/libkeccak-64/KeccakSpongeWidth1600.o
  CC(target) Release/obj.target/keccak/src/libkeccak-64/KeccakP-1600-opt64.o
  SOLINK_MODULE(target) Release/obj.target/keccak.node
  COPY Release/keccak.node
make: Leaving directory '/home/jbl/hello.moloch/node_modules/ethereumjs-util/node_modules/keccak/build'

> keccak@1.4.0 install /home/jbl/hello.moloch/node_modules/keccak
> npm run rebuild || echo "Keccak bindings compilation fail. Pure JS implementation will be used."


> keccak@1.4.0 rebuild /home/jbl/hello.moloch/node_modules/keccak
> node-gyp rebuild

make: Entering directory '/home/jbl/hello.moloch/node_modules/keccak/build'
  CXX(target) Release/obj.target/keccak/src/addon.o
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::Initialize(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:37:47: error: no matching function for call to ‘v8::Value::IntegerValue()’
     unsigned int rate = info[0]->IntegerValue();
                                               ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc:38:51: error: no matching function for call to ‘v8::Value::IntegerValue()’
     unsigned int capacity = info[1]->IntegerValue();
                                                   ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::AbsorbLastFewBits(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:56:48: error: no matching function for call to ‘v8::Value::IntegerValue()’
     unsigned char bits = info[0]->IntegerValue();
                                                ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::Squeeze(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:64:43: error: no matching function for call to ‘v8::Value::IntegerValue()’
     size_t length = info[0]->IntegerValue();
                                           ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note: candidate: v8::Maybe<long int> v8::Value::IntegerValue(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT Maybe<int64_t> IntegerValue(
                                        ^~~~~~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2859:40: note:   candidate expects 1 argument, 0 provided
../src/addon.cc: In static member function ‘static Nan::NAN_METHOD_RETURN_TYPE KeccakWrapper::Copy(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/addon.cc:75:82: error: no matching function for call to ‘v8::Value::ToObject()’
     KeccakWrapper* to = Nan::ObjectWrap::Unwrap<KeccakWrapper>(info[0]->ToObject());
                                                                                  ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cc:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2818:44: note: candidate: v8::MaybeLocal<v8::Object> v8::Value::ToObject(v8::Local<v8::Context>) const
   V8_WARN_UNUSED_RESULT MaybeLocal<Object> ToObject(
                                            ^~~~~~~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:2818:44: note:   candidate expects 1 argument, 0 provided
keccak.target.mk:129: recipe for target 'Release/obj.target/keccak/src/addon.o' failed
make: *** [Release/obj.target/keccak/src/addon.o] Error 1
make: Leaving directory '/home/jbl/hello.moloch/node_modules/keccak/build'
gyp ERR! build error 
gyp ERR! stack Error: `make` failed with exit code: 2
gyp ERR! stack     at ChildProcess.onExit (/usr/lib/node_modules/npm/node_modules/node-gyp/lib/build.js:194:23)
gyp ERR! stack     at ChildProcess.emit (events.js:314:20)
gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:276:12)
gyp ERR! System Linux 4.9.0-7-amd64
gyp ERR! command "/usr/bin/node" "/usr/lib/node_modules/npm/node_modules/node-gyp/bin/node-gyp.js" "rebuild"
gyp ERR! cwd /home/jbl/hello.moloch/node_modules/keccak
gyp ERR! node -v v14.5.0
gyp ERR! node-gyp -v v5.1.0
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
npm ERR!     /home/jbl/.npm/_logs/2020-07-04T15_31_01_547Z-debug.log
Keccak bindings compilation fail. Pure JS implementation will be used.

> secp256k1@3.7.0 install /home/jbl/hello.moloch/node_modules/secp256k1
> npm run rebuild || echo "Secp256k1 bindings compilation fail. Pure JS implementation will be used."


> secp256k1@3.7.0 rebuild /home/jbl/hello.moloch/node_modules/secp256k1
> node-gyp rebuild

make: Entering directory '/home/jbl/hello.moloch/node_modules/secp256k1/build'
  CXX(target) Release/obj.target/secp256k1/src/addon.o
  CXX(target) Release/obj.target/secp256k1/src/privatekey.o
../src/privatekey.cc: In function ‘Nan::NAN_METHOD_RETURN_TYPE privateKeyNegate(Nan::NAN_METHOD_ARGS_TYPE)’:
../src/privatekey.cc:73:61: warning: ignoring return value of ‘int secp256k1_ec_privkey_negate(const secp256k1_context*, unsigned char*)’, declared with attribute warn_unused_result [-Wunused-result]
   secp256k1_ec_privkey_negate(secp256k1ctx, &private_key[0]);
                                                             ^
  CXX(target) Release/obj.target/secp256k1/src/publickey.o
  CXX(target) Release/obj.target/secp256k1/src/signature.o
  CXX(target) Release/obj.target/secp256k1/src/ecdsa.o
  CXX(target) Release/obj.target/secp256k1/src/ecdh.o
  CC(target) Release/obj.target/secp256k1/src/secp256k1-src/src/secp256k1.o
  CC(target) Release/obj.target/secp256k1/src/secp256k1-src/contrib/lax_der_parsing.o
  CC(target) Release/obj.target/secp256k1/src/secp256k1-src/contrib/lax_der_privatekey_parsing.o
  SOLINK_MODULE(target) Release/obj.target/secp256k1.node
  COPY Release/secp256k1.node
make: Leaving directory '/home/jbl/hello.moloch/node_modules/secp256k1/build'

> sha3@1.2.3 install /home/jbl/hello.moloch/node_modules/sha3
> node-gyp rebuild

make: Entering directory '/home/jbl/hello.moloch/node_modules/sha3/build'
  CXX(target) Release/obj.target/sha3/src/addon.o
../src/addon.cpp: In static member function ‘static void SHA3Hash::Init(Nan::ADDON_REGISTER_FUNCTION_ARGS_TYPE)’:
../src/addon.cpp:83:27: error: no matching function for call to ‘v8::Object::Set(v8::Local<v8::String>&, v8::Local<v8::Function>&)’
   target->Set(className, f);
                           ^
In file included from /home/jbl/.cache/node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cpp:1:
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:3666:37: note: candidate: v8::Maybe<bool> v8::Object::Set(v8::Local<v8::Context>, v8::Local<v8::Value>, v8::Local<v8::Value>)
   V8_WARN_UNUSED_RESULT Maybe<bool> Set(Local<Context> context,
                                     ^~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:3666:37: note:   candidate expects 3 arguments, 2 provided
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:3669:37: note: candidate: v8::Maybe<bool> v8::Object::Set(v8::Local<v8::Context>, uint32_t, v8::Local<v8::Value>)
   V8_WARN_UNUSED_RESULT Maybe<bool> Set(Local<Context> context, uint32_t index,
                                     ^~~
/home/jbl/.cache/node-gyp/14.5.0/include/node/v8.h:3669:37: note:   candidate expects 3 arguments, 2 provided
sha3.target.mk:115: recipe for target 'Release/obj.target/sha3/src/addon.o' failed
make: *** [Release/obj.target/sha3/src/addon.o] Error 1
make: Leaving directory '/home/jbl/hello.moloch/node_modules/sha3/build'
gyp ERR! build error 
gyp ERR! stack Error: `make` failed with exit code: 2
gyp ERR! stack     at ChildProcess.onExit (/usr/lib/node_modules/npm/node_modules/node-gyp/lib/build.js:194:23)
gyp ERR! stack     at ChildProcess.emit (events.js:314:20)
gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:276:12)
gyp ERR! System Linux 4.9.0-7-amd64
gyp ERR! command "/usr/bin/node" "/usr/lib/node_modules/npm/node_modules/node-gyp/bin/node-gyp.js" "rebuild"
gyp ERR! cwd /home/jbl/hello.moloch/node_modules/sha3
gyp ERR! node -v v14.5.0
gyp ERR! node-gyp -v v5.1.0
gyp ERR! not ok 
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! sha3@1.2.3 install: `node-gyp rebuild`
npm ERR! Exit status 1
npm ERR! 
npm ERR! Failed at the sha3@1.2.3 install script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR!     /home/jbl/.npm/_logs/2020-07-04T15_31_11_680Z-debug.log
jbl@pc-alienware-jbl:~/hello.moloch$ sudo npm i

> websocket@github:web3-js/WebSocket-Node#905deb4812572b344f5801f8c9ce8bb02799d82e install /home/jbl/hello.moloch/node_modules/@nomiclabs/truffle-contract/node_modules/web3-providers-ws/node_modules/websocket
> (node-gyp rebuild 2> builderror.log) || (exit 0)

make: Entering directory '/home/jbl/hello.moloch/node_modules/@nomiclabs/truffle-contract/node_modules/web3-providers-ws/node_modules/websocket/build'
  CXX(target) Release/obj.target/bufferutil/src/bufferutil.o
bufferutil.target.mk:112: recipe for target 'Release/obj.target/bufferutil/src/bufferutil.o' failed
make: Leaving directory '/home/jbl/hello.moloch/node_modules/@nomiclabs/truffle-contract/node_modules/web3-providers-ws/node_modules/websocket/build'

> websocket@github:web3-js/WebSocket-Node#905deb4812572b344f5801f8c9ce8bb02799d82e install /home/jbl/hello.moloch/node_modules/@truffle/interface-adapter/node_modules/web3-providers-ws/node_modules/websocket
> (node-gyp rebuild 2> builderror.log) || (exit 0)

make: Entering directory '/home/jbl/hello.moloch/node_modules/@truffle/interface-adapter/node_modules/web3-providers-ws/node_modules/websocket/build'
  CXX(target) Release/obj.target/bufferutil/src/bufferutil.o
bufferutil.target.mk:112: recipe for target 'Release/obj.target/bufferutil/src/bufferutil.o' failed
make: Leaving directory '/home/jbl/hello.moloch/node_modules/@truffle/interface-adapter/node_modules/web3-providers-ws/node_modules/websocket/build'

> sha3@1.2.3 install /home/jbl/hello.moloch/node_modules/sha3
> node-gyp rebuild

gyp WARN EACCES current user ("jbl") does not have permission to access the dev dir "/root/.cache/node-gyp/14.5.0"
gyp WARN EACCES attempting to reinstall using temporary dev dir "/home/jbl/hello.moloch/node_modules/sha3/.node-gyp"
make: Entering directory '/home/jbl/hello.moloch/node_modules/sha3/build'
  CXX(target) Release/obj.target/sha3/src/addon.o
../src/addon.cpp: In static member function ‘static void SHA3Hash::Init(Nan::ADDON_REGISTER_FUNCTION_ARGS_TYPE)’:
../src/addon.cpp:83:27: error: no matching function for call to ‘v8::Object::Set(v8::Local<v8::String>&, v8::Local<v8::Function>&)’
   target->Set(className, f);
                           ^
In file included from /home/jbl/hello.moloch/node_modules/sha3/.node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cpp:1:
/home/jbl/hello.moloch/node_modules/sha3/.node-gyp/14.5.0/include/node/v8.h:3666:37: note: candidate: v8::Maybe<bool> v8::Object::Set(v8::Local<v8::Context>, v8::Local<v8::Value>, v8::Local<v8::Value>)
   V8_WARN_UNUSED_RESULT Maybe<bool> Set(Local<Context> context,
                                     ^~~
/home/jbl/hello.moloch/node_modules/sha3/.node-gyp/14.5.0/include/node/v8.h:3666:37: note:   candidate expects 3 arguments, 2 provided
/home/jbl/hello.moloch/node_modules/sha3/.node-gyp/14.5.0/include/node/v8.h:3669:37: note: candidate: v8::Maybe<bool> v8::Object::Set(v8::Local<v8::Context>, uint32_t, v8::Local<v8::Value>)
   V8_WARN_UNUSED_RESULT Maybe<bool> Set(Local<Context> context, uint32_t index,
                                     ^~~
/home/jbl/hello.moloch/node_modules/sha3/.node-gyp/14.5.0/include/node/v8.h:3669:37: note:   candidate expects 3 arguments, 2 provided
sha3.target.mk:115: recipe for target 'Release/obj.target/sha3/src/addon.o' failed
make: *** [Release/obj.target/sha3/src/addon.o] Error 1
make: Leaving directory '/home/jbl/hello.moloch/node_modules/sha3/build'
gyp ERR! build error 
gyp ERR! stack Error: `make` failed with exit code: 2
gyp ERR! stack     at ChildProcess.onExit (/usr/lib/node_modules/npm/node_modules/node-gyp/lib/build.js:194:23)
gyp ERR! stack     at ChildProcess.emit (events.js:314:20)
gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:276:12)
gyp ERR! System Linux 4.9.0-7-amd64
gyp ERR! command "/usr/bin/node" "/usr/lib/node_modules/npm/node_modules/node-gyp/bin/node-gyp.js" "rebuild"
gyp ERR! cwd /home/jbl/hello.moloch/node_modules/sha3
gyp ERR! node -v v14.5.0
gyp ERR! node-gyp -v v5.1.0
gyp ERR! not ok 
npm WARN ajv-keywords@2.1.1 requires a peer of ajv@^5.0.0 but none is installed. You must install peer dependencies yourself.
npm WARN eslint-plugin-prettier@3.1.2 requires a peer of prettier@>= 1.13.0 but none is installed. You must install peer dependencies yourself.
npm WARN eslint-plugin-react@7.7.0 requires a peer of eslint@^3.0.0 || ^4.0.0 but none is installed. You must install peer dependencies yourself.

npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! sha3@1.2.3 install: `node-gyp rebuild`
npm ERR! Exit status 1
npm ERR! 
npm ERR! Failed at the sha3@1.2.3 install script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR!     /root/.npm/_logs/2020-07-04T15_31_32_937Z-debug.log
jbl@pc-alienware-jbl:~/hello.moloch$ sudo apt-get install -y build-essentials
Reading package lists... Done
Building dependency tree       
Reading state information... Done
N: Ignoring file 'web-browser-opera.list.deprecated' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
E: Unable to locate package build-essentials
jbl@pc-alienware-jbl:~/hello.moloch$ sudo apt-get install -y build-essential
Reading package lists... Done
Building dependency tree       
Reading state information... Done
build-essential is already the newest version (12.3).
0 upgraded, 0 newly installed, 0 to remove and 10 not upgraded.
N: Ignoring file 'web-browser-opera.list.deprecated' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
jbl@pc-alienware-jbl:~/hello.moloch$ sudo apt-get install -y build-essential
Reading package lists... Done
Building dependency tree       
Reading state information... Done
build-essential is already the newest version (12.3).
0 upgraded, 0 newly installed, 0 to remove and 10 not upgraded.
N: Ignoring file 'web-browser-opera.list.deprecated' in directory '/etc/apt/sources.list.d/' as it has an invalid filename extension
jbl@pc-alienware-jbl:~/hello.moloch$ make -v
GNU Make 4.1
Built for x86_64-pc-linux-gnu
Copyright (C) 1988-2014 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
jbl@pc-alienware-jbl:~/hello.moloch$ sudo npm i

> websocket@github:web3-js/WebSocket-Node#905deb4812572b344f5801f8c9ce8bb02799d82e install /home/jbl/hello.moloch/node_modules/@nomiclabs/truffle-contract/node_modules/web3-providers-ws/node_modules/websocket
> (node-gyp rebuild 2> builderror.log) || (exit 0)

make: Entering directory '/home/jbl/hello.moloch/node_modules/@nomiclabs/truffle-contract/node_modules/web3-providers-ws/node_modules/websocket/build'
  CXX(target) Release/obj.target/bufferutil/src/bufferutil.o
bufferutil.target.mk:112: recipe for target 'Release/obj.target/bufferutil/src/bufferutil.o' failed
make: Leaving directory '/home/jbl/hello.moloch/node_modules/@nomiclabs/truffle-contract/node_modules/web3-providers-ws/node_modules/websocket/build'

> websocket@github:web3-js/WebSocket-Node#905deb4812572b344f5801f8c9ce8bb02799d82e install /home/jbl/hello.moloch/node_modules/@truffle/interface-adapter/node_modules/web3-providers-ws/node_modules/websocket
> (node-gyp rebuild 2> builderror.log) || (exit 0)

make: Entering directory '/home/jbl/hello.moloch/node_modules/@truffle/interface-adapter/node_modules/web3-providers-ws/node_modules/websocket/build'
  CXX(target) Release/obj.target/bufferutil/src/bufferutil.o
bufferutil.target.mk:112: recipe for target 'Release/obj.target/bufferutil/src/bufferutil.o' failed
make: Leaving directory '/home/jbl/hello.moloch/node_modules/@truffle/interface-adapter/node_modules/web3-providers-ws/node_modules/websocket/build'

> sha3@1.2.3 install /home/jbl/hello.moloch/node_modules/sha3
> node-gyp rebuild

gyp WARN EACCES current user ("jbl") does not have permission to access the dev dir "/root/.cache/node-gyp/14.5.0"
gyp WARN EACCES attempting to reinstall using temporary dev dir "/home/jbl/hello.moloch/node_modules/sha3/.node-gyp"
make: Entering directory '/home/jbl/hello.moloch/node_modules/sha3/build'
  CXX(target) Release/obj.target/sha3/src/addon.o
../src/addon.cpp: In static member function ‘static void SHA3Hash::Init(Nan::ADDON_REGISTER_FUNCTION_ARGS_TYPE)’:
../src/addon.cpp:83:27: error: no matching function for call to ‘v8::Object::Set(v8::Local<v8::String>&, v8::Local<v8::Function>&)’
   target->Set(className, f);
                           ^
In file included from /home/jbl/hello.moloch/node_modules/sha3/.node-gyp/14.5.0/include/node/node.h:67:0,
                 from ../src/addon.cpp:1:
/home/jbl/hello.moloch/node_modules/sha3/.node-gyp/14.5.0/include/node/v8.h:3666:37: note: candidate: v8::Maybe<bool> v8::Object::Set(v8::Local<v8::Context>, v8::Local<v8::Value>, v8::Local<v8::Value>)
   V8_WARN_UNUSED_RESULT Maybe<bool> Set(Local<Context> context,
                                     ^~~
/home/jbl/hello.moloch/node_modules/sha3/.node-gyp/14.5.0/include/node/v8.h:3666:37: note:   candidate expects 3 arguments, 2 provided
/home/jbl/hello.moloch/node_modules/sha3/.node-gyp/14.5.0/include/node/v8.h:3669:37: note: candidate: v8::Maybe<bool> v8::Object::Set(v8::Local<v8::Context>, uint32_t, v8::Local<v8::Value>)
   V8_WARN_UNUSED_RESULT Maybe<bool> Set(Local<Context> context, uint32_t index,
                                     ^~~
/home/jbl/hello.moloch/node_modules/sha3/.node-gyp/14.5.0/include/node/v8.h:3669:37: note:   candidate expects 3 arguments, 2 provided
sha3.target.mk:115: recipe for target 'Release/obj.target/sha3/src/addon.o' failed
make: *** [Release/obj.target/sha3/src/addon.o] Error 1
make: Leaving directory '/home/jbl/hello.moloch/node_modules/sha3/build'
gyp ERR! build error 
gyp ERR! stack Error: `make` failed with exit code: 2
gyp ERR! stack     at ChildProcess.onExit (/usr/lib/node_modules/npm/node_modules/node-gyp/lib/build.js:194:23)
gyp ERR! stack     at ChildProcess.emit (events.js:314:20)
gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:276:12)
gyp ERR! System Linux 4.9.0-7-amd64
gyp ERR! command "/usr/bin/node" "/usr/lib/node_modules/npm/node_modules/node-gyp/bin/node-gyp.js" "rebuild"
gyp ERR! cwd /home/jbl/hello.moloch/node_modules/sha3
gyp ERR! node -v v14.5.0
gyp ERR! node-gyp -v v5.1.0
gyp ERR! not ok 
npm WARN ajv-keywords@2.1.1 requires a peer of ajv@^5.0.0 but none is installed. You must install peer dependencies yourself.
npm WARN eslint-plugin-prettier@3.1.2 requires a peer of prettier@>= 1.13.0 but none is installed. You must install peer dependencies yourself.
npm WARN eslint-plugin-react@7.7.0 requires a peer of eslint@^3.0.0 || ^4.0.0 but none is installed. You must install peer dependencies yourself.

npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! sha3@1.2.3 install: `node-gyp rebuild`
npm ERR! Exit status 1
npm ERR! 
npm ERR! Failed at the sha3@1.2.3 install script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR!     /root/.npm/_logs/2020-07-04T15_32_54_080Z-debug.log
jbl@pc-alienware-jbl:~/hello.moloch$ 
```

## Funny little detail (the devil is found into details)

Those Moloch errors, above, are compile time erros, and really look like Democracy Earth 's so called "Sovereign" software, see : 

* go to [this page where I dissect Democracyu Earth 's `sovereign` software](https://github.com/pokusio/le-defi/blob/master/the-broken-list/democracy-earth/README.md)
* and `Ctrl + F` the string `gyp ERR! stack Error: `make` failed with exit code: 2` ... Funny, hum ? 



One less demon in this world.




And time to go back to real projects.
