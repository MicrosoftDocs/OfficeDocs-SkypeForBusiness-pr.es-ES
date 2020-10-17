---
title: 'Lync Server 2013: configuración de Microsoft SharePoint Server 2013 para buscar datos archivados de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d831638cf25df4f9c1b792c34815e8bed8c15e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525877"
---
# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="a4fbf-102">Configuración de Microsoft SharePoint Server 2013 para buscar datos archivados de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4fbf-102">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4fbf-103">_**Última modificación del tema:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="a4fbf-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="a4fbf-104">Una de las principales ventajas de almacenar la mensajería instantánea y las transcripciones de conferencias web en Microsoft Exchange Server 2013 en lugar de Microsoft Lync Server 2013 es que el almacenamiento de datos en la misma ubicación permite a los administradores usar una única herramienta para buscar datos de Exchange archivados o datos archivados de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-104">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="a4fbf-105">Como todos los datos se almacenan en la misma ubicación (Exchange), cualquier herramienta que pueda buscar datos archivados de Exchange también puede buscar datos archivados de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-105">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="a4fbf-106">Una herramienta que permite buscar datos archivados de forma sencilla es Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-106">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="a4fbf-107">Si quiere usar SharePoint para buscar datos de Lync Server, primero debe completar todos los pasos necesarios para configurar el archivado de Exchange en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-107">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="a4fbf-108">Una vez que se hayan integrado correctamente Exchange 2013 y Lync Server 2013, debe instalar la API administrada de servicios web Exchange versión 2,0 en el servidor de SharePoint; el programa de instalación de esa API se puede descargar desde el centro de descarga de Microsoft ( [https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305) ).</span><span class="sxs-lookup"><span data-stu-id="a4fbf-108">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="a4fbf-109">El archivo descargado (EWSManagedAPI.msi) se puede guardar en cualquier carpeta de su SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-109">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="a4fbf-110">Una vez se ha descargado el archivo, complete el siguiente procedimiento en SharePoint Server:</span><span class="sxs-lookup"><span data-stu-id="a4fbf-110">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="a4fbf-111">Para abrir una ventana de comandos haga clic en **Inicio**, en **Todos los programas**, en **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-111">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="a4fbf-112">En la ventana de comandos, use el comando **cd** para cambiar el directorio actual a la carpeta donde se ha guardado el archivo EWSManagedAPI.msi.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-112">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="a4fbf-113">Por ejemplo, si ha guardado el archivo en C: \\ downloads, escriba el siguiente comando en la ventana de comandos y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="a4fbf-113">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="a4fbf-114">Para instalar la API, escriba el siguiente comando y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="a4fbf-114">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="a4fbf-115">Una vez se ha instalado la API, restablezca IIS escribiendo el siguiente comando y presionando ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="a4fbf-115">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="a4fbf-116">Después de instalar los servicios Web de Exchange, debe configurar la autenticación de servidor a servidor entre SharePoint Server 2013 y Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-116">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="a4fbf-117">Para ello, primero abra el shell de administración de SharePoint 2013 y ejecute el siguiente conjunto de comandos:</span><span class="sxs-lookup"><span data-stu-id="a4fbf-117">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="a4fbf-118">Asegúrese de usar el URI para su servicio de detección automática.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-118">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="a4fbf-119">No use el URI de ejemplo https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 .</span><span class="sxs-lookup"><span data-stu-id="a4fbf-119">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="a4fbf-120">Después de crear el emisor de tokens y de configurar el servicio de token, ejecute estos comandos, asegurándose de sustituir la dirección URL de su sitio de SharePoint para la dirección URL de ejemplo. http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="a4fbf-120">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="a4fbf-121">Para configurar la autenticación de servidor a servidor para Exchange 2013, abra el shell de administración de Exchange y ejecute un comando similar a este (suponiendo que Exchange se haya instalado en la unidad C: y que use la ruta de acceso a la carpeta predeterminada):</span><span class="sxs-lookup"><span data-stu-id="a4fbf-121">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="a4fbf-122">Después de configurar la aplicación de socio, se recomienda detener y reiniciar Internet Information Services (IIS) en todos los servidores de buzones de correo y de acceso de cliente de Exchange.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-122">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="a4fbf-123">Puede reiniciar IIS mediante un comando similar a este, que reinicia el servicio en el equipo atl-exchange-001:</span><span class="sxs-lookup"><span data-stu-id="a4fbf-123">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="a4fbf-124">Este comando se puede ejecutar desde dentro del shell de administración de Exchange o desde cualquier otra ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-124">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="a4fbf-125">A continuación, ejecute un comando similar al siguiente, que ofrece al usuario especificado (en este ejemplo, kenmyer) el derecho a realizar la detección en Exchange:</span><span class="sxs-lookup"><span data-stu-id="a4fbf-125">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="a4fbf-126">Después de establecer la autenticación de servidor a servidor entre Exchange y SharePoint, el siguiente paso consiste en crear un sitio de eDiscovery en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-126">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="a4fbf-127">Esto se puede hacer ejecutando comandos similares a estos desde el shell de administración de SharePoint:</span><span class="sxs-lookup"><span data-stu-id="a4fbf-127">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="a4fbf-128">"eDiscovery" es la abreviatura de "detección electrónica" y normalmente hace referencia al proceso de mirar por los archivos electrónicos para buscar elementos que "se pueden calcular de manera razonable para llevar a pruebas admisibles) en un juzgado.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-128">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="a4fbf-129">Cuando el nuevo sitio esté listo, el siguiente paso consiste en configurar Exchange 2013 para que actúe como un origen de resultados para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-129">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="a4fbf-130">Puede hacerlo completando el siguiente procedimiento desde la página de administración central de SharePoint 2013:</span><span class="sxs-lookup"><span data-stu-id="a4fbf-130">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="a4fbf-131">En la página de Administración central haga clic en **Administrar aplicaciones de servicio** y, a continuación, en **Aplicación de servicio de búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-131">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="a4fbf-132">En la página Aplicación de servicio de búsqueda haga clic en **Orígenes de resultados** y, a continuación, en **Nuevo origen de resultados**.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-132">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="a4fbf-133">En el panel **Nuevo origen de resultados** escriba un nombre para el nuevo origen de resultados (por ejemplo, **Microsoft Exchange**) en el cuadro **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-133">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="a4fbf-134">Seleccione **Exchange** como **Protocolo**de origen de resultados y, a continuación, escriba la dirección URL de origen de servicios web para el servidor de Exchange en el cuadro **dirección URL de origen de Exchange** .</span><span class="sxs-lookup"><span data-stu-id="a4fbf-134">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="a4fbf-135">La dirección URL de origen debería ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4fbf-135">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="a4fbf-136">Asegúrese de que la opción **Usar Autodetección** no está seleccionada y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-136">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="a4fbf-137">Por último, cree un nuevo caso de eDiscovery y un nuevo conjunto de exhibición de documentos electrónicos completando el siguiente procedimiento desde el sitio de detección de SharePoint (por ejemplo, https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="a4fbf-137">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="a4fbf-138">En la página de contenido del sitio haga clic en **Crear un nuevo caso**.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-138">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="a4fbf-p110">En la página de contenido del sitio: nuevo sitio de SharePoint, escriba el alias de correo electrónico del usuario (por ejemplo, **kenmyer**) en el cuadro **Título** y, a continuación, agregue esa misma dirección URL al cuadro de **dirección de sitio web**. Eso producirá una dirección URL similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4fbf-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="a4fbf-141">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-141">Click **Create**.</span></span>

4.  <span data-ttu-id="a4fbf-142">Cuando aparezca la página de conjunto de eDiscovery, haga clic en **nuevo elemento** debajo de la opción de **identidad y preservar: conjuntos de detección**.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-142">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="a4fbf-143">En la página de nuevo: conjunto de detección, escriba el alias de correo electrónico del usuario en el cuadro de **nombre de conjunto de detección**.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-143">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="a4fbf-144">Escriba \*\*EDiscovery Lync \* \*\* en el cuadro **filtro** y, a continuación, haga clic en **Agregar & administrar orígenes**.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-144">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="a4fbf-p112">En la página para agregar y administrar orígenes, escriba el alias de correo electrónico del usuario en el primer cuadro de texto debajo de **Buzones**. Haga clic en el icono de buzón de marca que se encuentra junto al libro de texto para comprobar que SharePoint se puede conectar al buzón especificado.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-p112">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**. Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="a4fbf-147">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-147">Click **OK**.</span></span>

8.  <span data-ttu-id="a4fbf-148">En la página de conjunto de eDiscovery, haga clic en **Guardar** para guardar el nuevo conjunto de eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-148">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="a4fbf-149">En este momento, puede buscar el buzón especificado (kenmyer) y/o habilitar In-Place tiene la misma manera que lo haría para cualquier otro contenido de SharePoint o origen de resultados.</span><span class="sxs-lookup"><span data-stu-id="a4fbf-149">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

