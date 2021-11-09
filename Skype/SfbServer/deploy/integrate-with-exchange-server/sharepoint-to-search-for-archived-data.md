---
title: Configurar SharePoint server para buscar datos Skype Empresarial archivados
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Resumen: configure SharePoint Server para buscar datos archivados por Exchange Server y Skype Empresarial Server.'
ms.openlocfilehash: d3274c29ccdae22a382d045fc6db3ee448223332
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839632"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Configurar SharePoint server para buscar datos Skype Empresarial archivados
 
**Resumen:** Configure SharePoint Server para buscar datos archivados por Exchange Server 2016 o Exchange Server 2013 y Skype Empresarial Server.
  
Una de las principales ventajas de almacenar transcripciones de mensajería instantánea y conferencia web en Exchange Server en lugar de Skype Empresarial Server es que almacenar datos en la misma ubicación permite a los administradores usar una sola herramienta para buscar datos Exchange archivados o datos Skype Empresarial Server archivados. Dado que todos los datos se almacenan en el mismo lugar (Exchange) cualquier herramienta que pueda buscar datos Exchange también puede buscar datos Skype Empresarial Server archivados.
  
Una herramienta que facilita la búsqueda de datos archivados es Microsoft SharePoint Server 2013. Si desea usar SharePoint para buscar datos Skype Empresarial Server, primero debe completar todos los pasos necesarios para configurar el archivado Exchange en Skype Empresarial Server. Después de Exchange Server y Skype Empresarial Server se hayan integrado correctamente, debe instalar la API administrada Exchange [servicios web](https://go.microsoft.com/fwlink/p/?LinkId=258305) en el servidor SharePoint web. El archivo descargado (EWSManagedAPI.msi) se puede guardar en cualquier carpeta de su SharePoint Server.
  
Una vez se ha descargado el archivo, complete el siguiente procedimiento en SharePoint Server:
  
1. Para abrir una ventana de comandos haga clic en **Inicio**, en **Todos los programas**, en **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. En la ventana de comandos, use el comando cd para cambiar el directorio actual a la carpeta donde se ha guardado el archivo EWSManagedAPI.msi. Por ejemplo, si ha guardado el archivo en C:\Downloads escriba el siguiente comando en la ventana de comandos y, a continuación, presione ENTRAR:
    
   ```console
   cd C:\Downloads
   ```

3. Para instalar la API, escriba el siguiente comando y presione Entrar:
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Una vez instalada la API, restablezca IIS escribiendo el siguiente comando y presionando Entrar:
    
   ```console
   iisreset
   ```

Después Exchange se han instalado los servicios web, debe configurar la autenticación de servidor a servidor entre SharePoint Server y Exchange Server. Para ello, abra primero el Shell SharePoint administración y ejecute el siguiente conjunto de comandos:
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Asegúrese de usar el URI para su servicio de detección automática. No use el URI de ejemplo https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 . 
  
Después de crear el emisor de tokens y configurar el servicio de token, ejecute estos comandos, asegurándose de sustituir la dirección URL del sitio de SharePoint por la dirección URL de `http://atl-sharepoint-001` ejemplo:
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Para configurar la autenticación de servidor a servidor para Exchange Server, abra el Shell de administración de Exchange y ejecute un comando similar a este (suponiendo que Exchange se ha instalado en la unidad C: y que usa la ruta de acceso de carpeta predeterminada):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Después de configurar la aplicación asociada, se recomienda detener y reiniciar Internet Information Services (IIS) en todos los servidores de acceso de Exchange de correo y cliente. Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Este comando se puede ejecutar desde el Shell Exchange o desde cualquier otra ventana de comandos.
  
A continuación, ejecute un comando similar al siguiente, que da al usuario especificado (en este ejemplo, kenmyer) el derecho a realizar la detección en Exchange:
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Una vez establecida la autenticación de servidor a servidor entre Exchange y SharePoint, el siguiente paso es crear un sitio de exhibición de documentos electrónicos en SharePoint. Para ello, ejecute comandos similares a estos desde el Shell SharePoint administración:
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> "eDiscovery" es la abreviatura de "detección electrónica" y normalmente hace referencia al proceso de mirar por los archivos electrónicos para buscar elementos que "se pueden calcular de manera razonable para llevar a pruebas admisibles) en un juzgado. 
  
Cuando el nuevo sitio esté listo, el siguiente paso es configurar Exchange Server para que actúe como origen de resultados para SharePoint. Para ello, complete el siguiente procedimiento desde la página SharePoint Administración central:
  
1. En la página de Administración central haga clic en **Administrar aplicaciones de servicio** y, a continuación, en **Aplicación de servicio de búsqueda**.
    
2. En la página Aplicación de servicio de búsqueda haga clic en **Orígenes de resultados** y, a continuación, en **Nuevo origen de resultados**.
    
3. En el panel **Nuevo origen de resultados** escriba un nombre para el nuevo origen de resultados (por ejemplo, **Microsoft Exchange**) en el cuadro **Nombre**. Seleccione **Exchange** como el protocolo de origen de resultados y, a continuación, escriba la dirección URL de origen de servicios web para el servidor Exchange en el cuadro dirección **URL** Exchange origen. La dirección URL de origen debería ser similar a la siguiente:
    
    `https://atl-exchange-001.litwareinc.com/ews/exchange.asmx`
    
4. Asegúrese de que la opción **Usar Autodetección** no está seleccionada y, a continuación, haga clic en **Aceptar**.
    
Por último, cree un nuevo caso de exhibición de documentos electrónicos y un nuevo conjunto de exhibición de documentos electrónicos completando el siguiente procedimiento desde el sitio de detección de SharePoint (por ejemplo, `https://atl-sharepoint-001/sites/discovery` ):
  
1. En la página de contenido del sitio haga clic en **Crear un nuevo caso**.
    
2. En la página de contenido del sitio: nuevo sitio de SharePoint, escriba el alias de correo electrónico del usuario (por ejemplo, **kenmyer**) en el cuadro **Título** y, a continuación, agregue esa misma dirección URL al cuadro de **dirección de sitio web**. Eso producirá una dirección URL similar a la siguiente:
    
    `https://atl-sharepoint-001/sites/eDiscovery/kenmyer`
    
3. Haga clic en **Crear**.
    
4. Cuando aparezca la página de conjunto de eDiscovery, haga clic en **nuevo elemento** debajo de la opción de **identidad y preservar: conjuntos de detección**.
    
5. En la página de nuevo: conjunto de detección, escriba el alias de correo electrónico del usuario en el cuadro de **nombre de conjunto de detección**. Escriba **eDiscovery \\ Lync** _ en el cuadro _ *Filter** y, a continuación, haga clic en Agregar **administrar &amp; orígenes**.
    
6. En la página Agregar administrar orígenes, escriba el alias de correo electrónico del usuario en el &amp; primer cuadro de texto en **Buzones**. Haga clic en el icono de buzón de marca que se encuentra junto al libro de texto para comprobar que SharePoint se puede conectar al buzón especificado.
    
7. Haga clic en **Aceptar**.
    
8. En la página de conjunto de eDiscovery, haga clic en **Guardar** para guardar el nuevo conjunto de eDiscovery.
    
En este punto, puede buscar en el buzón especificado (kenmyer) o habilitar las In-Place de la misma manera que lo haría con cualquier otro SharePoint contenido o origen de resultados.
  

