---
title: 'Lync Server 2013: habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c94b75aff1b79650adc846d3d761580e9429035d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526797"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-06-24_

Es obligatorio tener compatibilidad para la federación con el fin de que los usuarios que dispongan de una cuenta con un cliente de confianza o con una organización de un socio, incluso dominios y usuarios de proveedores de mensajería instantánea pública que usted admita, puedan colaborar con los usuarios de su organización. La federación también es necesaria para usar un proveedor de servicios hospedados de Exchange para proporcionar correo de voz a usuarios de Telefonía IP empresarial cuyos buzones de correo se ubican en un servicio hospedado de Exchange como Microsoft Exchange Online. Cuando haya establecido una relación de confianza con estos dominios externos, puede autorizar a los usuarios de esos dominios para que tengan acceso a la implementación y participen en las comunicaciones de Lync Server. Esta relación de confianza se denomina federación y no está relacionada ni depende de una relación de confianza con Active Directory.

Para admitir el acceso de usuarios de dominios federados, es preciso que habilite la federación. Si habilita la federación en su organización, deberá especificar también si se van a implementar las opciones siguientes:

  - **Habilitar detección**     de dominio de socio Si habilita esta opción, Lync Server usa registros del sistema de nombres de dominio (DNS) para intentar detectar dominios que no aparecen en la lista de dominios permitidos, evaluar automáticamente el tráfico entrante de socios federados detectados y limitar o bloquear ese tráfico en función del nivel de confianza, la cantidad de tráfico y la configuración del administrador. Si no selecciona esta opción, el acceso de usuarios federados se habilitará solamente para los usuarios en los dominios que haya incluido en la lista de dominios admitidos. Independientemente de si selecciona esta opción o no, podrá especificar que se bloqueen o permitan dominios individuales, incluso restringir el acceso de servidores específicos que se ejecuten en el servicio perimetral de acceso del dominio federado. Para obtener información detallada sobre cómo controlar el acceso por parte de los dominios federados, consulte [configurar la compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).

  - **Enviar una declinación de responsabilidades de archivado a socios federados**     Aviso de declinación de responsabilidades se envía a los socios federados que el archivado de la implementación está en su ubicación. Si admite el archivado de las comunicaciones externas con los dominios de socios federados, debe habilitar la notificación de declinación de responsabilidad para avisar a los socios que sus mensajes están siendo archivados.

Si más adelante desea impedir, de forma temporal o permanente, el acceso de usuarios de dominios federados, puede deshabilitar la para su organización. Use el procedimiento que aparece en esta sección para habilitar o deshabilitar el acceso de usuarios federados en su organización, así como para especificar las opciones de federación apropiadas para su organización.

<div>


> [!NOTE]  
> Si se habilita la federación para la organización solo se indica que los servidores que ejecutan el servicio perimetral de acceso admiten el enrutamiento a dominios federados. Los usuarios de dominios federados no pueden participar en la mensajería instantánea o conferencias en su organización hasta que configure asimismo al menos una directiva para admitir el acceso de usuarios federados. Los usuarios de proveedores de servicios de mensajería instantánea pública no podrán participar en la mensajería instantánea ni en conferencias de la organización hasta que configure también al menos una directiva para admitir conectividad de mensajería instantánea pública. Lync Server no puede usar un servicio hospedado de Exchange para proporcionar servicios de contestador automático, Outlook Voice Access (incluido el correo de voz) o servicios de operador automático para usuarios cuyos buzones de correo se ubican en un servicio hospedado de Exchange hasta que configure una directiva de correo de voz hospedada que proporcione información de enrutamiento. Para más información sobre cómo configurar directivas para comunicarse con usuarios de dominios federados en otras organizaciones, consulte <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP Federated Domains for your Organization in Lync Server 2013</A> en la documentación de operaciones. Por otra parte, si desea admitir la comunicación con usuarios de los proveedores de servicios de mensajería instantánea, es preciso que configure directivas para aportar tal compatibilidad, así como para aportar compatibilidad a los proveedores de servicios individuales que desee. Para obtener más información, consulte <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP Federated Providers for your Organization in Lync Server 2013</A> en la documentación de operaciones. Para obtener información detallada sobre cómo crear una directiva de correo de voz hospedado, consulte <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage host Voice Mail policies in Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios federados en la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:
    
      - Para habilitar el acceso de usuarios federados en la organización, active la casilla **Habilitar comunicaciones con usuarios federados**.
    
      - Para deshabilitar el acceso de usuarios federados en la organización, desactive la casilla **Habilitar comunicaciones con usuarios federados**.

6.  Si activó la casilla **Habilitar comunicaciones con usuarios federados**, haga lo siguiente:
    
    1.  Si desea admitir la detección automática de dominios de socios, active la casilla **Habilitar detección de dominio de socio**.
    
    2.  Si la organización admite el archivado de comunicaciones externas, active la casilla **Enviar declinación de responsabilidades de archivado a los socios federados**.

7.  Haga clic en **Confirmar**.

Para permitir que los usuarios federados colaboren con los usuarios de su implementación de Lync Server 2013, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios federados. Para obtener más información, vea [Configure Policies to control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) en la documentación de implementación o en la documentación de operaciones. Para controlar el acceso a dominios federados específicos, consulte [configurar la compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) en la documentación de implementación o de operaciones.

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública mediante cmdlets de Windows PowerShell

La Federación y la conectividad de mensajería instantánea pública también se pueden administrar con Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>Para habilitar la Federación y la conectividad de mensajería instantánea pública

  - Para habilitar la federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>Para deshabilitar la Federación y la conectividad de mensajería instantánea pública

  - Para deshabilitar la federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

