# sample-web-server
テクノロジー（藤原）Node.jsによるサンプルWebサーバ

```
MacBook-Pro-2:fujiwara yutonagao$ git clone git@github.com:YutoNagao/sample-web-server.git
Cloning into 'sample-web-server'...
remote: Enumerating objects: 7, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 7 (delta 1), reused 5 (delta 1), pack-reused 0
Receiving objects: 100% (7/7), done.
Resolving deltas: 100% (1/1), done.
MacBook-Pro-2:fujiwara yutonagao$ cd sample-web-server/
MacBook-Pro-2:sample-web-server yutonagao$ code .
MacBook-Pro-2:sample-web-server yutonagao$ curl --silent --request GET --url https://api.thecatapi.com/v1/images/search
[{"breeds":[],"id":"bv0","url":"https://cdn2.thecatapi.com/images/bv0.jpg","width":4608,"height":3072}]MacBook-Pro-2:sample-web-server yutonagao$ curl --silent tps://api.thecatapi.com/v1/images/search?limit=3'
[{"breeds":[],"id":"ani","url":"https://cdn2.thecatapi.com/images/ani.jpg","width":1936,"height":2592},{"breeds":[],"id":"i5Bw5V_HM","url":"https://cdn2.thecatapi.com/images/i5Bw5V_HM.jpg","width":3024,"height":4032},{"breeds":[{"weight":{"imperial":"7 - 15","metric":"3 - 7"},"id":"toyg","name":"Toyger","vetstreet_url":"http://www.vetstreet.com/cats/toyger","temperament":"Playful, Social, Intelligent","origin":"United States","country_codes":"US","country_code":"US","description":"The Toyger has a sweet, calm personality and is generally friendly. He's outgoing enough to walk on a leash, energetic enough to play fetch and other interactive games, and confident enough to get along with other cats and friendly dogs.","life_span":"12 - 15","indoor":0,"lap":1,"alt_names":"","adaptability":5,"affection_level":5,"child_friendly":4,"dog_friendly":5,"energy_level":5,"grooming":1,"health_issues":2,"intelligence":5,"shedding_level":3,"social_needs":3,"stranger_friendly":5,"vocalisation":5,"experimental":0,"hairless":0,"natural":0,"rare":0,"rex":0,"suppressed_tail":0,"short_legs":0,"wikipedia_url":"https://en.wikipedia.org/wiki/Toyger","hypoallergenic":0}],"id":"O3F3_S1XN","url":"https://cdn2.thecatapi.com/images/O3F3_S1XN.jpg","width":1080,"height":1080}]MacBook-Pro-2:sample-web-server yutonagao$ brew install jq
Updating Homebrew...
==> Auto-updated Homebrew!
Updated 2 taps (homebrew/core and homebrew/cask).
==> New Formulae
swig@3
==> Updated Formulae
pyenv ✔             gibo                lmod                scons
aws-sdk-cpp         glib                mighttpd2           scrcpy
braid               glooctl             minio               ship
calicoctl           gmic                minio-mc            sops
certbot             graph-tool          nomad               telegraf
chakra              gst-plugins-good    opa                 terraform
circleci            hlint               paket               topgrade
envconsul           imagemagick         phpunit             vultr
exiftool            jdupes              procs               webpack
firebase-cli        jfrog-cli-go        pulumi              whois
flow                joplin              pybind11            wildfly-as
fluxctl             knot                rbspy               wtf
folly               libev               scalariform         yelp-tools
==> Deleted Formulae
swig@3.04

==> Installing dependencies for jq: oniguruma
==> Installing jq dependency: oniguruma
==> Downloading https://homebrew.bintray.com/bottles/oniguruma-6.9.2.mojave.bott
==> Downloading from https://akamai.bintray.com/c6/c613befafe81da48913ebd1a7eb03
######################################################################## 100.0%
==> Pouring oniguruma-6.9.2.mojave.bottle.tar.gz
🍺  /usr/local/Cellar/oniguruma/6.9.2: 17 files, 1.3MB
==> Installing jq
==> Downloading https://homebrew.bintray.com/bottles/jq-1.6.mojave.bottle.1.tar.
==> Downloading from https://akamai.bintray.com/71/71f0e76c5b22e5088426c971d5e79
######################################################################## 100.0%
==> Pouring jq-1.6.mojave.bottle.1.tar.gz
🍺  /usr/local/Cellar/jq/1.6: 18 files, 1MB
MacBook-Pro-2:sample-web-server yutonagao$ curl --silent --request GET --url 'https://api.thecatapi.com/v1/images/search?limit=3' | jq
[
  {
    "breeds": [],
    "id": "9hg",
    "url": "https://cdn2.thecatapi.com/images/9hg.jpg",
    "width": 600,
    "height": 434
  },
  {
    "breeds": [],
    "id": "c9m",
    "url": "https://cdn2.thecatapi.com/images/c9m.jpg",
    "width": 640,
    "height": 427
  },
  {
    "breeds": [],
    "id": "MTgxNjQ2OQ",
    "url": "https://cdn2.thecatapi.com/images/MTgxNjQ2OQ.jpg",
    "width": 642,
    "height": 386
  }
]
MacBook-Pro-2:sample-web-server yutonagao$ curl --silent --request GET --url 'https://api.thecatapi.com/v1/images/search?limit=3' > thecat.json
MacBook-Pro-2:sample-web-server yutonagao$ cd ..
MacBook-Pro-2:~ yutonagao$ npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (yutonagao) 
version: (1.0.0) 
description: 
git repository: 
keywords: 
author: 
license: (ISC) 
About to write to /Users/yutonagao/package.json:

{
  "name": "yutonagao",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC",
  "description": ""
}


Is this OK? (yes) 
MacBook-Pro-2:~ yutonagao$ npm install --save express
npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN yutonagao@1.0.0 No description
npm WARN yutonagao@1.0.0 No repository field.

+ express@4.17.1
added 50 packages from 37 contributors and audited 126 packages in 3.591s
found 0 vulnerabilities

MacBook-Pro-2:fujiwara yutonagao$ cd sample-web-server
MacBook-Pro-2:sample-web-server yutonagao$ mkdir mywebapi
MacBook-Pro-2:sample-web-server yutonagao$ cd mywebapi/
MacBook-Pro-2:mywebapi yutonagao$ vi index.js
MacBook-Pro-2:mywebapi yutonagao$ ls
index.js
MacBook-Pro-2:mywebapi yutonagao$ node index.js
Listening on port 3000
^C
MacBook-Pro-2:mywebapi yutonagao$ vi index.js 
MacBook-Pro-2:mywebapi yutonagao$ node index.js 
Listening on port 3000
^C
MacBook-Pro-2:mywebapi yutonagao$ vi index.js 
MacBook-Pro-2:mywebapi yutonagao$ mkdir web
MacBook-Pro-2:mywebapi yutonagao$ cd web/
MacBook-Pro-2:web yutonagao$ vi index.html
MacBook-Pro-2:web yutonagao$ cd ..
MacBook-Pro-2:mywebapi yutonagao$ node index.js
Listening on port 3000
^C


```
