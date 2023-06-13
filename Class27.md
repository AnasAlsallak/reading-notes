# Readings: Django Models

## Table of Contents

- [Django Models](#django-models)
- [Django Admin](#django-admin)
- [Django key components and workflow](#django-key-components-and-workflow)
- [Things I want to know more about](#things-i-want-to-know-more-about)

## Django Models

Django models are a crucial aspect of server-side web development, as they provide a way to define the structure of the data that your application will work with. Understanding how to create and manage Django models is essential for building robust and scalable web applications.

The purpose of Django models is to define the data structure for your application, which in turn creates the database schema. They serve as an abstraction layer between the application and After defining your Django models, you can use them to perform various database operations, such as creating, reading, updating, and deleting records. Django provides a high-level Object-Relational Mapping (ORM) framework that allows you to interact with the database using Python objects and methods instead of writing raw SQL queries.

To perform these operations, you can use the model's manager, which is an instance of the `django.db.models.Manager` class. By default, Django provides a manager named `objects` for every model. Here are some examples of common database operations using the `Book` model from the previous example:

    1. Creating a new record:

    ```python
    new_book = Book(title="The Catcher in the Rye", author="J.D. Salinger", publication_date="1951-07-16", price="10.99")
    new_book.save()
    ```

    2. Retrieving records:

    ```python
    all_books = Book.objects.all()
    books_by_author = Book.objects.filter(author="J.D. Salinger")
    ```

    3. Updating records:

    ```python
    book_to_update = Book.objects.get(id=1)
    book_to_update.price = "12.99"
    book_to_update.save()
    ```

    4. Deleting records:

    ```python
    book_to_delete = Book.objects.get(id=1)
    book_to_delete.delete()
    ```

Django models also support more advanced querying capabilities, such as chaining filters, excluding records based on certain criteria, and performing complex lookups using the `Q` object and the `F` object.

In addition to the database operations, Django models can include custom methods and properties to encapsulate business logic related to the data. This helps keep your code organized and maintainable.

By leveraging Django models and the ORM, you can build web applications that are easy to develop, maintain, and scale. The abstraction provided by Django models allows you to focus on the application logic rather than dealing with the intricacies of database management, making it an invaluable tool for server-side web development.

Source: [Mozilla Developer Network - Django Models](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models)

## Django Admin

The Django Admin interface is a powerful and essential tool for managing the data in your Django application. It provides a web-based interface for performing CRUD (Create, Read, Update, and Delete) operations on your application's data, making it an invaluable resource for developers and administrators alike. Understanding how to use and customize the Django Admin interface is crucial for efficiently managing your application's data and ensuring its smooth operation.

The primary features and functionality of the Django Admin interface include:

1. Authentication and authorization: The Django Admin interface is secured by default, requiring users to log in with a valid username and password. It also supports granular permissions, allowing you to control which users can access specific models and perform certain actions.

2. CRUD operations: The Admin interface allows you to easily create, read, update, and delete records for your application's models. It provides a user-friendly interface for managing your data without having to write custom views or forms.

3. Search and filtering: The Admin interface supports searching and filtering records based on specific fields, making it easy to find and manage the data you need.

4. Customization: The Django Admin interface is highly customizable, allowing you to tailor its appearance and functionality to suit the specific needs of your project.

To customize the Django Admin interface, you can perform the following actions:

    1. Register your models: To make your models accessible in the Admin interface, you need to register them in the `admin.py` file of your app. This can be done using the `admin.site.register()` function.

    ```python
    from django.contrib import admin
    from .models import Book

    admin.site.register(Book)
    ```

    2. Customize the model's admin options: You can create a custom admin class that inherits from `admin.ModelAdmin` and override its attributes and methods to customize the appearance and behavior of the model in the Admin interface. For example, you can define the `list_display`, `list_filter`, and `search_fields` attributes to control which fields are displayed, filterable, and searchable.

    ```python
    class BookAdmin(admin.ModelAdmin):
        list_display = ('title', 'author', 'publication_date', 'price')
        list_filter = ('author', 'publication_date')
        search_fields = ('title', 'author')

    admin.site.register(Book, BookAdmin)
    ```

    3. Customize forms and fields: You can further customize the Admin interface by defining custom forms and fields for your models. This allows you to control the layout, validation, and appearance of the forms used to create and edit records.

    4. Add custom actions: You can define custom actions that can be performed on multiple records at once, such as bulk updates or deletions.

By customizing the Django Admin interface, you can create a tailored experience that meets the specific needs of your project, making it an even more powerful tool for managing your application's data.

Source: [Mozilla Developer Network - Django Admin Site](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site)

## Django key components and workflow

Studying Django is essential for web developers because it is a powerful and flexible web framework that enables rapid development of web applications. By understanding the key components and workflow of a Django application, developers can efficiently build and maintain scalable and robust web applications.

The key components and workflow of a Django application, as discussed in the Beginner's Guide to Django, include:

1. Project: A Django project is a collection of configurations and apps that together form a web application. It contains one or more Django apps, each serving a specific functionality.

2. App: A Django app is a self-contained module that encapsulates a specific functionality of the web application. It consists of models, views, templates, and other components required to implement that functionality.

3. Model: A model is a Python class that represents a database table and defines the structure of the data that the application will work with. It serves as an abstraction layer between the application and the database.

4. View: A view is a Python function that handles a specific HTTP request and produces an HTTP response. It receives input from the user, processes it, and returns the appropriate response, which can be an HTML page, JSON data, or any other type of content.

5. Template: A template is a text file that defines the structure and layout of an HTML page. It can include placeholders for dynamic content, which are filled in with actual data when the template is rendered by a view.

6. URLconf: The URLconf is a Python module that maps URLs to views. It defines a set of patterns that are matched against the requested URL, and the first pattern that matches is used to determine which view should handle the request.

The workflow of a Django application can be summarized as follows:

1. A user sends an HTTP request to the application by entering a URL in their browser or clicking a link.

2. The Django application processes the request by matching the URL against the patterns defined in the URLconf. The first pattern that matches the requested URL is used to determine which view should handle the request.

3. The view function receives the request, processes it, and returns an HTTP response. This may involve querying the database using models, rendering a template with dynamic content, or performing other actions based on the request.

4. If a template is used, the view renders the template by filling in the placeholders with actual data, which can come from the database, user input, or other sources.

5. The rendered HTML content is sent back to the user as part of the HTTP response, which is displayed in their browser.

By understanding the key components and workflow of a Django application, developers can efficiently build and maintain scalable and robust web applications that meet the needs of their users.

Source: [A Complete Beginner's Guide to Django - Part 1](https://simpleisbetterthancomplex.com/series/2017/09/04/a-complete-beginners-guide-to-django-part-1.html)

## Things I want to know more about

The stuff above.

[Move Class 28](./Class28.md) | [Previous](./Class26.md)
