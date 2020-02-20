---
title: Modificar la acción predeterminada para clientes no admitidos explícitamente o restringidos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b33cdb0b2055c76d5a3fbfa1db893a1267318e8a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="a2f32-102">Modificar la acción predeterminada para clientes no admitidos explícitamente o restringidos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2f32-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2f32-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a2f32-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a2f32-104">Además de especificar la versión de clientes que desea admitir en su entorno de Lync Server 2013, también puede especificar una acción predeterminada para clientes que todavía no tienen definida una directiva de versión.</span><span class="sxs-lookup"><span data-stu-id="a2f32-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="a2f32-105">Esto le permite restringir las versiones de cliente que se usan en su entorno de Lync Server, lo que puede ayudarle a controlar los costos asociados con la compatibilidad con varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="a2f32-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="a2f32-106">Para modificar la acción predeterminada para clientes que no se admiten explícitamente o que están restringidos</span><span class="sxs-lookup"><span data-stu-id="a2f32-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="a2f32-107">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="a2f32-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a2f32-108">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a2f32-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a2f32-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a2f32-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a2f32-110">En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Configuración de versiones de cliente**.</span><span class="sxs-lookup"><span data-stu-id="a2f32-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="a2f32-111">En la página **Configuración de versiones de cliente**, haga doble clic en la configuración **Global** en la lista.</span><span class="sxs-lookup"><span data-stu-id="a2f32-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="a2f32-112">En el cuadro de diálogo **Editar configuración de versiones de cliente**, compruebe que la casilla **Habilitar control de versiones** esté activada y, a continuación, en **Acción predeterminada**, seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a2f32-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="a2f32-113">**Permitir**   permite que el cliente inicie sesión si la versión de cliente no coincide con ningún filtro de la lista **directivas de versiones de cliente** .</span><span class="sxs-lookup"><span data-stu-id="a2f32-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="a2f32-114">**Bloquear**   impide que el cliente inicie sesión si la versión de cliente no coincide con ningún filtro de la lista de **directivas de versión de cliente** .</span><span class="sxs-lookup"><span data-stu-id="a2f32-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="a2f32-115">**Bloquear con dirección URL**   impide que el cliente inicie sesión si la versión de cliente no coincide con ningún filtro de la lista **directivas de versiones de cliente** e incluye un mensaje de error con una dirección URL en la que se puede descargar un cliente más reciente.</span><span class="sxs-lookup"><span data-stu-id="a2f32-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="a2f32-116">**Permitir con dirección URL**   permite que el cliente inicie sesión si la versión de cliente no coincide con ningún filtro de la lista **directivas de versiones de cliente** e incluye un mensaje de error con una dirección URL en la que se puede descargar un cliente más reciente.</span><span class="sxs-lookup"><span data-stu-id="a2f32-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="a2f32-117">Si selecciona **Bloquear con dirección URL**, escriba en el cuadro **URL** la dirección URL de descarga del cliente que debe incluirse en el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="a2f32-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="a2f32-118">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a2f32-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="a2f32-119">Para deshabilitar el control de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="a2f32-119">To disable client version control</span></span>

  - <span data-ttu-id="a2f32-120">Para deshabilitar el control de versiones para permitir que todos los clientes inicien sesión independientemente de la versión de cliente, desactive la casilla **Habilitar control de versiones** y haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a2f32-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a2f32-121">Modificación de la acción predeterminada mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2f32-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a2f32-122">La acción predeterminada que se realizará cuando los usuarios intenten iniciar sesión mediante clientes que no son explícitamente compatibles o restringidos por una directiva de versión de cliente se pueden administrar mediante la interfaz de línea de comandos de Windows PowerShell y el cmdlet **set-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="a2f32-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="a2f32-123">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2f32-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a2f32-124">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="a2f32-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="a2f32-125">Para configurar la acción predeterminada para bloquear el acceso</span><span class="sxs-lookup"><span data-stu-id="a2f32-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="a2f32-p104">El siguiente comando establece la acción predeterminada Bloquear para el sitio Redmond. Esto bloqueará el registro de aquellos clientes para los que no exista ninguna regla de configuración de la versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="a2f32-p104">The following command sets the default action for the Redmond site Block. This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="a2f32-128">Para configurar la acción predeterminada para permitir el acceso</span><span class="sxs-lookup"><span data-stu-id="a2f32-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="a2f32-p105">En este ejemplo, la acción predeterminada para el sitio Redmond se establece en Permitir. Esto permitirá el registro de aquellos clientes para los que no exista ninguna regla de configuración de la versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="a2f32-p105">In this example, the default action for the Redmond site is set to Allow. This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="a2f32-131">Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="a2f32-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a2f32-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2f32-132">See Also</span></span>


[<span data-ttu-id="a2f32-133">Administración de dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2f32-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

