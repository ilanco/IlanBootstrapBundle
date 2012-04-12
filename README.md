IlanBootstrapBundle
===================

Twitter bootstrap integration for Symfony 2.


## Installation ##

Add the following code to your deps file:

    [IlanBootstrapBundle]
        git=http://github.com/ilanco/IlanBootstrapBundle.git
        target=/bundles/Ilan/Bundle/BootstrapBundle

And then run the vendors install command:

    $ ./bin/vendors install

Ensure the Ilan namespace can be loaded by updating your autoload.php:

    $loader->registerNamespaces(array(
        ...
        'Ilan'             => __DIR__.'/../vendor/bundles',
        ...
    ));

Then register the bundle in the `AppKernel.php` file:

    public function registerBundles()
    {
        $bundles = array(
            ...
            new Ilan\Bundle\BootstrapBundle(),
            ...
        );

        return $bundles;
    }

And finally don't forget to install the bundle assets into your web root:

    $ ./app/console assets:install web --symlink


## Basic html code for base.html.twig in app/Resources/views

``` html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8" />
        <title>{% block title %}Welcome!{% endblock %}</title>
        {% block stylesheets %}{% endblock %}
        <link rel="shortcut icon" href="{{ asset('favicon.ico') }}" />
    </head>
    <body>
        {% block body %}{% endblock %}
        {% block javascripts %}{% endblock %}
    </body>
</html>

```

