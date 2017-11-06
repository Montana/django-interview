1. [Middleware](#middleware) 
    a. How do you create custom middleware in django ?
        - Middleware is a regular python class that hooks into request/response life cycle.
        - Middleware is processed on every request response cycle of  a django application.
        - Middleware should register in `MIDDLWARE_CLASSES`
        - During request middleware are executed from top down in response cycle they are executed from bottom up.

        Middleware should define at least on of the following methods 

        ```
        process_request(request)
            # called during the request 
            pass 

        process_view(request, view_func, view_args, view_kwargs)
            # called during request


        # Called during response:
        process_exception(request, exception) (only if the view raised an exception)
            print(exception.message)
            pass 

        process_template_response(request, response) (only for template responses)
            pass 

        process_response(request, response)
            pass
        ```

      As middleware classes are invoked twice so it is importent to hook middleware in order.


      <img src="https://simpleisbetterthancomplex.com/media/2016-07-18-how-to-create-a-custom-django-middleware/middleware.svg">

      [ip filter middleware](middleware.py)



`
