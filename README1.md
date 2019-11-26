# Création d’un projet


> [ Pour créer un projet, nous allons utiliser Django pour créer l’ossature par défaut d’un projet ainsi que les fichiers de configuration par défaut.]

> Depuis un terminal en ligne de commande, déplacez-vous à l’aide de la commande cd dans un répertoire dans lequel vous souhaitez conserver votre code, puis lancez la commande suivante :

```
django-admin startproject nanproject
```

Cela va créer un répertoire **nanproject** dans le répertoire courant.

Voyons ce que startproject a créé :

```
nanproject/
        manage.py
        nanproject/
                __init__.py
                settings.py
                urls.py
                wsgi.py
```
Ces fichiers sont :

    - Le premier répertoire racine nanproject/ n’est qu’un contenant pour votre projet. Son nom n’a pas d’importance pour Django ; vous pouvez le renommer comme vous voulez.
    
    - manage.py : un utilitaire en ligne de commande qui vous permet d’interagir avec ce projet Django de différentes façons.
    
    - Le sous-répertoire nanproject/ correspond au paquet Python effectif de votre projet. C’est le nom du paquet Python que vous devrez utiliser pour importer ce qu’il contient (par ex. nanproject.urls).
    
    - nanproject/__init__.py : un fichier vide qui indique à Python que ce répertoire doit être considéré comme un paquet.
    
    - nanproject/settings.py : réglages et configuration de ce projet Django.
    
    - nanproject/urls.py : les déclarations des URL de ce projet Django, une sorte de « table des matières » de votre site Django.
    
    - nanproject/wsgi.py : un point d’entrée pour les serveurs Web compatibles WSGI pour déployer votre projet.


## Le serveur de développement

Vérifions que votre projet Django fonctionne. Déplacez-vous dans le répertoire nanproject si ce n’est pas déjà fait, et lancez les commandes suivantes :

```
python3 manage.py runserver
```
Vous verrez les messages suivants défiler en ligne de commande :

```
Performing system checks...

System check identified no issues (0 silenced).

You have unapplied migrations; your app may not work properly until they are applied.
Run 'python manage.py migrate' to apply them.

novembre 26, 2019 - 11:06:53
Django version 2.2, using settings 'nanproject.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```


# Création de l’application **appnan**


Pour créer votre application, assurez-vous d’être dans le même répertoire que manage.py et saisissez cette commande :

```
python3 manage.py startapp appnan
```


Cela va créer un répertoire **appnan**, qui est structuré de la façon suivante :

```
appnan/
    __init__.py
    admin.py
    apps.py
    migrations/
            __init__.py
    models.py
    tests.py
    views.py
```

## Configuration

Pour inclure l’application dans notre projet, nous avons besoin d’ajouter une référence à sa classe de configuration dans le réglage INSTALLED_APPS. La classe AppnanConfig se trouve dans le fichier appnan/apps.py, ce qui signifie que son chemin pointé est 'appnan.apps.AppnanConfig'. Modifiez le fichier nanproject/settings.py et ajoutez ce chemin pointé au réglage INSTALLED_APPS. Il doit ressembler à ceci :

```

Dans nanproject/settings.py

INSTALLED_APPS = [
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
        'appnan.apps.AppnanConfig',
]

```

Maintenant, Django sait qu’il doit inclure l’application appnan. Exécutons une autre commande :

```
python3 manage.py migrate
```

Ensuite

```
python3 manage.py runserver
```





`Edited by Princ'Gba and Dago`









