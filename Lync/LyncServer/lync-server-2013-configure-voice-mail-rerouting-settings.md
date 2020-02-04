---
title: 'Lync Server 2013: Configurar los valores para volver a enrutar el correo de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4ea243e87490bcabd48c866cce525d6bbd17077
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Configurar los valores para volver a enrutar el correo de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Las aplicaciones de sucursales y los servidores de sucursales supervivientes pueden ofrecer una supervivencia en el correo de voz durante una interrupción de la WAN, si la mensajería unificada de Exchange se instala en el sitio central y se implementa un operador automático de mensajes de mensajería unificada de Exchange (AA). Le recomendamos que el administrador de Exchange configure el AA para que acepte solo los mensajes, lo que deshabilita otras funciones genéricas, como la transferencia a un usuario o la transferencia a un operador. También puede usar un AA genérico o un AA personalizado para enrutar la llamada.

Para obtener más información, consulte la sección "prepararse para la supervivencia del correo de voz" de los [requisitos de resistencia de sitios de sucursales para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) en la documentación de planeación.

<div>

## <a name="to-configure-voice-mail-survivability"></a>Para configurar la supervivencia del correo de voz

1.  Pida a su administrador de Exchange que configure el AA para aceptar solo los mensajes (en el shell de Exchange use el cmdlet siguiente: **set-UMAutoAttendant \<AA nombre\> -CallSomeoneEnabled $false**. El parámetro que especifica que se permite dejar mensajes (*SendVoiceMsgEnabled*) es verdadero de forma predeterminada.

2.  En el shell de administración de Lync Server, use el cmdlet **New-CSVoiceMailReroutingConfiguration** para establecer el número de teléfono AA como el número de teléfono del operador automático de mensajería unificada de Exchange en la configuración de redireccionamiento del correo de voz en la sucursal superviviente o en el servidor de sucursal superviviente.
    
    <div>
    

    > [!NOTE]  
    > Si más adelante necesita modificar la configuración de redireccionamiento del correo de voz, use el cmdlet <STRONG>set-CsVoiceMailReRoutingConfiguration</STRONG> para hacerlo. Para obtener más información sobre <STRONG>New-</STRONG> and <STRONG>set-CSVoiceMailReroutingConfiguration</STRONG>, vaya a los temas de ayuda de Shell.

    
    </div>

3.  Establezca el número de acceso de suscriptor de mensajería unificada de Exchange que corresponda al plan de marcado de mensajería unificada de Exchange del usuario de la sucursal como número de acceso de suscriptor de mensajería unificada de Exchange en la configuración de redireccionamiento del correo de voz en el equipo con la sucursal o el servidor de sucursal
    
    <div>
    

    > [!NOTE]  
    > Configure el plan de marcado de los usuarios de mensajería unificada de Exchange de modo que solo haya un plan de marcado asociado con todos los usuarios de la sucursal que necesiten acceder a la funcionalidad obtener correo de voz durante una interrupción de WAN.

    
    </div>

**Paso siguiente** para los equipos de sucursales que sean revivientes o los servidores de sucursal supervivientes: [usuarios domésticos en un dispositivo o servidor de sucursal con la supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

