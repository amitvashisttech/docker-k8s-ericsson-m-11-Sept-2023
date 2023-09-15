
## Network Basic 
  131  docker run -d amitvashist7/docker-k8s-ericsson-e-11-sept-2023:v3
  132  docker ps
  133  docker inspect 48ce9477cb1d
  134  curl 172.17.0.2
  135  curl 172.17.0.2/info.html
  136  docker run -d amitvashist7/docker-k8s-ericsson-e-11-sept-2023:v3
  137  docker ps
  138  docker run -d -p 80:80 --name ntw-test-1 amitvashist7/docker-k8s-ericsson-e-11-sept-2023:v3
  139  docker ps
  140  docker run -d -p 80:80 --name ntw-test-2 amitvashist7/docker-k8s-ericsson-e-11-sept-2023:v3
  141  docker run -d -p 8081:80 --name ntw-test-2 amitvashist7/docker-k8s-ericsson-e-11-sept-2023:v3
  142  docker run -d -p 8081:80 --name ntw-test-3 amitvashist7/docker-k8s-ericsson-e-11-sept-2023:v3
  143  docker ps
  144  docker ps -a
  145  docker run -d -p 8081:80 --name ntw-test-4 amitvashist7/docker-k8s-ericsson-e-11-sept-2023:v3
  146  apt-get install net-tools -y
  147  netstat -tulnp
  148  docker run -d -P --name ntw-test-5 amitvashist7/docker-k8s-ericsson-e-11-sept-2023:v3
  149  docker ps




## Build an Network App Container
1. docker run -it --name network-image ubuntu 
> apt-get update 
> apt-get install net-tools iputils-ping -y 
> ifconfig 
> ip route 

## Open the next terminal & commit the Container with following command & make an image out of it. 
29  docker commit -p -m "My Network Test Ready Image" test-network-1 my-network-app:v1 



## Now you can create contaiers & network

   31  docker run -itd --name network-1 my-network-app:v1 
   32  docker ps 
   33  docker exec -it network-1 ifconfig 
   34  docker exec -it network-1 route -n 
   35  ls
   36  docker kill $(docker ps -q) 
   37  docker rm $(docker ps -qa) 
   38  ld
   39  ls
   40  docker run -itd --name default-network-1 my-network-app:v1 
   41  docker network ls
   42  docker run -itd --name none-network-2 --network none my-network-app:v1 
   43  docker run -itd --name host-network-3 --network host my-network-app:v1 
   44  docker ps 
   45  docker exec -it default-network-1 ip addr 
   46  docker exec -it default-network-1 ifconfig 
   47  docker exec -it default-network-1 route -n 
   48  docker exec -it none-network-2 ifconfig 
   49  docker exec -it none-network-2 route -n 
   50  docker exec -it default-network-1 route -n 
   51  docker exec -it host-network-3 route -n 
   52  route -n 
   53  docker exec -it host-network-3 ifconfig 
   54  ls
   55  docker network ls 
   56  docker network create mynet
   57  docker network ls 
   58  docker network inspect mynet
   59  ip addr 
   60  docker run -itd --name mynet-network-4 --network mynet my-network-app:v1 
   61  docker exec -it mynet-network-4 ifconfig 
   62  docker exec -it mynet-network-4 route -n 
   63  docker network create --help
   64  docker network create --driver "bridge" --subnet=172.28.0.0/16 --ip-range=172.28.5.0/24 --gateway=172.28.5.254 mybr0 
   65  docker network ls 
   66  docker network inspect mybr0
   67  docker run -itd --name mybr0-network-1 --network mybr0 my-network-app:v1 
   68  docker run -itd --name mybr0-network-2 --network mybr0 my-network-app:v1 
   69  docker run -itd --name mybr0-network-3 --network mybr0 my-network-app:v1 
   70  docker ps 
   71  docker exec -it mybr0-network-1 route -n 
   72  docker exec -it mybr0-network-2 route -n 
   73  docker exec -it mybr0-network-3 route -n 
   74  docker exec -it mybr0-network-1 ifconfig 
   75  docker exec -it mybr0-network-2 ifconfig 
   76  docker exec -it mybr0-network-3 ifconfig 
   77  docker exec -it mybr0-network-3 ping -c2 google.com
   78  docker exec -it mybr0-network-3 ping -c2 172.28.0.0
   79  docker exec -it mybr0-network-3 ping -c2 172.28.5.0
   80  docker exec -it mybr0-network-3 ping -c2 172.28.5.1
   81  docker exec -it mybr0-network-3 ping -c2 172.28.5.2
   82  ls
   83  docker images 
   84  docker network ls 
   85  docker run -d --name ntw-mybr0-5 --network mybr0 -P -v /root/docker-k8s-ericsson-e-11-Sept-2023:/var/www/html/myapp:ro amitvashist7/docker-k8s-ericsson-e-11-sept-2023:v3 
   86  docker ps 
   87  docker exec -it ntw-mybr0-5 ifconfig 
   88  docker inspect ntw-mybr0-5
   89  docker ps 
   90  ls
   91  cd docker-k8s-ericsson-e-11-Sept-2023/
   92  ls
   93  cd 01-Docker/
   94  ls
   95  cd 05-DockerNetwork/
   96  ls
   97  history 
   98  history > history_2.txt 
