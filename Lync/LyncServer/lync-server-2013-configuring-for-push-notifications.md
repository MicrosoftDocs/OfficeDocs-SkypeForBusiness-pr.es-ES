---
title: 'Lync Server 2013: Configurar las notificaciones de inserción'
TOCTitle: Configurar las notificaciones de inserción
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48276835
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar las notificaciones de inserción en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-12_

Las notificaciones de inserción, en la forma de distintivos, iconos o alertas, se pueden enviar a un dispositivo móvil aunque la aplicación móvil esté inactiva. Las notificaciones de inserción informan a un usuario de eventos como una invitación de mensajería instantánea nueva o perdida y correo de voz. El servicio de movilidad de Lync Server 2013 envía notificaciones al servicio de notificación de inserción basado en la nube de Lync Server, que envía las notificaciones al servicio de notificación de inserción de Apple (APNS) (si se trata de un dispositivo Apple que ejecuta el cliente de Lync 2010 Mobile) o al servicio de notificación de inserción de Microsoft (MPNS) (si se trata de un dispositivo Windows Phone que ejecuta el Lync 2010 Mobile o el cliente móvil de Lync 2013).

> [!IMPORTANT]  
> Si se usa Windows Phone con Lync 2010 Mobile o con el cliente de Lync 2013 Mobile, hay que tener las notificaciones de inserción muy en cuenta.<br />
> Si se usa Lync 2010 Mobile en dispositivos Apple, hay que tener las notificaciones de inserción muy en cuenta.<br />
> Si se usa Lync 2013 Mobile en dispositivos Apple, las notificaciones de inserción ya no serán necesarias.


Configure su topología para admitir las notificaciones de inserción mediante el siguiente procedimiento:

  - Si su entorno tiene un Lync Server 2010 o Lync Server 2013Servidor perimetral, debe agregar un nuevo proveedor de hospedaje, Microsoft Lync Online, y, a continuación, configurar la federación de hospedaje entre su organización y Lync Online.

  - Si su entorno tiene un Office Communications Server 2007 R2Servidor perimetral, debe configurar la federación SIP directa con push.lync.com.
    

    > [!NOTE]
    > Push.lync.com es un dominio de Microsoft Office 365 para el servicio de notificación de inserción.



  - Para habilitar las notificaciones de inserción, debe ejecutar el cmdlet **Set-CsPushNotificationConfiguration**. De manera predeterminada, las notificaciones de inserción están desactivadas.

  - Pruebe la configuración de federación y las notificaciones de inserción.

## Para configurar notificaciones de inserción con Lync Server 2013 o el Servidor perimetral de Lync Server 2010

1.  Inicie sesión en un equipo que tenga instalado Shell de administración de Lync Server y Ocscore como miembro del grupo RtcUniversalServerAdmins.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Agregue un proveedor de hospedaje en línea de Lync Server. En la línea de comandos, escriba:
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Por ejemplo:
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    

    > [!NOTE]
    > No puede tener más de una relación de federación con un solo proveedor de hospedaje. Es decir, si ya ha configurado un proveedor de hospedaje que tiene una relación de federación con sipfed.online.lync.com, no agregue otro proveedor de hospedaje para él, aunque la identidad del proveedor de hospedaje no sea LyncOnline.



4.  Configure la federación del proveedor de hospedaje entre su organización y el servicio de notificación de inserción en Lync Online. En la línea de comandos, escriba:
    
        New-CsAllowedDomain -Identity "push.lync.com"

## Para configurar notificaciones de inserción con el Servidor perimetral de Office Communications Server 2007 R2

1.  Inicie sesión en el Servidor perimetral como miembro del grupo RtcUniversalServerAdmins.

2.  Haga clic en **Iniciar**, en **Todos los programas**, en **Herramientas administrativas** y, a continuación, en **Administración del equipo**.

3.  En el árbol de la consola, expanda **Servicios y aplicaciones**, haga clic con el botón secundario en **Microsoft Office Communications Server 2007 R2** y, a continuación, haga clic en **Propiedades**.

4.  En la pestaña **Permitir**, haga clic en **Agregar**.

5.  En el cuadro de diálogo **Agregar socio federado**, realice el siguiente procedimiento:
    
      - En **Nombre de dominio del socio federado**, escriba **push.lync.com**.
    
      - En **Servidor perimetral de acceso al socio federado**, escriba **sipfed.online.lync.com**.
    
      - Haga clic en **Aceptar**.

## Para habilitar notificaciones de inserción

1.  Inicie sesión en un equipo que tenga instalado Shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Habilite las notificaciones de inserción. En la línea de comandos, escriba:
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Habilite la federación. En la línea de comandos, escriba:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

## Para probar la federación y las notificaciones de inserción

1.  Inicie sesión en un equipo que tenga instalado Shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Pruebe la configuración de la federación. En la línea de comandos, escriba:
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Por ejemplo:
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Pruebe las notificaciones de inserción. En la línea de comandos, escriba:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Por ejemplo:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

## Vea también

#### Otros recursos

[Test-CsFederatedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxPushNotification)

