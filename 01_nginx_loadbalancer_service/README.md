# What are you going to learn in this example #

* Simple pod manifest
* Simple svc manifest of load balancer type

## Implementation ##

1. Create nginx pod 
```console
kubectl appy -f nginx_pod.yaml
```
2. Check that your pod is running.
```console
kubectl get pods
NAME    READY   STATUS    RESTARTS   AGE
nginx   1/1     Running   0          8s
```

4. Create nginx service
 ```console
 kubectl appy -f nginx_svc.yaml
 ```

5. Check nginx service and enpoints
```
foo@bar:~$ k get svc
NAME            TYPE           CLUSTER-IP       EXTERNAL-IP                                                               PORT(S)        AGE
nginx-service   LoadBalancer   10.100.182.243   xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.us-east-1.elb.amazonaws.com   80:30892/TCP   7s
foo@bar:~$ k get endpoints
NAME            ENDPOINTS                         AGE
nginx-service   100.33.9.223:80                   26s
```

3. Test nginx service.
```
foo@bar:~$ curl xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx.us-east-1.elb.amazonaws.com
```
##**Output:**##

<html>
<head>
<title>Welcome to nginx!</title>
<style>
    body {
        width: 35em;
        margin: 0 auto;
        font-family: Tahoma, Verdana, Arial, sans-serif;
    }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>


