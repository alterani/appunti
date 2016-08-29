
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

> Stoppare un servizio (container name è l'id visualizzato da docker ps)
> <PRE><CODE>docker stop container_name </CODE></PRE> 

> Esempio esecuzione webserver nigix 
> Se nigix non è presente in locale lo scarica automaticamente da dockerhub	
> <PRE><CODE>docker run -d -p 80:80 --name webserver nginx</CODE></PRE>



	