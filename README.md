## headless-jd2-docker
## forked from https://hub.docker.com/r/plusminus/jdownloader2-headless/
## i fixed his privilege issue which requires the container to run as root
JDownloader 2 Headless Container with my.JDownloader.org Connection

## Things to in Order to get the best out of this Container
1. Create a folder on your host for the configuration files (eg. mkdir /config/jd2)
2. run `docker run -d --name jd2 -v /config/jd2:/opt/JDownloader/cfg -v /home/user/Downloads:/opt/downloads benst/jdownloader2-headless`
3. stop the container `docker stop jd2`
4. On your host, add your credentials to the file `org.jdownloader.api.myjdownloader.MyJDownloaderSettings.json` as in `{ "password" : "mypasswort", "email" : "email@home.org", }` and if you like your DeviceName `{  "devicename" : "foobar", }`
5. and change default Download Location in the file `org.jdownloader.settings.GeneralSettings.json` as in `{ "defaultdownloadfolder" : "/opt/downloads" }`
6. start the container `docker start jd2`
7. you can jump into the container with: `docker exec -it <containerName> bash` and then look into /opt/Jdownloader/logs it takes about one Minute to finish the extraction if your Webinterface needs a little Time before you see something
