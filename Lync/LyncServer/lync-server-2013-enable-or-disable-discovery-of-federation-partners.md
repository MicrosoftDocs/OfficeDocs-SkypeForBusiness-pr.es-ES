---
title: "Lync Server 2013: Habilitar o deshabilitar la detección de socios de federación"
TOCTitle: Habilitar o deshabilitar la detección de socios de federación
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48276033
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar o deshabilitar la detección de socios de federación en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-23_

En el momento en que implementa los servidores perimetrales y habilita la federación para la organización, debe especificar si se va a admitir la detección automática de los dominios de socios federados. Para cambiar esa configuración, siga el procedimiento de este tema.


> [!NOTE]
> En el procedimiento siguiente, se presupone que ya ha habilitado la federación para la organización. Para más información sobre cómo habilitar la federación, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013</A> en la documentación de implementación u operaciones.



## Para habilitar o deshabilitar la detección automática de dominios federados para la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y en **Configuración perimetral de acceso** .

4.  En la página **Configuración perimetral de acceso** , haga clic en **Global** , en **Editar** y, a continuación en **Mostrar detalles** .

5.  En **Editar configuración perimetral de acceso** , en **Habilitar comunicaciones con usuarios federados** , active o desactive la casilla **Habilitar detección de dominio de socio** para habilitar o deshabilitar la detección automática de dominios de socios.

6.  Haga clic en **Confirmar** .

Para permitir que los usuarios federados colaboren con los usuarios de su implementación de Lync Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios federados. Para obtener más información, consulte [Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública en Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) en la documentación referente a la implementación o a las operaciones. Para obtener más información sobre cómo controlar el acceso en dominios federados específicos, consulte [Administrar dominios federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Administrar proveedores federados SIP para la organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) y [Administrar socios federados XMPP para su organización en Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) en la documentación referente a la implementación o a las operaciones.

## Habilitar o deshabilitar la detección de socios federados mediante cmdlets de Windows PowerShell

La detección de socios federados se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para habilitar la detección de socios federados

  - Para habilitar la detección de socios federados, establezca el valor de la propiedad **EnablePartnerDiscovery** en True ($True). Tenga en cuenta que debe habilitar el enrutamiento SRV de DNS para poder cambiar el valor de esta propiedad.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

## Para deshabilitar la detección de socios federados

  - Para deshabilitar la detección de socios federados, establezca el valor de la propiedad **EnablePartnerDiscovery** en False ($False).
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

