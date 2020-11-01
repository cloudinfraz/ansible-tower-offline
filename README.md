# ansible-tower-offline
image list:

registry.redhat.io/ansible-tower-37/ansible-tower-rhel7:3.7.1

registry.redhat.io/rhscl/redis-5-rhel7:latest

registry.redhat.io/ansible-tower-37/ansible-tower-memcached-rhel7:latest

registry.redhat.io/ansible-tower-37/ansible-runner-rhel7:latest

registry.access.redhat.com/rhscl/postgresql-10-rhel7:1-59

docker.io/bitnami/postgresql:11.7.0-debian-10-r9

docker.io/bitnami/postgres-exporter:0.8.0-debian-10-r28

docker.io/bitnami/minideb:buster

docker.io/sonatype/nexus3

```
for example:

docker tag registry.redhat.io/ansible-tower-37/ansible-tower-rhel7:3.7.1 myregistry.com/ansible-tower-37/ansible-tower-rhel7:3.7.1
docker push ansible-tower-rhel7:3.7.1

```
# deploy ansible-tower

```
[all:vars]
admin_user=admin
admin_password='admin123'
secret_key='YWRtaW4xMjMK'
pg_username='postgres'
pg_password='redhat'
pg_database='towerdb'
pg_port=5432
pg_sslmode='prefer'  # set to 'verify-full' for client-side enforced SSL
kubernetes_context=default/api-int-ocp4-example-com:6443/kube:admin
kubernetes_namespace=tower

./setup_openshift.sh

```
