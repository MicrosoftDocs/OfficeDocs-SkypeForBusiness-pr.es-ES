---
title: "Lync Server 2013 : Activ. ou désactiv. de l’accès des utilisateurs distants"
TOCTitle: Habilitar y deshabilitar el acceso de usuarios remotos
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48276712
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar y deshabilitar el acceso de usuarios remotos en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-23_

Los usuarios remotos son usuarios de la organización que tienen una identidad persistente de Active Directory en la organización. Los usuarios remotos suelen iniciar sesión en Lync Server desde fuera del firewall con una red privada virtual (VPN) cuando no están conectados internamente a la red de su organización. Entre los usuarios se encuentran los empleados que trabajan en casa o fuera de la oficina, así como otros trabajadores remotos, como los proveedores de confianza, a los que se conceden credenciales corporativas. Si habilita el acceso de usuarios remotos, los usuarios remotos admitidos se conectan por Internet y no necesitan conectarse usando una VPN para colaborar con usuarios internos que usen Lync Server.

Si más adelante desea impedir de forma provisional o definitiva el acceso a usuarios de dominios federados, deshabilite la federación para la organización. Para habilitar o deshabilitar el acceso de usuarios federados en su organización, siga el procedimiento de esta sección, que también incluye las opciones de federación adecuadas que debe admitir la organización.


> [!NOTE]
> Al habilitar el acceso de usuarios remotos solo se especifica que los servidores que ejecuten el servicio perimetral de acceso permitan la comunicación con usuarios remotos, pero dichos usuarios no pueden participar en mensajes instantáneos ni en conferencias de la organización hasta que también se configure una directiva para administrar el uso del acceso de usuarios remotos. La configuración de directiva de Lync Server que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva de Lync Server es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto. Para obtener información detallada sobre la configuración de directivas para usar el acceso de usuarios remotos, vea <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configurar directivas para el control del acceso de usuarios remotos en Lync Server 2013</A>.



## Para habilitar o deshabilitar el acceso de usuarios remotos en la organización

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y luego en **Configuración perimetral de acceso**.

4.  En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.

5.  En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:
    
      - Para habilitar el acceso de usuarios remotos en la organización, active la casilla **Habilitar el acceso remoto de usuarios**.
    
      - Para deshabilitar el acceso remoto de usuarios en la organización, desactive la casilla **Habilitar el acceso remoto de usuarios**.

6.  Haga clic en **Confirmar**.

Para que los usuarios remotos inicien sesión en los servidores que ejecuten Lync Server, configure al menos una directiva de acceso externo para admitir el acceso de usuarios remotos. Para obtener información detallada, vea [Configurar directivas para el control del acceso de usuarios remotos en Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) en la documentación sobre implementación o sobre operaciones.

## Habilitar o deshabilitar el acceso de usuarios remotos con los cmdlets de Windows PowerShell

El acceso de usuario remoto se puede administrar mediante Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para habilitar el acceso de usuario remoto

  - Para habilitar el acceso de usuarios remotos, defina el valor de la propiedad **AllowOutsideUsers** en True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## Para deshabilitar el acceso de usuario remoto

  - Para deshabilitar el acceso de usuarios remotos, defina el valor de la propiedad **AllowOutsideUsers** en False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

