---
title: Eliminación de perfiles de directivas de ancho de banda de red
TOCTitle: Eliminación de perfiles de directivas de ancho de banda de red
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49889079
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminación de perfiles de directivas de ancho de banda de red

 

_**Última modificación del tema:** 2012-11-01_

Como parte del servicio de control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda de ciertas modalidades. En Microsoft Lync Server 2013, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo. Puede establecer las limitaciones generales de ancho de banda y sesión. Puede usar el Panel de control de Lync Server para crear, cambiar o eliminar un perfil de contenedor para estas directivas. Use los siguientes procedimientos para eliminar perfiles de directiva de ancho de banda de red. Para más información sobre cómo crear o cambiar un perfil de directiva de ancho de banda de red, vea [Creación o modificación de perfiles de directivas de ancho de banda](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

## Para eliminar un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ancho de banda**.

4.  En la página **Directiva de ancho de banda**, haga clic en el perfil de directiva de ancho de banda que desea eliminar.
    

    > [!NOTE]
    > Puede eliminar más de un perfil en la misma operación. Para hacerlo, pulse CTRL y seleccione varios perfiles manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los perfiles, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.



5.  En el menú **Editar** , haga clic en **Eliminar** .
    
    > [!WARNING]  
    > No puede eliminar un perfil de directiva de ancho de banda que esté asociado a un sitio de red. Primero debe eliminar la asociación establecida con el sitio de red para poder eliminar el perfil. Para más información sobre cómo modificar el sitio de red, vea <a href="lync-server-2013-creating-or-modifying-network-sites.md">Creación o modificación de sitios de red</a>.
    


## Vea también

#### Tareas

[Creación o modificación de perfiles de directivas de ancho de banda](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Visualización de la información de perfil de directiva de ancho de banda de red](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  

#### Otros recursos

[Configurar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

