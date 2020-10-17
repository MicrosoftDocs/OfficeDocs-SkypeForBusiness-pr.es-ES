---
title: 'Lync Server 2013: usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: add711ca547648a6071a22fee6a0bcd0eeb0f6c0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528207"
---
# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-10_

El proceso de alojamiento de usuarios en una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia es similar al de los usuarios que se retienen en un grupo de servidores front-end. Realice la aplicación de sucursal con funciones de supervivencia o el procedimiento de servidor de sucursal con funciones de supervivencia en el sitio central.

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a>Para hospedar a usuarios en un servidor o una aplicación de sucursal con funciones de supervivencia

1.  Antes de mover usuarios al servidor de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia, abra el shell de administración de Lync Server y, a continuación, haga lo siguiente:
    
      - Ejecute el cmdlet **Test-CsPstnOutboundCall** para comprobar que el servidor de sucursal con funciones de supervivencia se está ejecutando y que se ha configurado la conectividad de la red telefónica conmutada (RTC). Si tiene que modificar las propiedades de la puerta de enlace RTC, use el cmdlet **set-CsPstnGateway**.
    
      - Ejecute el cmdlet **Get-CsVoicePolicy** para comprobar que los usuarios que van a estar hospedados en el servidor de sucursal con funciones de supervivencia tienen la Directiva de enrutamiento de VoIP adecuada. Si necesita modificar la Directiva de VoIP, use el cmdlet **set-CsVoicePolicy**.
    
      - Ejecute el cmdlet **Get-CsVoicemailReroutingConfiguration** para comprobar que la configuración de reenrutamiento del correo de voz está configurada. Si necesita modificar la configuración de reenrutamiento del correo de voz, use el cmdlet **set-CsVoicemailReroutingConfiguration**.

2.  En el shell de administración de Lync Server, ejecute el cmdlet **Move-CsUser** para mover usuarios domésticos.

<div>


> [!NOTE]  
> También puede usar el panel de control de Lync Server para comprobar los requisitos previos y los usuarios domésticos.



</div>

<div>


> [!NOTE]  
> Los usuarios hospedados en una aplicación de sucursal con funciones de supervivencia de Lync Server no pueden crear salones de chat nuevos ni ver la tarjeta de la sala para las salas existentes.



</div>

</div>

<div>

## <a name="see-also"></a>Consulte también


[Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

