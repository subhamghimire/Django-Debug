
Install django toolbar on your system: 
<code>pip install django-debug-toolbar</code>
<h3>In settings.py Do Following</h3>
<code><pre>INSTALLED_APPS = [
    # ...
    'django.contrib.staticfiles',
    # ...
    'debug_toolbar',]
STATIC_URL = '/static/'
</pre></code>

Enable Middleware:
<code><pre>MIDDLEWARE = [
    # ...
    'debug_toolbar.middleware.DebugToolbarMiddleware',
    # ...]
</pre></code>

Configuring internal ips:
<code><pre>INTERNAL_IPS = [
    # ...
    '127.0.0.1',
    # ...]
</pre></code>

Setting up url conf:
<code><pre>from django.conf import settingsfrom django.conf.urls import include, url # For django versions before 2.0from django.urls import include, path # For django versions from 2.0 and up
if settings.DEBUG:
    import debug_toolbar
    urlpatterns = [
        path('__debug__/', include(debug_toolbar.urls)),

        # For django versions before 2.0:
        # url(r'^__debug__/', include(debug_toolbar.urls)),

    ] + urlpatterns
</pre></code>


