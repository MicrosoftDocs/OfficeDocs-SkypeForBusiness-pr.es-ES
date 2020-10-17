---
title: Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados
description: Habilitar o deshabilitar el envío de una declinación de responsabilidades de archivado a socios federados.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1523a19bc2758e170c044a306398bef45ec33f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563516"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a><span data-ttu-id="f08e6-103">Habilitar o deshabilitar el envío de una declinación de responsabilidades de archivado a socios federados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f08e6-103">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f08e6-104">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f08e6-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f08e6-p101">En el momento en que implementa los servidores perimetrales y habilita la federación para la organización, debe especificar si desea enviar de forma automática la notificación de renuncia de archivado a los socios federados. Si archiva las comunicaciones externas, debe habilitar el envío de notificaciones de renuncia de archivado. Para cambiar esa configuración, siga el procedimiento de este tema.</span><span class="sxs-lookup"><span data-stu-id="f08e6-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners. If you archive external communications, you should enable the sending of an archiving disclaimer. Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f08e6-108">En el procedimiento siguiente, se presupone que ya ha habilitado la federación para la organización.</span><span class="sxs-lookup"><span data-stu-id="f08e6-108">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="f08e6-109">Para obtener más información sobre cómo habilitar la Federación, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="f08e6-109">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="f08e6-110">Para habilitar o deshabilitar el envío de una renuncia de archivado a socios federados:</span><span class="sxs-lookup"><span data-stu-id="f08e6-110">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="f08e6-111">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f08e6-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f08e6-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f08e6-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f08e6-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f08e6-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f08e6-114">En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="f08e6-114">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="f08e6-115">En la pestaña **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="f08e6-115">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f08e6-116">En **Editar configuración perimetral de acceso**, vaya a **Habilitar comunicaciones con usuarios federados** y active o desactive la casilla **Enviar notificación de renuncia de archivado a los socios federados** para habilitar o deshabilitar el envío automático de notificaciones de renuncia de archivado.</span><span class="sxs-lookup"><span data-stu-id="f08e6-116">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="f08e6-117">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f08e6-117">Click **Commit**.</span></span>

<span data-ttu-id="f08e6-118">Para permitir que los usuarios federados colaboren con los usuarios de su implementación de Lync Server 2013, también debe haber configurado al menos una directiva de acceso externo para admitir el acceso de usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="f08e6-118">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="f08e6-119">Para obtener más información, vea [Manage XMPP Federated Partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="f08e6-119">For details, see [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="f08e6-120">Para obtener información detallada sobre cómo controlar el acceso a dominios federados específicos, vea [Configure Support for external external Domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) en la documentación de implementación o de operaciones.</span><span class="sxs-lookup"><span data-stu-id="f08e6-120">For details about controlling access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f08e6-121">Habilitación o deshabilitación de la declinación de responsabilidades de archivado mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f08e6-121">Enabling or Disabling the Archiving Disclaimer by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f08e6-122">El uso de la declinación de responsabilidades de archivado se puede administrar con Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f08e6-122">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="f08e6-123">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f08e6-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f08e6-124">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="f08e6-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="f08e6-125">Para habilitar la renuncia de archivado</span><span class="sxs-lookup"><span data-stu-id="f08e6-125">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="f08e6-126">Para habilitar la renuncia de archivado, establezca la propiedad **EnableArchivingDisclaimer** en True ($True):</span><span class="sxs-lookup"><span data-stu-id="f08e6-126">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="f08e6-127">Para deshabilitar la renuncia de archivado</span><span class="sxs-lookup"><span data-stu-id="f08e6-127">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="f08e6-128">Para deshabilitar la renuncia de archivado, establezca la propiedad **EnableArchivingDisclaimer** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="f08e6-128">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

