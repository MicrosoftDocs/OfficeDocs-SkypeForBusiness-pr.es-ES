---
title: 'Lync Server 2013: agregar comandos a los menús de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dfb79a985791e6994d8409339d12b12e1146ec5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="b1e3c-102">Agregar comandos a los menús de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1e3c-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1e3c-103">_**Última modificación del tema:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="b1e3c-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="b1e3c-104">Puede Agregar comandos personalizados a los menús de Lync 2013 y pasar el identificador uniforme de recursos (URI) SIP del usuario actual y los contactos seleccionados a la aplicación que inicia el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="b1e3c-105">Los comandos personalizados que agregue pueden aparecer en uno o varios de los siguientes menús:</span><span class="sxs-lookup"><span data-stu-id="b1e3c-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="b1e3c-106">El menú herramientas, en la barra de menús de la ventana principal de Lync</span><span class="sxs-lookup"><span data-stu-id="b1e3c-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="b1e3c-107">El menú contextual de contactos de la lista de contactos</span><span class="sxs-lookup"><span data-stu-id="b1e3c-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="b1e3c-108">El menú más opciones, en la ventana de conversación</span><span class="sxs-lookup"><span data-stu-id="b1e3c-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="b1e3c-109">El menú contextual de las personas que aparecen en la lista de participantes de la ventana de conversación</span><span class="sxs-lookup"><span data-stu-id="b1e3c-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="b1e3c-110">El menú opciones de una tarjeta de contacto</span><span class="sxs-lookup"><span data-stu-id="b1e3c-110">The options menu in a contact card</span></span>

<span data-ttu-id="b1e3c-111">Puede definir comandos personalizados para dos tipos de aplicaciones: aplicaciones que realizan una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b1e3c-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="b1e3c-112">Se aplica solo al usuario actual y se inicia en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="b1e3c-113">Incluya usuarios adicionales, como un programa de colaboración en línea, y se debe iniciar en el equipo de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="b1e3c-114">El comando personalizado se puede invocar de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="b1e3c-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="b1e3c-115">Seleccione uno o más usuarios y, a continuación, elija el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="b1e3c-116">Inicie una conversación de dos o varias partes y, a continuación, elija el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="b1e3c-117">Para agregar un comando personalizado</span><span class="sxs-lookup"><span data-stu-id="b1e3c-117">To add a custom command</span></span>

<span data-ttu-id="b1e3c-118">Use la configuración del registro de la tabla siguiente para agregar un comando a los menús.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="b1e3c-119">Estas entradas se colocan en el registro en una de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="b1e3c-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="b1e3c-120">Para el sistema operativo de\_32\_bits\\:\\el\\software\\del\\equipo\\local\\HKEY Microsoft Office 15,0 Lync SessionManager apps</span><span class="sxs-lookup"><span data-stu-id="b1e3c-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="b1e3c-121">Para el sistema operativo de\_64\_bits\\:\\HKEY\\local\\Machine\\software\\Wow6432Node\\Microsoft\\Office 15,0 Lync SessionManager apps</span><span class="sxs-lookup"><span data-stu-id="b1e3c-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="b1e3c-122">Entradas del registro de comandos personalizadas</span><span class="sxs-lookup"><span data-stu-id="b1e3c-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1e3c-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="b1e3c-123">Name</span></span></th>
<th><span data-ttu-id="b1e3c-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="b1e3c-124">Type</span></span></th>
<th><span data-ttu-id="b1e3c-125">Datos</span><span class="sxs-lookup"><span data-stu-id="b1e3c-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1e3c-126">Nombre</span><span class="sxs-lookup"><span data-stu-id="b1e3c-126">Name</span></span></p></td>
<td><p><span data-ttu-id="b1e3c-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b1e3c-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b1e3c-128">Nombre de la aplicación tal y como aparece en el menú.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1e3c-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="b1e3c-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="b1e3c-130">ÚLTIMAS</span><span class="sxs-lookup"><span data-stu-id="b1e3c-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="b1e3c-131">0 = ejecutable (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="b1e3c-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b1e3c-132">Requiere ApplicationInstallPath.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="b1e3c-133">1 = Protocolo</span><span class="sxs-lookup"><span data-stu-id="b1e3c-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1e3c-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="b1e3c-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="b1e3c-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b1e3c-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b1e3c-136">Ruta de acceso completa del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="b1e3c-137">Debe especificarse si ApplicationType es 0 (ejecutable).</span><span class="sxs-lookup"><span data-stu-id="b1e3c-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1e3c-138"> Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="b1e3c-138">Path</span></span></p></td>
<td><p><span data-ttu-id="b1e3c-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b1e3c-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b1e3c-140">Ruta completa para iniciarse junto con cualquier parámetro, incluidos los parámetros predeterminados <em>% User-ID%</em> y <em>% Contact-ID</em>.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1e3c-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="b1e3c-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="b1e3c-142">ÚLTIMAS</span><span class="sxs-lookup"><span data-stu-id="b1e3c-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="b1e3c-143">0 = sesión local.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-143">0 = Local session.</span></span> <span data-ttu-id="b1e3c-144">La aplicación se inicia en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-144">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="b1e3c-145">1 = sesión de dos partes (predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b1e3c-145">1 = Two-party session (default).</span></span> <span data-ttu-id="b1e3c-146">Lync 2013 inicia la aplicación de forma local y luego envía una notificación de escritorio al otro usuario.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="b1e3c-147">El otro usuario hace clic en la notificación para iniciar la aplicación en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="b1e3c-148">2 = sesión de varias partes.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-148">2 = Multiparty session.</span></span> <span data-ttu-id="b1e3c-149">Lync 2013 inicia la aplicación de forma local y después envía notificaciones de escritorio a los demás usuarios.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="b1e3c-150">El otro usuario hace clic en la notificación para iniciar la aplicación especificada en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1e3c-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="b1e3c-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="b1e3c-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="b1e3c-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="b1e3c-153">Una lista de los menús en los que aparecerá este comando, separados por puntos y comas.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="b1e3c-154">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="b1e3c-154">Possible values are:</span></span></p>
<p><span data-ttu-id="b1e3c-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="b1e3c-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="b1e3c-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="b1e3c-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="b1e3c-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="b1e3c-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="b1e3c-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="b1e3c-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="b1e3c-159">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="b1e3c-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="b1e3c-160">Si no se define ExtensibleMenu, se usan los valores predeterminados de MainWindowRightClick y ConversationWindowActions.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b1e3c-161">Por ejemplo, el siguiente editor del registro (. REG) muestra los resultados de agregar un elemento de menú de Contoso Sales Contact Manager en el menú de acciones en la ventana de conversación:</span><span class="sxs-lookup"><span data-stu-id="b1e3c-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a><span data-ttu-id="b1e3c-162">Para obtener acceso a un comando personalizado</span><span class="sxs-lookup"><span data-stu-id="b1e3c-162">To access a custom command</span></span>

<span data-ttu-id="b1e3c-163">Para obtener acceso a un comando personalizado después de agregarlo, siga uno de estos procedimientos, en función de los valores de ExtensibleMenu que defina:</span><span class="sxs-lookup"><span data-stu-id="b1e3c-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="b1e3c-164">**MainWindowActions**   en la ventana principal de Lync, haga clic en **herramientas**y, a continuación, haga clic en el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="b1e3c-165">**MainWindowRightClick**   en la ventana principal de Lync, haga clic con el botón secundario en un contacto y, a continuación, haga clic en el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="b1e3c-166">**ConversationWindowActions**   en la ventana de conversación, haga clic en el icono **más opciones** y, a continuación, haga clic en el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="b1e3c-167">**ConversationWindowRightClick**   en la ventana de conversación, haga clic con el botón secundario en el nombre de un contacto y, a continuación, haga clic en el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="b1e3c-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

