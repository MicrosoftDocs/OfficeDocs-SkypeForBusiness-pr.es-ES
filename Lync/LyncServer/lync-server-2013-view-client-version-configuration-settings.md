---
title: 'Lync Server 2013: ver la configuración de la versión de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9db03377f8f2fc880de61639f4eedc5b1c302d21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1a4f0-102">Ver la configuración de la versión del cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a4f0-102">View client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a4f0-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1a4f0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1a4f0-104">Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="1a4f0-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="1a4f0-105">La configuración de la versión de cliente global se instala con Lync Server 2013 y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor.</span><span class="sxs-lookup"><span data-stu-id="1a4f0-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="1a4f0-106">Si la configuración Global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="1a4f0-106">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="1a4f0-107">Puede ver la configuración de la versión del cliente en el panel de control de Lync Server 2013 o en el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a4f0-107">You can view client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a4f0-108">Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.</span><span class="sxs-lookup"><span data-stu-id="1a4f0-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="1a4f0-109">Para ver la configuración de la versión de cliente con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="1a4f0-109">To view client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1a4f0-110">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1a4f0-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a4f0-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a4f0-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1a4f0-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1a4f0-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1a4f0-113">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **configuración de versión de cliente** .</span><span class="sxs-lookup"><span data-stu-id="1a4f0-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="1a4f0-114">Haga doble clic en el nombre de la configuración de la versión del cliente que desea ver.</span><span class="sxs-lookup"><span data-stu-id="1a4f0-114">Double-click the name of the client version configuration you want to view.</span></span>

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1a4f0-115">Ver la configuración de la versión de cliente mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a4f0-115">Viewing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1a4f0-116">Puede ver la configuración de la versión de cliente con el cmdlet **Get-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1a4f0-116">You can view client version configuration settings by using the **Get-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="1a4f0-117">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a4f0-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1a4f0-118">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="1a4f0-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-configuration-information"></a><span data-ttu-id="1a4f0-119">Para ver la información de configuración de la versión del cliente</span><span class="sxs-lookup"><span data-stu-id="1a4f0-119">To view client version configuration information</span></span>

  - <span data-ttu-id="1a4f0-120">Para ver información sobre toda la configuración de la versión de cliente, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="1a4f0-120">To view information about all your client version configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionConfiguration
    
    <span data-ttu-id="1a4f0-121">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a4f0-121">That will return information similar to this:</span></span>
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

<span data-ttu-id="1a4f0-122">Para obtener más información, vea el tema de ayuda sobre el cmdlet [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="1a4f0-122">For details, see the Help topic for the [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

