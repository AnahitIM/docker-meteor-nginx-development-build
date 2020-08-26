# docker-meteor-nginx-development-build

This is the templete for meteor-mango-nginx setup docker.


# How tag and push image.

Pre-requirments:
1. Down docker conatiners (e.g: $ docker-compose donw)
2. Remove old images (e.g: $ docker image prune -a)
3. Optional: docker system prune

Build docker images by running following:
1. docker-compose up --build

Show list of created images:
1. docker images
ex:
REPOSITORY                  TAG                 IMAGE ID            CREATED             SIZE
kerpak_nginx                latest              380516b4f7b6        2 minutes ago       20.4MB
kerpak_app                  latest              f3380790ee06        2 minutes ago       1.26GB
<none>                      <none>              b375d0c801a3        4 minutes ago       2.71GB
mongo                       latest              409c3f937574        6 days ago          493MB
geoffreybooth/meteor-base   1.10.2              418df408ec35        3 months ago        1.59GB
node                        12.16.1             88c089733a3b        4 months ago        916MB
nginx                       1.16.0-alpine       ef04b00b089d        15 months ago       20.4MB

Get the kerpak_app image id (e.g: f3380790ee06)

Tag docker image
1. docker tag {iamage-id} docker.pkg.github.com/{username}/{repo}/{docker-image-name}:{docker-image-version}
(ex: docker tag f3380790ee06 docker.pkg.github.com/mkhitar-h/docker-meteor-nginx-images/kerpak:0.0.3)

Push docker image
2. docker push docker.pkg.github.com/{username}/{repo}/{docker-image-name}:{docker-image-version}
(ex. docker.pkg.github.com/mkhitar-h/docker-meteor-nginx-images/kerpak:0.0.3) 
Note: be sure to increase docker image version

See https://github.com/mkhitar-h/docker-meteor-nginx-images/blob/master/README.md to how deploy in AWS server.
