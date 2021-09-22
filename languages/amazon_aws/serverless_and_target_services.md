npm generate install for node

when we compile code


serverlss
"serverless to you"

you don't pay for server

no build, maintain, install, 

they tear up and down, every time


to us, it looks serverless

you just pay for compute part of it


⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻⎻


build spec yaml in client

what do we do??

we'll compile your code



pull from github

I'm gonna run w/ everything in 
buildspec.yml


install phase
run node js 10


prebuild commands


then post build

they take all your output, from cpoilations

put to s3 bucket, store it for you





npm
7.2.4






build server, any place that npm lives

s3 bucket
passes it to your output


afte ryou hit manual review


define deploy as beanstalk

whichever BS you decide

bs wakes up
grabs output from s3 bucket
and lays it out on operating system

then just runs





everything from build phase in s3 bucket
artifact bucket


open build phase, log file




go to client

which npm

locate npm



npm is just a build tool
what is node????



if broken
would have broken on build server


unless npm wrong version
builds successfully
(this is different, maybe can't even do this)


ci/cd, 
will vet out most errors when building



AWS CodeBuild us-east-1 (PreProdMomusRailsCodeBuild) Build succeeded for project PreProdMomu



dev envs





ec2

output is just a handoff

build off,
send to any aws target service
? cluster
ec2
s3



behaviors api gateway
lambda


aws target service




beanstlak cool,
b/c machine images
setup ruby java node, php, .net

if stuff to output that
don't use beanstalk
so you manage less stuff
so you can move faster





which node,
real answer
look at buildspec!!

That's what we're building

default latest version for node 10

probably 7.24.0 (via patrick's output)



7.24.0
and 7.25 s


7.2 => 7.3
or 7.2 => 7.8
could be bad



none of our targets are macs
centos7



that's why docker images are so cool
docker image of centos7


use docker containers w/ correct version you want

don't have 2 worry about your mac version (brew update, etc.)




would've died in build if it was wrong


call patrick 




it's a roub goldberg machine essentially