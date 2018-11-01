---
title: Habilitar el control de admisión de llamadas en Lync Server 2013
TOCTitle: Habilitar el control de admisión de llamadas en Lync Server 2013
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48275839
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar el control de admisión de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-19_

Después de configurar las opciones de red para la implementación del control de admisión de llamadas, debe habilitar el CAC para que se apliquen las directivas de ancho de banda.

Para ver más detalles, consulte la documentación del Shell de administración de Lync Server correspondiente a los siguientes cmdlets:

  - [Get-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Set-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Remove-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkConfiguration)

## Para habilitar el control de admisión de llamadas usando el shell de administración

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsNetworkConfiguration para habilitar el CAC en su red. Por ejemplo, ejecute lo siguiente:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    Si desea deshabilitar el CAC en la red, ejecute lo siguiente:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

## Para habilitar el control de admisión de llamadas usando el Panel de control de Lync Server

1.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **Global**.

4.  Haga clic en **Global** en la lista y, a continuación, seleccione **Mostrar detalles** en el menú **Edición**.

5.  En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas**.
    

    > [!NOTE]
    > Si desea deshabilitar el control de admisión de llamadas en toda la implementación, desactive esta casilla.



6.  Haga clic en **Confirmar**.

