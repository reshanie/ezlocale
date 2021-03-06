EzLocale
========

EzLocale is a language library that makes translation easier (hence the name).

Throw gettext in the trash, because you'll never need to manually translate again.

Powered by Google Translate, with the googletrans module. https://github.com/ssut/py-googletrans

``$ pip install ezlocale``


Basic Usage
-----------

.. code-block:: python

    import ezlocale

    # set default language to Spanish
    ezlocale.DEST = ezlocale.language.ES

    # easier translation
    _ = ezlocale.gettext

    name = input(_("What's your name? > "))

    print(_("Hello, %s!" % name))


``¿Cuál es tu nombre? > Patrick``

``¡Hola, Patrick!``


To get a language by its name, just use ``ezlocale.get_language(name)`` (case insensitive)

You can also use a different language with each call.

.. code-block:: python

    >>> ezlocale.gettext("Hello!", dest=ezlocale.get_language("Latin"))
    'Salve!'
    >>> ezlocale.gettext("¡Hola!", dest=ezlocale.language.EN, src=ezlocale.language.AUTO)  # anything to english
    'Hello!'

To


To clear the translation cache, use ``ezlocale.clear_cache()``

EzLocale uses an LFU cache for each language to make sure resources aren't wasted.
http://github.com/reshanie/faste/