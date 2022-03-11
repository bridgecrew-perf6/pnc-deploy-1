# 301 - Transferred to the [official organization](https://github.com/Preben-Norwegian-Community)

# pnc-deploy
The deploy of Preben Norwegian Community software

## Project purpose

All the software, which is deployed with **Docker** and managed with **DockerHUB**, needs a **docker-compose.yml** file to be deployed. This repos contains two folders, one for the **development** deployment and one for the **prod** deployment. Apart from the docker-compose.yml, there are also **many .env.example** files that shows the **properties that the .env configuration files should have**. There are also other **.example** files that act as **placeholders** for private files. There is also a **nginx.conf** for **Nginx** configuration.

## Deployment structure

The **services** are:
* Everything passes through **Nginx**
* The **Web App** made with Vue.js is built and served as **static assets** on the path `/`
* The **Rest APIs** made with Node.js are served on the path `/api`
* The **Webcomponents** made with Vue.js are built and served as **static assets** on the path `/webcomponents`
* The **Redis DB** used by the APIs is just **used internally*

Some **volumes** are **physical** so that the data can be easily accessed and exported/imported.

**Watchtower** is used, so that when there is a new image available on DockerHUB it is automatically downloaded and deployed. **This way at every push (actually merge) on Github the deployment is handled automatically**.
