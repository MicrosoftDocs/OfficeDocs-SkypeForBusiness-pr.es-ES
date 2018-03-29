---
title: Configurar SharePoint Server para buscar datos archivados de Skype Empresarial
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Resumen: Configurar servidor de SharePoint para buscar datos archivados por 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.'
ms.openlocfilehash: 161e4dd530490d22d14f5392539e2cc3d788d6bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a><span data-ttu-id="cea7f-103">Configurar SharePoint Server para buscar datos archivados de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="cea7f-103">Configure SharePoint Server to search for archived Skype for Business data</span></span>
 
<span data-ttu-id="cea7f-104">**Resumen:** Configurar el servidor de SharePoint para buscar datos archivados por 2016 de Exchange Server o Exchange Server 2013 y Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cea7f-104">**Summary:** Configure SharePoint Server to search for data archived by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="cea7f-105">Una de las principales ventajas de almacenar transcripciones de conferencias Web y mensajería instantánea en 2016 de Exchange Server o Exchange Server 2013 en lugar de Skype para Business Server 2015 es que el almacenamiento de datos en la misma ubicación permite a los administradores utilizar una única herramienta para búsqueda de datos archivados de Exchange o archivado Skype para los datos del servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="cea7f-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Exchange Server 2016 or Exchange Server 2013 instead of Skype for Business Server 2015 is that storing data in the same location allows administrators to use a single tool to search for archived Exchange data and/or archived Skype for Business Server data.</span></span> <span data-ttu-id="cea7f-106">Dado que todos los datos se almacenan en el mismo lugar (Exchange) también puede buscar cualquier herramienta que puede buscar los datos archivados de Exchange archivado Skype para los datos de Business Server.</span><span class="sxs-lookup"><span data-stu-id="cea7f-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Skype for Business Server data.</span></span>
  
<span data-ttu-id="cea7f-107">Una herramienta que facilita la búsqueda de datos archivados es 2013 de Microsoft SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="cea7f-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="cea7f-108">Si desea usar SharePoint para buscar datos de Business Server de Skype, primero debe completar todos los pasos necesarios para configurar Exchange archiving en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="cea7f-108">If you would like to use SharePoint to search for Skype for Business Server data, you must first complete all the steps involved in configuring Exchange archiving in Skype for Business Server.</span></span> <span data-ttu-id="cea7f-109">Después de Skype para Business Server y Exchange Server se han integrado correctamente, a continuación, debe instalar la [API administrada de servicios Web](https://go.microsoft.com/fwlink/p/?LinkId=258305) de Exchange en el servidor de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cea7f-109">After Exchange Server and Skype for Business Server have been successfully integrated, you must then install the Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) on your SharePoint Server.</span></span> <span data-ttu-id="cea7f-110">El archivo descargado (EWSManagedAPI.msi) se puede guardar en cualquier carpeta en el servidor de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cea7f-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>
  
<span data-ttu-id="cea7f-111">Una vez se ha descargado el archivo, complete el siguiente procedimiento en SharePoint Server:</span><span class="sxs-lookup"><span data-stu-id="cea7f-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>
  
1. <span data-ttu-id="cea7f-112">Para abrir una ventana de comandos, haga clic en **Inicio**, en **Todos los programas**, en **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="cea7f-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>
    
2. <span data-ttu-id="cea7f-113">En la ventana de comandos, utilice el comando cd para cambiar el directorio actual a la carpeta donde se ha guardado el archivo EWSManagedAPI.msi.</span><span class="sxs-lookup"><span data-stu-id="cea7f-113">In the command window, use the cd command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="cea7f-114">Por ejemplo, si ha guardado el archivo en C:\Downloads escriba el comando siguiente en la ventana de comandos y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="cea7f-114">For example, if you have saved the file to C:\Downloads type the following command in the command window and then press Enter:</span></span>
    
   ```
   cd C:\Downloads
   ```

3. <span data-ttu-id="cea7f-115">Para instalar la API, escriba el comando siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="cea7f-115">To install the API, type the following command then press Enter:</span></span>
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. <span data-ttu-id="cea7f-116">Después de haber instalado la API, restablecer IIS escribiendo el comando siguiente y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="cea7f-116">After the API has been installed, reset IIS by typing the following command and pressing Enter:</span></span>
    
   ```
   iisreset
   ```

<span data-ttu-id="cea7f-117">Después de instalar servicios Web de Exchange, a continuación, debe configurar la autenticación de servidor a servidor entre SharePoint Server y Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="cea7f-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server and Exchange Server.</span></span> <span data-ttu-id="cea7f-118">Para ello, abra el Shell de administración de SharePoint y ejecutar el siguiente conjunto de comandos:</span><span class="sxs-lookup"><span data-stu-id="cea7f-118">To do this, first open the SharePoint Management Shell and run the following set of commands:</span></span>
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> <span data-ttu-id="cea7f-119">Asegúrese de usar el URI para su servicio de detección automática.</span><span class="sxs-lookup"><span data-stu-id="cea7f-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="cea7f-120">No utilice el URI de ejemplo https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span><span class="sxs-lookup"><span data-stu-id="cea7f-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span> 
  
<span data-ttu-id="cea7f-121">Después de haber creado al emisor de tokens y configurado el servicio de token de ejecutar estos comandos, asegurándose de que se sustituya la dirección URL del sitio de SharePoint para la dirección URL de ejemplohttp://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="cea7f-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

<span data-ttu-id="cea7f-122">Para configurar la autenticación de servidor a servidor de Exchange Server, abra el Shell de administración de Exchange y ejecutar un comando similar al siguiente (suponiendo que se ha instalado Exchange en la unidad C: y que TI utiliza la ruta de la carpeta predeterminada):</span><span class="sxs-lookup"><span data-stu-id="cea7f-122">To configure server-to-server authentication for Exchange Server, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

<span data-ttu-id="cea7f-123">Después de configurar la aplicación asociada se recomienda detener y reiniciar servicios de Internet Information Server (IIS) en todos los buzones y el cliente acceso a servidores Exchange.</span><span class="sxs-lookup"><span data-stu-id="cea7f-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="cea7f-124">Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:</span><span class="sxs-lookup"><span data-stu-id="cea7f-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="cea7f-125">Este comando se puede ejecutar desde el Shell de administración de Exchange o desde cualquier otra ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="cea7f-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>
  
<span data-ttu-id="cea7f-126">A continuación, ejecute un comando similar al siguiente, que proporcione al usuario (en este ejemplo, kenmyer) derecho al descubrimiento de Exchange:</span><span class="sxs-lookup"><span data-stu-id="cea7f-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

<span data-ttu-id="cea7f-127">Una vez se ha establecido la autenticación de servidor a servidor entre Exchange y SharePoint, el siguiente paso es crear un sitio de eDiscovery en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cea7f-127">After server-to-server authentication has been established between Exchange and SharePoint, your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="cea7f-128">Que se puede realizar mediante la ejecución de comandos similares a éstos desde el Shell de administración de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="cea7f-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> <span data-ttu-id="cea7f-129">"eDiscovery" es la abreviatura de "detección electrónica" y normalmente hace referencia al proceso de mirar por los archivos electrónicos para buscar elementos que "se pueden calcular de manera razonable para llevar a pruebas admisibles) en un juzgado.</span><span class="sxs-lookup"><span data-stu-id="cea7f-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span> 
  
<span data-ttu-id="cea7f-130">Cuando el nuevo sitio esté listo, el siguiente paso es configurar Exchange Server para que actúe como resultado origen para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cea7f-130">When the new site is ready, the next step is to configure Exchange Server to act as a result source for SharePoint.</span></span> <span data-ttu-id="cea7f-131">Puede hacerlo completando el procedimiento siguiente desde la página Administración Central de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="cea7f-131">You can do that by completing the following procedure from the SharePoint Central Administration page:</span></span>
  
1. <span data-ttu-id="cea7f-132">En la página de Administración central haga clic en **Administrar aplicaciones de servicios** y, a continuación, en **Aplicación de servicio de búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="cea7f-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>
    
2. <span data-ttu-id="cea7f-133">En la página Aplicación de servicio de búsqueda, haga clic en **Orígenes de resultados** y después en **Nuevo origen de resultados**.</span><span class="sxs-lookup"><span data-stu-id="cea7f-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>
    
3. <span data-ttu-id="cea7f-134">En el panel **Nuevo origen de resultados**, escriba un nombre para el nuevo origen (por ejemplo, **Microsoft Exchange**) en el cuadro **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="cea7f-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="cea7f-135">Seleccione **Exchange** como el **protocolo**de origen de resultados y, a continuación, escriba la URL de origen de servicios web para el servidor de Exchange en el cuadro **Dirección URL de origen de Exchange** .</span><span class="sxs-lookup"><span data-stu-id="cea7f-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="cea7f-136">La dirección URL de origen debería ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="cea7f-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. <span data-ttu-id="cea7f-137">Asegúrese de que la opción **Usar Autodetección** no está seleccionada y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cea7f-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>
    
<span data-ttu-id="cea7f-138">Finalmente, cree un nuevo caso de eDiscovery y un nuevo eDiscovery establecer completando el procedimiento siguiente desde el sitio de SharePoint del descubrimiento (por ejemplo,https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="cea7f-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>
  
1. <span data-ttu-id="cea7f-139">En la página de contenido del sitio haga clic en **Crear un nuevo caso**.</span><span class="sxs-lookup"><span data-stu-id="cea7f-139">On the Site Contents page click **Create a new case**.</span></span>
    
2. <span data-ttu-id="cea7f-p110">En la página de contenido del sitio: nuevo sitio de SharePoint, escriba el alias de correo electrónico del usuario (por ejemplo, **kenmyer**) en el cuadro **Título** y, a continuación, agregue esa misma dirección URL al cuadro de **dirección de sitio web**. Eso producirá una dirección URL similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="cea7f-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. <span data-ttu-id="cea7f-142">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="cea7f-142">Click **Create**.</span></span>
    
4. <span data-ttu-id="cea7f-143">Cuando aparezca la página de conjunto de exhibición de documentos electrónicos, haga clic en **nuevo elemento** dentro de **Identidad y Preservar: conjuntos de detección**.</span><span class="sxs-lookup"><span data-stu-id="cea7f-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>
    
5. <span data-ttu-id="cea7f-144">En la página de nuevo: conjunto de detección, escriba el alias de correo electrónico del usuario en el cuadro de **nombre de conjunto de detección**.</span><span class="sxs-lookup"><span data-stu-id="cea7f-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="cea7f-145">Escriba \*\*eDiscovery Lync\* \*\* en el **filtro** y, a continuación, haga clic en **Agregar &amp; administrar orígenes de**.</span><span class="sxs-lookup"><span data-stu-id="cea7f-145">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add &amp; Manage Sources**.</span></span>
    
6. <span data-ttu-id="cea7f-146">En el complemento &amp; administrar orígenes de página, escriba el alias de correo electrónico del usuario en el primer cuadro de texto en **buzones**.</span><span class="sxs-lookup"><span data-stu-id="cea7f-146">On the Add &amp; Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="cea7f-147">Haga clic en el icono de buzón de marca que se encuentra junto al libro de texto para comprobar que SharePoint se puede conectar al buzón especificado.</span><span class="sxs-lookup"><span data-stu-id="cea7f-147">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>
    
7. <span data-ttu-id="cea7f-148">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cea7f-148">Click **OK**.</span></span>
    
8. <span data-ttu-id="cea7f-149">En la página de conjunto de exhibición de documentos electrónicos, haga clic en **Guardar** para guardar el nuevo conjunto de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="cea7f-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>
    
<span data-ttu-id="cea7f-150">En este momento puede buscar en el buzón especificado (kenmyer) o activar en contexto mantiene la misma forma que lo haría con cualquier otro origen de contenido o resultado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cea7f-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>
  

