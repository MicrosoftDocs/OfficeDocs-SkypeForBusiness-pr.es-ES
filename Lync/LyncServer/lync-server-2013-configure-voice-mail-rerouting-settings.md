---
title: 'Lync Server 2013: configurar las opciones de redireccionamiento del correo de voz'
description: 'Lync Server 2013: configurar las opciones de reenrutamiento del correo de voz.'
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
ms.openlocfilehash: 669ea5585f9e732b6a49d9749b8939c14b4e0d9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566736"
---
# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>Configurar la configuración de reenrutamiento del correo de voz en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Las aplicaciones de sucursal con funciones de supervivencia y los servidores de sucursal con funciones de supervivencia pueden proporcionar supervivencia de correo de voz para usuarios de sucursal durante una interrupción de la WAN, si la mensajería unificada (UM) de Exchange está instalada en el sitio central y se implementa un operador automático de mensajes de mensajería unificada (AA) de Exchange. Recomendamos que su administrador de Exchange configure el Operador automático para que acepte solo mensajes, con lo cual se deshabilita el resto de la funcionalidad general como, por ejemplo, las transferencias a un usuario o a un operador. También puede usar un AA genérico o un AA personalizado para enrutar la llamada.

Para obtener más información, consulte la sección "preparación para la supervivencia del correo de voz" de [Branch-site Resiliency Requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) en la documentación referente a la planeación.

<div>

## <a name="to-configure-voice-mail-survivability"></a>Para configurar las funciones de supervivencia del correo de voz

1.  Pida al administrador de Exchange que configure el AA para que acepte sólo mensajes (en el shell de Exchange, use el siguiente cmdlet: **set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**. El parámetro que especifica que se debe permitir dejar mensajes (*SendVoiceMsgEnabled*) es "true" de forma predeterminada.

2.  En el shell de administración de Lync Server, use el cmdlet **New-CSVoiceMailReroutingConfiguration** para establecer el número de teléfono AA como el número de teléfono del operador automático de mensajería unificada de Exchange en la configuración de reenrutamiento del correo de voz en la aplicación de sucursal con funciones de supervivencia o con el servidor de sucursal con funciones de supervivencia.
    
    <div>
    

    > [!NOTE]  
    > Si, más tarde, necesita modificar la configuración de reenrutamiento del correo de voz, use para ello el cmdlet <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG>. Para ver más detalles acerca de <STRONG>New-</STRONG> y <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, consulte los temas de ayuda del shell.

    
    </div>

3.  Establezca el número de acceso de suscriptor de mensajería unificada de Exchange que corresponda al plan de marcado de mensajería unificada de Exchange del usuario de sucursal como el número de acceso de suscriptor de mensajería unificada de Exchange en la configuración de reenrutamiento del correo de voz de la aplicación de sucursal con funciones de supervivencia o servidor de sucursal
    
    <div>
    

    > [!NOTE]  
    > Configure el plan de marcado de los usuarios de mensajería unificada de Exchange para que solo haya un plan de marcado asociado a todos los usuarios de la sucursal que necesiten tener acceso a la funcionalidad obtener correo de voz durante una interrupción de la WAN.

    
    </div>

**Paso siguiente** para las aplicaciones de sucursal con funciones de supervivencia o servidores de sucursal con funciones de supervivencia: [usuarios particulares en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

