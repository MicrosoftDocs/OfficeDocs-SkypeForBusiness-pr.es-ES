---
title: "Config. MS SharePoint Server 2013 para buscar datos archivados de MS Lync Server 2013"
TOCTitle: "Conf. Micros. SharePoint Server 2013 pr rech. données Microsoft LS 2013 arch."
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49888902
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de Microsoft SharePoint Server 2013 para buscar datos archivados de Microsoft Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Una de las ventajas principales de almacenar transcripciones de conferencias web y mensajería instantánea en Microsoft Exchange Server 2013 en lugar de Microsoft Lync Server 2013 es el hecho de que el almacenamiento de datos en la misma ubicación habilita a los administradores a usar una herramienta sencilla para buscar datos de Exchange y/o datos de Lync Server archivados. Dado que todos los datos se almacenan en el mismo lugar (Exchange) cualquier herramienta que puede buscar datos de Exchange archivados también puede buscar datos de Lync Server archivados.

Una herramienta que facilita la búsqueda de datos archivados es Microsoft SharePoint Server 2013. Si desea usar SharePoint para buscar datos de Lync Server, debe completar primero todos los pasos implicados en la configuración del archivado de Exchange en Lync Server. Una vez que Exchange 2013 y Lync Server 2013 se han integrado correctamente, debe instalar a continuación la API administrada de servicios web de Exchange versión 2.0 en su SharePoint; el programa de instalación para dicha API se puede descargar en el Centro de descarga de Microsoft ([http://go.microsoft.com/fwlink/?linkid=258305\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=258305%26clcid=0xc0a)). El archivo descargado (EWSManagedAPI.msi) se puede guardar en cualquier carpeta de su SharePoint Server.

Una vez se ha descargado el archivo, complete el siguiente procedimiento en SharePoint Server:

1.  Para abrir una ventana de comandos haga clic en **Inicio**, en **Todos los programas**, en **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

2.  En la ventana de comandos, use el comando **cd** para cambiar el directorio actual a la carpeta donde se ha guardado el archivo EWSManagedAPI.msi. Por ejemplo, si ha guardado el archivo en C:\\Descargas escriba el siguiente comando en la ventana de comandos y, a continuación, presione ENTRAR:
    
        cd C:\Downloads

3.  Para instalar la API, escriba el siguiente comando y, a continuación, presione ENTRAR:
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  Una vez se ha instalado la API, restablezca IIS escribiendo el siguiente comando y presionando ENTRAR:
    
        iisreset

Una vez se han instalado los servicios web de Exchange, debe configurar la autenticación de servidor a servidor entre SharePoint Server 2013 y Exchange 2013. Para ello, abra primero el shell de administración de SharePoint 2013 y ejecute el siguiente conjunto de comandos:

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()


> [!NOTE]
> Asegúrese de usar el URI para su servicio de detección automática. No use el URI de muestra https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.



Una vez ha creado el emisor de tokens y ha configurado el servicio de token, ejecute estos comandos, asegurándose de sustituir la dirección URL de su sitio de SharePoint por la dirección URL de muestra http://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Para configurar la autenticación de servidor a servidor para Exchange 2013, abra el shell de administración de Exchange y ejecute un comando similar a este (suponiendo que Exchange se ha instalado en la unidad C: y que usa la ruta de acceso de carpeta predeterminada):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

Tras configurar la aplicación de socio, se recomienda que detenga y reinicie Internet Information Services (IIS) en todos sus servidores de acceso de cliente y buzón de Exchange. Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:

    iisreset atl-exchange-001

Este comando se puede ejecutar desde dentro del shell de administración de Exchange o desde cualquier otra ventana de comandos.

A continuación, ejecute un comando similar al siguiente, que ofrece al usuario especificado (en este ejemplo, kenmyer) la detección correcta para hacer en Exchange:

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Una vez se ha establecido la autenticación servidor a servidor entre Exchange y SharePoint su siguiente paso es crear un sitio de eDiscovery en SharePoint. eso se puede realizar ejecutando comandos similares a estos desde el shell de administración de SharePoint:

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"


> [!NOTE]
> "eDiscovery" es la abreviatura de "detección electrónica" y normalmente hace referencia al proceso de mirar por los archivos electrónicos para buscar elementos que "se pueden calcular de manera razonable para llevar a pruebas admisibles) en un juzgado.



Cuando el nuevo sitio esté preparado, el siguiente paso será configurar Exchange 2013 para que actúe como el origen de resultados para SharePoint. Puede hacerlo completando el siguiente procedimiento desde la página de Administración central de SharePoint 2013:

1.  En la página de Administración central haga clic en **Administrar aplicaciones de servicio** y, a continuación, en **Aplicación de servicio de búsqueda**.

2.  En la página Aplicación de servicio de búsqueda haga clic en **Orígenes de resultados** y, a continuación, en **Nuevo origen de resultados**.

3.  En el panel **Nuevo origen de resultados** escriba un nombre para el nuevo origen de resultados (por ejemplo, **Microsoft Exchange**) en el cuadro **Nombre**. Seleccione **Exchange** como el origen de resultados **Protocolo** y, a continuación, especifique la dirección URL de origen de servicios web para su servidor Exchange en el cuadro de **dirección URL de origen de Exchange**. La dirección URL de origen debería ser similar a la siguiente:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  Asegúrese de que la opción **Usar Autodetección** no está seleccionada y, a continuación, haga clic en **Aceptar**.

Por último, cree un nuevo caso de eDiscovery y un nuevo conjunto de eDiscovery completando el siguiente procedimiento desde el sitio de detección de SharePoint (por ejemplo, https://atl-sharepoint-001/sites/discovery):

1.  En la página de contenido del sitio haga clic en **Crear un nuevo caso**.

2.  En la página de contenido del sitio: nuevo sitio de SharePoint, escriba el alias de correo electrónico del usuario (por ejemplo, **kenmyer**) en el cuadro **Título** y, a continuación, agregue esa misma dirección URL al cuadro de **dirección de sitio web**. Eso producirá una dirección URL similar a la siguiente:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  Haga clic en **Crear**.

4.  Cuando aparezca la página de conjunto de eDiscovery, haga clic en **nuevo elemento** debajo de la opción de **identidad y preservar: conjuntos de detección**.

5.  En la página de nuevo: conjunto de detección, escriba el alias de correo electrónico del usuario en el cuadro de **nombre de conjunto de detección**. Escriba **eDiscovery Lync\*** en el cuadro para **filtrar** y, a continuación, haga clic en **Agregar y administrar orígenes**.

6.  En la página para agregar y administrar orígenes, escriba el alias de correo electrónico del usuario en el primer cuadro de texto debajo de **Buzones**. Haga clic en el icono de buzón de marca que se encuentra junto al libro de texto para comprobar que SharePoint se puede conectar al buzón especificado.

7.  Haga clic en **Aceptar**.

8.  En la página de conjunto de eDiscovery, haga clic en **Guardar** para guardar el nuevo conjunto de eDiscovery.

En este momento puede buscar el buzón especificado (kenmyer) y/o habilitar conservaciones locales de la misma manera que lo haría para cualquier otro contenido de SharePoint u origen de resultados.

