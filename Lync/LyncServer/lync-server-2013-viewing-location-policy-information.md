---
title: Visualización de la información de una directiva de ubicación
TOCTitle: Visualización de la información de una directiva de ubicación
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48274519
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de la información de una directiva de ubicación

 

_**Última modificación del tema:** 2012-11-01_

En Lync Server 2013, puede usar la directiva de ubicación para aplicar opciones de configuración relacionadas con las funciones de 9-1-1 mejorado (E9-1-1) y la configuración de ubicación para usuarios o contactos. La directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia. Por ejemplo, puede usar la directiva de ubicación para definir qué número constituye una llamada de emergencia (por ejemplo, 911 en los EE. UU.), si se debe informar a la seguridad corporativa de forma automática y cómo se debe desviar la llamada.

Puede configurar las directivas de ubicación en el grupo **Configuración de red** de Panel de control de Lync Server 2013. Desde Panel de control de Lync Server puede ver, crear, modificar o eliminar directivas de ubicación. Use el siguiente procedimiento para ver información acerca de las directivas de ubicación. Para obtener detalles sobre la creación o modificación de directivas de ubicación, vea [Creación o modificación de una directiva de ubicación](lync-server-2013-creating-or-modifying-a-location-policy.md).

## Para ver información acerca de una nueva directiva de ubicación

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ubicación**.

4.  En la página **Directiva de ubicación**, seleccione la directiva de ubicación que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.
    

    > [!NOTE]
    > Solo puede ver información acerca de una directiva de ubicación cada vez.



Aparece de forma predeterminada una única directiva, denominada Global, que no puede eliminarse ni cambiarse de nombre. Sin embargo, puede modificar la directiva Global. Esta directiva se aplicará a todos los usuarios y contactos, a menos que cree directivas de sitio o directivas por usuario. Las directivas por usuario deben aplicarse a usuarios específicos.

## Vea también

#### Tareas

[Creación o modificación de una directiva de ubicación](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Crear directivas de ubicación en Lync Server 2013](lync-server-2013-create-location-policies.md)  
[Crear o modificar un sitio de red en Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)  

#### Otros recursos

[New-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsLocationPolicy)  
[Set-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsLocationPolicy)

