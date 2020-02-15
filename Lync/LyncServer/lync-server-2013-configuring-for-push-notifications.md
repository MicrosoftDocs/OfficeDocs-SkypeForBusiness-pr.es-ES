---
title: 'Lync Server 2013: configuración de notificaciones de inserción'
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
ms.openlocfilehash: f92ae27b919df6a32f06921df97746680a68b030
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Configuración de notificaciones de inserción en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-12_

Las notificaciones de inserción, en la forma de distintivos, iconos o alertas, se pueden enviar a un dispositivo móvil aunque la aplicación móvil se encuentre inactiva. Las notificaciones de inserción notifican a un usuario eventos como correo de voz o invitaciones de mensajería instantánea nuevas o perdidas. El servicio de movilidad Lync Server 2013 envía las notificaciones al servicio de notificación de inserción de Lync Server basado en la nube, que a su vez envía las notificaciones al servicio de notificación de inserción de Apple (APNS) (para un dispositivo Apple que ejecuta el cliente móvil de Lync 2010) o el Servicio de notificaciones de inserción de Microsoft (MPNS) (para un dispositivo de Windows Phone que ejecuta Lync 2010 Mobile o Lync 2013 Mobile Client).

<div>


> [!IMPORTANT]  
> Si usa Windows Phone con Lync 2010 Mobile o Lync 2013 Mobile Client, la notificación de inserción es una consideración importante.<BR>Si usa Lync 2010 Mobile en dispositivos Apple, la notificación de inserción es una consideración importante.<BR>Si usa Lync 2013 Mobile en dispositivos Apple, ya no necesitará notificaciones de inserción.



</div>

Configure su topología para admitir las notificaciones de inserción mediante el siguiente procedimiento:

  - Si su entorno tiene un servidor perimetral de Lync Server 2010 o Lync Server 2013, debe agregar un nuevo proveedor de hospedaje, Microsoft Lync Online y, a continuación, configurar la Federación del proveedor de hospedaje entre su organización y Lync Online.

  - Si su entorno tiene un servidor perimetral de Office Communications Server 2007 R2, debe configurar la Federación SIP directa con push.lync.com.
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com es un dominio de Microsoft Office 365 para el servicio de notificación de inserción.

    
    </div>

  - Para habilitar las notificaciones de inserción, debe ejecutar el cmdlet **Set-CsPushNotificationConfiguration**. De manera predeterminada, las notificaciones de inserción están desactivadas.

  - Pruebe la configuración de federación y las notificaciones de inserción.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>Para configurar notificaciones de inserción con Lync Server 2013 o el servidor perimetral de Lync Server 2010

1.  Inicie sesión en un equipo en el que esté instalado shell de administración de Lync Server y Ocscore como miembro del grupo RtcUniversalServerAdmins.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Agregue un proveedor de hospedaje de Lync Server online. En la línea de comandos, escriba lo siguiente:
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Por ejemplo:
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > No puede tener más de una relación de federación con un solo proveedor de hospedaje. Es decir, si ya ha configurado un proveedor de hospedaje que tiene una relación de federación con sipfed.online.lync.com, no agregue otro proveedor de hospedaje para él, aunque la identidad del proveedor de hospedaje no sea LyncOnline.

    
    </div>

4.  Configure la federación del proveedor de hospedaje entre su organización y el servicio de notificación de inserción en Lync Online. En la línea de comandos, escriba:
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>Para configurar notificaciones de inserción con el servidor perimetral de Office Communications Server 2007 R2

1.  Inicie sesión en el servidor perimetral como miembro del grupo RtcUniversalServerAdmins.

2.  Haga clic en **Iniciar**, en **Todos los programas**, en **Herramientas administrativas** y, a continuación, en **Administración del equipo**.

3.  En el árbol de la consola, expanda **Servicios y aplicaciones**, haga clic con el botón secundario en **Microsoft Office Communications Server 2007 R2** y, a continuación, haga clic en **Propiedades**.

4.  En la pestaña **Permitir**, haga clic en **Agregar**.

5.  En el cuadro de diálogo **Agregar socio federado**, realice el siguiente procedimiento:
    
      - En **Nombre de dominio del socio federado**, escriba **push.lync.com**.
    
      - En **Servidor perimetral de acceso al socio federado**, escriba **sipfed.online.lync.com**.
    
      - Haga clic en **Aceptar**.

</div>

<div>

## <a name="to-enable-push-notifications"></a>Para habilitar notificaciones de inserción

1.  Inicie sesión en un equipo en el que se instalen Shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Habilite las notificaciones de inserción. En la línea de comandos, escriba:
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Habilite la federación. En la línea de comandos, escriba:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>Para probar la federación y las notificaciones de inserción

1.  Inicie sesión en un equipo en el que se instalen Shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Pruebe la configuración de la federación. En la línea de comandos, escriba:
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Por ejemplo:
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Pruebe las notificaciones de inserción. En la línea de comandos, escriba:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Por ejemplo:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>Vea también


[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

