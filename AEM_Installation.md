
Before installation AEM make sure you have environment of Java(oracle JDK)

## Install Docker:
	sudo pacman -S docker
	
## AEM Installation Process: 

Extract AEM zip files and install by run these commands from that location

	sudo systemctl start docker

	sudo systemctl enable docker //Enable Docker as a service, no need to start everytime after rebooting

	sudo docker image load -i=aem_author_v6.3.2.tar

	sudo docker image load -i=aem_publish_v6.3.2.tar

	sudo docker run --network=host --name=author registry.gitlab.com/aem-docker/6.3.2:author -p 4502:4502 -p 9511:9511

	sudo docker run --network=host --name=publish registry.gitlab.com/aem-docker/6.3.2:publish -p 4503:4503 -p 9512:9512 


Start Command in every morning:

    sudo systemctl start docker
    sudo docker start author
    sudo docker start publish

## Access the Author instance:

    localhost:4502
        
<em>Where default username **author** and password **author**</em><br>
## Access the Publish instance:

     localhost:4503
        
<em>Where default username **publish** and password **publish**</em><br>
## Restore command(It will cleanup all packedges):

	sudo docker stop author
	sudo docker rm author

	sudo docker stop publish
	sudo docker rm publish
  
