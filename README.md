# A24-Assignment2
#  StudentProject - Multi-App Django with Docker & Jenkins  

##  Project Overview  
**StudentProject** is a Django-based web application that demonstrates:  
* **Multi-App Django Structure** (`app1` & `app2`)  
* **No Database Requirement** (Only static views & templates)  
* **Dockerized Deployment** for portability  
* **CI/CD with Jenkins** to automate building & pushing the image to Docker Hub  

## How to Run the Project Locally  
Follow these steps to set up and run the project on your local machine.

### **Clone the Repository**
```sh
git https://github.com/aryan2511115/A24-Assignment2.git
cd Assignment2
```
### 2. Run Using Docker
If you want to run the project inside a Docker container, use:
```sh
docker build -t aj410721/assignment2:0.0.1.RELEASE .
docker run -d -p 8000:8000 aj410721/assignment2:0.0.1.RELEASE
```
Now, open http://127.0.0.1:8000/ in your browser.
### 3. Pull from Docker Hub
Instead of building manually, you can pull the prebuilt image:
```sh
docker pull gunjanpandya/assignment2:0.0.1.RELEASE
docker run -d -p 8000:8000 gunjanpandya/assignment2:0.0.1.RELEASE
```
your project will be live on http://127.0.0.1:8000/
### 4. Jenkins CI/CD Pipeline
The Jenkins pipeline automates:

Pulling code from GitHub
Building a Docker image
Pushing it to Docker Hub To trigger the pipeline, push any changes to GitHub, and Jenkins will do the rest!
### 6. Conclusion
This project demonstrates a full CI/CD pipeline with Django, Docker, and Jenkins. It ensures that every code change is automatically built, tested, and deployed using best DevOps practices.
