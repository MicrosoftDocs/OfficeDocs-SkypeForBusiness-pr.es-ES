---
title: Eliminar una colección existente de valores de configuración de reuniones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96fe774830a8efc6f0cc88a2dd929b3126335b51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5bd8f-102">Eliminar una colección existente de opciones de configuración de reuniones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd8f-102">Delete an existing collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bd8f-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5bd8f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5bd8f-104">Puede eliminar un sitio o una configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="5bd8f-104">You can delete a site or user configuration.</span></span> <span data-ttu-id="5bd8f-105">No se puede quitar la configuración global.</span><span class="sxs-lookup"><span data-stu-id="5bd8f-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="5bd8f-106">Si elimina la configuración global, esta se restablece automáticamente a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5bd8f-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a><span data-ttu-id="5bd8f-107">Para eliminar un sitio o una configuración de reunión de usuario</span><span class="sxs-lookup"><span data-stu-id="5bd8f-107">To delete a site or user meeting configuration</span></span>

1.  <span data-ttu-id="5bd8f-108">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5bd8f-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5bd8f-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5bd8f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5bd8f-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5bd8f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5bd8f-111">En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="5bd8f-111">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="5bd8f-112">En la lista de configuraciones de reunión, haga clic en la configuración de sitio o de grupo que desea eliminar, haga clic en **Editar** y después en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5bd8f-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5bd8f-113">Quitar la configuración de la reunión mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bd8f-113">Removing Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5bd8f-114">La configuración de la reunión se puede eliminar con Windows PowerShell y el cmdlet Remove-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5bd8f-114">Meeting settings can be deleted by using Windows PowerShell and the Remove-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="5bd8f-115">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5bd8f-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5bd8f-116">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="5bd8f-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a><span data-ttu-id="5bd8f-117">Para quitar una colección especificada de valores de configuración de reuniones</span><span class="sxs-lookup"><span data-stu-id="5bd8f-117">To remove a specified collection of meeting configuration settings</span></span>

  - <span data-ttu-id="5bd8f-118">Este comando quita la configuración de la reunión aplicada al sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="5bd8f-118">This command removes the meeting configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="5bd8f-119">Para quitar todas las opciones de configuración de reunión aplicadas al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="5bd8f-119">To remove all the meeting configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="5bd8f-120">Este comando quita todas las opciones de configuración de reunión aplicadas al ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="5bd8f-120">This command removes all the meeting configuration settings applied to the site scope:</span></span>
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a><span data-ttu-id="5bd8f-121">Para quitar todas las opciones de configuración de la reunión que admiten usuarios anónimos de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="5bd8f-121">To remove all the meeting configuration settings that admit anonymous users by default</span></span>

  - <span data-ttu-id="5bd8f-122">Esta opción quita todas las opciones de configuración que permiten a los usuarios anónimos ser admitidos de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="5bd8f-122">And this one removes all the settings that allow anonymous users to be admitted by default:</span></span>
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

<span data-ttu-id="5bd8f-123">Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="5bd8f-123">For more information, see the help topic for the [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

