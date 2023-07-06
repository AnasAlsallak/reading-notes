# Readings 32: Permissions & Postgresql

## Table of Contents

- [DRF permissions](#drf-permissions)
- [SELECT statement](#select-statement)
- [DRF Generic Views](#drf-generic-views)
- [Things I want to know more about](#things-i-want-to-know-more-about)

## DRF permissions

 Authentication and authorization are crucial for any production API to ensure secure access. Django REST Framework (DRF) provides a permissions system that allows granular control over which endpoints a user can access.

The key components of DRF permissions are:

1. Permission classes: These define the logic for checking if a user has permission to access an API view. DRF has default classes like IsAuthenticated, IsAdminUser, etc. We can also write custom permission classes.

2. Applying permissions to views: We apply permission classes to API views to check user permissions for that view. For example, we can apply IsAuthenticated to require authentication, and IsAdminUser to only allow admin users.

3. Object-level permissions: DRF also allows applying permissions to individual objects, to control who can access them. We define a .has_object_permission() method on the serializer class to check object permissions.

The purpose of the DRF permissions system is to allow fine-grained control over who can access API data and endpoints. By applying permissions at the view and object level, we can ensure that sensitive data and endpoints are only accessible to authorized users. This helps secure the API by preventing unauthorized access.

In summary, DRF permissions are a key tool for authentication and authorization in Django REST Framework, and help build secure APIs by controlling access at a granular level.

## SELECT statement

The SELECT statement is the primary way to query data from a database table in SQL. It allows us to specify which columns we want to retrieve, from which tables, and any conditions to filter the results.

To retrieve all columns from a table called 'employees', we would use the following SELECT statement:

SELECT * FROM employees;

The * wildcard selects all columns from the table. This statement would return all rows from the employees table, with data for all columns.

The SELECT statement is crucial for accessing and managing data in a SQL database. By using it, we can retrieve specific data that we need, filter and sort it, and join it across multiple tables. This allows us to query a database in a precise and powerful way.

The SELECT statement is the main way to read data from a SQL database, and is a fundamental part of managing and accessing data. To select all columns from a table, we use the * wildcard.

## DRF Generic Views

 Generic views are important for building REST APIs efficiently in Django REST Framework. They provide reusable logic for common operations like CRUD (create, retrieve, update, delete), and allow us to focus on customizing our API rather than reimplementing the same logic repeatedly.

Some examples of using generic views to build a RESTful API are:

    1. ListCreateAPIView: To create a list endpoint that also allows creating new objects. For example, to list and create new users:

    ```python
    class UserList(ListCreateAPIView):
        queryset = User.objects.all()
        serializer_class = UserSerializer
    ```

    2. RetrieveUpdateDestroyAPIView: To retrieve, update or delete an object instance. For example, to manage a single user object:

    ```python 
    class UserDetail(RetrieveUpdateDestroyAPIView):
        queryset = User.objects.all()
        serializer_class = UserSerializer
    ```

    3. CreateAPIView: To simply create a new object. For example:

    ```python
    class UserCreate(CreateAPIView):
        queryset = User.objects.all()
        serializer_class = UserSerializer
    ```

    4. ListAPIView: To simply list a queryset. For example: 

    ```python
    class UserList(ListAPIView):
        queryset = User.objects.all()
        serializer_class = UserSerializer
    ```

Generic views reduce duplication and allow us to build REST APIs faster in DRF. They provide reusable logic for common operations like listing, creating, retrieving, updating and deleting objects. By using generic views, we can focus on customizing our API rather than reimplementing generic functionality.

## Things I want to know more about

Get more in-depth DRF permissions, DRF Generic Views.

[Move Class 34](./Class33.md) | [Previous](./Class31.md)
