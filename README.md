**STEP FOR EXECUTION**
>**BUILDING A FUNCTION**

faas-cli new --lang java8 apifun

>**PUSHING THE FUNCTION INTO LOCAL REPOSITORY**

docker tag apifun aditik/apifun

**DEPLOYING A FUNCTION USING API**
{
 "service": "apifun",
  "image": "aditik/apifun",
  "envProcess": "function",
  "envVars": { "write_debug": "true"},
  "constraints": [],
  "labels": {},
  "registryAuth":"YWRpdGlrOmFkaXRpLmtAMTIz==",
 "annotations": {"prometheus.io.scrape": "false"},
  "secrets": [],
  "limits": {},
  "requests": {}
}
**OUTPUT**
Name:           apifun-55cd77f8d5-fnps5
Namespace:      openfaas-fn
Priority:       0
Node:           geekbull-sve15118fnb/192.168.0.135
Start Time:     Fri, 13 Sep 2019 12:58:38 +0530
Labels:         faas_function=apifun
                pod-template-hash=55cd77f8d5
Annotations:    prometheus.io.scrape: false
Status:         Running
IP:             10.244.0.18
Controlled By:  ReplicaSet/apifun-55cd77f8d5
Containers:
  apifun:
    Container ID:   docker://8cc5462592f5746a049be727e055723ff59d7ec60fc36ba978c733b84630f642
    Image:          aditik/apifun
    Image ID:       docker-pullable://aditik/apifun@sha256:490db5341d2bec1196b49a357500c2c2df47a4d161ddb5e13ade360ff1c2824c
    Port:           8080/TCP
    Host Port:      0/TCP
    State:          Waiting
      Reason:       CrashLoopBackOff
    Last State:     Terminated
      Reason:       Error
      Exit Code:    1
      Started:      Fri, 13 Sep 2019 13:15:08 +0530
      Finished:     Fri, 13 Sep 2019 13:15:08 +0530
    Ready:          False
    Restart Count:  8
    Liveness:       http-get http://:8080/_/health delay=2s timeout=1s period=2s #success=1 #failure=3
    Readiness:      http-get http://:8080/_/health delay=2s timeout=1s period=2s #success=1 #failure=3
    Environment:
      fprocess:     function
      write_debug:  true
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from default-token-j778b (ro)
Conditions:
  Type              Status
  Initialized       True 
  Ready             False 
  ContainersReady   False 
  PodScheduled      True 
Volumes:
  default-token-j778b:
    Type:        Secret (a volume populated by a Secret)
    SecretName:  default-token-j778b
    Optional:    false
QoS Class:       BestEffort
Node-Selectors:  <none>
Tolerations:     node.kubernetes.io/not-ready:NoExecute for 300s
                 node.kubernetes.io/unreachable:NoExecute for 300s
Events:
  Type     Reason     Age                  From                           Message
  ----     ------     ----                 ----                           -------
  Normal   Scheduled  21m                  default-scheduler              Successfully assigned openfaas-fn/apifun-55cd77f8d5-fnps5 to geekbull-sve15118fnb
  Normal   Started    20m (x4 over 21m)    kubelet, geekbull-sve15118fnb  Started container apifun
  Normal   Pulled     19m (x5 over 21m)    kubelet, geekbull-sve15118fnb  Container image "aditik/apifun" already present on machine
  Normal   Created    19m (x5 over 21m)    kubelet, geekbull-sve15118fnb  Created container apifun
  Warning  BackOff    71s (x101 over 21m)  kubelet, geekbull-sve15118fnb  Back-off restarting failed container


