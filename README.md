# k8s-datadog-monitoring

1. Change the ENV variables on yaml file (envname,DD_API_KEY,TOKEN,name:APPNAME1)
2. If you want APM to be enabled, please keep env variable as below
```
	          - name: DD_APM_ENABLED
                    value: "true"
```
3. Once yaml is changed according to your env, run it using below command
```
	kubectl -n your_namespace create -f deploy/
```
4. When we are writing this repo, the latest datadog is  7.19.2
5. Basic commands for troubleshooting
```
       agent status
       agent version
       s6-svstat /var/run/s6/services/agent/
```
6. We are deploying it on EKS cluster, you can use for 1.16+ kubernetes version, you can use deploy/datadog-node-agent-eks_1.16.yaml
