---
title: Visualización de la información de perfil de directiva de ancho de banda de red
TOCTitle: Visualización de la información de perfil de directiva de ancho de banda de red
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49889806
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de la información de perfil de directiva de ancho de banda de red

 

_**Última modificación del tema:** 2013-02-23_

Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades. En Microsoft Lync Server 2013, solo se pueden asignar limitaciones de ancho de banda a modalidades de audio y vídeo. Puede establecer limitaciones generales de ancho de banda y sesión. Puede usar Panel de control de Lync Server para crear, modificar o eliminar un perfil de contenedor para estas directivas. Cada perfil de directiva de ancho de banda se puede asociar a uno o más sitios de red. Utilice los siguientes procedimientos para ver un perfil de directiva de ancho de banda. Para crear o modificar un perfil de directiva de ancho de banda, consulte [Creación o modificación de perfiles de directivas de ancho de banda](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

## Para modificar un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ancho de banda**.

4.  En la página **Directiva de ancho de banda**, haga clic en el perfil de directiva de ancho de banda que desea modificar.

5.  En el menú **Editar** , haga clic en **Mostrar detalles** .

## Consulta de la información del perfil de directiva de ancho de banda de red usando los cmdlets de Lync Server PowerShell

Los perfiles de ancho de banda de red también se pueden consultar usando Lync Server PowerShell y el cmdlet Get-CsNetworkBandwidthPolicyProfile. Este cmdlet se puede ejecutar desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Visualización de la información del perfil de directiva de ancho de banda de red

  - Para consultar información sobre todos los perfiles de directiva de ancho de banda de red, escriba el siguiente comando en el Shell de administración de Lync Server y pulse ENTRAR:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Devolverá información similar a la siguiente:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

Si desea más información, consulte el tema de ayuda relativo al cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

## Vea también

#### Tareas

[Creación o modificación de perfiles de directivas de ancho de banda](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Eliminación de perfiles de directivas de ancho de banda de red](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  

#### Otros recursos

[Configurar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-call-admission-control.md)

