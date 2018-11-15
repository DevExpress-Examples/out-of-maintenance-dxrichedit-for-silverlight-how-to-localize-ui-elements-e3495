<!-- default file list -->
*Files to look at*:

* [App.xaml.cs](./CS/App.xaml.cs)
* [MainPage.xaml](./CS/MainPage.xaml) (VB: [MainPage.xaml.vb](./VB/MainPage.xaml.vb))
* [MainPage.xaml.cs](./CS/MainPage.xaml.cs) (VB: [MainPage.xaml.vb](./VB/MainPage.xaml.vb))
<!-- default file list end -->
# DXRichEdit for Silverlight: How to localize UI elements


<p>This example illustrates how to localize a sample Silverlight application with RichEditControl. Please follow these steps to accomplish this task:</p><p>1) Download all necessary satellite assemblies from the <a href="https://www.devexpress.com/Support/Center/p/A421">The collection of localized DevExpress assemblies</a> KB article.</p><p>2) Copy them from the DevExpress.DLL folder to the SL folder: <DevExpress_Install_Path>\Components\Bin\Silverlight\. In this example, we will copy ...\DevExpress.DLL\de folder from the archive to the SL folder.</p><p>3) Modify the *.csproj (*.vbproj for VB.NET) file of your project to add your culture: <SupportedCultures>de</SupportedCultures></p><p>4) Open the project in VS and update the Application_Startup event handler in the App.xaml.cs (Application.xaml.vb for VB.NET) file as follows:</p><p><br />


```cs
       private void Application_Startup(object sender, StartupEventArgs e) {<newline/>
           Thread.CurrentThread.CurrentCulture = new CultureInfo("de");<newline/>
           Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");<newline/>
           this.RootVisual = new MainPage();<newline/>
       }<newline/>

```



```vb
       Private Sub Application_Startup(ByVal sender As Object, ByVal e As StartupEventArgs)<newline/>
           Thread.CurrentThread.CurrentCulture = New CultureInfo("de")<newline/>
           Thread.CurrentThread.CurrentUICulture = New CultureInfo("de-DE")<newline/>
           this.RootVisual = New MainPage()<newline/>
       End Sub
```

 </p><p>5) Rebuild the project. When your Silverlight application is built, satellite assemblies are automatically put into the *.xap file from SL folder.</p><p><strong>NOTE:</strong> Starting from version v2011 vol 2, we install localized satellite assemblies for German, Spanish, Japanese and Russian languages along with our components, because they are fully localized for these languages. The installer also register satellite assemblies in the GAC. You can download partially localized satellite assemblies for other languages here: <a href="https://www.devexpress.com/Support/Center/p/A421">The collection of localized DevExpress assemblies</a>. This KB article also describes how to localize resources that are not yet translated. If you wish your application to use the same language that is used on the user machine, feel free to deploy satellite assemblies with your application.</p>

<br/>


