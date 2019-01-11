**Exercise 1.1.**

:~ $ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
:~ $ docker run -d nginx
4ec2625f0e10e1b7e7540880b06dfeca31b93b3137d59876d6f5cd7828a59804
:~ $ docker run -d nginx
6c3f225f117444fc49f09ca4824d7771b6cda494156f1e138c8739437351e5a4
:~ $ docker run -d nginx
43181e2bb8136bb7547db2ea1825c186393db5470ba051698053865ee262c299
:~ $ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
43181e2bb813        nginx               "nginx -g 'daemon of…"   26 seconds ago      Up 25 seconds       80/tcp              determined_cohen
6c3f225f1174        nginx               "nginx -g 'daemon of…"   29 seconds ago      Up 28 seconds       80/tcp              lucid_ptolemy
4ec2625f0e10        nginx               "nginx -g 'daemon of…"   34 seconds ago      Up 32 seconds       80/tcp              hardcore_newton
:~ $ docker stop 4318 6c3f
4318
6c3f
:~ $ docker rm 4318 6c3f
4318
6c3f
:~ $ docker ps -a
CONTAINER ID        IMAGE                 COMMAND                  CREATED             STATUS                      PORTS               NAMES
4ec2625f0e10        nginx                 "nginx -g 'daemon of…"   2 minutes ago       Up 2 minutes                80/tcp              hardcore_newton
83772f5364c4        nginx                 "nginx -g 'daemon of…"   12 minutes ago      Exited (0) 12 minutes ago                       quizzical_lichterman
d10070e3dc91        weatherapp_frontend   "npm start"              10 months ago       Exited (0) 10 months ago                        weatherapp_frontend_1
b9d01910526f        weatherapp_backend    "npm start"              10 months ago       Exited (0) 10 months ago                        weatherapp_backend_1
:~ $ docker stop 8377
8377
:~ $ docker rm 8377
8377
:~ $ docker ps -a
CONTAINER ID        IMAGE                 COMMAND                  CREATED             STATUS                     PORTS               NAMES
4ec2625f0e10        nginx                 "nginx -g 'daemon of…"   5 minutes ago       Up 5 minutes               80/tcp              hardcore_newton
d10070e3dc91        weatherapp_frontend   "npm start"              10 months ago       Exited (0) 10 months ago                       weatherapp_frontend_1
b9d01910526f        weatherapp_backend    "npm start"              10 months ago       Exited (0) 10 months ago                       weatherapp_backend_1
:~ $ 


**Exercise 1.2.**

:~ $ docker images
REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
nginx                 latest              7042885a156a        5 days ago          109MB
weatherapp_backend    latest              400d69f74761        10 months ago       705MB
weatherapp_frontend   latest              b61be4883cf1        10 months ago       731MB
<none>                <none>              9887522be8c8        10 months ago       705MB
<none>                <none>              90425fef6bd4        10 months ago       705MB
<none>                <none>              96de08a2c0e5        10 months ago       731MB
<none>                <none>              6c118f4633b3        10 months ago       705MB
<none>                <none>              4b44aa254dc5        10 months ago       731MB
<none>                <none>              11af70cc907a        10 months ago       705MB
<none>                <none>              c2a79b3c1385        10 months ago       705MB
<none>                <none>              aeb0d0778d95        10 months ago       705MB
<none>                <none>              1876e72de3a7        10 months ago       705MB
<none>                <none>              e36883a18269        10 months ago       705MB
<none>                <none>              2af3a3cf4bc5        10 months ago       705MB
<none>                <none>              2d876cd85370        10 months ago       705MB
<none>                <none>              cb0c5fa16644        10 months ago       705MB
<none>                <none>              9fba5176c04f        10 months ago       705MB
<none>                <none>              72af2bfd2857        10 months ago       731MB
node                  8.9.4               b87c2ad8344d        12 months ago       676MB
:~ $ docker ps -a
CONTAINER ID        IMAGE                 COMMAND                  CREATED             STATUS                     PORTS               NAMES
4ec2625f0e10        nginx                 "nginx -g 'daemon of…"   10 minutes ago      Up 10 minutes              80/tcp              hardcore_newton
d10070e3dc91        weatherapp_frontend   "npm start"              10 months ago       Exited (0) 10 months ago                       weatherapp_frontend_1
b9d01910526f        weatherapp_backend    "npm start"              10 months ago       Exited (0) 10 months ago                       weatherapp_backend_1
:~ $ docker image prune -a
WARNING! This will remove all images without at least one container associated to them.
Are you sure you want to continue? [y/N] y
Deleted Images:
deleted: sha256:e36883a1826992947c834b3e6b5821f77197b7a26cba39f0bb301bcb5ec12d04
deleted: sha256:04ea35ee6ab511d981126fe0a47404f8592b92cd70744e1ce41f3d311d9d97bb
deleted: sha256:6bdd0f0a8a476edd363b2c0f1e33518957680ae6bdcf75b2fa25260bb35df0ac
deleted: sha256:e8c0d103d7a2449e12fc38945ddbea5a244c10c710db9653f06fef5a6dc27be2
deleted: sha256:2d876cd853708e66f1378088c3dccfbaefb082d91adc32c665e86df274cbee36
deleted: sha256:b8af24d028525ac2e7ac062d5f1fd3ef72abd18d7ef54e862100ccc5481244f7
deleted: sha256:595141023de18f7c74f4b10200bf7cb160d35612c43ef168f2551c79ced1b84f
deleted: sha256:2ec5c8a768c5ac0766860d2c912d60666bf5d19aafdf00327e396bd954b3a4cb
deleted: sha256:90425fef6bd4c486e7a3b47482b05afb3f5dea3be4227157dc84986b509eb457
deleted: sha256:0e392c973216e4744b8a92cae973fb5c0acbca515845604e2c26c35d062b4461
deleted: sha256:2cdf941198c743361573dbeffdce509d5d2aca76838ce730052709f8d7397498
deleted: sha256:7f4505e1883022c7bc1b95df272ea268cd3f5b18f60d81eaf95301f106917f35
deleted: sha256:4b44aa254dc56f55a538c963dda6151d4e6a932861c0f23d5fa66cc33b7635e5
deleted: sha256:e01d7b9cd27f9031ad44a134d7144d9d8fb6a6462eb17893ae14c4cb0162927e
deleted: sha256:785f65f2ff9673a8d71084307f28abd0bece2091b2c6742accca3b22c0c6036d
deleted: sha256:831dc7c40259f4ab45d50f8b757c6c0ae55a1a4e43a3e711b6cf61027b1e7712
deleted: sha256:af020a24bf8db4c9b97c046d42d46871b30465a7af409bfd7cc68b06506e0558
deleted: sha256:dadd0b46b0b19b7b41fd55b948c738060734402c98d424dccbaa07e1aaf6ab71
deleted: sha256:9887522be8c8fa84d7c164a0e499f83d79d442fc926ab8232fc3299456cb686c
deleted: sha256:41bce90eacb8ea95504fd480cbd6ae67c0fdbefa1dac5587d0b3c6cb16703475
deleted: sha256:52515ee290d9118e87864113f76537521e80a3b9d94230cd85f90d48e916e024
deleted: sha256:3ba7545579e624fa9e27161bff0199a56ab182fd7de029c3cdb9fbc892d99b81
deleted: sha256:aeb0d0778d952b52ed59dbc8cb33d75187195defef791592db957b9588c5338c
deleted: sha256:4c4ddb6e00a8d666ad1574c5aa99c3b83167d9618ba4978c6242ca62971e920f
deleted: sha256:ef019bb5685e7e078f90095ff5cb7baa408a6873e34daa77d5b0afad4da33d21
deleted: sha256:197fb8ad0119f9996baa5ed5de2233ce77dbfd2f90f84f9661fbaeedf0fccd43
untagged: node:8.9.4
untagged: node@sha256:6054aa20c5b7d198524d9bd56c7b2d4fde046b6825e8261ccbf441444a5f4d39
deleted: sha256:9fba5176c04f77fe01004918e2a73d396a378724a3360687804e3a0683003c20
deleted: sha256:0ebd50946086a81f970920d7f72e4b95f62d6d04d4b8bab7a3de7fed69ae5826
deleted: sha256:09650957d667c9dbcaa4b0a8ae4d748e9face3b0fcb731aa60f11e814373d103
deleted: sha256:7f404b027dbe4caaf8b31cf4a778ec79e45962060b44c75a5d4743e4480e327b
deleted: sha256:cb0c5fa166443e668371e1bad5ee829ff02a1a09b32caf2c48e81dd7da686419
deleted: sha256:f47a5bb97b8df05564ff15aef050221d5c85edd34a82cba424a0a383bd7f8a06
deleted: sha256:5a0bc2c5c30594740b6d8e818e298dc4efdd607604cc589a8c8891db3e4075dc
deleted: sha256:dab5efcf40ebc35ca31f5c3592e0a67d48b1e689d7f1799abeabae39115e9ac9
deleted: sha256:c2a79b3c13850c6d7583bd063280356d3fd019cfb0015240f9be78b511155c9c
deleted: sha256:8eb9a9f0bb37b6422590b33ae1854f3c70ce08bf060398151ddbef86cf0d1a37
deleted: sha256:61472fb6b19c26d1860f4f4de89fc79d2a2af2a368c8a69518f59392e46f430a
deleted: sha256:29c1ad09f04b08c34444ef6ca898d5b9935b72109b33be04b4b7804cbf7f7732
deleted: sha256:2af3a3cf4bc5a7574d4bb491b5c2591cec22c80c6a8674048bc98139b6bb48d7
deleted: sha256:a77659cb08ce12d2258d76fed45b707a22225b20fda7956e0de11b809bf4e266
deleted: sha256:5dda1c0e220e492c89eef6e8cbb2db0e44c6215df5b54426b8939c920beaeeb0
deleted: sha256:fc698b9c7e91580564c7ba33384850783bdee9de8b332d53fd5ac6a7f8060f42
deleted: sha256:72af2bfd28573aedcccb95186e6bdf35a4535eb24d450a2b7913f116377a285b
deleted: sha256:c7325d66efed0cfc23ae359f370bedd10bbd197d503ff5e51a69d1906a6f276b
deleted: sha256:9ce7e50a422031259d533068cf20b2e8a7030aa2c9c1100e2c1a0ce2c3a158f8
deleted: sha256:e7f67d1b4bf757b4ed5c6a5acfb24c0d2fbddcba02d9bd355dc14e35f8d37465
deleted: sha256:9fdcabdff2488b757756de34db1a33fbc177821cab0ea814f5453247afecf7ff
deleted: sha256:45671ffe82b4cc41cc902c71f2647292629e7d1e1f4f2b21a9564b6e939d150b
deleted: sha256:11af70cc907ab855d1b443281705b65fec2a7f43bf76c4fe05d8fcaf65de1156
deleted: sha256:568a64ed4ac842fcfc80002ec9f31bc3d9c838e56d5a5457c106a7bb862661b6
deleted: sha256:a0f18f11904f569e8d12200944fe3d67a347e63e3398aa04c7a571305d5258d7
deleted: sha256:7588bc8062b11720dd125fe3609535759ce0c377efa489371838a06a7ebe8e07
deleted: sha256:1876e72de3a79a89fd11fa5f1cf8a04f4bbe4884493eb294e4672e652c719fa5
deleted: sha256:8732c08985cfbbec6b7961d2dfd68d37a1b5c1192673c4ca643a06aba281060a
deleted: sha256:49bd260a1579fef8bbbc5046305741379496cfc709c53901a3b123b96cf52b6e
deleted: sha256:d5ca665bf0aa1af7ca190e442bd48be61f3ee60840717844c58caa3ef59b278a
deleted: sha256:96de08a2c0e582c01e33ae92c2ea3d777f2d5f54db61bf935eee513f7436a2ec
deleted: sha256:b9edb0c8ab7e64d4a05ccde68bfb4c65eea9456f744d1787d7447d52451c6332
deleted: sha256:61a376a586dee1ea90491b20e3fd7167e2e3843c8fa09a6478337b13a8468e6f
deleted: sha256:32fde623eca772c13021f21b55b547be68d2c271cca20c3906a1dc38a2034f2f
deleted: sha256:ba8ca5215be70f83ccce6d5f963b37e6de29bde35fbf96e3735337d5c4c0480d
deleted: sha256:dac9f2787a1c649dd453d1d881a31fd294091c8e71543e80a629dbdc3e927dd8
deleted: sha256:6c118f4633b384a6c82d967485f61aa8b84aafdd7992fc9d64ee4fb2046dea7c
deleted: sha256:c9be3da4276523965b91791b15234502138da90389f68d14c576940bedb50519
deleted: sha256:5953b28a1d58fd9972b8f498e9023d116d804915da71ec0164660ea1c9013a6d
deleted: sha256:2991698da857d61a332895fa13bd7343452843f9b103366b358c104dffc8fac8

Total reclaimed space: 102.8kB
:~ $ docker images
REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
nginx                 latest              7042885a156a        5 days ago          109MB
weatherapp_backend    latest              400d69f74761        10 months ago       705MB
weatherapp_frontend   latest              b61be4883cf1        10 months ago       731MB
:~ $ docker container prune
WARNING! This will remove all stopped containers.
Are you sure you want to continue? [y/N] y
Deleted Containers:
d10070e3dc915b719a136f789b7219b1773fb4577841c778b96dec305a1f1c01
b9d01910526f9ca048938d3e7b1b04513b772d8adbaa1161e8925eb91cc6dd12

Total reclaimed space: 110B
:~ $ docker stop 7042 400d b61b
Error response from daemon: No such container: 7042
Error response from daemon: No such container: 400d
Error response from daemon: No such container: b61b
:~ $ docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
4ec2625f0e10        nginx               "nginx -g 'daemon of…"   14 minutes ago      Up 14 minutes       80/tcp              hardcore_newton
:~ $ docker images
REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
nginx                 latest              7042885a156a        5 days ago          109MB
weatherapp_backend    latest              400d69f74761        10 months ago       705MB
weatherapp_frontend   latest              b61be4883cf1        10 months ago       731MB
:~ $ docker stop 4ec2
4ec2
:~ $ docker rm 4ec2
4ec2
:~ $ docker images
REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
nginx                 latest              7042885a156a        5 days ago          109MB
weatherapp_backend    latest              400d69f74761        10 months ago       705MB
weatherapp_frontend   latest              b61be4883cf1        10 months ago       731MB
:~ $ docker rm 7042 400d b61b
Error: No such container: 7042
Error: No such container: 400d
Error: No such container: b61b
:~ $ image prune
-bash: image: command not found
:~ $ docker image prune
WARNING! This will remove all dangling images.
Are you sure you want to continue? [y/N] y
Total reclaimed space: 0B
:~ $ docker images
REPOSITORY            TAG                 IMAGE ID            CREATED             SIZE
nginx                 latest              7042885a156a        6 days ago          109MB
weatherapp_backend    latest              400d69f74761        10 months ago       705MB
weatherapp_frontend   latest              b61be4883cf1        10 months ago       731MB
:~ $ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
:~ $ docker rmi 7042 4 b
Untagged: nginx:latest
Untagged: nginx@sha256:b543f6d0983fbc25b9874e22f4fe257a567111da96fd1d8f1b44315f1236398c
Deleted: sha256:7042885a156a01cc99e5a531f41ff47ea2facf655d4fc605aa80b216489586a4
Deleted: sha256:fb06e7fd070131bf49b9c5558eb0b3beecb698b5122e6d989c1a1cc009710d2d
Deleted: sha256:cc266db60daae61318dc085eeb60a3c6a876d6fc75f9fa7d7f7f9a47d4353f33
Deleted: sha256:7b4e562e58dcb7fbe1e27bb274f0ff8bfeb2fd965203380436e159df9f218900
Error: No such image: 4
Error: No such image: b
:~ $ docker rmi 40 b6
Untagged: weatherapp_backend:latest
Deleted: sha256:400d69f74761c94029eae76e5cbf4a3c495ee284f6a0811560aaa4bee19d1267
Deleted: sha256:a0ffc09b002d7fb29a23b9eb989ec3592715849b4b33235cd8da4b7079b01632
Deleted: sha256:99c7e233922f5a705bce7f761e014c878327d18371c8f150cfc9c24eedeab1e7
Deleted: sha256:ebb652b539df92ababb187578042d3883a3238632ac28d60d6c0d7f6caff392e
Deleted: sha256:7fc06176205538a295173c5b8b3fef70e34703d784659bf7f1d006350a71ece4
Deleted: sha256:f4c46d9173ffc37ab098a75ecfcbf186fc71983b4b1af8f8ab38772c3f24e262
Deleted: sha256:1e98ddc91ad6fc89b856286effe5acdb6bec53cfdc25d4e74565c03eaa2da48c
Deleted: sha256:cf1b9699c0947ea3a117d48d96dd90b09054a0276fd426709048fcbcba082f19
Deleted: sha256:c5901404bcd59ea41fd2ce637bc6ae44583b0293c79f3bd8404863dcaed218dd
Deleted: sha256:8b8b93cfd7373bf03c281faadf50079271342c4bb0b41b744823cd1d4641f6e4
Untagged: weatherapp_frontend:latest
Deleted: sha256:b61be4883cf1a3caef98fd8d648bbfb65c385965ac8691f8184c9e50b19e7d81
Deleted: sha256:46332a5a577a182c5664064f8ab20841de121aae108f33eda59f65a9d282cb87
Deleted: sha256:f407f1c9a87374d1d5f1dbfc42be6cfd07db8d6bebf58dd28ba800198c33511d
Deleted: sha256:c540daedbf3403a883bf6b7ade62f8a488738ce0e72a060b425bbd619498c52e
Deleted: sha256:1d4a255537e64df93e4331ef6f482cb9c7c9837db9a88b9db011aaefa9845271
Deleted: sha256:b1b5fa00594d98bd69afead96820281c73058a51ca49665f3a7bfdda07d1b7f9
Deleted: sha256:c805cb6464e95662a0e611abc58023841471654e21ec09dca77a6bbb6b7d96f1
Deleted: sha256:c28354202ecc1418a3a0c422111476b292949b6eec683810da8588a8a0e47075
Deleted: sha256:c04be3f00fcfd6312665a1748f13b7c69922144798a0fa2277bd1247f74a8515
Deleted: sha256:30e693a3f7e584bad4fa9bf3dfd612651c712d346aba8dd70fbe41b3b9ac7a14
Deleted: sha256:11ee21138c03425ed58470ea14ff0a51d735acfdbfa78a07473f41aac1ad0fa0
Deleted: sha256:c055ea122ebfada5a29619bc87a209b655d786e0f3713b1c914552c39b527b5c
Deleted: sha256:b87c2ad8344dd1c1fdfd09060a99ff5dbac4a1fe1a079ad871dfa228fc628e1c
Deleted: sha256:5152d2d6a4dc6d2092b40e3dab7ada423c1d8d62d7badf5c629a95820ace8fbc
Deleted: sha256:dcace20a23c940ade751a77122653ee7fc8814f9cf211d061dfbda9d2e72eaf7
Deleted: sha256:9014dfa0202e35e8529ed2b4f8183923181aebde8900c38add158de90edcc7d1
Deleted: sha256:4face6a18020b9f70276b1ae5125b4d47dcecaea41adf5cc03eea159ede381bc
Deleted: sha256:a176968aca6e2da9dde867a49fcfb03e84f3a003481cb4c990ae45d551e686bd
Deleted: sha256:ccfcaf8fb471a2ec475db4fe91958b532e8cc1ba84ac42c51cb484346dc8ffc5
Deleted: sha256:7152b3dd92f68f075f10409f8a0060cc1e2cfe05bc39e9066d6962ab4fe16ccc
Deleted: sha256:4bcdffd70da292293d059d2435c7056711fab2655f8b74f48ad0abe042b63687
:~ $ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
:~ $ 


**Exercise 1.3.**

:~ $ docker run -d --rm -it --name webtest ubuntu:16.04  sh -c 'read website; sleep 3; curl http://$website;'
31bb1bdd65db6cec1d5f1cd4955bf78668dc7331aeadfe94b7d7431a2d177ee4
:~ $ docker exec -it webtest bash
root@31bb1bdd65db:/# apt-get update; apt-get install curl
Installing ubuntu…
Running hooks in /etc/ca-certificates/update.d...
done.
root@31bb1bdd65db:/# exit
exit
:~ $ docker attach webtest
helsinki.fi
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
:~ $ 


**Exercise 1.4.**

Dockerfile:

FROM ubuntu:16.04 

WORKDIR /exercise1_4
RUN apt-get update && apt-get install -y curl

COPY ./script1.sh .

CMD ./script1.sh


script1.sh:

read website; sleep 3; curl http://$website;


Commands:
:exercise1_4 $ docker build -t curler .
Sending build context to Docker daemon  3.072kB
Lots of stuff...
Successfully built f34642c328dc
Successfully tagged curler:latest
:exercise1_4 $ docker run -it curler
helsinki.fi
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>


**Exercise 1.5.**

Dockerfile:

FROM node:10

WORKDIR /app

COPY . .

RUN npm install

EXPOSE 5000

CMD ["npm", "start"]


Commands:

:frontend-example-docker $ docker build .

docker run -p 5000:5000 f41c


**Exercise 1.6.**

Dockerfile:

FROM node:10

WORKDIR /app

COPY . .

RUN npm install

EXPOSE 8000

CMD ["npm", "start"]


Commands: 

docker build -t back1 .

docker run -v $(pwd)/logs.txt:/app/logs.txt -p 8000:8000 back1


**Exercise 1.7.**


Backend Dockerfile:

FROM node:10

WORKDIR /app

COPY . .

RUN npm install

EXPOSE 8000

CMD FRONT_URL=http://localhost:5000 npm start


Commands: same as previously


Frontend Dockerfile:

FROM node:10

WORKDIR /app

COPY . .

RUN npm install

EXPOSE 5000

CMD API_URL=http://localhost:8000 npm start


Commands: same as previously




**Exercise 1.8**

Docker Hub: ekettu/ratebeer

