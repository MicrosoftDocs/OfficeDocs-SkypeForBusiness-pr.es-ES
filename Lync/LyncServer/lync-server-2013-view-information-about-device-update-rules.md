---
title: Ver información sobre las reglas de actualización de dispositivos
TOCTitle: Ver información sobre las reglas de actualización de dispositivos
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994077(v=OCS.15)
ms:contentKeyID: 52061769
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ver información sobre las reglas de actualización de dispositivos

 

_**Última modificación del tema:** 2013-02-23_

Conozca todos los detalles de las reglas de actualización de dispositivo que ya tiene importadas, como el tipo, el modelo, la marca de dispositivo para la que son válidas y la versión y el tipo de la actualización, así como la configuración local y el grupo de la actualización. Esta información está disponible para todas las reglas de actualización de dispositivo importadas, tanto para las que están pendientes de aprobación como para las implementadas (aprobadas), recuperadas (restauradas) y las que haya decidido no usar (restablecer). Acceda a esta información desde el Panel de control de Lync Server o Windows PowerShell.


> [!NOTE]
> Para más información sobre cómo importar, aprobar, restablecer, restaurar y quitar reglas, consulte los temas de <A href="lync-server-2013-device-update-rules.md">Reglas de actualización de dispositivos en Lync Server 2013</A>.



## Para ver reglas de actualización de dispositivo mediante el Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, después, en el botón de navegación **Actualización de dispositivo**. Las reglas importadas aparecerán recogidas en la página **Actualización de dispositivo**.

## Ver reglas de actualización de dispositivo con cmdlets de Windows PowerShell

También se puede consultar información detallada sobre cualquier regla de actualización de dispositivo a través de Windows PowerShell y el cmdlet **Get-CsDeviceUpdateRule**. Este cmdlet se ejecuta desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



## Para ver todas las reglas de actualización de dispositivo

  - El siguiente comando devuelve información sobre todas las reglas de actualización de dispositivo que hay configuradas en la organización:
    
        Get-CsDeviceUpdateRule
    
    El comando devuelve información similar a la siguiente en relación con cada una de las reglas de actualización de dispositivo:
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

## Para ver todas las reglas de actualización de dispositivo en un servidor web específico

  - Para ver las reglas de actualización de dispositivo en un equipo concreto, use el parámetro Filter seguido por la identidad del servidor y el carácter comodín (\*). Por ejemplo:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

Para más información detallada, vea el tema de ayuda relativo al cmdlet [Get-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDeviceUpdateRule).

