---
title: "Lync Server 2013 : Activ. ou désactiv. de l’accès des utilisateurs anonymes"
TOCTitle: Habilitar y deshabilitar el acceso anónimo de usuarios
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49129322
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar y deshabilitar el acceso anónimo de usuarios en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-23_

Los usuarios anónimos son usuarios que no disponen de una cuenta de usuario en Servicios de dominio de Active Directory de la organización o en un dominio federado permitido, pero que pueden recibir una invitación para participar de forma remota en una conferencia local. Al permitir la participación anónima en las reuniones, se habilita a usuarios anónimos (es decir, usuarios cuya identidad solo se comprueba a través de la clave de reunión o conferencia) a participar en las reuniones. Para permitir la participación anónima es necesario habilitarla para la organización.

Si, posteriormente, desea evitar temporal o permanentemente el acceso de usuarios anónimos, puede deshabilitarlo para la organización. Use el procedimiento que se describe en esta sección para habilitar o deshabilitar el acceso de usuarios anónimos para la organización.


> [!NOTE]
> Al habilitar el permiso del acceso de usuarios anónimos para la organización, solo se especifica que los servidores en los que se ejecute el servicio perimetral de acceso permitan el acceso de usuarios anónimos. Los usuarios anónimos no pueden participar en ninguna reunión de la organización hasta que también se configure al menos una directiva de conferencia y se aplique a uno o varios usuarios o grupos de usuarios. Los únicos usuarios que pueden invitar a usuarios anónimos a reuniones son aquellos usuarios que tengan asignada una directiva de conferencia configurada para permitir usuarios anónimos. Para obtener más información acerca de cómo configurar directivas de conferencia para admitir la invitación a usuarios anónimos, consulte <A href="lync-server-2013-conferencing-policies.md">Directivas de conferencia de Lync Server 2013</A>.



## Para habilitar o deshabilitar el acceso de usuarios anónimos para la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Configuración perimetral de acceso** .

4.  En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:
    
      - Para habilitar el acceso de usuarios anónimos para la organización, active la casilla de verificación **Habilitar comunicaciones con usuarios anónimos**.
    
      - Para deshabilitar el acceso de usuarios anónimos para la organización, desactive la casilla de verificación **Habilitar comunicaciones con usuarios anónimos**.

6.  Haga clic en **Confirmar**.

## Habilitar o deshabilitar el acceso de usuarios anónimos con los cmdlets de Windows PowerShell

Puede administrar el acceso de usuarios anónimos usando el cmdlet Windows PowerShell y el **Set-CsAccessEdgeConfiguration**. Puede ejecutar este cmdlet desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para habilitar el acceso de usuarios anónimos

  - Para habilitar el acceso de usuarios anónimos, ajuste el valor de la propiedad **AllowAnonymousUsers** en True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## Para deshabilitar el acceso de usuarios anónimos

  - Para deshabilitar el acceso de usuarios anónimos, ajuste el valor de la propiedad **AllowAnonymousUsers** en False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

## Vea también

#### Conceptos

[Referencia de configuración de directivas de conferencias en Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

