---
title: 'Lync Server 2013: Ver registros de uso de RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9042eca0b8ddd1f04b34c3fea0b57dd6235b69c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a>Ver los registros de uso de RTC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Un registro de uso de la red de telefonía pública conmutada (RTC) especifica una clase de llamada (como interna, local o de larga distancia) que pueden realizar varios usuarios o grupos de usuarios de una organización. Para obtener más información, consulte [registros de uso de RTC en Lync Server 2013](lync-server-2013-pstn-usage-records.md) en la documentación de planeación.

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a>Para ver un registro de uso de RTC mediante el panel de control de Lync Server

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Uso de RTC**.

4.  En la página **Uso de RTC**, resalte el registro de uso de RTC que desee ver, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
    <div>
    

    > [!NOTE]  
    > Una página de solo lectura del registro de uso de RTC seleccionado muestra las rutas y las directivas de voz asociadas.

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Ver la información de uso de RTC mediante cmdlets de Windows PowerShell

También puede ver los usos de RTC mediante Windows PowerShell y el cmdlet **Get-CsPstnUsage** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Para ver la información de uso de RTC con cmdlets de Windows PowerShell

  - Para ver información sobre todos los usos de RTC, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsPstnUsage
    
    Este comando devolverá información similar a la siguiente:
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

Para obtener más información, vea [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

