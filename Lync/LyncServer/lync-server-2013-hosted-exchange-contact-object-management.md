---
title: 'Lync Server 2013: Administración de objetos de contactos de Hosted Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c67438745ee7cbb9de0ccfdef1d5d8959bb4679c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Administración de objetos de contactos de Hosted Exchange en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-25_

Debe configurar un objeto de contacto para cada número de acceso de número de operador automático y de suscriptor en la implementación entre locales.

Para la integración con la mensajería unificada de Exchange hospedada, OCSUMUtil. exe no se puede usar para administrar objetos de contacto, porque depende de la configuración de MU de Exchange Active Directory. En una implementación entre instalaciones, Lync Server 2013 y mensajería unificada de Exchange hospedado se instalan en bosques independientes sin confianza entre ellos. Por razones de seguridad, los administradores de Lync Server 2013 no tienen acceso directo a la configuración de Active Directory de mensajería unificada de Exchange. Como resultado, Lync Server 2013 proporciona un modelo diferente para administrar los objetos de contacto en un *espacio de direcciones SIP compartido* que sea accesible tanto para Lync Server 2013 como para el servicio hospedado de mensajería unificada de Exchange.

<div>

## <a name="hosted-contact-object-workflow"></a>Flujo de objeto de contacto hospedado

Estos son los pasos generales para trabajar con el administrador de inquilinos de Exchange hospedado para administrar los objetos de contacto:

1.  El administrador de Exchange solicita números de teléfono para los objetos de contacto de acceso de suscriptor de mensajería unificada de Exchange y operador automático.

2.  El administrador de Lync Server 2013 crea un objeto de contacto para cada número de teléfono y asigna una directiva de correo de voz hospedado a cada objeto de contacto.

3.  El administrador de Lync Server 2013 proporciona los números de teléfono para el administrador de Exchange.

4.  El administrador de Exchange asigna los números de teléfono a los planes de marcado correctos de MU de Exchange para los operadores automáticos y el acceso de suscriptor.

<div>


> [!NOTE]  
> No es necesario configurar ninguna configuración del plan de marcado de Lync Server 2013 en los objetos de contacto, tal y como lo hace en las implementaciones locales.



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>Configurar objetos de contactos hospedados

<div>


> [!NOTE]  
> Antes de que los objetos de contacto de Lync Server 2013 se puedan habilitar para la mensajería unificada de Exchange hospedada, se debe implementar una directiva de correo de voz hospedada que se aplica. La Directiva puede tener un ámbito global, de nivel de sitio o por usuario, siempre y cuando se aplique al objeto de contacto que desea habilitar. Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.



</div>

Para configurar los objetos de contacto de acceso del operador automático y del suscriptor hospedados en una implementación entre locales, debe usar los siguientes cmdlets:

  - **New-CsExUmContact** crea un nuevo objeto de contacto para la mensajería unificada hospedada.

  - **Set-CsExUmContact** modifica un objeto de contacto existente para la mensajería unificada de Exchange hospedada.

En el ejemplo siguiente se crea un objeto de contacto de operador automático:

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

Este ejemplo crea un nuevo objeto de contacto de mensajería unificada de Exchange con la dirección SIP sip:exumaa1@fabrikam.com. El nombre del grupo en el que se ejecuta el servicio de registro de 2013 de Lync Server es RedmondPool.litwareinc.com. La unidad organizativa de Active Directory donde se almacenará esta información es OU = ExUmContacts, DC = litwareinc, DC = com. El número de teléfono del objeto de contacto es 2065554567. El parámetro opcional-autoattendant $True especifica que este objeto es un objeto de contacto de operador automático. Establecer el parámetro-autooperador en falso (el valor predeterminado) especifica un objeto de contacto de acceso de suscriptor.

Para obtener más información sobre los cmdlets New-CsExUmContact y set-CsExUmContact, consulte la documentación del shell de administración de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

