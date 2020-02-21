---
title: 'Lync Server 2013: agregar comandos a los menús de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b6377824a7d96e6bb7b0ae6c60c79f3ee4c05b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="920ea-102">Agregar comandos a los menús de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="920ea-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="920ea-103">_**Última modificación del tema:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="920ea-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="920ea-104">Puede Agregar comandos personalizados a los menús de Lync 2013 y pasar el identificador uniforme de recursos (URI) de SIP del usuario actual y los contactos seleccionados a la aplicación que inicia el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="920ea-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="920ea-105">Los comandos personalizados que usted agrega pueden aparecer en uno o en varios de los menús siguientes:</span><span class="sxs-lookup"><span data-stu-id="920ea-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="920ea-106">En el menú Herramientas, en la barra de menús en la ventana principal de Lync</span><span class="sxs-lookup"><span data-stu-id="920ea-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="920ea-107">En el menú contextual de contactos en la lista de contactos</span><span class="sxs-lookup"><span data-stu-id="920ea-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="920ea-108">El menú más opciones, en la ventana de conversación</span><span class="sxs-lookup"><span data-stu-id="920ea-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="920ea-109">En el menú contextual para las personas que aparecen en la lista de participantes de la ventana Conversación</span><span class="sxs-lookup"><span data-stu-id="920ea-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="920ea-110">En el menú de opciones de una tarjeta de contacto</span><span class="sxs-lookup"><span data-stu-id="920ea-110">The options menu in a contact card</span></span>

<span data-ttu-id="920ea-111">Puede definir comandos personalizados para dos tipos de aplicaciones; en definitiva, para las aplicaciones que implican cualquiera de los siguientes supuestos:</span><span class="sxs-lookup"><span data-stu-id="920ea-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="920ea-112">Se aplican únicamente al usuario actual y se inician en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="920ea-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="920ea-113">Suponen la participación de usuarios adicionales, como un programa de colaboración en línea, y deben iniciarse en el equipo de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="920ea-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="920ea-114">El comando personalizado puede invocarse de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="920ea-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="920ea-115">Seleccione uno o más usuarios y elija el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="920ea-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="920ea-116">Inicie una conversación de dos o más participantes y elija el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="920ea-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="920ea-117">Para agregar un comando personalizado</span><span class="sxs-lookup"><span data-stu-id="920ea-117">To add a custom command</span></span>

<span data-ttu-id="920ea-118">Use la configuración del registro de la tabla siguiente para agregar un comando a los menús.</span><span class="sxs-lookup"><span data-stu-id="920ea-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="920ea-119">Estas entradas se colocan en el registro en una de las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="920ea-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="920ea-120">Para el sistema operativo de\_32\_bits\\:\\el\\software\\del\\equipo\\local\\HKEY Microsoft Office 15,0 Lync SessionManager apps</span><span class="sxs-lookup"><span data-stu-id="920ea-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="920ea-121">Para sistemas operativos de 64\_bits\_:\\HKEY\\Wow6432Node\\de\\software\\del\\equipo\\local\\de Microsoft Office 15,0 Lync SessionManager apps</span><span class="sxs-lookup"><span data-stu-id="920ea-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="920ea-122">Entradas del Registro de comandos personalizados</span><span class="sxs-lookup"><span data-stu-id="920ea-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="920ea-123">Nombre</span><span class="sxs-lookup"><span data-stu-id="920ea-123">Name</span></span></th>
<th><span data-ttu-id="920ea-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="920ea-124">Type</span></span></th>
<th><span data-ttu-id="920ea-125">Datos</span><span class="sxs-lookup"><span data-stu-id="920ea-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="920ea-126">Nombre</span><span class="sxs-lookup"><span data-stu-id="920ea-126">Name</span></span></p></td>
<td><p><span data-ttu-id="920ea-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="920ea-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="920ea-128">Nombre de la aplicación tal como aparece en el menú.</span><span class="sxs-lookup"><span data-stu-id="920ea-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920ea-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="920ea-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="920ea-130">ÚLTIMAS</span><span class="sxs-lookup"><span data-stu-id="920ea-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="920ea-131">0 = Ejecutable (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="920ea-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="920ea-132">Requiere ApplicationInstallPath.</span><span class="sxs-lookup"><span data-stu-id="920ea-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="920ea-133">1 = Protocolo</span><span class="sxs-lookup"><span data-stu-id="920ea-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="920ea-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="920ea-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="920ea-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="920ea-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="920ea-136">Ruta de acceso completa del ejecutable.</span><span class="sxs-lookup"><span data-stu-id="920ea-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="920ea-137">Debe especificarse si ApplicationType es igual a 0 (ejecutable).</span><span class="sxs-lookup"><span data-stu-id="920ea-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920ea-138">Path</span><span class="sxs-lookup"><span data-stu-id="920ea-138">Path</span></span></p></td>
<td><p><span data-ttu-id="920ea-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="920ea-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="920ea-140">Ruta de acceso completa que debe iniciarse junto con cualquier parámetro, incluidos los parámetros predeterminados <em>%user-id%</em> y <em>%contact-id%</em>.</span><span class="sxs-lookup"><span data-stu-id="920ea-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="920ea-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="920ea-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="920ea-142">ÚLTIMAS</span><span class="sxs-lookup"><span data-stu-id="920ea-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="920ea-p102">0 = Sesión local. La aplicación se inicia en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="920ea-p102">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="920ea-145">1 = Sesión entre dos participantes (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="920ea-145">1 = Two-party session (default).</span></span> <span data-ttu-id="920ea-146">Lync 2013 inicia la aplicación de forma local y, a continuación, envía una notificación de escritorio al otro usuario.</span><span class="sxs-lookup"><span data-stu-id="920ea-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="920ea-147">El otro usuario hace clic en la notificación para iniciar la aplicación en su equipo.</span><span class="sxs-lookup"><span data-stu-id="920ea-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="920ea-148">2 = Sesión de varios participantes.</span><span class="sxs-lookup"><span data-stu-id="920ea-148">2 = Multiparty session.</span></span> <span data-ttu-id="920ea-149">Lync 2013 inicia la aplicación de forma local y, a continuación, envía notificaciones de escritorio a los demás usuarios.</span><span class="sxs-lookup"><span data-stu-id="920ea-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="920ea-150">El otro usuario hace clic en la notificación para iniciar la aplicación especificada en su equipo.</span><span class="sxs-lookup"><span data-stu-id="920ea-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="920ea-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="920ea-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="920ea-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="920ea-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="920ea-153">Una lista de los menús en los que aparecerá este comando, separados por punto y coma.</span><span class="sxs-lookup"><span data-stu-id="920ea-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="920ea-154">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="920ea-154">Possible values are:</span></span></p>
<p><span data-ttu-id="920ea-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="920ea-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="920ea-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="920ea-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="920ea-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="920ea-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="920ea-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="920ea-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="920ea-159">ContactCardMenu</span><span class="sxs-lookup"><span data-stu-id="920ea-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="920ea-160">Si no se define ExtensibleMenu, se utilizan los valores predeterminados de MainWindowRightClick y ConversationWindowActions.</span><span class="sxs-lookup"><span data-stu-id="920ea-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="920ea-161">Por ejemplo, en el archivo de Editor del Registro (.REG) siguiente se muestran los resultados obtenidos al agregar un elemento de menú del Administrador de contactos de Contoso Sales al menú Acciones en la ventana Conversación:</span><span class="sxs-lookup"><span data-stu-id="920ea-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

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

## <a name="to-access-a-custom-command"></a><span data-ttu-id="920ea-162">Para obtener acceso a un comando personalizado</span><span class="sxs-lookup"><span data-stu-id="920ea-162">To access a custom command</span></span>

<span data-ttu-id="920ea-163">Para obtener acceso a un comando personalizado después de que se haya agregado, siga uno de estos procedimientos, según los valores de ExtensibleMenu que defina:</span><span class="sxs-lookup"><span data-stu-id="920ea-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="920ea-164">**MainWindowActions**   en la ventana principal de Lync, haga clic en **herramientas**y, a continuación, haga clic en el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="920ea-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="920ea-165">**MainWindowRightClick**   en la ventana principal de Lync, haga clic con el botón secundario en un contacto y, a continuación, haga clic en el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="920ea-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="920ea-166">**ConversationWindowActions**   en la ventana conversación, haga clic en el icono **más opciones** y, a continuación, haga clic en el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="920ea-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="920ea-167">**ConversationWindowRightClick**   en la ventana conversación, haga clic con el botón secundario en el nombre de un contacto y, a continuación, haga clic en el comando personalizado.</span><span class="sxs-lookup"><span data-stu-id="920ea-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

