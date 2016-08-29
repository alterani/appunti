
COMANDI SHELL
=============

Appunti su docker: installazione e comandi
------------------------------------------
In questo file sono riportati appuntie snippet su docker.
Per la documentazione ufficiale visitare il sito http://docs.docker.com



### Versione

> Versione di docker
> <PRE><CODE>docker --version</CODE></PRE> 

> Versione di docker-composer
> <PRE><CODE>docker-compose --version</CODE></PRE>  

> Versione di docker-machie	
> <PRE><CODE>docker-machine --version</CODE></PRE>


### Avviare immagini

> Visualizza immagini disponibili
> <PRE><CODE>docker images</CODE></PRE> 

> Visualizzare i precessi docker in esecuzione
> <PRE><CODE>docker ps </CODE></PRE> 

> Visualizzare tutti i precessi anche quelli terminati
> <PRE><CODE>docker ps -a </CODE></PRE> 


> Stoppare un servizio (container name è l'id visualizzato da docker ps)
> <PRE><CODE>docker stop container_name </CODE></PRE> 

> Esempio esecuzione webserver nigix 
> Se nigix non è presente in locale lo scarica automaticamente da dockerhub	
> <PRE><CODE>docker run -d -p 80:80 --name webserver nginx</CODE></PRE>

### COMANDO DOCKER RUN

> Docker run nome_immagine esegue il docker
> <PRE><CODE>docker run nome_immagine</CODE></PRE> 

> ###### *Opzione -d* 
> fa girare il docker come servizio in background.
> Nell'esempio sotto il servizio nigix gira in background grazie all'opzione -> d es:
> <PRE><CODE>docker run -d -p 80:80 --name webserver nginx</CODE></PRE>  

> ###### *Opzione -p porta_locale:porta_esterna*
> (port-forwording) esporta  la porta su quella esterna così
> il servizio è disponibile sul server che ospita il docker.
> Nell'esempio sotto il servizio del docker nigix avviato è disponibile
> sulla porta 80 della macchina.  	
> <PRE><CODE>docker run -d -p 80:80 --name webserver nginx</CODE></PRE> 

> ###### *Opzione --name nome_servizio* 
> con questa opzione si specifica il nome del servizio che apparirà lanciando
> il comando docker  es:
> <PRE><CODE>docker run -d -p 80:80 --name webserver nginx</CODE></PRE> 

### CREARE UN' IMMAGINE

> segui l'esempio riportato sul sito ufficiale.
> * Crea la cartella 
> * Crea il file Dockerfile
> * Edita il file Dockerfile con le sezioni FROM, RUN, CMD (vedi link per esempio)
> * Lancia il comando *docker build -t nomeImmagine .* (senza dimenticare il punto)
> https://docs.docker.com/engine/getstarted/step_four/

### PUSH SU hub.docker.com

> Dopo aver creato l'immagine per poterla inviare all'hub bisogna
creare un repository sul nel proprio account.
> Dopo aver creato il repository bisogna taggare l'immagina appena creata.
> Per poter taggare è necessaio conoscere l'id dell'immagina che è possibile trovare attraverso il comando docker images.
> <PRE><CODE>ddocker tag 13d0f7f1b8f6 alterani/docker-whale:latest</CODE></PRE>
> Effettuare il login:
> <PRE><CODE>docker login --username=yourhubusername --email=youremail@company.com --password=yourpassword</CODE></PRE>
> Effettuare il push usando il nome dell'immagine creata:
> <PRE><CODE>docker push alterani/docker-whale</CODE></PRE>


### RIMUOVERE UN' IMMAGINE IN LOCALE

> Per poter rimuovere un immagina usare il comando sotto, è possibile usare sia il nome che l'id.
> <PRE><CODE>docker rmi -f 7d9495d03763</CODE></PRE>
> <PRE><CODE>docker rmi -f docker-whale</CODE></PRE>




	