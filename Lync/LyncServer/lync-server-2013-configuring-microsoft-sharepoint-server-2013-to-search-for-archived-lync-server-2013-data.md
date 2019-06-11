---
title: 'Lync Server 2013: configuración de Microsoft SharePoint Server 2013 para buscar datos de archivo de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 381db352aae635358dfd62cc1965ea238960bf8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>Configuración de Microsoft SharePoint Server 2013 para buscar datos archivados de Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-04_

Una de las principales ventajas de almacenar la mensajería instantánea y las transcripciones de conferencias web en Microsoft Exchange Server 2013 en lugar de Microsoft Lync Server 2013 es el hecho de que el almacenamiento de datos en la misma ubicación permita a los administradores usar una única herramienta para buscar para datos de Exchange archivados o datos archivados de Lync Server. Como todos los datos se almacenan en el mismo lugar (Exchange), cualquier herramienta que pueda buscar datos archivados de Exchange también puede buscar datos archivados de Lync Server.

Una herramienta que facilita la búsqueda de datos archivados es Microsoft SharePoint Server 2013. Si desea usar SharePoint para buscar datos de Lync Server, primero debe completar todos los pasos necesarios para configurar el archivado de Exchange en Lync Server. Después de que Exchange 2013 y Lync Server 2013 se hayan integrado correctamente, debe instalar la versión 2,0 de la API administrada de servicios web Exchange en el servidor de SharePoint. el programa de instalación de esa API se puede descargar desde el centro de descargas[http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)de Microsoft (). The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.

Una vez se ha descargado el archivo, complete el siguiente procedimiento en SharePoint Server:

1.  Para abrir una ventana de comandos, haga clic en **Inicio**, en **Todos los programas**, en **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.

2.  En la ventana de comandos, use el comando **cd** para cambiar el directorio actual a la carpeta donde se ha guardado el archivo EWSManagedAPI.msi. Por ejemplo, si ha guardado el archivo en C:\\descargas, escriba el siguiente comando en la ventana de comandos y, a continuación, presione ENTRAR:
    
        cd C:\Downloads

3.  Para instalar la API, escriba el siguiente comando y, a continuación, presione ENTRAR:
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  Una vez se ha instalado la API, restablezca IIS escribiendo el siguiente comando y presionando ENTRAR:
    
        iisreset

Una vez instalados los servicios Web de Exchange, debe configurar la autenticación de servidor a servidor entre SharePoint Server 2013 y Exchange 2013. Para ello, primero abra el shell de administración de SharePoint 2013 y ejecute el siguiente conjunto de comandos:

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> Asegúrese de usar el URI para su servicio de detección automática. No use el URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1de ejemplo.



</div>

Una vez que haya creado el emisor de tokens y haya configurado el servicio de token, ejecute estos comandos, asegurándose de sustituir la dirección URL de su sitio de SharePoint para la dirección URL de ejemplo.http://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Para configurar la autenticación de servidor a servidor para Exchange 2013, abra el shell de administración de Exchange y ejecute un comando similar a este (suponiendo que Exchange se haya instalado en el disco C: y que use la ruta de la carpeta predeterminada):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

Después de configurar la aplicación asociada, se recomienda que detenga y reinicie servicios de Internet Information Server (IIS) en todos los servidores de acceso de cliente y de buzón de Exchange. Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:

    iisreset atl-exchange-001

Este comando se puede ejecutar desde el shell de administración de Exchange o desde cualquier otra ventana de comandos.

A continuación, ejecute un comando similar al siguiente, que proporciona al usuario especificado (en este ejemplo, kenmyer) el derecho de realizar la detección en Exchange:

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Una vez que se ha establecido la autenticación de servidor a servidor entre Exchange y SharePoint, el siguiente paso es crear un sitio de eDiscovery en SharePoint. Esto puede hacerse ejecutando comandos similares a estos desde el shell de administración de SharePoint:

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> "eDiscovery" es la abreviatura de "detección electrónica" y normalmente hace referencia al proceso de mirar por los archivos electrónicos para buscar elementos que "se pueden calcular de manera razonable para llevar a pruebas admisibles) en un juzgado.



</div>

Cuando el nuevo sitio está listo, el siguiente paso es configurar Exchange 2013 para que funcione como origen de resultados de SharePoint. Puede hacerlo completando el siguiente procedimiento desde la página de administración central de SharePoint 2013:

1.  En la página de Administración central haga clic en **Administrar aplicaciones de servicios** y, a continuación, en **Aplicación de servicio de búsqueda**.

2.  En la página Aplicación de servicio de búsqueda, haga clic en **Orígenes de resultados** y después en **Nuevo origen de resultados**.

3.  En el panel **Nuevo origen de resultados**, escriba un nombre para el nuevo origen (por ejemplo, **Microsoft Exchange**) en el cuadro **Nombre**. Seleccione **Exchange** como **Protocolo**de origen de resultados y, a continuación, escriba la dirección URL de origen de servicios web para su servidor de Exchange en el cuadro **dirección URL de origen de Exchange** . La dirección URL de origen debería ser similar a la siguiente:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  Asegúrese de que la opción **Usar Autodetección** no está seleccionada y, a continuación, haga clic en **Aceptar**.

Por último, cree un nuevo caso de eDiscovery y un nuevo conjunto de eDiscovery completando el siguiente procedimiento desde el sitio de detección de SharePoint (por ejemplo,https://atl-sharepoint-001/sites/discovery):

1.  En la página de contenido del sitio haga clic en **Crear un nuevo caso**.

2.  En la página de contenido del sitio: nuevo sitio de SharePoint, escriba el alias de correo electrónico del usuario (por ejemplo, **kenmyer**) en el cuadro **Título** y, a continuación, agregue esa misma dirección URL al cuadro de **dirección de sitio web**. Eso producirá una dirección URL similar a la siguiente:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  Haga clic en **Crear**.

4.  Cuando aparezca la página de conjunto de exhibición de documentos electrónicos, haga clic en **nuevo elemento** dentro de **Identidad y Preservar: conjuntos de detección**.

5.  En la página de nuevo: conjunto de detección, escriba el alias de correo electrónico del usuario en el cuadro de **nombre de conjunto de detección**. Escriba **eDiscovery Lync\* ** en el cuadro **filtro** y, a continuación, haga clic en **Agregar & administrar fuentes**.

6.  En la página para agregar y administrar orígenes, escriba el alias de correo electrónico del usuario en el primer cuadro de texto debajo de **Buzones**. Haga clic en el icono de buzón de marca que se encuentra junto al libro de texto para comprobar que SharePoint se puede conectar al buzón especificado.

7.  Haga clic en **Aceptar**.

8.  En la página de conjunto de exhibición de documentos electrónicos, haga clic en **Guardar** para guardar el nuevo conjunto de exhibición de documentos electrónicos.

En este momento, puede buscar en el buzón especificado (kenmyer) o habilitar las conservaciones locales de la misma manera que lo haría para cualquier otro origen de resultados o contenido de SharePoint.

</div>

<span> </span>

</div>

</div>

</div>

