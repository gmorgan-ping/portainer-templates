# Ping Identity - App Templates

This repository hosts Ping Identity application templates (**'Apps Templates'**) definitions for portainer.

To deploy a Portainer instance with the Ping App Templates referenced by default, run the Docker command below on a Linux server with Docker/Docker-Compose installed. This will create an Admin Console at http://hostname:9000/ with default credentials (admin/2FederateM0re).

    docker run -d \
    -p 9000:9000 \
    -p 8000:8000 \
    --name=portainer \
    --restart=always \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v portainer_data:/data portainer/portainer \
    -H unix:///var/run/docker.sock \
    --templates https://raw.githubusercontent.com/gmorgan-ping/portainer-templates/master/templates-ping.json \
    --logo "https://raw.githubusercontent.com/gmorgan-ping/portainer-templates/master/ping-logo.svg" \
    --admin-password='$2y$05$phwSg3ykaHLBDYEEpUHfFeePAlN52B5jX.EOS4GsVPtr9wd008iSO'
