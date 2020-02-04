---
title: Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados
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
ms.openlocfilehash: 1f53e03ebfdc24ff969ff44a9b39149456ab3f16
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a><span data-ttu-id="9db27-102">Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9db27-102">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9db27-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9db27-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9db27-104">En el momento de implementar los servidores perimetrales y habilitar la Federación de su organización, debe haber especificado si se enviará automáticamente la renuncia de archivado a los socios federados.</span><span class="sxs-lookup"><span data-stu-id="9db27-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="9db27-105">Si archiva las comunicaciones externas, debe habilitar el envío de una renuncia de archivado.</span><span class="sxs-lookup"><span data-stu-id="9db27-105">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="9db27-106">Use el procedimiento de este tema para cambiar esa configuración.</span><span class="sxs-lookup"><span data-stu-id="9db27-106">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="9db27-107">En el procedimiento siguiente se supone que ya ha habilitado la Federación de su organización.</span><span class="sxs-lookup"><span data-stu-id="9db27-107">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="9db27-108">Para obtener más información sobre cómo habilitar la Federación, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="9db27-108">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="9db27-109">Para habilitar o deshabilitar el envío de una renuncia de archivado a socios federados</span><span class="sxs-lookup"><span data-stu-id="9db27-109">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="9db27-110">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9db27-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9db27-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9db27-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9db27-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9db27-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9db27-113">En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**, haga clic en **configuración del borde de Access**.</span><span class="sxs-lookup"><span data-stu-id="9db27-113">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="9db27-114">En la ficha **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="9db27-114">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9db27-115">En **Editar configuración del límite de acceso**, en **Habilitar la comunicación con usuarios federados**, Active o desactive la casilla **Enviar renuncia de archivado a socios federados** para habilitar o deshabilitar el envío automático de la renuncia de archivado.</span><span class="sxs-lookup"><span data-stu-id="9db27-115">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="9db27-116">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9db27-116">Click **Commit**.</span></span>

<span data-ttu-id="9db27-117">Para permitir a los usuarios federados colaborar con los usuarios de su implementación de Lync Server 2013, también debe haber configurado al menos una directiva de acceso externa para admitir el acceso de usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="9db27-117">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="9db27-118">Para obtener más información, vea [administrar los socios de XMPP federados en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="9db27-118">For details, see [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="9db27-119">Para obtener más información sobre cómo controlar el acceso a dominios federados específicos, vea [configurar la compatibilidad de dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) en la documentación de implementación o de operaciones.</span><span class="sxs-lookup"><span data-stu-id="9db27-119">For details about controlling access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9db27-120">Habilitar o deshabilitar la renuncia de archivado mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9db27-120">Enabling or Disabling the Archiving Disclaimer by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9db27-121">El uso de la renuncia de archivado se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9db27-121">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="9db27-122">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9db27-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9db27-123">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="9db27-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="9db27-124">Para habilitar la renuncia de archivado</span><span class="sxs-lookup"><span data-stu-id="9db27-124">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="9db27-125">Para habilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en True ($True):</span><span class="sxs-lookup"><span data-stu-id="9db27-125">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="9db27-126">Para deshabilitar la renuncia de archivado</span><span class="sxs-lookup"><span data-stu-id="9db27-126">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="9db27-127">Para deshabilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="9db27-127">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

