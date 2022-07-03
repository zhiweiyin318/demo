# Install

openshift-gitOps

```bash
$ oc get pods -n openshift-gitops
NAME                                                          READY   STATUS    RESTARTS   AGE
cluster-9c48d9557-l79l9                                       1/1     Running   0          3m8s
kam-7c7f9478f9-pkx89                                          1/1     Running   0          3m8s
openshift-gitops-application-controller-0                     1/1     Running   0          3m5s
openshift-gitops-applicationset-controller-7bc6558665-54gf8   1/1     Running   0          3m5s
openshift-gitops-dex-server-6856f4bcc6-gvj8g                  1/1     Running   0          3m4s
openshift-gitops-redis-97574d6-mfw88                          1/1     Running   0          3m5s
openshift-gitops-repo-server-dbbcf86df-j67kh                  1/1     Running   0          3m5s
openshift-gitops-server-6c8c96f857-5k2q6                      1/1     Running   0          3m5s
[centos@yzw ~]$
[centos@yzw ~]$
[centos@yzw ~]$
[centos@yzw ~]$ oc get crds | grep argo
applications.argoproj.io                                                 2022-06-17T01:25:18Z
applicationsets.argoproj.io                                              2022-06-17T01:25:19Z
appprojects.argoproj.io                                                  2022-06-17T01:25:20Z
argocds.argoproj.io                                                      2022-06-17T01:25:17Z
[centos@yzw ~]$ oc get routes.route.openshift.io -n openshift-gitops
NAME                      HOST/PORT                                                                                              PATH   SERVICES                  PORT    TERMINATION            WILDCARD
kam                       kam-openshift-gitops.apps.server-foundation-410-qdfpt.dev04.red-chesterfield.com                              kam                       8443    passthrough/None       None
openshift-gitops-server   openshift-gitops-server-openshift-gitops.apps.server-foundation-410-qdfpt.dev04.red-chesterfield.com          openshift-gitops-server   https   passthrough/Redirect   None
[centos@yzw ~]$ oc extract secret/openshift-gitops-cluster -n openshift-gitops --to=-
# admin.password
qYyCKaFzPulXnx6p27f1MURmW0QZdeOb
```