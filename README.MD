Tema 18 - Kubernetes

* Requisitos:

	- Docker
	- Minikube
	- Kubectl
	- Jenkins
	
* Configurando o Jenkins:
		
		1.	Criar novo item
		2.	Colocar o nome do Job e escolher a opção 'Pipeline'
		3.	Em seguida no campo Pipeline definition escolher a opção 'Pipeline script from SCM'
		4.	No campo SCM escolher a opção 'Git'
		5.	No campo Repository URL inserir: 'https://github.com/julianooen/Calculator-go-kubernetes.git'
		6.	Em Branch Specifier preencher com '*/master'
		7.	Em Script Path preencher com 'Jenkinsfile'
	
* Resultados:
	
	- Após rodar o job, no console é possível encontrar a url do minikube para acesser a aplicação
    ```
    + minikube service gocalculator
    |-----------|--------------|-------------|---------------------------|
    | NAMESPACE |     NAME     | TARGET PORT |            URL            |
    |-----------|--------------|-------------|---------------------------|
    | default   | gocalculator |        8080 | http://192.168.49.2:31199 |
    |-----------|--------------|-------------|---------------------------|
    ```

* Acessando o serviço:

	Operações:
	- Soma: http://{minikubeIPandPort}/calc/sum/10/5
	- Subtração: http://{minikubeIPandPort}/calc/sub/10/5
	- Divisão: http://{minikubeIPandPort}/calc/div/10/5
	- Multiplicação: http://{minikubeIPandPort}/calc/mul/10/5
	- Histórico: http://{minikubeIPandPort}/calc/history
