Class **Phalcon\\Mvc\\Router**
==============================

*implements* :doc:`Phalcon\\Mvc\\RouterInterface <Phalcon_Mvc_RouterInterface>`, :doc:`Phalcon\\DI\\InjectionAwareInterface <Phalcon_DI_InjectionAwareInterface>`

Phalcon\\Mvc\\Router is the standard framework router. Routing is the process of taking a URI endpoint (that part of the URI which comes after the base URL) and decomposing it into parameters to determine which module, controller, and action of that controller should receive the request    

.. code-block:: php

    <?php

    $router = new Phalcon\Mvc\Router();
    
      $router->add(
    	"/documentation/{chapter}/{name}.{type:[a-z]+}",
    	array(
    		"controller" => "documentation",
    		"action"     => "show"
    	)
    );
    
    $router->handle();
    
    echo $router->getControllerName();



Methods
---------

public  **__construct** ([*boolean* $defaultRoutes])

Phalcon\\Mvc\\Router constructor



public  **setDI** (:doc:`Phalcon\\DiInterface <Phalcon_DiInterface>` $dependencyInjector)

Sets the dependency injector



public :doc:`Phalcon\\DiInterface <Phalcon_DiInterface>`  **getDI** ()

Returns the internal dependency injector



protected *string*  **_getRewriteUri** ()

Get rewrite info. This info is read from $_GET['_url']. This returns '/' if the rewrite information cannot be read



public  **removeExtraSlashes** (*boolean* $remove)

Set whether router must remove the extra slashes in the handled routes



public  **setDefaultNamespace** (*string* $namespaceName)

Sets the name of the default namespace



public  **setDefaultModule** (*string* $moduleName)

Sets the name of the default module



public  **setDefaultController** (*string* $controllerName)

Sets the default controller name



public  **setDefaultAction** (*string* $actionName)

Sets the default action name



public  **setDefaults** (*array* $defaults)

Sets an array of default paths. This defaults apply for all the routes 

.. code-block:: php

    <?php

     $router->setDefaults(array(
    	'module' => 'common',
    	'action' => 'index'
     ));




public  **handle** ([*string* $uri])

Handles routing information received from the rewrite engine 

.. code-block:: php

    <?php

     $router->handle('/posts/edit/1');




public :doc:`Phalcon\\Mvc\\Router\\Route <Phalcon_Mvc_Router_Route>`  **add** (*string* $pattern, [*string/array* $paths], [*string* $httpMethods])

Adds a route to the router on any HTTP method 

.. code-block:: php

    <?php

     $router->add('/about', 'About::index');




public :doc:`Phalcon\\Mvc\\Router\\Route <Phalcon_Mvc_Router_Route>`  **addGet** (*string* $pattern, [*string/array* $paths])

Adds a route to the router that only match if the HTTP method is GET



public :doc:`Phalcon\\Mvc\\Router\\Route <Phalcon_Mvc_Router_Route>`  **addPost** (*string* $pattern, [*string/array* $paths])

Adds a route to the router that only match if the HTTP method is POST



public :doc:`Phalcon\\Mvc\\Router\\Route <Phalcon_Mvc_Router_Route>`  **addPut** (*string* $pattern, [*string/array* $paths])

Adds a route to the router that only match if the HTTP method is PUT



public :doc:`Phalcon\\Mvc\\Router\\Route <Phalcon_Mvc_Router_Route>`  **addPatch** (*string* $pattern, [*string/array* $paths])

Adds a route to the router that only match if the HTTP method is PATCH



public :doc:`Phalcon\\Mvc\\Router\\Route <Phalcon_Mvc_Router_Route>`  **addDelete** (*string* $pattern, [*string/array* $paths])

Adds a route to the router that only match if the HTTP method is DELETE



public :doc:`Phalcon\\Mvc\\Router\\Route <Phalcon_Mvc_Router_Route>`  **addOptions** (*string* $pattern, [*string/array* $paths])

Add a route to the router that only match if the HTTP method is OPTIONS



public :doc:`Phalcon\\Mvc\\Router\\Route <Phalcon_Mvc_Router_Route>`  **addHead** (*string* $pattern, [*string/array* $paths])

Adds a route to the router that only match if the HTTP method is HEAD



public  **mount** (*unknown* $group)

Mounts a group of routes in the router



public  **clear** ()

Removes all the pre-defined routes



public *string*  **getNamespaceName** ()

Returns the processed namespace name



public *string*  **getModuleName** ()

Returns the processed module name



public *string*  **getControllerName** ()

Returns the processed controller name



public *string*  **getActionName** ()

Returns the processed action name



public *array*  **getParams** ()

Returns the processed parameters



public :doc:`Phalcon\\Mvc\\Router\\Route <Phalcon_Mvc_Router_Route>`  **getMatchedRoute** ()

Returns the route that matchs the handled URI



public *array*  **getMatches** ()

Returns the sub expressions in the regular expression matched



public *bool*  **wasMatched** ()

Checks if the router macthes any of the defined routes



public :doc:`Phalcon\\Mvc\\Router\\Route <Phalcon_Mvc_Router_Route>` [] **getRoutes** ()

Returns all the routes defined in the router



public :doc:`Phalcon\\Mvc\\Router\\Route <Phalcon_Mvc_Router_Route>`  **getRouteById** (*string* $id)

Returns a route object by its id



public :doc:`Phalcon\\Mvc\\Router\\Route <Phalcon_Mvc_Router_Route>`  **getRouteByName** (*string* $name)

Returns a route object by its name



