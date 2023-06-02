# Sonarqube - Openshift

## 1. Adjust on namespace
##### If you need adjust namespace, edit line 5
    name: sonarqube
    
## 2. Adjust on secret
##### If you need data decode of secret (lines 15,16,16,18) use the command below
    # echo "c29uYXI=" | base64 -d
    # sonar

##### If you want edit value, execute the command below
    # echo -n "S3NH@" | base64
    # UzNOSEA=
    
## 3. Adjust PV / PVC
##### If you need change the storageClass edit line 27
    storageClassName: thin

##### If you need change size of PVC edit line 33
    storage: 1Gi

## 4. Adjust Route / Ingress
##### To edit the host route, edit line 181
    host: sonarqube.apps.paas.domain.lab


## After that you can apply the yaml
    oc apply -f sonarqube-postgresql.yaml

## If you wanna delete the app
    pc delete -f sonarqube-postgresql.yaml
