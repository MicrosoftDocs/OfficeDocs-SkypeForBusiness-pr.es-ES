---
title: Habilitación del control de admisión de llamadas
TOCTitle: Habilitación del control de admisión de llamadas
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48274233
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitación del control de admisión de llamadas

 

_**Última modificación del tema:** 2012-11-01_

El control de admisión de llamadas (CAC) consiste en una red de regiones, sitios y subredes que permiten aplicar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Una vez configurada la red CAC, debe habilitar el CAC para aplicar las limitaciones de ancho de banda. Puede usar Panel de control de Lync Server para hacerlo.

## Para habilitar el CAC desde Panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Global**.

4.  En la página **Global**, haga clic en la configuración **Global**.
    

    > [!NOTE]
    > Solo puede configurarse una red por cada implementación de Microsoft Lync Server 2013, de modo que nunca habrá más de una configuración de red en la lista. No podrá cambiar el nombre de la configuración Global.



5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas** y, a continuación, haga clic en **Confirmar**.

Al hacer clic en **Confirmar**, realizará una prueba de la configuración. Se cerrará el cuadro de diálogo **Editar configuración global** y el programa le devolverá a la página **Global**. Recibirá una advertencia si se descubren errores o incoherencias en la configuración de red que pudieran impedir el buen funcionamiento de la red (por ejemplo, si cada región no está conectada a otra región en una ruta interregional).

Si hace cambios en la configuración de red, puede volver a ejecutar la comprobación de validación abriendo la configuración Global y haciendo clic en **Confirmar**. No es necesario deshabilitar previamente el CAC: deje activada la casilla y haga clic en **Confirmar**. Puede hacerlo en cualquier momento aunque no haga cambios en la configuración.

## Vea también

#### Conceptos

[Información general sobre el control de admisión de llamadas en Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)  

#### Otros recursos

[Planear el control de admisión de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Configurar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Get-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkConfiguration)  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkConfiguration)

