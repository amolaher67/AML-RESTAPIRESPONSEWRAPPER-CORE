# AML-RESTAPIRESPONSEWRAPPER-CORE
Now that we already implemeted our custom middlerware, we can then create a static class to simplify adding the middleware to the application’s pipeline:

Hide   Copy Code
public static class ApiResponseMiddlewareExtension
{
    public static IApplicationBuilder UseAPIResponseWrapperMiddleware(this IApplicationBuilder builder)
    {
        return builder.UseMiddleware<APIResponseMiddleware>();
    }
}
And the final step to use our custom middleware is to call the extension method that we created above within the Configure() method of Startup class:

Hide   Copy Code
app.UseAPIResponseMiddleware();
