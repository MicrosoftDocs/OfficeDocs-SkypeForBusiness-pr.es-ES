---
title: 'Lync Server 2013: habilitar o deshabilitar la detección de socios de Federación'
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
ms.openlocfilehash: 3e6fd924d4aef6a9a6657829fa225da9595f52fe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>Habilitar o deshabilitar la detección de socios de Federación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

En el momento en que implementa los servidores perimetrales y habilita la federación para la organización, debe especificar si se va a admitir la detección automática de los dominios de socios federados. Para cambiar esa configuración, siga el procedimiento de este tema.

<div>


> [!NOTE]  
> En el procedimiento siguiente, se presupone que ya ha habilitado la federación para la organización. Para obtener más información sobre cómo habilitar la Federación, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de implementación o en la documentación de operaciones.



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Para habilitar o deshabilitar la detección automática de dominios federados para la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, en **Habilitar comunicaciones con usuarios federados**, active o desactive la casilla **Habilitar detección de dominio de socio** para habilitar o deshabilitar la detección automática de dominios de socios.

6.  Haga clic en **Confirmar**.

Para permitir que los usuarios federados colaboren con los usuarios de su implementación de Lync Server, también debe haber configurado al menos una directiva de acceso externo para admitir el acceso de usuarios federados. Para obtener más información, consulte [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) en la documentación de implementación o en la documentación de operaciones. Para obtener información detallada sobre cómo controlar el acceso a dominios federados específicos, consulte [Manage SIP Federated Domains for your Organization in Lync server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) Federated Servers for your organization in Lync Server 2013 y [Manage XMPP federated Partners en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) en la documentación de operaciones.

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la detección de socios de Federación mediante cmdlets de Windows PowerShell

La detección de socios de Federación se puede administrar con Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>Para habilitar la detección de socios de Federación

  - Para habilitar la detección de socios federados, establezca el valor de la propiedad **EnablePartnerDiscovery** en True ($True). Tenga en cuenta que debe habilitar el enrutamiento SRV de DNS para poder cambiar el valor de esta propiedad.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>Para deshabilitar la detección de socios de Federación

  - Para deshabilitar la detección de socios federados, establezca el valor de la propiedad **EnablePartnerDiscovery** en False ($False).
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

