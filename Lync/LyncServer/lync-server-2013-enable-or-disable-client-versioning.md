---
title: 'Lync Server 2013: habilitar o deshabilitar el control de versiones de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d86fc41847485cbe797da9e9c9ace4a0a8794280
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="76d68-102">Habilitar o deshabilitar el control de versiones de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76d68-102">Enable or disable client versioning in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76d68-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="76d68-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="76d68-104">Las opciones de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente, ya sea de forma global o para determinados sitios.</span><span class="sxs-lookup"><span data-stu-id="76d68-104">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="76d68-105">La configuración de la versión de cliente global se instala con Lync Server 2013 y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor.</span><span class="sxs-lookup"><span data-stu-id="76d68-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="76d68-106">Cuando la configuración global está habilitada, las directivas de versión de cliente que haya implementado surtirán efecto cuando los usuarios intenten iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="76d68-106">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="76d68-107">Puede deshabilitar la configuración de versión de cliente global si no desea que se produzca ningún control de versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="76d68-107">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="76d68-108">Puede habilitar o deshabilitar el control de versiones de cliente desde el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="76d68-108">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76d68-109">Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.</span><span class="sxs-lookup"><span data-stu-id="76d68-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="76d68-110">Para habilitar o deshabilitar el control de versiones de cliente mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="76d68-110">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="76d68-111">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="76d68-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="76d68-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="76d68-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="76d68-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="76d68-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="76d68-114">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación **configuración de versión de cliente** .</span><span class="sxs-lookup"><span data-stu-id="76d68-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="76d68-115">Haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="76d68-115">Do the following:</span></span>
    
      - <span data-ttu-id="76d68-116">Para habilitar o deshabilitar de forma global el control de versiones de cliente, haga doble clic en la configuración **global** y, a continuación, modifique la configuración.</span><span class="sxs-lookup"><span data-stu-id="76d68-116">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="76d68-117">Para habilitar o deshabilitar el control de versiones de cliente para un sitio en particular, haga clic en **nuevo**, seleccione el sitio, haga clic en **Aceptar**y, a continuación, modifique la configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="76d68-117">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="76d68-118">Habilitación o deshabilitación del control de versiones de cliente mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="76d68-118">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="76d68-119">Puede habilitar o deshabilitar el control de versiones de cliente mediante el cmdlet **set-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="76d68-119">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="76d68-120">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76d68-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="76d68-121">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="76d68-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="76d68-122">Para habilitar el control de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="76d68-122">To enable client versioning</span></span>

  - <span data-ttu-id="76d68-123">Puede habilitar el control de versiones del cliente estableciendo la propiedad **Enabled** en True ($true).</span><span class="sxs-lookup"><span data-stu-id="76d68-123">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="76d68-124">Para deshabilitar el control de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="76d68-124">To disable client versioning</span></span>

  - <span data-ttu-id="76d68-125">Puede deshabilitar el control de versiones del cliente estableciendo la propiedad **Enabled** en False ($false).</span><span class="sxs-lookup"><span data-stu-id="76d68-125">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="76d68-126">Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="76d68-126">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

