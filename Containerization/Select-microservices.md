(https://opentelemetry.io/docs/demo/architecture/)
Identify microservices from different languages . from above architecture , i;m going to containerize the services in 3 languages i.e Go, java, python

**Go**--> product catalog service

**java**-->ad service, queue(kafka) service

**python**-->recommendation service

# product catalog service
open this repo (https://github.com/Harshitha-Rachapalle/project-opentelemetry-demo) where all source code is provided by the opentelemetry official project

> Then click src

> product-catalog

> readme.md file from this we need get same results in ec2 server by following those commands

### open ec2 server in gitbash (in my case )
cd project-opentelemetry-demo/ ( this repo is i forked from official opentelemetry project)

cd src/

ls

cd product-catalog/

go build -o product-catalog .  (here -o is destination where binary name is product-catalog)

./product-catalog

when we run this we can get output which is same in readme file

i.e 
Loading Product Catalog...
 
Loaded 10 products

Product Catalog reload interval: 10



..>the dependencies for go language is written in go.mod
