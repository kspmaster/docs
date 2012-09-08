Class **Phalcon\\Mvc\\View**
============================

*extends* :doc:`Phalcon\\Mvc\\User <Phalcon_Mvc_User>`

Phalcon\\Mvc\\View is a class for working with the "view" portion of the model-view-controller pattern. That is, it exists to help keep the view script separate from the model and controller scripts. It provides a system of helpers, output filters, and variable escaping. 

.. code-block:: php

    <?php

     //Setting views directory
     $view = new Phalcon\Mvc\View();
     $view->setViewsDir('app/views/');
    
     $view->start();
     //Shows recent posts view (app/views/posts/recent.phtml)
     $view->render('posts', 'recent');
     $view->finish();
    
     //Printing views output
     echo $view->getContent();



Constants
---------

integer **LEVEL_MAIN_LAYOUT**

integer **LEVEL_AFTER_TEMPLATE**

integer **LEVEL_LAYOUT**

integer **LEVEL_BEFORE_TEMPLATE**

integer **LEVEL_ACTION_VIEW**

integer **LEVEL_NO_RENDER**

Methods
---------

public **__construct** (*array* $options)

Phalcon\\Mvc\\View constructor



public **setViewsDir** (*string* $viewsDir)

Sets views directory. Depending of your platform, always add a trailing slash or backslash



*string* public **getViewsDir** ()

Gets views directory



public **setBasePath** (*string* $basePath)

Sets base path. Depending of your platform, always add a trailing slash or backslash 

.. code-block:: php

    <?php

     $view->setBasePath(__DIR__.'/');




public **setRenderLevel** (*string* $level)

Sets the render level for the view 

.. code-block:: php

    <?php

     //Render the view related to the controller only
     $this->view->setRenderLevel(Phalcon\Mvc\View::LEVEL_VIEW);




public **setMainView** (*unknown* $viewPath)

Sets default view name. Must be a file without extension in the views directory 

.. code-block:: php

    <?php

     //Renders as main view views-dir/inicio.phtml
     $this->view->setMainView('inicio');




public **setTemplateBefore** (*string|array* $templateBefore)

Appends template before controller layout



public **cleanTemplateBefore** ()

Resets any template before layouts



public **setTemplateAfter** (*string|array* $templateAfter)

Appends template after controller layout



public **cleanTemplateAfter** ()

Resets any template before layouts



public **setParamToView** (*string* $key, *mixed* $value)

Adds parameters to views (alias of setVar)



public **setVar** (*string* $key, *mixed* $value)

Adds parameters to views



*array* public **getParamsToView** ()

Returns parameters to views



*string* public **getControllerName** ()

Gets the name of the controller rendered



*string* public **getActionName** ()

Gets the name of the action rendered



public **getParams** ()

Gets extra parameters of the action rendered



public **start** ()

Starts rendering process enabling the output buffering



*array* protected **_loadTemplateEngines** ()

Loads registered template engines, if none is registered it will use Phalcon\\Mvc\\View\\Engine\\Php



protected **_engineRender** ()

Checks whether view exists on registered extensions and render it



public **registerEngines** (*array* $engines)

Register templating engines 

.. code-block:: php

    <?php

    $this->view->registerEngines(array(
      ".phtml" => "Phalcon\Mvc\View\Engine\Php",
      ".mhtml" => "MyMustacheEngine"
    ));




public **render** (*string* $controllerName, *string* $actionName, *array* $params)

Executes render process from dispatching data 

.. code-block:: php

    <?php

     $view->start();
     //Shows recent posts view (app/views/posts/recent.phtml)
     $view->render('posts', 'recent');
     $view->finish();




public **pick** (*string* $renderView)

Choose a view different to render than last-controller/last-action 

.. code-block:: php

    <?php

     class ProductsController extends Phalcon\Mvc\Controller
     {
    
        public function saveAction()
        {
    
             //Do some save stuff...
    
             //Then show the list view
             $this->view->pick("products/list");
        }
     }




public **partial** (*string* $partialPath)

Renders a partial view 

.. code-block:: php

    <?php

     //Show a partial inside another view
     $this->partial('shared/footer');




public **finish** ()

Finishes the render process by stopping the output buffering



:doc:`Phalcon\\Cache\\Backend <Phalcon_Cache_Backend>` protected **_createCache** ()

Create a Phalcon\\Cache based on the internal cache options



:doc:`Phalcon\\Cache\\Backend <Phalcon_Cache_Backend>` public **getCache** ()

Returns the cache instance used to cache



public **cache** (*boolean|array* $options)

Cache the actual view render to certain level



public **setContent** (*string* $content)

Externally sets the view content <code>$this->view->setContent("<h1>hello</h1>");



*string* public **getContent** ()

Returns cached ouput from another view stage



public **getActiveRenderPath** ()

public **disable** ()

Disable view. No show any view or template



public **setDI** (*unknown* $dependencyInjector)

public **getDI** ()

public **setEventsManager** (*unknown* $eventsManager)

public **getEventsManager** ()

public **__get** (*unknown* $propertyName)
