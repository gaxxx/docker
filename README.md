# docker
docker hub binding

# dockerhub 

create repos in dockerhub
![docker repos](https://github.com/gaxxx/docker/raw/master/snapshots/docker-repo.png)


# github setting

create directories with the same name of repos in dockerhub
![github repos](https://github.com/gaxxx/docker/raw/master/snapshots/github.png)

# setup

1. dockerHub setup
	for echo repo
	setup rules like this
	![github repos](https://github.com/gaxxx/docker/raw/master/snapshots/autobuild.png)

2. github  setup
	* create Dockerfile in each directory and make sure it works
	* create tags to trigger tag build in dockerhub

		```
			// add a tag for toolbox 
			git tag toolbox-v0.1
			// push to make it run
			git push origin tags
			
		```

	* push to release branch to trigger release build in dockerhub
		
		```
			// create release for toolbox if not present
			git branch release-toolbox
			// checkout to release branch
			git checkout release-toolbox
			// merge from master
			git merge master
			// push to build, maybe you need to setup upstream
			git push
		```

3. have fun
![github repos](https://github.com/gaxxx/docker/raw/master/snapshots/build.png)
