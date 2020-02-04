---
title: 'Lync Server 2013: Configurar las notificaciones de inserción'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c34b49d6c968effa46005a01df286d14fcff394c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Configurar las notificaciones de inserción en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-12_

Las notificaciones push, en forma de insignias, iconos o alertas, se pueden enviar a un dispositivo móvil incluso cuando la aplicación móvil no está activa. Las notificaciones push notifican a un usuario de eventos como una invitación o un correo de voz nuevos o perdidos. El servicio de movilidad de Lync Server 2013 envía las notificaciones al servicio de notificaciones de inserción de Lync Server basado en la nube, que después envía las notificaciones al servicio de notificaciones push de Apple (APN) (para dispositivos Apple que ejecutan el cliente móvil de Lync 2010) o el Servicio de notificaciones push de Microsoft (MPNS) (para un dispositivo Windows Phone que ejecuta Lync 2010 Mobile o el cliente móvil Lync 2013).

<div>


> [!IMPORTANT]  
> Si usa Windows Phone con Lync 2010 Mobile o Lync 2013 Mobile Client, la notificación push es una consideración importante.<BR>Si usa Lync 2010 Mobile en dispositivos Apple, la notificación push es una consideración importante.<BR>Si usa Lync 2013 Mobile en dispositivos Apple, ya no necesita notificaciones Push.



</div>

Configure su topología para que admita las notificaciones de inserción de la siguiente manera:

  - Si su entorno tiene un servidor perimetral de Lync Server 2010 o de Lync Server 2013, necesita agregar un nuevo proveedor de hospedaje, Microsoft Lync Online y, a continuación, configurar la Federación de proveedores de hospedaje entre su organización y Lync Online.

  - Si su entorno tiene un servidor perimetral de Office Communications Server 2007 R2, necesita configurar la Federación SIP directa con push.lync.com.
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com es un dominio de Microsoft Office 365 para el servicio de notificaciones de inserción.

    
    </div>

  - Para habilitar las notificaciones de inserción, debe ejecutar el cmdlet **set-CsPushNotificationConfiguration** . De manera predeterminada, las notificaciones de inserción están desactivadas.

  - Pruebe la configuración de Federación y las notificaciones de inserción.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>Para configurar las notificaciones de inserción con Lync Server 2013 o el servidor perimetral de Lync Server 2010

1.  Inicie sesión en un equipo en el que el shell de administración de Lync Server y Ocscore estén instalados como miembro del grupo RtcUniversalServerAdmins.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Agregue un proveedor de hospedaje de Lync Server online. En la línea de comandos, escriba lo siguiente:
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Por ejemplo:
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > No puede tener más de una relación de Federación con un solo proveedor de hospedaje. Es decir, si ya ha configurado un proveedor de hospedaje que tiene una relación de Federación con sipfed.online.lync.com, no agregue otro proveedor de hospedaje para él, incluso si la identidad del proveedor de hospedaje es distinta de LyncOnline.

    
    </div>

4.  Configure la Federación de proveedores de hospedaje entre su organización y el servicio de notificaciones de inserción en Lync Online. En la línea de comandos, escriba:
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>Para configurar las notificaciones de inserción con el servidor perimetral de Office Communications Server 2007 R2

1.  Inicie sesión en el servidor perimetral como miembro del grupo RtcUniversalServerAdmins.

2.  Haga clic en **Inicio**, en **todos los programas**, en **herramientas administrativas**y, por último, en **Administración de equipos**.

3.  En el árbol de consola, expanda **servicios y aplicaciones**, haga clic con el botón secundario en **Microsoft Office Communications Server 2007 R2**y, a continuación, haga clic en **propiedades**.

4.  En la pestaña **permitir** , haga clic en **Agregar**.

5.  En el cuadro de diálogo **Agregar socio federado** , haga lo siguiente:
    
      - En **nombre de dominio del socio federado**, escriba **Push.Lync.com**.
    
      - En el **servidor perimetral de acceso del socio federado**, escriba **sipfed.online.Lync.com**.
    
      - Haga clic en **Aceptar**.

</div>

<div>

## <a name="to-enable-push-notifications"></a>Para habilitar las notificaciones de inserción

1.  Inicie sesión en un equipo en el que el shell de administración de Lync Server y Ocscore estén instalados como miembro del rol CsAdministrator.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Habilitar las notificaciones de inserción. En la línea de comandos, escriba:
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Habilitar la Federación. En la línea de comandos, escriba:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>Para probar la Federación y las notificaciones de inserción

1.  Inicie sesión en un equipo en el que el shell de administración de Lync Server y Ocscore estén instalados como miembro del rol CsAdministrator.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Pruebe la configuración de Federación. En la línea de comandos, escriba lo siguiente:
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Por ejemplo:
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Probar las notificaciones de inserción. En la línea de comandos, escriba lo siguiente:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Por ejemplo:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>Vea también


[Prueba-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

