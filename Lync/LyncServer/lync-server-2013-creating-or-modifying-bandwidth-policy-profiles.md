---
title: Creación o modificación de perfiles de directivas de ancho de banda
TOCTitle: Creación o modificación de perfiles de directivas de ancho de banda
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48274355
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación o modificación de perfiles de directivas de ancho de banda

 

_**Última modificación del tema:** 2012-10-15_

Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda de ciertas modalidades. En Microsoft Lync Server 2013, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo. Puede establecer las limitaciones generales de ancho de banda y sesión. Puede usar Panel de control de Lync Server para crear, modificar o eliminar un perfil de contenedor para estas directivas. Cada perfil de directiva de ancho de banda se puede asociar a uno o más sitios de red. Use los siguientes procedimientos para crear o modificar un perfil de directiva de ancho de banda. Para eliminar un perfil de directiva de ancho de banda, vea [Eliminación de perfiles de directivas de ancho de banda de red](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

## Para crear un nuevo perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ancho de banda**.

4.  En la página **Directiva de ancho de banda**, haga clic en **Nuevo**.

5.  En **Nuevo perfil de directiva de ancho de banda**, escriba un nombre en el campo **Nombre**. Este nombre debe ser diferente al resto de perfiles de directiva de ancho de banda.

6.  En el campo **Límite de audio**, escriba un valor numérico. Este valor es la cantidad máxima de ancho de banda que se puede asignar a todas las conexiones de audio, expresado en kbps.

7.  Especifique un valor numérico en el campo **Límite de sesión de audio**. Este valor es la cantidad máxima de ancho de banda que se puede asignar a una conexión de audio individual, expresado en kbps. El valor debe ser mayor o igual que 40.

8.  Especifique un valor numérico en el campo **Límite de vídeo**. Este valor es la cantidad máxima de ancho de banda que se puede asignar a todas las conexiones de vídeo, expresado en kbps.

9.  Especifique un valor numérico en el campo **Límite de sesión de vídeo**. Este valor es la cantidad máxima de ancho de banda que se puede asignar a una conexión de vídeo individual, expresado en kbps. El valor debe ser mayor o igual que 100.

10. (Opcional) Escriba un valor en el campo **Descripción** para proporcionar información sobre este perfil de directiva de ancho de banda más allá de lo que se pueda deducir de su nombre.

11. Haga clic en **Confirmar**.
    

    > [!NOTE]
    > Crear un nuevo perfil de directiva de ancho de banda no supone la aplicación automática de las restricciones de ancho de banda. Primero debe asociar el perfil de directiva a un sitio. Para obtener más información sobre cómo asociar el perfil de directiva a un sitio, consulte <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creación o modificación de sitios de red</A>.



## Para modificar un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ancho de banda**.

4.  En la página **Directiva de ancho de banda**, haga clic en el perfil de directiva de ancho de banda que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar perfil de directiva de ancho de banda**, modifique los campos según sea necesario (para obtener más información, consulte la sección "Para crear un nuevo perfil de directiva de ancho de banda" expuesta anteriormente en este tema).

7.  Haga clic en **Confirmar**.
    

    > [!NOTE]
    > Cuando modifique el perfil de directiva de ancho de banda, se actualizarán inmediatamente las limitaciones de ancho de banda de todos los sitios de red asociados a este perfil de directiva de ancho de banda.



## Vea también

#### Tareas

[Eliminación de perfiles de directivas de ancho de banda de red](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  

#### Otros recursos

[Configurar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

