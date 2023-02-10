1. What is MVC?: Model-View-Controller (MVC) is a design pattern used in software engineering to separate the concerns of an application into distinct components. The pattern consists of three main components


	1. Model: The model represents the data and the underlying business logic of an application. It is responsible for maintaining the state of the application and providing an interface for accessing and manipulating the data.
    
	2.  View: The view is responsible for rendering the data to the user. It receives data from the controller, and it formats and presents the data to the user in a way that is easy to understand and use.
    
	3.  Controller: The controller acts as the intermediary between the model and the view. It is responsible for receiving user input, making decisions based on that input, and determining the next steps for the application. The controller retrieves data from the model, processes it, and passes it to the view to be displayed to the user.

2. Advantage? 

	- provides a clear separation of concerns, which makes it easier to maintain and scale the application as it grows. 

	- By separating the data from the presentation and user interaction logic, it is possible to make changes to one component without affecting the others. 

	- This makes the code more maintainable and easier to test, and it also enables developers to work on different components of the application in parallel![[Pasted image 20230201193238.png]]

3. Example:
	- 	 ![[Pasted image 20230201194244.png]]
	1.  **사용자가 웹사이트에 접속 (Users)**
	2.  **Controller는 사용자가 요청한 웹페이지를 서비스하기 위해서 모델을 호출 (Manipulates)**
	3.  **Model은 데이터베이스나 파일과 같은 데이터 소스를 제어한 후 그 결과를 Return**
	4.  **Controller는 Model이 리턴한 결과를 View에 반영 (Updates)**
	5.  **데이터가 반영된 View는 사용자에게 보여짐 (Sees)**
	
