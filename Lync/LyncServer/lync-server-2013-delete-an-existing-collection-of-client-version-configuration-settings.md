---
title: Eliminar una colección existente de parámetros de configuración de la versión de cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a71df7af1f0a6158cb61e780b44ed4227d32018
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b43fe-102">Eliminar una colección existente de parámetros de configuración de la versión de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b43fe-102">Delete an existing collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b43fe-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b43fe-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b43fe-104">Si desea quitar la configuración de cliente que se ha configurado previamente para un sitio, puede quitar la configuración del panel de control de Lync Server 2013 o del shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b43fe-104">If you want to remove the client configuration settings that have been previously configured for a site, you can remove the settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="b43fe-105">Para quitar los valores de configuración del cliente mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="b43fe-105">To remove client configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b43fe-106">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b43fe-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b43fe-107">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b43fe-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b43fe-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b43fe-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b43fe-109">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **configuración de versión de cliente** .</span><span class="sxs-lookup"><span data-stu-id="b43fe-109">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="b43fe-110">Seleccione el sitio, haga clic en **Editar**, haga clic en **eliminar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b43fe-110">Select the site, click **Edit**, click **Delete**, and then click **OK**.</span></span>

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b43fe-111">Quitar la configuración de la versión de cliente mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b43fe-111">Removing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b43fe-112">Puede eliminar la configuración de la versión del cliente mediante el cmdlet **Remove-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b43fe-112">You can delete client version configuration settings by using the **Remove-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="b43fe-113">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b43fe-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b43fe-114">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="b43fe-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a><span data-ttu-id="b43fe-115">Para quitar una colección especificada de parámetros de configuración de la versión de cliente</span><span class="sxs-lookup"><span data-stu-id="b43fe-115">To remove a specified collection of client version configuration settings</span></span>

  - <span data-ttu-id="b43fe-116">El siguiente comando quita la configuración de la versión del cliente que se aplica al sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="b43fe-116">The following command removes the client version configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="b43fe-117">Para quitar todas las opciones de configuración de la versión del cliente que se aplican al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="b43fe-117">To remove all the client version configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="b43fe-118">Este comando quita todas las opciones de configuración de la versión del cliente configuradas en el ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="b43fe-118">This command removes all the client version configuration settings configured at the site scope:</span></span>
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a><span data-ttu-id="b43fe-119">Para quitar toda la configuración de la versión de cliente basada en el valor de la propiedad DefaultAction</span><span class="sxs-lookup"><span data-stu-id="b43fe-119">To remove all the client version configuration settings based on the value of the DefaultAction property</span></span>

  - <span data-ttu-id="b43fe-120">Y este comando elimina toda la configuración de la versión de cliente en la que la acción predeterminada se ha establecido en "bloquear":</span><span class="sxs-lookup"><span data-stu-id="b43fe-120">And this command removes all the client version configuration settings where the default action has been set to "Block":</span></span>
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

<span data-ttu-id="b43fe-121">Para obtener más información, vea el tema de ayuda sobre el cmdlet [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="b43fe-121">For details, see the Help topic for the [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

