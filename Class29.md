# Readings 29: Django Custom User

## Table of Contents

- [Django user model](#django-user-model)
- [Creating and implementing a Custom User Model in Django](#creating-and-implementing-a-custom-user-model-in-django)
- [DjangoX](#djangox)
- [Things I want to know more about](#things-i-want-to-know-more-about)

## Django user model

Django framework provides a default User model for handling user authentication. However, this model may not always meet the specific needs of your project. For instance, the username field in the default User model is case-sensitive, which may not be ideal for all applications.

To overcome these limitations, Django allows you to create a custom User model. This can be done by subclassing `AbstractBaseUser` and `BaseUserManager` from `django.contrib.auth.base_user`. This approach provides more flexibility and is recommended for all new Django projects.

Here's a brief overview of how to create a custom User model:

1. Create a new model that inherits from `AbstractBaseUser` and `PermissionsMixin`. This new model will serve as your custom User model.

2. Define any additional fields that you need for your application.

3. Define a `USERNAME_FIELD`, which specifies the field that will be used as the username.

4. Define a `REQUIRED_FIELDS` list, which specifies the fields that will be prompted for when creating a user via the `createsuperuser` management command.

5. Define a custom manager for the User model that inherits from `BaseUserManager`. This manager should define `create_user` and `create_superuser` methods.

6. Update your Django settings to use the custom User model. This can be done by setting the `AUTH_USER_MODEL` setting to point to your custom User model.

7. Finally, make sure to create a new database migration for your custom User model and apply it to your database.

## Creating and implementing a Custom User Model in Django

Creating and implementing a Custom User Model in Django involves several steps:

1. **Create a new Django app**: This is typically named "users" or something similar. This app will contain the custom user model.

2. **Create a Custom User Model**: In the models.py file of your new app, you'll need to create a custom user model. This model should inherit from `AbstractBaseUser` and `PermissionsMixin`. The `AbstractBaseUser` provides the core implementation of a User model and `PermissionsMixin` provides fields needed for handling roles and permissions. Here's an example:

    ```python
    from django.contrib.auth.models import AbstractBaseUser, PermissionsMixin
    from django.db import models

    class CustomUser(AbstractBaseUser, PermissionsMixin):
        email = models.EmailField(unique=True)
        is_staff = models.BooleanField(default=False)
        is_active = models.BooleanField(default=True)
    ```

    In this example, the `email` field is used as the unique identifier instead of a username.

3. **Create a Custom Manager**: Since you're customizing the User model, you also need to define a custom manager for it. This manager should inherit from `BaseUserManager` and provide `create_user` and `create_superuser` methods. Here's an example:

    ```python
    from django.contrib.auth.models import BaseUserManager

    class CustomUserManager(BaseUserManager):
        def create_user(self, email, password=None, **extra_fields):
            if not email:
                raise ValueError('The Email field must be set')
            email = self.normalize_email(email)
            user = self.model(email=email, **extra_fields)
            user.set_password(password)
            user.save(using=self._db)
            return user

        def create_superuser(self, email, password=None, **extra_fields):
            extra_fields.setdefault('is_staff', True)
            extra_fields.setdefault('is_superuser', True)
            return self.create_user(email, password, **extra_fields)
    ```

    In this example, the `create_user` method normalizes the email by lowercasing the domain part of it, and then creates a user instance. The `create_superuser` method creates a user who has both `is_staff` and `is_superuser` set to True.

4. **Update settings.py**: In your settings.py file, you need to tell Django to use your new custom user model. You do this by setting the `AUTH_USER_MODEL` setting to point to your model. If your app is named "users" and your model is named "CustomUser", you would add the following line to settings.py:

    ```python
    AUTH_USER_MODEL = 'users.CustomUser'
    ```

5. **Update Admin**: If you want to use Django's built-in admin, you'll need to create a custom ModelAdmin for your user model and register it. Here's an example:

    ```python
    from django.contrib import admin
    from django.contrib.auth.admin import UserAdmin
    from .models import CustomUser

    class CustomUserAdmin(UserAdmin):
        model = CustomUser

    admin.site.register(CustomUser, CustomUserAdmin)
    ```

    This tells the admin to use your custom user model instead of the built-in one.

Remember to run migrations after these changes to update your database schema.

The information above is based on the article "Django Best Practices: Custom User Model" from the DEV Community.

## DjangoX

Ah, I see. DjangoX is a project template for Django created by William S. Vincent. It's not an extension or library, but rather a boilerplate project that includes a set of pre-configured tools and practices to kickstart your Django development.

DjangoX includes the following:

1. Django 3.0 and Python 3.8
2. User log in/out, sign up, password reset via django-allauth
3. Static files configured with Whitenoise
4. Styling with Bootstrap v4
5. Debugging with django-debug-toolbar
6. DRY forms with django-crispy-forms

This boilerplate can save you a lot of time when starting a new Django project because it includes a lot of the initial setup that you would otherwise have to do manually. It also includes some best practices and tools that are commonly used in Django development.

For example, if you're building a web application that requires user authentication, instead of setting up django-allauth from scratch, you can use DjangoX which already has it configured. You can then focus on building the unique parts of your application.

Studying DjangoX can be beneficial because it can provide insights into how experienced Django developers structure their projects and which tools they use. It can also help you understand how different components of a Django project fit together. However, it's important to have a solid understanding of Django itself before diving into DjangoX, as it assumes familiarity with Django's concepts and structures.

## Things I want to know more about

The stuff above.

[Move Class 30](./Class30.md) | [Previous](./Class27.md)
