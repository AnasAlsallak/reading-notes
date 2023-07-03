# Readings 31: Django REST Framework & Docker

## Table of Contents

- [Docker](#docker)
- [Building a Django library website](#building-a-django-library-website)
- [Django REST Framework](#django-rest-framework)
- [Things I want to know more about](#things-i-want-to-know-more-about)

## Docker

Docker containers are a key tool in modern software development, particularly in the realm of DevOps and cloud computing. They help to streamline the development and deployment of applications by creating isolated, self-sufficient packages that contain everything needed to run an application. Here are the key components of a Docker container:

1. Docker Image: This is a lightweight, standalone, executable package that includes everything needed to run a piece of software, including the code, a runtime, libraries, environment variables, and config files. Docker images are read-only and form the basis of a Docker container.

2. Dockerfile: This is a text file that contains all the commands, in order, needed to build a given Docker image. It's like a blueprint for creating Docker images.

3. Docker Containers: These are runtime instances of Docker images. Containers encapsulate the application, its dependencies, and the environment in which it runs. This ensures that the application works uniformly despite differences in OS and infrastructure.

4. Docker Engine: This is the runtime that runs and manages the containers. It's the core of the Docker platform.

5. Docker Compose: This is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application's services, and then with a single command, you create and start all the services from your configuration.

6. Docker Hub: This is a cloud-based registry service that allows you to link code repositories, build details, and more. It provides a centralized resource for container image discovery, distribution, change management, and team collaboration.

These components work together to ensure that applications run the same way regardless of where they are deployed, eliminating the "it works on my machine" problem. This uniformity simplifies the development, testing, and deployment process, making it more efficient and less error-prone. It also makes it easier to scale applications, since new containers can be easily created and deployed as needed.

## Building a Django library website

Building a library website using Django involves several steps. Django follows the Model-View-Template (MVT) architectural pattern, which is a variant of the Model-View-Controller (MVC) pattern. Here are the primary steps:

1. **Set Up Your Development Environment**: Before you start, you need to set up your development environment. This includes installing Python, Django, and setting up a virtual environment if necessary.

2. **Create a Django Project**: Use the `django-admin startproject` command to create a new Django project. This will create a new directory with the project settings.

3. **Create a Django App**: Within your project, you can create one or more apps (components of the project) using the `python manage.py startapp` command. For a library website, you might create an app called 'books' or 'library'.

4. **Define Your Models**: Models in Django represent the data structures of your application. They are essentially the schema for your database tables. For a library website, you might have models like Book, Author, Publisher, etc. Each model maps to a single database table.

5. **Create Your Database**: After defining your, you can use Django's database API to create your database. Django supports several databases like SQLite, PostgreSQL, MySQL, etc. You can create the database tables using the `python manage.py makemigrations` and `python manage.py migrate` commands.

6. **Define Your Views**: Views in Django handle the logic and control flow of your application. They receive HTTP requests and return HTTP responses. Views access the data needed to satisfy requests via models, and delegate to templates for formatting.

7. **Create Your Templates**: Templates in Django are how you create the HTML (or other code) that your views will send as responses. They provide a way to separate your Python code from your HTML code. Django's template language is very powerful and allows you to create reusable layouts, handle data from your views, and more.

8. **Map URLs to Views**: Django uses a URL dispatcher which maps URL patterns to views. You'll define these patterns in your app's urls.py file.

9. **Create Forms (if necessary)**: If your website needs to accept input from users, you'll use Django's forms. Forms can handle form validation, display form fields, and more.

10. **Test Your Application**: Django comes with a built-in testing framework that you can use to write unit tests for your models, views, forms, and other parts of your application.

11. **Deploy Your Application**: Once you're happy with your application, you can deploy it to a server. There are many options for deploying Django applications, including services like Heroku, AWS, and Google Cloud.

Django is designed for reusability and pluggability of components, rapid development, and the principle of don't repeat yourself (DRY). So, you can always extend your application by adding more apps to it as your project grows.

To clarify  what do we mean by a **library website**, in the context of software development, typically refers to a web application that provides online access to a library's resources. It's essentially a digital platform that represents a physical library on the internet.

Here are some of the key features that a library website might include:

1. **Catalog Search**: Users should be able to search the library's catalog of books, periodicals, and other materials. This might involve a simple search box, or more advanced search features like by author, genre, publication date, etc.

2. **User Accounts**: Users might have their own accounts where they can check out books, place holds, renew items, and manage their library account.

3. **Information Pages**: The website would likely include pages with information about the library, such as its location, hours, policies, and events.

4. **Digital Resources**: Many libraries offer digital resources, such as e-books, audiobooks, and online databases. The library website would provide access to these resources.

5. **Help and Support**: The website might include a help section, FAQs, or a way to contact library staff for support.

6. **Community Features**: Some library websites include features like book clubs, reading lists, or forums where users can discuss books.

Building a library website would involve many of the same steps as building any other web application, but with a focus on these specific features.

## Django REST Framework

Django is a high-level Python framework that encourages rapid development and clean, pragmatic design. It's built by experienced developers and takes care of much of the hassle of web development, so you can focus on writing your app without needing to reinvent the wheel. It’s free and open source. Django follows the MVT (Model-View-Template) architectural pattern and it includes features like authentication, URL routing, template engine, ORM, and database schema migrations.

On the other hand, Django REST Framework, often abbreviated as "DRF", is a toolkit that is built on top of Django for building Web APIs. It's a powerful and flexible toolkit for building Web APIs and it's used to build APIs for your Django application. 

Some of the reasons you might want to use REST framework:

1. Web browsable API is a huge usability win for your developers.
2. Authentication policies including packages for OAuth1a and OAuth2.
3. Serialization that supports both ORM and non-ORM data sources.
4. Customizable all the way down - just use regular function-based views if you don't need the more features.
5. Extensive documentation, and great community support.
6. Used and trusted by internationally recognised companies including Mozilla, Red Hat, Heroku, and Eventbrite.

So, in summary, Django is used for building full-fledged web applications while Django REST Framework is used to build APIs for web applications built using Django or other platforms.

## Things I want to know more about

Get more in-depth into Django REST Framework & Docker.

[Move Class 32](./Class32.md) | [Previous](./Class30.md)
