---
title: 'Lync Server 2013: ver información acerca de las reglas de actualización de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fef5d58116da6b8cbc07ce2b16f3dd4f6b28ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506387"
---
# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Ver información sobre las reglas de actualización de dispositivos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Vea detalles sobre las reglas de actualización de dispositivos que ya se han importado, como el tipo, modelo y la marca de los dispositivos a los que se aplica la actualización; versión y tipo de actualización; y la configuración regional y de grupo de servidores para la actualización. La información está disponible para todas las reglas de actualización de dispositivos importadas (las que están pendientes de aprobación, implementadas (aprobadas), recuperadas (restauradas) y aquellas que decidió no usar (restablecer). Obtenga acceso a esta información desde el panel de control de Lync Server o Windows PowerShell.

<div>


> [!NOTE]  
> Para más información sobre cómo importar, aprobar, restablecer, restaurar y quitar reglas, vea los temas que aparecen en las <A href="lync-server-2013-device-update-rules.md">reglas de actualización de dispositivos en Lync Server 2013</A>.



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>Para ver las reglas de actualización de dispositivos mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, en el botón de navegación **actualización de dispositivos** . Las reglas importadas se enumeran en la página de **actualización de dispositivos** .

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Visualización de reglas de actualización de dispositivos mediante cmdlets de Windows PowerShell

La información detallada sobre todas las reglas de actualización de dispositivos también se puede ver con Windows PowerShell y el cmdlet **Get-CsDeviceUpdateRule** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


> [!NOTE]  
> Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>Para ver todas las reglas de actualización de dispositivos

  - El siguiente comando devuelve información sobre todas las reglas de actualización de dispositivos configuradas para su uso en la organización:
    
        Get-CsDeviceUpdateRule
    
    El comando devuelve información similar a la siguiente para cada una de las reglas de actualización de dispositivos:
    
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

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>Para ver todas las reglas de actualización de dispositivos en un servidor Web específico

  - Para ver las reglas de actualización de dispositivos en un equipo específico, use el parámetro filter seguido de la identidad del servidor y el carácter comodín ( \* ). Por ejemplo:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

