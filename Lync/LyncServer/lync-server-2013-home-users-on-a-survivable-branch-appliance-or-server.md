---
title: 'Lync Server 2013: Usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceabf8fe7d8f9068e60bbc20406d2496f815b04b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-10_

El proceso de alojamiento de usuarios en un dispositivo de sucursal con la supervivencia o con el reviviente es similar al proceso de alojamiento de usuarios en un grupo de servidores front-end. Lleve a cabo el procedimiento de servidor de sucursal o de servidor de sucursal superviviente en el sitio central.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Para usuarios domésticos en un equipo de sucursal o servidor de sucursal con la supervivencia

1.  Antes de mover usuarios al servidor de sucursal con la supervivencia o el servidor de sucursal superviviente, abra el shell de administración de Lync Server y, a continuación, realice todas las acciones siguientes:
    
      - Ejecute el cmdlet **Test-CsPstnOutboundCall** para comprobar que el servidor de sucursal con la supervivencia está en ejecución y que la conectividad de la red telefónica conmutada (RTC) está configurada. Si necesita modificar las propiedades de la puerta de enlace RTC, use el cmdlet **set-CsPstnGateway**.
    
      - Ejecute el cmdlet **Get-CsVoicePolicy** para comprobar que los usuarios que van a estar alojados en el servidor de sucursal con la supervivencia tienen la Directiva de enrutamiento de VoIP adecuada. Si necesita modificar la Directiva VoIP, use el cmdlet **set-CsVoicePolicy**.
    
      - Ejecute el cmdlet **Get-CsVoicemailReroutingConfiguration** para comprobar que la configuración de redireccionamiento del correo de voz está configurada. Si necesita modificar la configuración de redireccionamiento del correo de voz, use el cmdlet **set-CsVoicemailReroutingConfiguration**.

2.  En el shell de administración de Lync Server, ejecute el cmdlet **Move-CsUser** para mover usuarios domésticos.

<div>


> [!NOTE]  
> También puede usar el panel de control de Lync Server para comprobar los requisitos previos y los usuarios domésticos.



</div>

<div>


> [!NOTE]  
> Los usuarios que estén alojados en un equipo con la aplicación de Lync Server superviviente no pueden crear nuevos salones de chat o ver la tarjeta de la sala de las habitaciones existentes.



</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Prueba-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

