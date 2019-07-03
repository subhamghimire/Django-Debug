
:heart:Install django debug toolbar on your system:   [![](https://img.shields.io/badge/pip-django__toolbar-yellowgreen.svg)](https://pypi.org/project/django-debug-toolbar/)

<code>pip install django-debug-toolbar</code>
<h3>In settings.py Do Following</h3>
<code><pre>INSTALLED_APPS = [
    # ...
    'django.contrib.staticfiles',
    # ...
    'debug_toolbar',]
STATIC_URL = '/static/'
</pre></code>

*Enable Middleware*:
<code><pre>MIDDLEWARE = [
    # ...
    'debug_toolbar.middleware.DebugToolbarMiddleware',
    # ...]
</pre></code>

*Configure internal ips*:
<code><pre>INTERNAL_IPS = [
    # ...
    '127.0.0.1',
    # ...]
</pre></code>

<h3>In The Project's urls.py Do Following</h3>

_Setting up url conf_:
<pre>
from django.conf import settings
from django.conf.urls import include, url # For django versions before 2.0from django.urls import include, path # For django versions from 2.0 and up 

if settings.DEBUG:
    import debug_toolbar
    urlpatterns = [
        path('__debug__/', include(debug_toolbar.urls)),
        # For django versions before 2.0:
        # url(r'^__debug__/', include(debug_toolbar.urls)),
    ] + urlpatterns
</pre>
