```
PHLLMBP-SSCOLERI:~ stevenscoleri$ docker run -it --privileged -d docker:dind /bin/sh
a7b94acdad2c365dd0fa3df1c5fa9d867115f1c18bf5c7a19e5e4efc198b7dd3
PHLLMBP-SSCOLERI:~ stevenscoleri$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
a7b94acdad2c        docker:dind         "dockerd-entrypoint.…"   3 seconds ago       Up 2 seconds        2375/tcp            pedantic_cray
4e809f2df064        55a341bacc5a        "/bin/bash"              4 weeks ago         Up 12 days                              unruffled_wing
PHLLMBP-SSCOLERI:~ stevenscoleri$ docker kill pedantic_cray
pedantic_cray
PHLLMBP-SSCOLERI:~ stevenscoleri$
PHLLMBP-SSCOLERI:~ stevenscoleri$ docker run -it --entrypoint="/bin/sh" --privileged -d docker:dind
98a85b6fe2d5f5cc5fd240bc5786e090e70719ab1efb9bda5009fb3c65cd5683
PHLLMBP-SSCOLERI:~ stevenscoleri$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
98a85b6fe2d5        docker:dind         "/bin/sh"           3 seconds ago       Up 2 seconds        2375/tcp            cocky_murdock
4e809f2df064        55a341bacc5a        "/bin/bash"         4 weeks ago         Up 12 days                              unruffled_wing
PHLLMBP-SSCOLERI:~ stevenscoleri$ docker kill cocky_murdock
cocky_murdock
PHLLMBP-SSCOLERI:~ stevenscoleri$
PHLLMBP-SSCOLERI:~ stevenscoleri$
PHLLMBP-SSCOLERI:~ stevenscoleri$ docker run --privileged -d docker:dind
3415814e1dd5e1ee1b70cd7da015ca7aecc11ebdb5ce25f8dcd5dd07b0eb4f65
PHLLMBP-SSCOLERI:~ stevenscoleri$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
3415814e1dd5        docker:dind         "dockerd-entrypoint.…"   5 seconds ago       Up 5 seconds        2375/tcp            vibrant_villani
4e809f2df064        55a341bacc5a        "/bin/bash"              4 weeks ago         Up 12 days                              unruffled_wing
PHLLMBP-SSCOLERI:~ stevenscoleri$ docker exec -it vibrant_villani /bin/sh
/ # docker run --privileged -d docker:dind
Unable to find image 'docker:dind' locally
dind: Pulling from library/docker
169185f82c45: Pull complete
34c29055ee42: Pull complete
29802c64cdfc: Pull complete
bebe6d49c797: Pull complete
32d22b42c09e: Pull complete
c2c2284587d0: Pull complete
e92ceb70fb83: Pull complete
2e73e8c1bfd2: Pull complete
ee0b89129978: Pull complete
cf94363eed74: Pull complete
Digest: sha256:54cebe5015fbe725c29c203214120e8936f65fda5311c6f5e7c2e5037c0939a0
Status: Downloaded newer image for docker:dind
9ef70f9245b401b89197ebc132d8cf2bc6a3df05fd221317ed52997551a09412
/ # docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
9ef70f9245b4        docker:dind         "dockerd-entrypoint.…"   2 seconds ago       Up 2 seconds        2375/tcp            nervous_feynman
/ # docker exec -it nervous_feynman /bin/sh
/ # docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
/ # docker run --privileged -d docker:dind
Unable to find image 'docker:dind' locally
dind: Pulling from library/docker
169185f82c45: Pull complete
34c29055ee42: Pull complete
29802c64cdfc: Pull complete
bebe6d49c797: Pull complete
32d22b42c09e: Pull complete
c2c2284587d0: Pull complete
e92ceb70fb83: Pull complete
2e73e8c1bfd2: Pull complete
ee0b89129978: Pull complete
cf94363eed74: Pull complete
Digest: sha256:54cebe5015fbe725c29c203214120e8936f65fda5311c6f5e7c2e5037c0939a0
Status: Downloaded newer image for docker:dind
ef5547d2b211458af34e45368bbb3d87041a70932349eea96cc60e39678242c2
/ # docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
ef5547d2b211        docker:dind         "dockerd-entrypoint.…"   30 seconds ago      Up 28 seconds       2375/tcp            naughty_sanderson
/ # docker exec -it naughty_sanderson /bin/sh
/ # docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
/ #
