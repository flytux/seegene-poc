$ openssl req -x509 -newkey rsa:4096 -sha256 -days 3650 -nodes \
  -keyout nexus.key -out nexus.crt -subj '/CN=nexus.local' \
  -addext 'subjectAltName=DNS:nexus.local'

$ kubectl create secret tls nexus-tls --key nexus.key --cert nexus.crt -n nexus


$ openssl req -x509 -newkey rsa:4096 -sha256 -days 3650 -nodes \
  -keyout docker.key -out docker.crt -subj '/CN=docker.local' \
  -addext 'subjectAltName=DNS:docker.local'

$ kubectl create secret tls docker-tls --key docker.key --cert docker.crt -n nexus
