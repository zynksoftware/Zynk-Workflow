---
slug: troubleshooting-the-sage-50-uk-connector
redirect_from: "/article/702-troubleshooting-the-sage-50-uk-connector"
title: Troubleshooting the Sage 50 UK Connector
---

## Failed to connect to Sage 50 UK: Username is already in use
Zynk is failing to connect to Sage, because the Sage user is already logged in.

* This may be another user, if Zynk is using a shared Sage user account like 'manager'
* This may be another instance of Zynk, if Zynk runs on a schedule, and the scheduled workflow run was interrupted before Zynk logged out.

To resolve this issue, log the user out of Sage (e.g. open Sage, login, then logoff and close Sage)

## Sage 50 2018 (v24 onwards) - Running reporting tasks results in 'The field xxxx does not exist' error
When Exporting/Generating Reports from Sage 50 2018 (v24 onwards) via Zynk, you might see an error like the following: 

```
The field 'SALES_ORDER.ORDER_NUMBER' does not exist.
   at Sage.Reporting.Engine.ExecutionEngine.ExecuteReportInternal(IReportRenderer renderer, SubReportExecution subReportContext)
   at Sage.Reporting.Engine.ExecutionEngine.ExecuteReport(IReportRenderer renderer, SubReportExecution subReportContext, Boolean withProgress)
   at Sage.Reporting.Engine.Integration.ExportService.RunEngineForSingleReport(ExportFlags flags, IReportRenderer oRenderer, ExecutionEngine oEngine, IDataSerializer oDataSource, Boolean withProgress)
   at Sage.Reporting.Engine.Integration.ExportService.RunSingle(ExportBatchItem item, Type rendererType, String filename, ExportFlags flags, Boolean enableNotifications, Boolean withProgress)
   at Sage.Reporting.Engine.Integration.ExportService.Sage.Reporting.Engine.Integration.IExportService.Run(ExportType type, String filename, ExportFlags flags)
   at Zynk.Sage.Reporting.Sage50.ExportReportBase.RunInternal(IProgress progress, ILog log, ZynkObject input)
```

To resolve this issue you will need to update the Zynk.exe.config file which resides in the Zynk install directory to include an assembly binding to the correct version of the Sage 50 Reporting DLL's. The assembly binding snippet to include in the config file is:

```xml
<dependentAssembly>
	<assemblyIdentity name="Sage.Reporting.Engine.Integration" publicKeyToken="0a4a2ad97614f98d" culture="neutral" />
	<bindingRedirect oldVersion="0.0.0.0-3.2.0.0" newVersion="4.0.0.0" />
</dependentAssembly>
<dependentAssembly>
	<assemblyIdentity name="Sage.Reporting.Engine" publicKeyToken="0a4a2ad97614f98d" culture="neutral" />
	<bindingRedirect oldVersion="0.0.0.0-3.2.0.0" newVersion="4.0.0.0" />
</dependentAssembly>
<dependentAssembly>
	<assemblyIdentity name="Sage.Reporting.Model" publicKeyToken="0a4a2ad97614f98d" culture="neutral" />
	<bindingRedirect oldVersion="0.0.0.0-3.2.0.0" newVersion="4.0.0.0" />
</dependentAssembly>
```

The original Zynk.exe.config file will look something like:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <configSections>
    <!-- For more information on Entity Framework configuration, visit http://go.microsoft.com/fwlink/?LinkID=237468 -->
    <section name="entityFramework" type="System.Data.Entity.Internal.ConfigFile.EntityFrameworkSection, EntityFramework, Version=6.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" requirePermission="false" />
    <!-- For more information on Entity Framework configuration, visit http://go.microsoft.com/fwlink/?LinkID=237468 -->
  </configSections>
  <appSettings>
    <add key="DatabaseCommandTimeOut.Default" value="3600" />
    <add key="DatabaseConnectionTimeOut.Default" value="3600" />
    <add key="DatabaseCommandTimeOut.Long" value="3600" />
  </appSettings>
  <!--<startup>
		<supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/>
	</startup>-->
  <system.serviceModel>
    <bindings>
      <basicHttpBinding>
        <binding name="sugarsoapBinding" closeTimeout="00:01:00" openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00" allowCookies="false" bypassProxyOnLocal="false" hostNameComparisonMode="StrongWildcard" maxBufferSize="5242880" maxBufferPoolSize="5242880" maxReceivedMessageSize="5242880" messageEncoding="Text" textEncoding="utf-8" transferMode="Buffered" useDefaultWebProxy="true">
          <readerQuotas maxDepth="32" maxStringContentLength="5242880" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384" />
          <security mode="None">
            <transport clientCredentialType="None" proxyCredentialType="None" realm="" />
            <message clientCredentialType="UserName" algorithmSuite="Default" />
          </security>
        </binding>
        <binding name="BasicHttpBinding_IApi" closeTimeout="00:01:00" openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00" allowCookies="false" bypassProxyOnLocal="false" hostNameComparisonMode="StrongWildcard" maxBufferSize="524288" maxBufferPoolSize="524288" maxReceivedMessageSize="524288" messageEncoding="Text" textEncoding="utf-8" transferMode="Buffered" useDefaultWebProxy="true">
          <readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384" />
          <security mode="Transport">
            <transport clientCredentialType="None" proxyCredentialType="None" realm="" />
            <message clientCredentialType="UserName" algorithmSuite="Default" />
          </security>
        </binding>
      </basicHttpBinding>
    </bindings>
    <client>
      <endpoint address="http://localhost/sugar/soap.php" binding="basicHttpBinding" bindingConfiguration="sugarsoapBinding" contract="Sugar.sugarsoapPortType" name="sugarsoapPort" />
      <endpoint address="https://api.fast-serve.net/Api.svc/soap" binding="basicHttpBinding" bindingConfiguration="BasicHttpBinding_IApi" contract="EasyWebstoreApi.IApi" name="BasicHttpBinding_IApi" />
    </client>
  </system.serviceModel>
  <runtime>
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
      <dependentAssembly>
        <assemblyIdentity name="Newtonsoft.Json" publicKeyToken="30ad4fe6b2a6aeed" />
        <codeBase version="9.0.0.0" href="Newtonsoft.Json.9.0.1.19813.dll" />
        <codeBase version="7.0.0.0" href="Newtonsoft.Json.7.0.1.18622.dll" />
        <codeBase version="6.0.0.0" href="Newtonsoft.Json.6.0.8.18111.dll" />
        <codeBase version="4.0.2.13623" href="Newtonsoft.Json.4.0.2.13623.dll" />
      </dependentAssembly>
      <dependentAssembly>
        <assemblyIdentity name="RestSharp" publicKeyToken="598062e77f915f75" culture="neutral" />
        <codeBase version="100.0.0.0" href="RestSharp.105.2.3.0.dll" />
        <codeBase version="104.2.0.0" href="RestSharp.104.1.0.0.dll" />
      </dependentAssembly>
      <dependentAssembly>
        <assemblyIdentity name="FileHelpers" publicKeyToken="3e0c08d59cc3d657" culture="neutral" />
        <codeBase version="2.0.0.0" href="FileHelpers.2.0.0.0.dll" />
        <codeBase version="3.1.5.0" href="FileHelpers.3.1.5.0.dll" />
      </dependentAssembly>
    </assemblyBinding>
  </runtime>
  <startup>
    <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5.2" />
  </startup>
  <entityFramework>
    <defaultConnectionFactory type="System.Data.Entity.Infrastructure.SqlCeConnectionFactory, EntityFramework">
      <parameters>
        <parameter value="System.Data.SqlServerCe.4.0" />
      </parameters>
    </defaultConnectionFactory>
    <providers>
      <provider invariantName="System.Data.SqlServerCe.4.0" type="System.Data.Entity.SqlServerCompact.SqlCeProviderServices, EntityFramework.SqlServerCompact" />
    </providers>
  </entityFramework>
  <system.data>
    <DbProviderFactories>
      <remove invariant="System.Data.SqlServerCe.4.0" />
      <add name="Microsoft SQL Server Compact Data Provider 4.0" invariant="System.Data.SqlServerCe.4.0" description=".NET Framework Data Provider for Microsoft SQL Server Compact" type="System.Data.SqlServerCe.SqlCeProviderFactory, System.Data.SqlServerCe, Version=4.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91" />
    </DbProviderFactories>
  </system.data>
</configuration>
```

Once the assemblyBinding entries have been added to the app.cofig file, it will look something like:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
	<configSections>
		<!-- For more information on Entity Framework configuration, visit http://go.microsoft.com/fwlink/?LinkID=237468 -->
		<section name="entityFramework" type="System.Data.Entity.Internal.ConfigFile.EntityFrameworkSection, EntityFramework, Version=6.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" requirePermission="false" />
		<!-- For more information on Entity Framework configuration, visit http://go.microsoft.com/fwlink/?LinkID=237468 -->
	</configSections>
	<appSettings>
		<add key="DatabaseCommandTimeOut.Default" value="3600" />
		<add key="DatabaseConnectionTimeOut.Default" value="3600" />
		<add key="DatabaseCommandTimeOut.Long" value="3600" />
	</appSettings>
	<!--<startup>
		<supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/>
	</startup>-->
	<system.serviceModel>
		<bindings>
			<basicHttpBinding>
				<binding name="sugarsoapBinding" closeTimeout="00:01:00" openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00" allowCookies="false" bypassProxyOnLocal="false" hostNameComparisonMode="StrongWildcard" maxBufferSize="5242880" maxBufferPoolSize="5242880" maxReceivedMessageSize="5242880" messageEncoding="Text" textEncoding="utf-8" transferMode="Buffered" useDefaultWebProxy="true">
					<readerQuotas maxDepth="32" maxStringContentLength="5242880" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384" />
					<security mode="None">
						<transport clientCredentialType="None" proxyCredentialType="None" realm="" />
						<message clientCredentialType="UserName" algorithmSuite="Default" />
					</security>
				</binding>
				<binding name="BasicHttpBinding_IApi" closeTimeout="00:01:00" openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00" allowCookies="false" bypassProxyOnLocal="false" hostNameComparisonMode="StrongWildcard" maxBufferSize="524288" maxBufferPoolSize="524288" maxReceivedMessageSize="524288" messageEncoding="Text" textEncoding="utf-8" transferMode="Buffered" useDefaultWebProxy="true">
					<readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384" />
					<security mode="Transport">
						<transport clientCredentialType="None" proxyCredentialType="None" realm="" />
						<message clientCredentialType="UserName" algorithmSuite="Default" />
					</security>
				</binding>
			</basicHttpBinding>
		</bindings>
		<client>
			<endpoint address="http://localhost/sugar/soap.php" binding="basicHttpBinding" bindingConfiguration="sugarsoapBinding" contract="Sugar.sugarsoapPortType" name="sugarsoapPort" />
			<endpoint address="https://api.fast-serve.net/Api.svc/soap" binding="basicHttpBinding" bindingConfiguration="BasicHttpBinding_IApi" contract="EasyWebstoreApi.IApi" name="BasicHttpBinding_IApi" />
		</client>
	</system.serviceModel>
	<runtime>
		<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
			<dependentAssembly>
				<assemblyIdentity name="Newtonsoft.Json" publicKeyToken="30ad4fe6b2a6aeed" />
				<codeBase version="9.0.0.0" href="Newtonsoft.Json.9.0.1.19813.dll" />
				<codeBase version="7.0.0.0" href="Newtonsoft.Json.7.0.1.18622.dll" />
				<codeBase version="6.0.0.0" href="Newtonsoft.Json.6.0.8.18111.dll" />
				<codeBase version="4.0.2.13623" href="Newtonsoft.Json.4.0.2.13623.dll" />
			</dependentAssembly>
			<dependentAssembly>
				<assemblyIdentity name="RestSharp" publicKeyToken="598062e77f915f75" culture="neutral" />
				<codeBase version="100.0.0.0" href="RestSharp.105.2.3.0.dll" />
				<codeBase version="104.2.0.0" href="RestSharp.104.1.0.0.dll" />
			</dependentAssembly>
			<dependentAssembly>
				<assemblyIdentity name="FileHelpers" publicKeyToken="3e0c08d59cc3d657" culture="neutral" />
				<codeBase version="2.0.0.0" href="FileHelpers.2.0.0.0.dll" />
				<codeBase version="3.1.5.0" href="FileHelpers.3.1.5.0.dll" />
			</dependentAssembly>
			<dependentAssembly>
				<assemblyIdentity name="Sage.Reporting.Engine.Integration" publicKeyToken="0a4a2ad97614f98d" culture="neutral" />
				<bindingRedirect oldVersion="0.0.0.0-3.2.0.0" newVersion="4.0.0.0" />
			</dependentAssembly>
			<dependentAssembly>
				<assemblyIdentity name="Sage.Reporting.Engine" publicKeyToken="0a4a2ad97614f98d" culture="neutral" />
				<bindingRedirect oldVersion="0.0.0.0-3.2.0.0" newVersion="4.0.0.0" />
			</dependentAssembly>
			<dependentAssembly>
				<assemblyIdentity name="Sage.Reporting.Model" publicKeyToken="0a4a2ad97614f98d" culture="neutral" />
				<bindingRedirect oldVersion="0.0.0.0-3.2.0.0" newVersion="4.0.0.0" />
			</dependentAssembly>
		</assemblyBinding>
	</runtime>
	<startup>
		<supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5.2" />
	</startup>
	<entityFramework>
		<defaultConnectionFactory type="System.Data.Entity.Infrastructure.SqlCeConnectionFactory, EntityFramework">
			<parameters>
				<parameter value="System.Data.SqlServerCe.4.0" />
			</parameters>
		</defaultConnectionFactory>
		<providers>
			<provider invariantName="System.Data.SqlServerCe.4.0" type="System.Data.Entity.SqlServerCompact.SqlCeProviderServices, EntityFramework.SqlServerCompact" />
		</providers>
	</entityFramework>
	<system.data>
		<DbProviderFactories>
			<remove invariant="System.Data.SqlServerCe.4.0" />
			<add name="Microsoft SQL Server Compact Data Provider 4.0" invariant="System.Data.SqlServerCe.4.0" description=".NET Framework Data Provider for Microsoft SQL Server Compact" type="System.Data.SqlServerCe.SqlCeProviderFactory, System.Data.SqlServerCe, Version=4.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91" />
		</DbProviderFactories>
	</system.data>
</configuration>
```

## What does the Exclusive Mode error mean?
If you receive the below error in Zynk it generally means that a Sage back up is taking place at the time of the workflow run:

Program is in exclusive mode. Logon cannot proceed   
at System.RuntimeType.ForwardCallToInvokeMember(String memberName,   
BindingFlags flags, Object target, Int32[] aWrapperTypes, MessageData&   
msgData) at SageDataObject120.IWorkSpace.Connect(String Path, String Usr,   
String Psw, String Unique) at Zynk.Sage.Sage50.Sage50Base.Connect()

Please wait for the back up to complete before trying to run Zynk again.

## What do I do if my Sage 50 information changes?
If you have changed the location, version or login information (username or password) of your Sage 50 data you will have to update these settings in your Workflow. The process to update your connection details varies depending on the version of Zynk you are using. You can find the version number in the application under Help > About.

### Zynk V2.1+
Zynk will automatically detect the version of Sage you have installed, so you only need to update the connection if your username, password or data location has changed. Refer to the instructions for Zynk v2.0 - 2.0.3 for how to do this.

### Zynk V2.0 - 2.0.3
1. Click the 'Connection Manager' button on the main toolbar.
2. Double click on the Sage 50 connection you need to update.
3. Follow the instructions on [Connecting to Sage 50 UK](connecting-to-sage-50-uk) to update your Sage 50 details.

### Zynk V1.X
Click the 'Workflow Properties' tab and then click the button next to the 'Variables' to edit the list of 'Workflow Variables', select the following variable names from your Workflows Variables and press the 'Delete' key on your keyboard for each one :

 * SAGE50_BUGFIX
 * SAGE50_DATAPATH
 * SAGE50_MAJOR
 * SAGE50_MINOR
 * SAGE50_NAME
 * SAGE50_USERNAME
 * SAGE50_PASSWORD

Once you have deleted all of the above variables, if you Save your workflow and then select 'Run Workflow' you will be prompted to re enter your Sage login information once the Workflow reaches the first Sage 50 task.
