---
title: Configuración de Lync Server 2013 para usar el archivado de Microsoft Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3f8ab22ed23adbce2d6cbd6ccbf1f378476ff00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a><span data-ttu-id="0ce6b-102">Configuración de Microsoft Lync Server 2013 para usar el archivado de Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ce6b-102">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ce6b-103">_**Última modificación del tema:** 2014-06-24_</span><span class="sxs-lookup"><span data-stu-id="0ce6b-103">_**Topic Last Modified:** 2014-06-24_</span></span>

<span data-ttu-id="0ce6b-104">Microsoft Lync Server 2013 ofrece a los administradores la opción de enviar mensajes instantáneos y las transcripciones de conferencias web archivadas en el buzón de correo de un usuario de Microsoft Exchange Server 2013, en lugar de una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-104">Microsoft Lync Server 2013 gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Microsoft Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="0ce6b-105">Si se habilita esta opción, las transcripciones se escribirán en la carpeta Purga del buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-105">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="0ce6b-106">La carpeta Purga es una carpeta oculta que se encuentra en la carpeta Elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-106">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="0ce6b-107">Aunque esta carpeta no está visible para los usuarios finales, la carpeta la indiza el motor de búsqueda de Exchange y se puede detectar mediante la búsqueda de correo de Exchange y/o Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-107">Although this folder is not visible to end-users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="0ce6b-108">Debido a que la información se almacena en la misma carpeta que usa la característica de conservación local de Exchange (responsable de archivar el correo electrónico y otras comunicaciones de Exchange), los administradores pueden usar una única herramienta para buscar todas las comunicaciones electrónicas archivadas para un usuario.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-108">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0ce6b-109">Para deshabilitar por completo el archivado de una conversación de Lync, también debe deshabilitar el historial de conversaciones de Lync.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-109">To completely disable archiving of Lync conversation, you must also disable Lync conversation history.</span></span> <span data-ttu-id="0ce6b-110">Para obtener más información, vea los siguientes temas: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">administrar el archivado de comunicaciones internas y externas en Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-ClientPolicy</A>y <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-ClientPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-110">For more information, see the following topics: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>, and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span></span>



</div>

<span data-ttu-id="0ce6b-111">Para archivar transcripciones a Exchange 2013 debe comenzar con la configuración de la autenticación de servidor a servidor entre los dos servidores.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-111">In order to archive transcripts to Exchange 2013 you must begin by configuring server-to-server authentication between the two servers.</span></span> <span data-ttu-id="0ce6b-112">Una vez que se haya habilitado la autenticación de servidor a servidor, podrá realizar las siguientes tareas en Microsoft Lync Server 2013 (tenga en cuenta que, según la configuración y la configuración, es posible que no tenga que completar todas estas tareas):</span><span class="sxs-lookup"><span data-stu-id="0ce6b-112">After server-to-server authentication is in place you can then carry out the following tasks in Microsoft Lync Server 2013 (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1.  <span data-ttu-id="0ce6b-113">Habilite el archivado de Exchange modificando los valores de configuración de archivado de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-113">Enable Exchange archiving by modifying your Lync Server archiving configuration settings.</span></span> <span data-ttu-id="0ce6b-114">Este paso es obligatorio en todas las implementaciones.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-114">This step is required for all deployments.</span></span>

2.  <span data-ttu-id="0ce6b-115">Habilite el archivado de comunicaciones externas/internas de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-115">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="0ce6b-116">Este paso es obligatorio en todas las implementaciones.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-116">This step is required for all deployments.</span></span>

3.  <span data-ttu-id="0ce6b-117">Configure la propiedad ExchangeArchivingPolicy de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-117">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="0ce6b-118">Este paso solo es necesario en Lync Server y Exchange se encuentran en bosques diferentes.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-118">This step is only required in Lync Server and Exchange are located in different forests.</span></span>

<div>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="0ce6b-119">Paso 1: habilitar el archivado de Exchange</span><span class="sxs-lookup"><span data-stu-id="0ce6b-119">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="0ce6b-120">El archivado en Lync Server se administra principalmente mediante la configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-120">Archiving in Lync Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="0ce6b-121">Al instalar Lync Server 2013, se le asigna automáticamente una única colección global de esta configuración.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-121">When you install Lync Server 2013 you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="0ce6b-122">(Los administradores pueden, opcionalmente, crear nuevas colecciones de opciones de archivado en el ámbito del sitio). De forma predeterminada, el archivado no está habilitado en la configuración global ni está habilitado el archivado de Exchange en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-122">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="0ce6b-123">Para poder usar los administradores de archivado de Exchange, debe configurar las propiedades EnableArchiving y EnableExchangeArchiving en estas opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-123">In order to use Exchange archiving administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="0ce6b-124">La propiedad EnableArchiving se puede establecer en uno de estos tres valores posibles:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-124">The EnableArchiving property can be set to one of three possible values:</span></span>

  - <span data-ttu-id="0ce6b-125">**None**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-125">**None**.</span></span> <span data-ttu-id="0ce6b-126">El archivado está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-126">Archiving is disabled.</span></span> <span data-ttu-id="0ce6b-127">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-127">This is the default value.</span></span> <span data-ttu-id="0ce6b-128">Si EnableArchiving se establece en ninguno, no se archivará nada en la base de datos de archivado de Lync Server o en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-128">If EnableArchiving is set to None then nothing will be archived in either your Lync Server archiving database or in Exchange 2013.</span></span>

  - <span data-ttu-id="0ce6b-129">**Solo**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-129">**ImOnly**.</span></span> <span data-ttu-id="0ce6b-130">Solo se archivan las transcripciones de mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-130">Only instant message transcripts are archived.</span></span> <span data-ttu-id="0ce6b-131">Si habilita el archivado de Exchange, estas transcripciones se archivarán en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-131">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="0ce6b-132">Si el archivado de Exchange está deshabilitado, estas transcripciones se archivarán en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-132">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

  - <span data-ttu-id="0ce6b-133">**ImAndWebConf**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-133">**ImAndWebConf**.</span></span> <span data-ttu-id="0ce6b-134">Se archivan las transcripciones de mensajes instantáneos y las transcripciones de conferencias por Internet.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-134">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="0ce6b-135">Si habilita el archivado de Exchange, estas transcripciones se archivarán en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-135">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="0ce6b-136">Si el archivado de Exchange está deshabilitado, estas transcripciones se archivarán en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-136">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

<span data-ttu-id="0ce6b-137">La propiedad EnableExchangeArchiving es un valor booleano: establezca EnableExchangeArchiving en true ($True) para habilitar el archivado de Exchange o establezca EnableExchangeArchiving en false ($False) para deshabilitar el archivado de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-137">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="0ce6b-138">Por ejemplo, este comando permite el archivado de transcripciones de mensajería instantánea y también permite el archivado de Exchange:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-138">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

<span data-ttu-id="0ce6b-139">Para deshabilitar el archivado de Exchange, use un comando similar al siguiente, que permite el archivado de mensajería instantánea pero deshabilita el archivado en Exchange (es decir, las transcripciones se archivarán en Lync Server):</span><span class="sxs-lookup"><span data-stu-id="0ce6b-139">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Lync Server):</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> <span data-ttu-id="0ce6b-140">Si la propiedad EnableArchiving se establece en None, Lync Server no archivará ni el correo instantáneo ni las transcripciones de conferencias por Internet.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-140">If the EnableArchiving property is set to None then Lync Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="0ce6b-141">En este caso, el servidor simplemente ignorará el valor configurado de la propiedad EnableExchangeArchiving.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-141">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>



</div>

<span data-ttu-id="0ce6b-142">El archivado de Exchange también se puede habilitar (o deshabilitar) mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-142">Exchange archiving can also be enabled (or disabled) by using the Lync Server Control Panel.</span></span> <span data-ttu-id="0ce6b-143">Para ello, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-143">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="0ce6b-144">En el Panel de control, haga clic en **Supervisión y archivado** y, luego, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-144">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2.  <span data-ttu-id="0ce6b-145">En la pestaña **Configuración de archivado**, haga doble clic en la recopilación de opciones de archivado que quiera modificar (por ejemplo, **Global**).</span><span class="sxs-lookup"><span data-stu-id="0ce6b-145">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3.  <span data-ttu-id="0ce6b-146">En el panel **Editar configuración de archivado**, haga clic en la lista desplegable **Configuración de archivado** y seleccione **Archivar sesiones de mensajería instantánea** (para archivar solo las sesiones de mensajería instantánea) o **Archivar sesiones de mensajería instantánea y conferencias web** (para archivar las sesiones tanto de conferencia web como de mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="0ce6b-146">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4.  <span data-ttu-id="0ce6b-147">Después de elegir los elementos para archivar, seleccione la casilla **integración de Exchange Server** para habilitar el archivado de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-147">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="0ce6b-148">Para deshabilitar el archivado de Exchange, desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-148">To disable Exchange archiving, clear this checkbox.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ce6b-149">La casilla <STRONG>Integración de Exchange Server</STRONG> no estará disponible si la opción <STRONG>Configuración de archivado</STRONG> está establecida en <STRONG>Deshabilitar archivado</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-149">The <STRONG>Exchange Server integration</STRONG> checkbox will not be available if the <STRONG>Archiving setting</STRONG> is set to <STRONG>Disable archiving</STRONG>.</span></span> <span data-ttu-id="0ce6b-150">Debe habilitar primero el archivado y, después, habilitar el archivado de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-150">You must enable archiving first and then enable Exchange archiving.</span></span>



</div>

<span data-ttu-id="0ce6b-151">Si Lync Server 2013 y Exchange 2013 se encuentran en el mismo bosque, el archivado para usuarios individuales (o, al menos, para los usuarios que tienen cuentas de correo electrónico en Exchange 2013) se administra mediante las directivas de retención local de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-151">If Lync Server 2013 and Exchange 2013 are located in the same forest then archiving for individual users (or at least for users who have email accounts on Exchange 2013) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="0ce6b-152">Si tiene usuarios alojados en una versión anterior de Exchange, el archivado de esos usuarios se administrará mediante las directivas de archivado de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-152">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Lync Server archiving policies.</span></span> <span data-ttu-id="0ce6b-153">Tenga en cuenta que solo los usuarios con cuentas en Exchange 2013 pueden tener las transcripciones de Lync archivadas en Exchange.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-153">Note that only users with accounts on Exchange 2013 can have their Lync transcripts archived to Exchange.</span></span>

<span data-ttu-id="0ce6b-154">Si Lync Server 2013 y Exchange 2013 se encuentran en bosques diferentes, el archivado para usuarios individuales se administra mediante la configuración de la propiedad ExchangeArchivingPolicy para cada cuenta de usuario individual.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-154">If Lync Server 2013 and Exchange 2013 are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="0ce6b-155">Mire el paso 3 para más información.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-155">See Step 3 for more information.</span></span>

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="0ce6b-156">Paso 2: habilitar el archivado de comunicaciones internas o externas</span><span class="sxs-lookup"><span data-stu-id="0ce6b-156">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="0ce6b-157">Una vez que haya habilitado el archivado (y el archivado de Exchange), debe modificar las directivas de archivado apropiadas para asegurarse de que las sesiones de usuario se hayan archivado realmente.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-157">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="0ce6b-158">Tenga en cuenta que simplemente habilitar el archivado (paso 1) no provoca que Lync Server empiece a archivar la mensajería instantánea y las transcripciones de conferencias por Internet.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-158">Note that simply enabling archiving (Step 1) does not cause Lync Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="0ce6b-159">Hay que usar directivas de archivado para habilitar el archivado externo o interno.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-159">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="0ce6b-160">Al instalar Lync Server 2013, también se instala una única directiva de archivado global que contiene dos propiedades:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-160">When you install Lync Server 2013 you also install a single, global archiving policy that contains two properties:</span></span>

  - <span data-ttu-id="0ce6b-p119">**ArchiveInternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones internas (solo las sesiones de los usuarios que tienen cuentas de Active Directory en la organización).</span><span class="sxs-lookup"><span data-stu-id="0ce6b-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

  - <span data-ttu-id="0ce6b-p120">**ArchiveExternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones externas (sesiones en las que al menos un usuario no tiene una cuenta de Active Directory en la organización).</span><span class="sxs-lookup"><span data-stu-id="0ce6b-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="0ce6b-165">Los valores de estas propiedades están establecidos de forma predeterminada en False, lo que implica que no se archivan las sesiones de comunicaciones ni internas ni externas.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-165">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="0ce6b-166">Para modificar la directiva global, puede usar el shell de administración de Lync Server y el cmdlet Set-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-166">To modify the global policy, you can use the Lync Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="0ce6b-167">El siguiente comando habilita el archivado de las sesiones de comunicaciones internas y externas:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-167">This command enables the archiving of both internal and external communication sessions:</span></span>

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="0ce6b-p122">Otra opción consiste en usar el cmdlet New-CsArchivingPolicy para crear una directiva para el sitio o por usuario. Por ejemplo, este comando permite crear una directiva de archivado específica para un usuario con el nombre RedmondArchivingPolicy:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="0ce6b-p123">Si crea una directiva específica para un usuario, necesitará asignar dicha directiva a los usuarios correspondientes. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

<span data-ttu-id="0ce6b-172">Las directivas de archivado también se pueden administrar mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-172">Archiving policies can also be managed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="0ce6b-173">Desde el Panel de control, haga clic en **Supervisión y archivado** y haga clic en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-173">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="0ce6b-174">Para modificar una directiva existente, haga doble clic en la directiva (por ejemplo, Global) y, en el panel **Editar directiva de archivado**, active o desactive las casillas **Archivar comunicaciones internas** o **Archivar comunicaciones externas**, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-174">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="0ce6b-175">Para crear una nueva Directiva de archivado, haga clic en **nuevo** y, a continuación, seleccione **Directiva del sitio** o **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-175">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="0ce6b-176">Si crea una directiva de usuario, necesitará tener acceso a las cuentas de usuario correspondientes (desde la pestaña **Usuarios**) y asignar la nueva directiva a dichos usuarios.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-176">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="0ce6b-177">Paso 3: configurar la propiedad ExchangeArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="0ce6b-177">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="0ce6b-178">Si Lync Server 2013 y Exchange 2013 se encuentran en diferentes bosques, no basta con que simplemente habilite el archivado de Exchange en la configuración de archivado; eso no hará que los mensajes instantáneos y las transcripciones de conferencias web se archiven en Exchange.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-178">If Lync Server 2013 and Exchange 2013 are located in different forests then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="0ce6b-179">En su lugar, también debe configurar la propiedad ExchangeArchivingPolicy en cada una de las cuentas de usuario de Lync Server relevantes.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-179">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Lync Server user accounts.</span></span> <span data-ttu-id="0ce6b-180">Esta propiedad se puede establecer en uno de los cuatro valores posibles:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-180">This property can be set to one of four possible values:</span></span>

1.  <span data-ttu-id="0ce6b-181">No inicializados.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-181">Uninitialized.</span></span> <span data-ttu-id="0ce6b-182">Indica que el archivado se basará en la configuración de conservación local configurada para el buzón del usuario de Exchange. Si no se ha habilitado la retención local en el buzón del usuario, el usuario tendrá su mensajería y sus expedientes de conferencia web archivados en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-182">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Lync Server.</span></span>

2.  <span data-ttu-id="0ce6b-183">**UseLyncArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-183">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="0ce6b-184">Indica que la mensajería instantánea y las transcripciones de conferencias web del usuario deben archivarse en Lync Server en lugar de en Exchange.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-184">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Lync Server rather than in Exchange.</span></span>

3.  <span data-ttu-id="0ce6b-185">**NoArchiving**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-185">**NoArchiving**.</span></span> <span data-ttu-id="0ce6b-186">Indica que las transcripciones de mensajería instantánea y de las conferencias web no necesitan archivarse.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-186">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="0ce6b-187">Tenga en cuenta que esta configuración sobrescribe las directivas de archivado de Lync Server asignadas al usuario.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-187">Note that this setting overrides any Lync Server archiving policies assigned to the user.</span></span>

4.  <span data-ttu-id="0ce6b-188">**ArchivingToExchange**.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-188">**ArchivingToExchange**.</span></span> <span data-ttu-id="0ce6b-189">Indica que la mensajería instantánea del usuario y las transcripciones de conferencias web deberían archivarse en Exchange independientemente de la configuración de retención local que tenga (o no) se haya asignado al buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-189">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="0ce6b-190">Por ejemplo, para configurar una cuenta de usuario de modo que la mensajería instantánea y las transcripciones de conferencias web se archiven siempre a Exchange, puede usar un comando similar a este en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-190">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="0ce6b-191">Si desea establecer la misma directiva de archivado para un grupo de usuarios (por ejemplo, todos los usuarios hospedados en un Grupo de registradores específico), utilice un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-191">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="0ce6b-192">Tenga en cuenta que debe usar el shell de administración de Lync Server (y Windows PowerShell) para configurar el valor de la propiedad ExchangeArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-192">Note that you must use the Lync Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="0ce6b-193">Esta propiedad no se expone a los administradores en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ce6b-193">This property is not exposed to administrators in the Lync Server Control Panel.</span></span>

<span data-ttu-id="0ce6b-194">Si desea ver una lista de los usuarios a los que se ha asignado una directiva de archivado específica, use un comando similar al siguiente, que devuelve el nombre para mostrar de Active Directory de todos los usuarios para los que se ha establecido la propiedad ExchangeArchivingPolicy como Uninitialized:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-194">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

<span data-ttu-id="0ce6b-195">Del mismo modo, este comando devuelve el nombre para mostrar de los usuarios que no tienen la propiedad ExchangeArchivingPolicy establecida como UseLyncArchivingPolicy:</span><span class="sxs-lookup"><span data-stu-id="0ce6b-195">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

