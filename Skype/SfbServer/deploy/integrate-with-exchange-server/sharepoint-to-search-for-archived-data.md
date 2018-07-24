---
title: Configurar SharePoint Server para buscar datos archivados de Skype Empresarial
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Resumen: Configure SharePoint Server para buscar datos archivados por el servidor de Exchange y Skype para Business Server.'
ms.openlocfilehash: efd3fc67faacba503736968786988aaf01f45073
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971802"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Configurar SharePoint Server para buscar datos archivados de Skype Empresarial
 
**Resumen:** Configurar el servidor de SharePoint para buscar datos archivados, 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server.
  
Una de las principales ventajas de almacenar transcripciones de conferencias Web y mensajería instantánea de Exchange Server en lugar de Skype para Business Server es que almacenar los datos en la misma ubicación permite a los administradores utilizar una sola herramienta para buscar datos archivados de Exchange o archivado Skype para los datos de Business Server. Debido a que los datos se almacenan en la misma sitúan (Exchange) también puede buscar cualquier herramienta que puede buscar datos archivados de Exchange archivado Skype para los datos de Business Server.
  
Una herramienta que facilita la búsqueda de datos archivados es Microsoft SharePoint Server 2013. Si desea usar SharePoint para buscar Skype para los datos de Business Server, primero debe completar todos los pasos necesarios para configurar el archivado de Exchange en Skype para Business Server. Después de Skype para Business Server y Exchange Server se han integrado correctamente, a continuación, debe instalar la [API administrada de servicios Web](https://go.microsoft.com/fwlink/p/?LinkId=258305) de Exchange en el servidor de SharePoint. El archivo descargado (EWSManagedAPI.msi) se puede guardar en cualquier carpeta en el servidor de SharePoint.
  
Una vez se ha descargado el archivo, complete el siguiente procedimiento en SharePoint Server:
  
1. Para abrir una ventana de comandos, haga clic en **Inicio**, en **Todos los programas**, en **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. En la ventana de comandos, use el comando cd para cambiar el directorio actual a la carpeta donde se ha guardado el archivo EWSManagedAPI.msi. Por ejemplo, si ha guardado el archivo en C:\Downloads escriba el comando siguiente en la ventana de comandos y, a continuación, presione ENTRAR:
    
   ```
   cd C:\Downloads
   ```

3. Para instalar la API, escriba el comando siguiente, a continuación, presione ENTRAR:
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Después de haber instalado la API, restablezca IIS escribiendo el siguiente comando y presione ENTRAR:
    
   ```
   iisreset
   ```

Después de haber instalado los servicios Web Exchange, a continuación, debe configurar la autenticación de servidor a servidor entre SharePoint Server y Exchange Server. Para ello, abra el Shell de administración de SharePoint y ejecute el siguiente conjunto de comandos:
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Asegúrese de usar el URI para su servicio de detección automática. No use el URI de ejemplo https://autodiscover.litwareinc.com/autodiscover/metadata/json/1. 
  
Después de haber creado al emisor de tokens y configurado el servicio de token, ejecute estos comandos, asegurándose de sustituir la dirección URL del sitio de SharePoint para la dirección URL de ejemplohttp://atl-sharepoint-001:
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Para configurar la autenticación de servidor a servidor para Exchange Server, abra el Shell de administración de Exchange y ejecute un comando similar al siguiente (suponiendo que se ha instalado Exchange en la unidad C: y que TI utiliza la ruta de acceso de la carpeta predeterminada):
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Después de configurar la aplicación de socio, se recomienda que detenga y reinicie Internet Information Services (IIS) en todos los buzones de correo y el cliente de acceso servidores Exchange. Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:
  
```
iisreset atl-exchange-001
```

Este comando se puede ejecutar desde dentro de la consola de administración de Exchange o desde cualquier otra ventana de comandos.
  
A continuación, ejecute un comando similar a la siguiente, que ofrece al usuario especificado (en este ejemplo, kenmyer) la detección correcta para hacer en Exchange:
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Después de que se ha establecido la autenticación de servidor a servidor entre Exchange y SharePoint, el siguiente paso es crear un sitio de exhibición de documentos electrónicos en SharePoint. Que se puede realizar mediante la ejecución de comandos similares a estos desde el Shell de administración de SharePoint:
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "eDiscovery" es la abreviatura de "detección electrónica" y normalmente hace referencia al proceso de mirar por los archivos electrónicos para buscar elementos que "se pueden calcular de manera razonable para llevar a pruebas admisibles) en un juzgado. 
  
Cuando esté listo el sitio nuevo, el siguiente paso es configurar Exchange Server para que actúe como resultado origen para SharePoint. Puede hacer al completar el procedimiento siguiente desde la página de Administración Central de SharePoint:
  
1. En la página de Administración central haga clic en **Administrar aplicaciones de servicios** y, a continuación, en **Aplicación de servicio de búsqueda**.
    
2. En la página Aplicación de servicio de búsqueda, haga clic en **Orígenes de resultados** y después en **Nuevo origen de resultados**.
    
3. En el panel **Nuevo origen de resultados**, escriba un nombre para el nuevo origen (por ejemplo, **Microsoft Exchange**) en el cuadro **Nombre**. Seleccione **Exchange** como el **protocolo**de origen de resultados y, a continuación, escriba la URL de origen de servicios web para el servidor de Exchange en el cuadro **Dirección URL de origen de Exchange** . La dirección URL de origen debería ser similar a la siguiente:
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Asegúrese de que la opción **Usar Autodetección** no está seleccionada y, a continuación, haga clic en **Aceptar**.
    
Por último, cree un nuevo caso de exhibición de documentos electrónicos y un nuevo conjunto completando el siguiente procedimiento desde el sitio de detección de SharePoint (por ejemplo, de eDiscoveryhttps://atl-sharepoint-001/sites/discovery):
  
1. En la página de contenido del sitio haga clic en **Crear un nuevo caso**.
    
2. En la página de contenido del sitio: nuevo sitio de SharePoint, escriba el alias de correo electrónico del usuario (por ejemplo, **kenmyer**) en el cuadro **Título** y, a continuación, agregue esa misma dirección URL al cuadro de **dirección de sitio web**. Eso producirá una dirección URL similar a la siguiente:
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Haga clic en **Crear**.
    
4. Cuando aparezca la página de conjunto de exhibición de documentos electrónicos, haga clic en **nuevo elemento** dentro de **Identidad y Preservar: conjuntos de detección**.
    
5. En la página de nuevo: conjunto de detección, escriba el alias de correo electrónico del usuario en el cuadro de **nombre de conjunto de detección**. Escriba **exhibición de documentos electrónicos Lync\* ** en el **filtro de** cuadro y, a continuación, haga clic en **Agregar &amp; administrar orígenes de**.
    
6. En el complemento &amp; administrar orígenes de página, escriba el alias de correo electrónico del usuario en el primer cuadro de texto en **los buzones de correo**. Haga clic en el icono de buzón de marca que se encuentra junto al libro de texto para comprobar que SharePoint se puede conectar al buzón especificado.
    
7. Haga clic en **Aceptar**.
    
8. En la página de conjunto de exhibición de documentos electrónicos, haga clic en **Guardar** para guardar el nuevo conjunto de exhibición de documentos electrónicos.
    
En este momento puede buscar el buzón especificado (kenmyer) y/o habilitar suspensiones en contexto la misma manera que lo haría para cualquier otro origen de contenido o el resultado de SharePoint.
  

