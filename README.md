lowercase-dashed-routing
========================

lowercase-dashed/hyphenated-routing-for-asp-net-mvc/like-this

[NuGet Package](https://www.nuget.org/packages/LowercaseDashedRoute/).
Install with NuGet: `PM> Install-Package LowercaseDashedRoute`

[See my blog post & discussion](http://www.ata.io/lowercase-dashed-route/?utm_source=github&utm_medium=link&utm_content=bottom+link&utm_campaign=lowercase-dashed-route)

Requires .NET 4.0 or .NET 4.5.


<h3>Example</h3>
<strong>If you use:</strong>
Html.ActionLink("User Profile", "UserProfile", "Account")

**Without** Lowercase Dashed Route the url is:<br />
`yoursite.com/Account/UserProfile`

**<u>With</u>** Lowercase Dashed Route the url is:<br />
`yoursite.com/account/user-profile`

<h3>Initial Configuration</h3>
Open RouteConfig.cs in App_Start folder. Comment out old routes.MapRoute(...) call and instead use:

```c#
routes.Add(new LowercaseDashedRoute("{controller}/{action}/{id}",
    new RouteValueDictionary(
        new { controller = "Home", action = "Index", id = UrlParameter.Optional }),
        new DashedRouteHandler()
    )
);
```

If you are using areas, use the code below in your XxxAreaRegistration.cs file instead of default one and replace "AreaName"s with yours:
```c#
var route = new LowercaseDashedRoute("AreaName/{controller}/{action}/{id}",
        new RouteValueDictionary(
            new
            {
                action = "Index",
                id = UrlParameter.Optional
            }),
        new DashedRouteHandler()
    );
context.Routes.Add("AreaName_default", route);
```

Developers: <br/>
[Ata Sasmaz](http://www.ata.io/?utm_source=github&utm_medium=link&utm_content=bottom+link&utm_campaign=lowercase-dashed-route)

[![githalytics.com alpha](https://cruel-carlota.pagodabox.com/68aaf0cf0d381566c247ed5749e15135 "githalytics.com")](http://githalytics.com/AtaS/lowercase-dashed-route)
