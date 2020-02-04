---
title: 'Lync Server 2013: Habilitar o deshabilitar la detección de socios de federación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f97a6ab26a3b8b3f011a62cd92bbd0271f781a1a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

En el momento de implementar los servidores perimetrales y de habilitar la Federación de su organización, debe haber especificado si se debe admitir la detección automática de dominios federados de socios. Use el procedimiento de este tema para cambiar esa configuración.

<div>


> [!NOTE]  
> En el procedimiento siguiente se supone que ya ha habilitado la Federación de su organización. Para obtener más información sobre cómo habilitar la Federación, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de implementación o en la documentación de operaciones.



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Para habilitar o deshabilitar la detección automática de dominios federados para su organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**, haga clic en **configuración del borde de Access**.

4.  En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración del límite de acceso**, en **habilitar las comunicaciones con usuarios federados**, Active o desactive la casilla **Habilitar la detección** de dominios asociados para habilitar o deshabilitar la detección automática de dominios asociados.

6.  Haga clic en **Confirmar**.

Para permitir que los usuarios federados colaboren con los usuarios de su implementación de Lync Server, también debe haber configurado al menos una directiva de acceso externa para admitir el acceso de usuarios federados. Para obtener más información, vea [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) en la documentación de implementación o en la documentación de operaciones. Para más información sobre cómo controlar el acceso a dominios federados específicos, consulte [administrar dominios federados SIP para su organización en Lync server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [administrar proveedores federados SIP para su organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) y [administrar XMPP federados socios en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) en la documentación de operaciones.

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la detección de socios de Federación mediante cmdlets de Windows PowerShell

El descubrimiento de los socios de la Federación se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>Para habilitar la detección de socios de Federación

  - Para habilitar la detección de socios de Federación, establezca el valor de la propiedad **EnablePartnerDiscovery** en True ($true). Tenga en cuenta que debe habilitar el enrutamiento SRV de DNS para poder cambiar este valor de propiedad.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>Para deshabilitar la detección de socios de Federación

  - Para deshabilitar la detección de socios de Federación, establezca el valor de la propiedad **EnablePartnerDiscovery** en False ($false):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

