---
title: 'Lync Server 2013: administración de objetos de contacto de Exchange hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15abe045504653fe7a64d8bc6ef82af3ac87ba37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Administración de objetos de contacto de Exchange hospedado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-25_

Es preciso configurar un objeto de contacto para cada número de operador automático y número de acceso de suscriptor en la implementación local.

Para la integración con mensajería unificada hospedada de Exchange, ocsumutil.exe no es válido para administrar objetos de contacto, ya que depende de la configuración de mensajería unificada de Exchange de Active Directory. En una implementación entre entornos, Lync Server 2013 y la mensajería unificada de Exchange hospedada se instalan en bosques independientes que no tienen confianza entre ellos. Por motivos de seguridad, los administradores de Lync Server 2013 no tienen acceso directo a la configuración de Active Directory de mensajería unificada de Exchange. Como resultado, Lync Server 2013 proporciona un modelo diferente para administrar objetos de contacto en un *espacio de direcciones SIP compartido* que es accesible tanto para Lync Server 2013 como para el servicio de mensajería unificada de Exchange hospedado.

<div>

## <a name="hosted-contact-object-workflow"></a>Flujo de trabajo de objetos de contacto hospedados

A continuación, se exponen los pasos generales para trabajar con el administrador de arrendatarios de Exchange hospedado para administrar objetos de contacto:

1.  El administrador de Exchange solicita números de teléfono para el acceso de objetos de contacto del operador automático y del suscriptor de mensajería unificada de Exchange.

2.  El administrador de Lync Server 2013 crea un objeto de contacto para cada número de teléfono y asigna una directiva de correo de voz hospedado a cada objeto de contacto.

3.  El administrador de Lync Server 2013 proporciona los números de teléfono al administrador de Exchange.

4.  El administrador de Exchange asigna los números de teléfono a los planes de marcado de mensajería unificada de Exchange para el acceso de suscriptores y operadores automáticos.

<div>


> [!NOTE]  
> No es necesario configurar ninguna configuración de plan de marcado de Lync Server 2013 en los objetos de contacto, como lo haría con las implementaciones locales.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>Configuración de objetos de contacto hospedados

<div>


> [!NOTE]  
> Antes de que Lync Server 2013 los objetos de contacto se puedan habilitar para la mensajería unificada de Exchange hospedada, debe implementarse una directiva de correo de voz hospedada que se les aplique. La directiva puede ser de ámbito global, de nivel de sitio o de ámbito de usuario, siempre y cuando se aplique al objeto de contacto que desea habilitar. Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.



</div>

Para configurar objetos de contacto de acceso de suscriptor y operador automático en una implementación local, debe usar los cmdlets siguientes:

  - **New-CsExUmContact** crea un objeto de contacto para mensajería unificada hospedada.

  - **Set-CsExUmContact** modifica un objeto de contacto ya creado para mensajería unificada hospedada.

El ejemplo siguiente crea un objeto de contacto de operador automático.

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

Este ejemplo crea un objeto de contacto de mensajería unificada de Exchange con la dirección SIP sip:exumaa1@fabrikam.com. El nombre del grupo de servidores en el que se ejecuta el servicio de registro 2013 de Lync Server es RedmondPool.litwareinc.com. La unidad organizativa de Active Directory donde se guardará esta información es OU=ExUmContacts,DC=litwareinc,DC=com. El número de teléfono del objeto de contacto es 2065554567. El parámetro opcional -AutoAttendant $True especifica que se trata de un objeto de contacto de operador automático. Si el parámetro -AutoAttendant se establece en False (valor predeterminado), se especifica un objeto de contacto con acceso de suscriptor.

Para obtener más información sobre los cmdlets New-CsExUmContact y set-CsExUmContact, consulte la documentación del shell de administración de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

