# ViewData-wrong-type
ViewData variable in Identity Razor pages throws an error

After creating a brand new project everything seems fine. I run the application, register a new user. I click on the email address link next to the Logout button and everything works fine. But, after I scaffold Identity razor pages if I try clicking on the email address I get an error stating that ViewData is of the wrong type.

Please note that I also thought everything was fine when after scaffolding Identity and I tried to click on the email to get to the profile for the first time it worked just fine. Then a second or third time I got the error.

The error point to line 7 of the Index.cshtml located in the Identity scaffolded pages. I have commented the lines where ViewData is used in this page, but I still get the error only with a small difference.

**For some reason ViewData is of IndexModel type. Below is the error I get: 

An unhandled exception occurred while processing the request.
InvalidOperationException: The model item passed into the ViewDataDictionary is of type 'WebApplication7.Areas.Identity.Pages.Account.Manage.IndexModel', but this ViewDataDictionary instance requires a model item of type 'System.String'.
Microsoft.AspNetCore.Mvc.ViewFeatures.ViewDataDictionary.EnsureCompatible(object value)

Stack Query Cookies Headers
InvalidOperationException: The model item passed into the ViewDataDictionary is of type 'WebApplication7.Areas.Identity.Pages.Account.Manage.IndexModel', but this ViewDataDictionary instance requires a model item of type 'System.String'.
Microsoft.AspNetCore.Mvc.ViewFeatures.ViewDataDictionary.EnsureCompatible(object value)
Microsoft.AspNetCore.Mvc.ViewFeatures.ViewDataDictionary..ctor(ViewDataDictionary source, object model, Type declaredModelType)
lambda_method(Closure , ViewDataDictionary )
Microsoft.AspNetCore.Mvc.Razor.Internal.RazorPagePropertyActivator.CreateViewDataDictionary(ViewContext context)
Microsoft.AspNetCore.Mvc.Razor.Internal.RazorPagePropertyActivator.Activate(object page, ViewContext context)
Microsoft.AspNetCore.Mvc.Razor.RazorPageActivator.Activate(IRazorPage page, ViewContext context)
Microsoft.AspNetCore.Mvc.Razor.RazorView.RenderPageCoreAsync(IRazorPage page, ViewContext context)
Microsoft.AspNetCore.Mvc.Razor.RazorView.RenderPageAsync(IRazorPage page, ViewContext context, bool invokeViewStarts)
Microsoft.AspNetCore.Mvc.Razor.RazorView.RenderAsync(ViewContext context)
Microsoft.AspNetCore.Mvc.TagHelpers.PartialTagHelper.RenderPartialViewAsync(TextWriter writer, object model)
Microsoft.AspNetCore.Mvc.TagHelpers.PartialTagHelper.ProcessAsync(TagHelperContext context, TagHelperOutput output)
Microsoft.AspNetCore.Razor.Runtime.TagHelpers.TagHelperRunner.RunAsync(TagHelperExecutionContext executionContext)
WebApplication7.Areas.Identity.Pages.Account.Manage.Areas_Identity_Pages_Account_Manage_Index.ExecuteAsync() in Index.cshtml
+
<h4>@ViewData["Title"]</h4>
Microsoft.AspNetCore.Mvc.Razor.RazorView.RenderPageCoreAsync(IRazorPage page, ViewContext context)
Microsoft.AspNetCore.Mvc.Razor.RazorView.RenderPageAsync(IRazorPage page, ViewContext context, bool invokeViewStarts)
Microsoft.AspNetCore.Mvc.Razor.RazorView.RenderAsync(ViewContext context)
Microsoft.AspNetCore.Mvc.ViewFeatures.ViewExecutor.ExecuteAsync(ViewContext viewContext, string contentType, Nullable<int> statusCode)
Microsoft.AspNetCore.Mvc.Internal.ResourceInvoker.InvokeResultAsync(IActionResult result)
Microsoft.AspNetCore.Mvc.Internal.ResourceInvoker.InvokeNextResultFilterAsync<TFilter, TFilterAsync>()
Microsoft.AspNetCore.Mvc.Internal.ResourceInvoker.Rethrow(ResultExecutedContext context)
Microsoft.AspNetCore.Mvc.Internal.ResourceInvoker.ResultNext<TFilter, TFilterAsync>(ref State next, ref Scope scope, ref object state, ref bool isCompleted)
Microsoft.AspNetCore.Mvc.Internal.ResourceInvoker.InvokeResultFilters()
Microsoft.AspNetCore.Mvc.Internal.ResourceInvoker.InvokeNextResourceFilter()
Microsoft.AspNetCore.Mvc.Internal.ResourceInvoker.Rethrow(ResourceExecutedContext context)
Microsoft.AspNetCore.Mvc.Internal.ResourceInvoker.Next(ref State next, ref Scope scope, ref object state, ref bool isCompleted)
Microsoft.AspNetCore.Mvc.Internal.ResourceInvoker.InvokeFilterPipelineAsync()
Microsoft.AspNetCore.Mvc.Internal.ResourceInvoker.InvokeAsync()
Microsoft.AspNetCore.Builder.RouterMiddleware.Invoke(HttpContext httpContext)
Microsoft.AspNetCore.Authentication.AuthenticationMiddleware.Invoke(HttpContext context)
Microsoft.AspNetCore.StaticFiles.StaticFileMiddleware.Invoke(HttpContext context)
Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.MigrationsEndPointMiddleware.Invoke(HttpContext context)
Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware.Invoke(HttpContext httpContext)
Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore.DatabaseErrorPageMiddleware.Invoke(HttpContext httpContext)
Microsoft.AspNetCore.Diagnostics.DeveloperExceptionPageMiddleware.Invoke(HttpContext context)
