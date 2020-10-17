---
title: Configurar Lync Server 2013 para usar el archivado de Microsoft Exchange Server 2013
description: Configurar Lync Server 2013 para usar el archivado de Microsoft Exchange Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80b0673071ec38246e366fe7556b39bd495895d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542946"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a><span data-ttu-id="c7d8e-103">Configuración de Microsoft Lync Server 2013 para usar el archivado de Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7d8e-103">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7d8e-104">_**Última modificación del tema:** 2014-06-24_</span><span class="sxs-lookup"><span data-stu-id="c7d8e-104">_**Topic Last Modified:** 2014-06-24_</span></span>

<span data-ttu-id="c7d8e-105">Microsoft Lync Server 2013 ofrece a los administradores la opción de hacer que las transcripciones de mensajería instantánea y de conferencias web se archiven en un buzón de correo de Microsoft Exchange Server 2013 de un usuario en lugar de una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-105">Microsoft Lync Server 2013 gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Microsoft Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="c7d8e-106">Si se habilita esta opción, las transcripciones se escribirán en la carpeta Purga del buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-106">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="c7d8e-107">La carpeta Purga es una carpeta oculta que se encuentra en la carpeta Elementos recuperables.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-107">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="c7d8e-108">Aunque esta carpeta no es visible para los usuarios finales, el motor de búsqueda de Exchange indiza la carpeta y se puede detectar mediante la búsqueda en buzones de Exchange o Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-108">Although this folder is not visible to end-users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="c7d8e-109">Debido a que la información se almacena en la misma carpeta que usa la característica de retención de In-Place de Exchange (responsable de archivar el correo electrónico y otras comunicaciones de Exchange), los administradores pueden usar una única herramienta para buscar todas las comunicaciones electrónicas archivadas para un usuario.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-109">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c7d8e-110">Para deshabilitar por completo el archivado de la conversación de Lync, también debe deshabilitar el historial de conversaciones de Lync.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-110">To completely disable archiving of Lync conversation, you must also disable Lync conversation history.</span></span> <span data-ttu-id="c7d8e-111">Para obtener más información, vea los temas siguientes: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Administración del archivado de comunicaciones internas y externas en Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>y <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-CsClientPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-111">For more information, see the following topics: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>, and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span></span>



</div>

<span data-ttu-id="c7d8e-112">Para archivar transcripciones en Exchange 2013 debe empezar configurando la autenticación de servidor a servidor entre los dos servidores.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-112">In order to archive transcripts to Exchange 2013 you must begin by configuring server-to-server authentication between the two servers.</span></span> <span data-ttu-id="c7d8e-113">Una vez implementada la autenticación de servidor a servidor, puede llevar a cabo las siguientes tareas en Microsoft Lync Server 2013 (tenga en cuenta que, según la configuración y la configuración, es posible que no necesite completar todas estas tareas):</span><span class="sxs-lookup"><span data-stu-id="c7d8e-113">After server-to-server authentication is in place you can then carry out the following tasks in Microsoft Lync Server 2013 (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1.  <span data-ttu-id="c7d8e-114">Habilite el archivado de Exchange modificando las opciones de configuración de archivado de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-114">Enable Exchange archiving by modifying your Lync Server archiving configuration settings.</span></span> <span data-ttu-id="c7d8e-115">Este paso es obligatorio para todas las implementaciones.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-115">This step is required for all deployments.</span></span>

2.  <span data-ttu-id="c7d8e-116">Habilite el archivado de comunicaciones externas/internas de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-116">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="c7d8e-117">Este paso es obligatorio para todas las implementaciones.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-117">This step is required for all deployments.</span></span>

3.  <span data-ttu-id="c7d8e-118">Configure la propiedad ExchangeArchivingPolicy para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-118">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="c7d8e-119">Este paso solo es necesario en Lync Server y Exchange se encuentran en bosques diferentes.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-119">This step is only required in Lync Server and Exchange are located in different forests.</span></span>

<div>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="c7d8e-120">Paso 1: habilitar el archivado de Exchange</span><span class="sxs-lookup"><span data-stu-id="c7d8e-120">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="c7d8e-121">El archivado en Lync Server se administra principalmente mediante las opciones de configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-121">Archiving in Lync Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="c7d8e-122">Al instalar Lync Server 2013, se le asigna automáticamente una colección global única de estas opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-122">When you install Lync Server 2013 you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="c7d8e-123">(De manera opcional, los administradores pueden crear nuevas colecciones de configuraciones de archivado en el ámbito de sitio). De forma predeterminada, el archivado no está habilitado en la configuración global, ni está habilitado para el archivado de Exchange en esta configuración.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-123">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="c7d8e-124">Para poder usar los administradores de archivado de Exchange, debe configurar las propiedades EnableArchiving y EnableExchangeArchiving en estas opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-124">In order to use Exchange archiving administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="c7d8e-125">La propiedad EnableArchiving se puede establecer en uno de estos tres valores posibles:</span><span class="sxs-lookup"><span data-stu-id="c7d8e-125">The EnableArchiving property can be set to one of three possible values:</span></span>

  - <span data-ttu-id="c7d8e-126">**Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-126">**None**.</span></span> <span data-ttu-id="c7d8e-127">El archivado está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-127">Archiving is disabled.</span></span> <span data-ttu-id="c7d8e-128">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-128">This is the default value.</span></span> <span data-ttu-id="c7d8e-129">Si EnableArchiving se establece en None, no se archivará nada en la base de datos de archivado de Lync Server o en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-129">If EnableArchiving is set to None then nothing will be archived in either your Lync Server archiving database or in Exchange 2013.</span></span>

  - <span data-ttu-id="c7d8e-130">**Solo**.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-130">**ImOnly**.</span></span> <span data-ttu-id="c7d8e-131">Solo se archivarán las transcripciones de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-131">Only instant message transcripts are archived.</span></span> <span data-ttu-id="c7d8e-132">Si está habilitado el archivado de Exchange, estas transcripciones se archivarán en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-132">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="c7d8e-133">Si el archivado de Exchange está deshabilitado, estas transcripciones se archivarán en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-133">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

  - <span data-ttu-id="c7d8e-134">**ImAndWebConf**.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-134">**ImAndWebConf**.</span></span> <span data-ttu-id="c7d8e-135">Se archivarán las transcripciones de mensajería instantánea y de las conferencias web.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-135">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="c7d8e-136">Si está habilitado el archivado de Exchange, estas transcripciones se archivarán en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-136">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="c7d8e-137">Si el archivado de Exchange está deshabilitado, estas transcripciones se archivarán en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-137">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

<span data-ttu-id="c7d8e-138">La propiedad EnableExchangeArchiving es un valor booleano: establezca EnableExchangeArchiving en true ($True) para habilitar el archivado de Exchange o establezca EnableExchangeArchiving en false ($False) para deshabilitar el archivado de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-138">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="c7d8e-139">Por ejemplo, este comando habilita el archivado de transcripciones de mensajería instantánea y también permite archivado de Exchange:</span><span class="sxs-lookup"><span data-stu-id="c7d8e-139">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

<span data-ttu-id="c7d8e-140">Para deshabilitar el archivado de Exchange, use un comando similar al siguiente, que permite el archivado de mensajería instantánea pero deshabilita el archivado en Exchange (es decir, las transcripciones se archivarán en Lync Server):</span><span class="sxs-lookup"><span data-stu-id="c7d8e-140">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Lync Server):</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> <span data-ttu-id="c7d8e-141">Si la propiedad EnableArchiving está establecida en None, Lync Server no archivará las transcripciones de mensajería instantánea y de conferencias web.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-141">If the EnableArchiving property is set to None then Lync Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="c7d8e-142">En este caso, el servidor simplemente ignorará el valor configurado de la propiedad EnableExchangeArchiving.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-142">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>



</div>

<span data-ttu-id="c7d8e-143">El archivado de Exchange también se puede habilitar (o deshabilitar) mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-143">Exchange archiving can also be enabled (or disabled) by using the Lync Server Control Panel.</span></span> <span data-ttu-id="c7d8e-144">Para ello, lleve a cabo el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7d8e-144">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="c7d8e-145">En el Panel de control, haga clic en **Configuración y archivado** y, a continuación, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-145">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2.  <span data-ttu-id="c7d8e-146">En la pestaña **Configuración de archivado**, haga doble clic en la recopilación de opciones de archivado que desea modificar (por ejemplo, la recopilación **Global**).</span><span class="sxs-lookup"><span data-stu-id="c7d8e-146">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3.  <span data-ttu-id="c7d8e-147">En el panel **Editar configuración de archivado**, haga clic en la lista desplegable **Configuración de archivado** y seleccione **Archivar sesiones de mensajería instantánea** (para archivar solo las sesiones de mensajería instantánea) o **Archivar sesiones de mensajería instantánea y conferencias web** (para archivar tanto las sesiones de conferencia web y mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="c7d8e-147">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4.  <span data-ttu-id="c7d8e-148">Después de elegir los elementos que se van a archivar, active la casilla **integración de Exchange Server** para habilitar el archivado de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-148">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="c7d8e-149">Para deshabilitar el archivado de Exchange, desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-149">To disable Exchange archiving, clear this checkbox.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7d8e-150">La casilla <STRONG>Integración con Exchange Server</STRONG> no estará disponible si la opción <STRONG>Configuración de archivado</STRONG> está configurada como <STRONG>Deshabilitar archivado</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-150">The <STRONG>Exchange Server integration</STRONG> checkbox will not be available if the <STRONG>Archiving setting</STRONG> is set to <STRONG>Disable archiving</STRONG>.</span></span> <span data-ttu-id="c7d8e-151">Primero debe habilitar el archivado y, a continuación, habilitar el archivado de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-151">You must enable archiving first and then enable Exchange archiving.</span></span>



</div>

<span data-ttu-id="c7d8e-152">Si Lync Server 2013 y Exchange 2013 están ubicados en el mismo bosque, el archivado para usuarios individuales (o al menos para usuarios que tienen cuentas de correo en Exchange 2013) se administra mediante las directivas de suspensión de Exchange In-Place.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-152">If Lync Server 2013 and Exchange 2013 are located in the same forest then archiving for individual users (or at least for users who have email accounts on Exchange 2013) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="c7d8e-153">Si tiene usuarios hospedados en una versión anterior de Exchange, el archivado para esos usuarios se administrará con las directivas de archivado de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-153">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Lync Server archiving policies.</span></span> <span data-ttu-id="c7d8e-154">Tenga en cuenta que solo los usuarios con cuentas en Exchange 2013 pueden archivar sus transcripciones de Lync en Exchange.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-154">Note that only users with accounts on Exchange 2013 can have their Lync transcripts archived to Exchange.</span></span>

<span data-ttu-id="c7d8e-155">Si Lync Server 2013 y Exchange 2013 están ubicados en bosques diferentes, el archivado para usuarios individuales se administra configurando la propiedad ExchangeArchivingPolicy para cada cuenta de usuario individual.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-155">If Lync Server 2013 and Exchange 2013 are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="c7d8e-156">Vea el paso 3 para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-156">See Step 3 for more information.</span></span>

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="c7d8e-157">Paso 2: Habilitación del archivado de comunicaciones internas o externas</span><span class="sxs-lookup"><span data-stu-id="c7d8e-157">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="c7d8e-158">Una vez que haya habilitado el archivado (y el archivado de Exchange), debe modificar las directivas de archivado adecuadas para asegurarse de que las sesiones de usuario se archiven realmente.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-158">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="c7d8e-159">Tenga en cuenta que, al habilitar el archivado (paso 1), no se produce que Lync Server comience a archivar las transcripciones de mensajería instantánea y la conferencia Web.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-159">Note that simply enabling archiving (Step 1) does not cause Lync Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="c7d8e-160">En su lugar, debe usar directivas de archivado para habilitar el archivado externo o interno.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-160">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="c7d8e-161">Al instalar Lync Server 2013, también se instala una única directiva de archivado global que contiene dos propiedades:</span><span class="sxs-lookup"><span data-stu-id="c7d8e-161">When you install Lync Server 2013 you also install a single, global archiving policy that contains two properties:</span></span>

  - <span data-ttu-id="c7d8e-p119">**ArchiveInternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones internas (solo las sesiones de los usuarios de su organización que dispongan de cuentas de Active Directory).</span><span class="sxs-lookup"><span data-stu-id="c7d8e-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

  - <span data-ttu-id="c7d8e-p120">**ArchiveExternal**. Cuando se establece en True ($True), indica que solo se archivarán las sesiones de comunicaciones externas (sesiones en las que al menos usuario de su organización no disponga de cuenta de Active Directory).</span><span class="sxs-lookup"><span data-stu-id="c7d8e-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="c7d8e-166">De forma predeterminada, estos valores de propiedades están establecidos como False, lo que implica que no se archivan ni las sesiones de comunicaciones internas ni externas.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-166">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="c7d8e-167">Para modificar la directiva global, puede usar el shell de administración de Lync Server y el cmdlet Set-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-167">To modify the global policy, you can use the Lync Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="c7d8e-168">El comando siguiente habilita el archivado de las sesiones de comunicaciones internas y externas:</span><span class="sxs-lookup"><span data-stu-id="c7d8e-168">This command enables the archiving of both internal and external communication sessions:</span></span>

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="c7d8e-p122">De forma alternativa, puede usar el cmdlet New-CsArchivingPolicy para crear una nueva directiva para el sitio o por usuario. Por ejemplo, este comando permite crear una directiva de archivado específica para un usuario con el nombre RedmondArchivingPolicy:</span><span class="sxs-lookup"><span data-stu-id="c7d8e-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="c7d8e-p123">Si crea una directiva específica para un usuario, necesitará asignar dicha directiva a los usuarios correspondientes. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c7d8e-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

<span data-ttu-id="c7d8e-173">Las directivas de archivado también se pueden administrar mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-173">Archiving policies can also be managed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="c7d8e-174">Desde el Panel de control, haga clic en **Supervisión  y archivado** y haga clic en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-174">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="c7d8e-175">Para modificar una directiva existente, haga doble clic en la directiva (por ejemplo, Global) y, a continuación, en el panel **Editar directiva de archivado**, active o desactive las casillas **Archivar comunicaciones internas** o **Archivar comunicaciones externas** según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-175">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="c7d8e-176">Para crear una nueva Directiva de archivado, haga clic en **nuevo** y, a continuación, seleccione **Directiva de sitio** o **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-176">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="c7d8e-177">Si crea una nueva directiva de usuario, deberá tener acceso a las cuentas de usuario correspondientes (desde la pestaña **Usuarios**) y asignar dichos usuarios a la nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-177">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="c7d8e-178">Paso 3: Configuración de la propiedad ExchangeArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="c7d8e-178">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="c7d8e-179">Si Lync Server 2013 y Exchange 2013 están ubicados en bosques diferentes, no basta con habilitar el archivado de Exchange en las opciones de configuración de archivado; eso no provocará que se archiven las transcripciones de mensajería instantánea y de conferencias web en Exchange.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-179">If Lync Server 2013 and Exchange 2013 are located in different forests then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="c7d8e-180">En su lugar, también debe configurar la propiedad ExchangeArchivingPolicy en cada una de las cuentas de usuario de Lync Server relevantes.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-180">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Lync Server user accounts.</span></span> <span data-ttu-id="c7d8e-181">Esta propiedad puede establecerse con uno de los cuatro valores posibles:</span><span class="sxs-lookup"><span data-stu-id="c7d8e-181">This property can be set to one of four possible values:</span></span>

1.  <span data-ttu-id="c7d8e-182">Sin inicializar.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-182">Uninitialized.</span></span> <span data-ttu-id="c7d8e-183">Indica que el archivado se basará en la configuración de retención de In-Place configurada para el buzón de Exchange del usuario; Si no se ha habilitado la retención de In-Place en el buzón del usuario, el usuario tendrá archivado sus expedientes de mensajería y conferencias web en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-183">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Lync Server.</span></span>

2.  <span data-ttu-id="c7d8e-184">**UseLyncArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-184">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="c7d8e-185">Indica que la mensajería instantánea del usuario y las transcripciones de conferencias web deben archivarse en Lync Server en lugar de en Exchange.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-185">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Lync Server rather than in Exchange.</span></span>

3.  <span data-ttu-id="c7d8e-186">No **archivar**.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-186">**NoArchiving**.</span></span> <span data-ttu-id="c7d8e-187">Indica que las transcripciones de mensajería instantánea y de las conferencias web no deben archivarse.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-187">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="c7d8e-188">Tenga en cuenta que esta configuración reemplaza cualquier directiva de archivado de Lync Server asignada al usuario.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-188">Note that this setting overrides any Lync Server archiving policies assigned to the user.</span></span>

4.  <span data-ttu-id="c7d8e-189">**ArchivingToExchange**.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-189">**ArchivingToExchange**.</span></span> <span data-ttu-id="c7d8e-190">Indica que la mensajería instantánea del usuario y las transcripciones de conferencias web deben archivarse en Exchange independientemente de la configuración de retención de In-Place que se haya asignado (o no) al buzón del usuario.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-190">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="c7d8e-191">Por ejemplo, para configurar una cuenta de usuario para que las transcripciones de mensajería instantánea y de conferencias web siempre se archiven en Exchange, puede usar un comando similar al siguiente desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="c7d8e-191">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="c7d8e-192">Si desea establecer la misma directiva de archivado para un grupo de usuarios (por ejemplo, todos los usuarios hospedados en un Grupo de registradores específico), utilice un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7d8e-192">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="c7d8e-193">Tenga en cuenta que debe usar el shell de administración de Lync Server (y Windows PowerShell) para poder configurar el valor de la propiedad ExchangeArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-193">Note that you must use the Lync Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="c7d8e-194">Esta propiedad no se expone a los administradores en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7d8e-194">This property is not exposed to administrators in the Lync Server Control Panel.</span></span>

<span data-ttu-id="c7d8e-195">Si desea ver una lista de los usuarios a los que se ha asignado una directiva de archivado específica, utilice un comando similar al siguiente, que devuelve el nombre para mostrar de Active Directory de todos los usuarios para los que se ha establecido la propiedad ExchangeArchivingPolicy como Uninitialized:</span><span class="sxs-lookup"><span data-stu-id="c7d8e-195">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

<span data-ttu-id="c7d8e-196">Del mismo modo, este comando devuelve el nombre para mostrar de los usuarios que no tienen la propiedad ExchangeArchivingPolicy establecida como UseLyncArchivingPolicy:</span><span class="sxs-lookup"><span data-stu-id="c7d8e-196">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

