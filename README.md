# Docker
Docker is a tool that is used to automate the deployment of applications in lightweight containers so that applications can work efficiently in different environments in isolation. <br>
## Project Overview
This project uses Docker to deploy a simple front-end and back-end server connected with a reverse proxy and load-balancer.<br> 

## Build and Run
<p>Each directory in this repository corresponds to a different stage of development of the final reverse proxy server. This dropdown contains the specific command needed to build each image and run the container.</p>
<details>
  <summary>Task0</summary>
  <h5>Build</h5>

```
  docker build -f ./Dockerfile -t softy-pinko:task0 .
```

  <h5>Run</h5>

```
  docker run -it --rm --name softy-pinko-task0 softy-pinko:task0
```

</details>
<details>
  <summary>Task1</summary>
  <h5>Build</h5>

```
  docker build -f ./Dockerfile -t softy-pinko:task1 .
```

  <h5>Run</h5>

```
  docker run -it --rm --name softy-pinko-task1 softy-pinko:task1
```
<h5>Check localhost:5252/api/hello</h5>

<a>http://localhost:5252/api/hello</a><br>

</details>
<details>
  <summary>Task2</summary>
  <h5>Build</h5>

```
  docker build -f ./Dockerfile -t softy-pinko:task2 .
```

  <h5>Run</h5>

```
  docker run -it --rm --name softy-pinko-task2 softy-pinko:task2
```
<h5>Check localhost:9000</h5>

<a>http://localhost:9000</a><br>
</details>
<details>
  <summary>Task3</summary>
  <h5>Build Back End</h5>

```
  docker build -f ./back-end/Dockerfile -t softy-pinko-back-end:task3 ./back-end
```

  <h5>Run Back End</h5>

```
  docker run -p 5252:5252 -d -it --rm --name softy-pinko-back-end-task3 softy-pinko-back-end:task3
```
<h5>Check localhost:5252/api/hello</h5>

<a>http://localhost:5252/api/hello</a><br>

  <h5>Build Front End</h5>

```
  docker build -f ./front-end/Dockerfile -t softy-pinko-front-end:task3 ./front-end
```

  <h5>Run Front End</h5>

```
  docker run -p 9000:9000 -it --rm --name softy-pinko-front-end-task3 softy-pinko-front-end:task3
```
<h5>Check localhost:9000</h5>

<a>http://localhost:9000</a><br>
</details>

<details><summary>Task4</summary>
    <h5>Build</h5>

```
  docker-compose build
```

  <h5>Run</h5>

```
  docker-compose up
```
<h5>Check localhost:9000</h5>

<a>http://localhost:9000</a><br>
<h5>Check localhost:5252/api/hello</h5>

<a>http://localhost:5252/api/hello</a><br>
</details>

<details><summary>Task5</summary>
    <h5>Build</h5>

```
  docker-compose build
```

  <h5>Run</h5>

```
  docker-compose up
```
<h5>Check localhost:80</h5>

<a>http://localhost:80</a><br>
</details>

<details><summary>Task6</summary>
    <h5>Build</h5>

```
  docker-compose build
```

  <h5>Run</h5>

```
  docker-compose up --scale back-end=2
```
<h5>Check localhost:80</h5>

<a>http://localhost:80</a><br>
</details>
