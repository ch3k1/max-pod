Calculate how many pods you can run in your k8s cluster (EKS) based on aws formula 
```ENI * (# of IPv4 per ENI - 1) + 2```. 
On aws each instance type has a different upper limit

### Usage

For example, an t2.medium	has 3 network interfaces and private IPv4 addresses per interface 6

n is the number of Elastic Network Interfaces (ENI) of the instance type
m is the number of IP addresses of a single ENI

```
./max_pod_per_instance.sh -n 3 -m 6
```

If you have more than 1 worker node, in this example, I am using 5 worker node on AWS
```
./max_pod_per_instance.sh -n 3 -m 6 -i 5
```
