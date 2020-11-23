

* [Kubernetes Dashboard](http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#/login)

* [Tutorial OKE](https://docs.oracle.com/en/solutions/monitor-applications-on-kubernetes/add-oracle-management-cloud-integration.html#GUID-B72CC43F-9167-4B36-8AB7-E3B7223D3B3C)


```
oci -v
oci ce cluster create-kubeconfig --cluster-id ocid1.cluster.oc1.phx.aaaaaaaaaftgimjymi2gmodemu4dqnrwhbtdcn3bmfqtcojsmcqweobsgzqt --file $HOME/.kube/config --region us-phoenix-1 --token-version 2.0.0
cd ..
mv .kube .kube.bkp
mkdir -p $HOME/.kube
oci ce cluster create-kubeconfig --cluster-id ocid1.cluster.oc1.phx.aaaaaaaaaftgimjymi2gmodemu4dqnrwhbtdcn3bmfqtcojsmcqweobsgzqt --file $HOME/.kube/config --region us-phoenix-1 --token-version 2.0.0
cd .oci
mkdir .oci
cd .oci
nano config
oci ce cluster create-kubeconfig --cluster-id ocid1.cluster.oc1.phx.aaaaaaaaaftgimjymi2gmodemu4dqnrwhbtdcn3bmfqtcojsmcqweobsgzqt --file $HOME/.kube/config --region us-phoenix-1 --token-version 2.0.0
oci setup repair-file-permissions --file /Users/rvaldes/.oci/config
oci setup repair-file-permissions --file /Users/rvaldes/.ssh/id_rsa.pub
oci ce cluster create-kubeconfig --cluster-id ocid1.cluster.oc1.phx.aaaaaaaaaftgimjymi2gmodemu4dqnrwhbtdcn3bmfqtcojsmcqweobsgzqt --file $HOME/.kube/config --region us-phoenix-1 --token-version 2.0.0
nano config
oci ce cluster create-kubeconfig --cluster-id ocid1.cluster.oc1.phx.aaaaaaaaaftgimjymi2gmodemu4dqnrwhbtdcn3bmfqtcojsmcqweobsgzqt --file $HOME/.kube/config --region us-phoenix-1 --token-version 2.0.0
ls -l
openssl genrsa -out ~/.oci/oci_api_key.pem -aes128 2048
ll
rm oci_api_key.pem
openssl genrsa -out ~/.oci/oci_api_key.pem 2048
chmod go-rwx ~/.oci/oci_api_key.pem
openssl rsa -pubout -in ~/.oci/oci_api_key.pem -out ~/.oci/oci_api_key_public.pem
cat ~/.oci/oci_api_key_public.pem | pbcopy
nano config
ls -l
nano config
oci ce cluster create-kubeconfig --cluster-id ocid1.cluster.oc1.phx.aaaaaaaaaftgimjymi2gmodemu4dqnrwhbtdcn3bmfqtcojsmcqweobsgzqt --file $HOME/.kube/config --region us-phoenix-1 --token-version 2.0.0
export KUBECONFIG=$HOME/.kube/config
kubectl get nodes
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.3/aio/deploy/recommended.yaml
nano oke-admin-service-account.yaml
kubectl apply -f oke-admin-service-account.yaml
kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep oke-admin |\nawk '{print $1}')
kubectl proxy
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.3/aio/deploy/recommended.yaml\n
kubectl apply
kubectl apply -f oke-admin-service-account.yaml
kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep oke-admin |\nawk '{print $1}')
kubectl proxy
kubectl get pod
kubectl get pod -n kube-system
kubectl get all -n kubernetes-dashboard
kubectl get nodes
kubectl
kubectl get pod --namespace=kubernetes-dashboard
cd Desarrollo
ll
cd devsecops
ls -l
cd oci
ll
mkdir oke
cd oke
git clone https://github.com/spring-guides/gs-accessing-data-rest.git
cd gs-accessing-data-rest
ls -l
cd complete
ls -l
./gradlew clean bootRun
java -version
history |gre home
history |grep home
export JAVA_HOME=`/usr/libexec/java_home -v 11.0.7`
./gradlew clean bootRun
docker ps
docker stop 6f
./gradlew clean bootRun
curl -i -X POST -H "Content-Type:application/json" -d "{  \"firstName\" : \"Frodo\",  \"lastName\" : \"Baggins\" }"
curl -i -X POST -H "Content-Type:application/json" -d "{  \"firstName\" : \"Frodo\",  \"lastName\" : \"Baggins\" }" http://localhost:8080/people
curl http://localhost:8080/people
cd Desarrollo/devsecops
cd gs-accessing-data-rest
ls -al
cd complete
ls -al
cp build.gradle build.gradle.ORIG
nano build.gradle
cd gradle
ll
cd wrapper
ls -al
ll
cp gradle-wrapper.properties gradle-wrapper.properties.ORIG
nano gradle-wrapper.properties
cd ..
pwd
./gradlew clean jar dockerBuildImage\n\n
pwd
cd gradle
cd wrapper
ll
nano gradle-wrapper.properties
./gradlew clean jar dockerBuildImage\n\n
cd ..
./gradlew clean jar dockerBuildImage\n\n
cd gradle
ll
cd wrapper
ls -l
cp gradle-wrapper.properties.ORIG gradle-wrapper.properties
cd ..
./gradlew clean jar dockerBuildImage\n\n
ll
nano build.gradle
./gradlew clean jar dockerBuildImage\n\n
./gradlew clean jar dockerBuildImage --info\n\n
./gradlew clean jar dockerBuildImage --debug\n\n
./gradlew clean jar dockerBuildImage --info\n\n
./gradlew clean jar dockerBuildImage --scan\n\n
cd gradle/wrapper
ls -l
nano gradle-wrapper.properties
cd ..
./gradlew clean jar dockerBuildImage --scan\n\n
docker images
docker images |grep omc-sample
nano build.gradle
./gradlew clean jar dockerBuildImage\n\n
docker images |grep df5
```
