---
title: 'Lync Server 2013: Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública'
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
ms.openlocfilehash: edbf03ee2e2772e6df1425ffd666176c1947f0e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-06-24_

La compatibilidad con la Federación es necesaria para habilitar a los usuarios que tienen una cuenta con un cliente de confianza o una organización asociada, incluidos los dominios y usuarios de los proveedores de mensajería instantánea (mi) pública a los que usted proporciona soporte técnico, para colaborar con los usuarios de su Organización. La Federación también es necesaria para usar un proveedor de servicios de Exchange hospedado para proporcionar correo de voz a usuarios de voz de empresa cuyos buzones se encuentran en un servicio de Exchange hospedado como Microsoft Exchange Online. Una vez que haya establecido una relación de confianza con estos dominios externos, puede autorizar a los usuarios de esos dominios a que tengan acceso a su implementación y participen en las comunicaciones de Lync Server. Esta relación de confianza se denomina Federación y no está relacionada con una relación de confianza de Active Directory o no depende de ella.

Para admitir el acceso de usuarios de dominios federados, debe habilitar la Federación. Si habilita la Federación de su organización, también debe especificar si desea implementar las siguientes opciones:

  - **Habilitar detección**   de dominios asociados si habilita esta opción, Lync Server usará los registros del sistema de nombres de dominio (DNS) para intentar descubrir dominios no incluidos en la lista de dominios permitidos, evaluar automáticamente el tráfico entrante de socios federados descubiertos y limitar o bloquear ese tráfico en función del nivel de confianza, la cantidad de tráfico y la configuración del administrador. Si no selecciona esta opción, acceso de usuarios federados solo se habilitará para los usuarios de los dominios que incluya en la lista de dominios permitidos. Independientemente de si selecciona esta opción, puede especificar que los dominios individuales se bloqueen o se permitan, incluido el acceso restringido a servidores específicos que ejecuten el servicio perimetral de acceso en el dominio federado. Para obtener más información sobre cómo controlar el acceso por parte de los dominios federados, consulte [configurar la compatibilidad de dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).

  - **Enviar una renuncia de archivado a los socios**     federados el aviso de declinación de responsabilidades se envía a los socios federados que el archivado de la implementación está en su lugar. Si admite el archivado de comunicaciones externas con dominios federados, debe habilitar la notificación de renuncia de archivado para avisar a los socios de que sus mensajes se han archivado.

Si posteriormente desea impedir de forma temporal o permanente el acceso de los usuarios de dominios federados, puede deshabilitar la Federación de su organización. Use el procedimiento de esta sección para habilitar o deshabilitar el acceso de usuarios federados de su organización, incluyendo la especificación de las opciones de Federación adecuadas para que la organización admita.

<div>


> [!NOTE]  
> Habilitar la Federación para la organización solo especifica que los servidores que ejecutan el servicio perimetral de acceso admiten el enrutamiento a dominios federados. Los usuarios de dominios federados no pueden participar en conversaciones o conferencias de su organización hasta que también configure al menos una directiva para admitir el acceso de usuarios federados. Los usuarios de proveedores de servicios de mensajería instantánea pública no pueden participar en mensajes instantáneos o conferencias de su organización hasta que también configure al menos una directiva para que admita la conectividad de mensajería instantánea pública. Lync Server no puede usar un servicio de Exchange hospedado para proporcionar contestador automático, Outlook Voice Access (incluido el correo de voz) o servicios de operador automático para usuarios cuyos buzones se encuentran en un servicio de Exchange hospedado hasta que se configure una directiva de correo de voz hospedado que proporciona información de enrutamiento. Para obtener más información sobre cómo configurar directivas para la comunicación con usuarios de dominios federados en otras organizaciones, consulte <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">administrar dominios federados SIP para su organización en Lync Server 2013</A> en la documentación de operaciones. Además, si desea admitir la comunicación con usuarios de proveedores de servicios de mensajería instantánea, debe configurar directivas para admitirlo y también configurar la compatibilidad de los proveedores de servicios individuales que desee admitir. Para obtener más información, vea <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">administrar proveedores federados SIP para su organización en Lync Server 2013</A> en la documentación de operaciones. Para obtener detalles sobre la creación de una directiva de correo de voz hospedada, vea <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Administrar directivas de correo de voz hospedado en Lync Server 2013</A> en la documentación de implementación.



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Para habilitar o deshabilitar el acceso de usuarios federados para su organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**y, después, en **configuración del borde de Access**.

4.  En la página **configuración de perímetro de Access** , haga clic en **global**, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En **Editar configuración del límite de acceso**, realice una de las siguientes acciones:
    
      - Para habilitar el acceso de usuarios federados para su organización, active la casilla **Habilitar comunicaciones con usuarios federados** .
    
      - Para deshabilitar el acceso de usuarios federados para su organización, desactive la casilla **Habilitar comunicaciones con usuarios federados** .

6.  Si seleccionó la casilla **Habilitar comunicaciones con usuarios federados** , haga lo siguiente:
    
    1.  Si desea admitir el descubrimiento automático de dominios asociados, active la casilla de verificación **Habilitar la detección de dominios asociados** .
    
    2.  Si su organización admite el archivado de comunicaciones externas, active la casilla de verificación **Enviar renuncia de archivado a socios federados** .

7.  Haga clic en **Confirmar**.

Para permitir que los usuarios federados colaboren con los usuarios de su implementación de Lync Server 2013, también debe configurar al menos una directiva de acceso externa para admitir el acceso de usuarios federados. Para obtener más información, vea [configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) en la documentación de implementación o en la documentación de operaciones. Para controlar el acceso a dominios federados específicos, vea [configurar la compatibilidad de dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) en la documentación de implementación o de operaciones.

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública mediante cmdlets de Windows PowerShell

La Federación y la conectividad de mensajería instantánea pública también se pueden administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>Para habilitar la Federación y la conectividad de mensajería instantánea pública

  - Para habilitar la Federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>Para deshabilitar la Federación y la conectividad de mensajería instantánea pública

  - Para deshabilitar la Federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

