---
title: "Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados"
TOCTitle: Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48276652
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar o deshabilitar el envío de una renuncia de archivado a socios federados en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-23_

En el momento en que implementa los servidores perimetrales y habilita la federación para la organización, debe especificar si desea enviar de forma automática la notificación de renuncia de archivado a los socios federados. Si archiva las comunicaciones externas, debe habilitar el envío de notificaciones de renuncia de archivado. Para cambiar esa configuración, siga el procedimiento de este tema.


> [!NOTE]
> En el procedimiento siguiente, se presupone que ya ha habilitado la federación para la organización. Para más información sobre cómo habilitar la federación, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de implementación u operaciones.



## Para habilitar o deshabilitar el envío de una renuncia de archivado a socios federados:

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y en **Configuración perimetral de acceso** .

4.  En la pestaña **Configuración perimetral de acceso** , haga clic en **Global** , en **Editar** y en **Mostrar detalles** .

5.  En **Editar configuración perimetral de acceso** , vaya a **Habilitar comunicaciones con usuarios federados** y active o desactive la casilla **Enviar notificación de renuncia de archivado a los socios federados** para habilitar o deshabilitar el envío automático de notificaciones de renuncia de archivado.

6.  Haga clic en **Confirmar** .

Si desea habilitar a los usuarios federados para que colaboren con los usuarios de su implementación de Lync Server 2013, es preciso que haya configurado al menos una directiva de acceso externo para que los usuarios federados dispongan de acceso. Para más información, consulte [Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) en la documentación de implementación u operaciones. Para más información sobre el control de acceso para dominios federados específicos, consulte [Configurar la compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) en la documentación de implementación u operaciones.

## Habilitar o deshabilitar la renuncia de archivado con los cmdlets de Windows PowerShell

El uso de la renuncia de archivado puede administrarse con Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Ejecute este cmdlet desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para habilitar la renuncia de archivado

  - Para habilitar la renuncia de archivado, establezca la propiedad **EnableArchivingDisclaimer** en True ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## Para deshabilitar la renuncia de archivado

  - Para deshabilitar la renuncia de archivado, establezca la propiedad **EnableArchivingDisclaimer** en False ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

