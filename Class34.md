# Readings 34: API Deployment

## Table of Contents

- [configuring Django settings key principles](#configuring-django-settings-key-principles)
- [White Noise library](#white-noise-library)
- [Things I want to know more about](#things-i-want-to-know-more-about)

## configuring Django settings key principles

API deployment is a crucial aspect of software development, especially in web development frameworks like Django. It involves making your application programming interface (API) available to the components of your software that need to use it. Proper organization and configuration of Django settings are essential for successful API deployment, as they ensure that the application behaves correctly in different environments (development, staging, production, etc.).

According to the "Django Settings Best Practices" reading from Django Stars, the following key principles should be followed when organizing and configuring Django settings for a project:

1. **Keep configurations in the environment**: This principle suggests that configurations should be separated from the code. This is because configurations change depending on the environment, but the code does not.

2. **Use Django-environ**: Django-environ allows you to use Twelve-factor methodology to configure your Django application with environment variables. It's a great tool to keep your sensitive credentials safe and make your configuration more flexible.

3. **Structure Django settings**: It's recommended to split settings into several files rather than keeping all settings in a single file. This makes it easier to understand and manage settings. A common practice is to have separate settings files for different environments like base.py, dev.py, prod.py, and staging.py.

4. **Don't hardcode sensitive settings, and don't put them in VCS**: Sensitive information like secret keys and passwords should not be hardcoded in settings. Instead, they should be taken from environment variables or secret files that are not stored in the version control system.

5. **Configure Django settings module**: The DJANGO_SETTINGS_MODULE environment variable should be configured to point to the correct settings file depending on the environment.

6. **Use constants for settings values**: It's a good practice to use constants in settings files, as it makes it easier to manage and change values.

7. **Keep settings in VCS**: Except for sensitive information, all other settings should be kept in the version control system. This ensures that all developers work with the same configurations and makes it easier to manage changes in settings.

These principles provide a robust and flexible approach to managing Django settings, which is crucial for successful API deployment.

Source: [Configuring Django Settings: Best Practices](https://djangostars.com/blog/configuring-django-settings-best-practices/)

## White Noise library

API deployment is a crucial aspect of studying software engineering as it involves the process of making an application's functionality accessible to other developers or users. Understanding how to efficiently serve static files in a Django application is essential for ensuring optimal performance and user experience.

According to the White Noise library documentation, it contributes to the efficient serving of static files in a Django application by simplifying the process and improving performance. White Noise allows you to serve static files directly from your Django application, eliminating the need for a separate web server like Nginx or Apache.

To integrate White Noise into a Django project, you can follow these steps:

1. Install White Noise: You can install White Noise using pip by running the command `pip install whitenoise`.

2. Configure Django settings: In your Django project's settings file, add `'whitenoise.middleware.WhiteNoiseMiddleware'` to the `MIDDLEWARE` setting. This middleware will handle serving static files.

3. Collect static files: Run the command `python manage.py collectstatic` to collect all the static files from your Django project into a single directory.

4. Configure White Noise: In your Django project's settings file, add the following configuration for White Noise:

    ```python
    STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')
    STATIC_URL = '/static/'
    STATICFILES_STORAGE = 'whitenoise.storage.CompressedManifestStaticFilesStorage'
    ```

    This configuration specifies the location where the collected static files will be stored (`STATIC_ROOT`), the URL prefix for serving static files (`STATIC_URL`), and the storage backend to use (`STATICFILES_STORAGE`).

5. Deploy your Django application: Deploy your Django application as you normally would, ensuring that White Noise is included in the deployment process.

By following these steps, you can integrate the White Noise library into your Django project and efficiently serve static files, improving the performance and reliability of your application.

Source: [White Noise Documentation](https://whitenoise.readthedocs.io/en/stable/)

## Things I want to know more about

Get more in-depth into JWT, Django app deployment.

[Move Class 35](./Class35.md) | [Previous](./Class33.md)
