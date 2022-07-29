# Pyhon-Webapp-Docker

Slight docker code used to make python app like flask, remy, pysimpleguiweb,.... linked with lets-encrypt and nginx-proxy:  https://github.com/jwilder/docker-letsencrypt-nginx-proxy-companion

Clone any code that you want to host on the web : git clone https://github.com/jpchoffray/Shannon-for-Dummies.git

Im using the python code of one of my colleagues " Shannon for dummies "

If you want to host it as well you need to add small changes to the code 

  line 36 and 37: 
  
    Web_Version=True
    Web_Remote=True
    
  line 69:
  
    web_cfg={"web_ip":'YOUR-IP',"web_port":8080,"web_start_browser":False}
    
  line 383: 
  
    window = sg.Window('Shannon\'s Equation for Dummies', layout ,disable_close=True, finalize=True, element_justification='center', **web_cfg)
    
  add line 655:
  
    window2['-Losses-'].Update('2')

Create a network named `nginx-proxy` with the 2 letsencrypt and nginx-proxy containers inside 

Use `docker inspect <container-name>` when launching you container to get the ip of it and change YOUR-IP in the code

Create the image for the python web-app with `docker-compose build`

Now launch your container with `docker-compose up -d`

You can check the logs with `docker logs python3.8` or `docker-compose logs`

You can check the status of your container with `docker ps -a`

