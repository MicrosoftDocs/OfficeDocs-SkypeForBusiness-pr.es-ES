﻿---
title: 'Lync Server 2013: Administración de objetos de contactos de Hosted Exchange'
TOCTitle: Administración de objetos de contactos de Hosted Exchange
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48277112
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administración de objetos de contactos de Hosted Exchange en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-25_

Es preciso configurar un objeto de contacto para cada número de operador automático y número de acceso de suscriptor en la implementación local.

Para la integración con mensajería unificada hospedada de Exchange, ocsumutil.exe no es válido para administrar objetos de contacto, ya que depende de la configuración de mensajería unificada de Exchange de Active Directory. En una implementación local, Lync Server 2013 y la mensajería unificada hospedada de Exchange se instalan en bosques distintos y sin confianza mutua. Por motivos de seguridad, los administradores de Lync Server 2013 no disponen de acceso directo a la configuración de mensajería unificada de Exchange de Active Directory. Como consecuencia, Lync Server 2013 proporciona un modelo diferente para administrar los objetos de contacto en un *espacio de direcciones SIP compartido* al que tienen acceso Lync Server 2013 y el servicio de mensajería unificada de Exchange.

## Flujo de trabajo de objetos de contacto hospedados

A continuación, se exponen los pasos generales para trabajar con el administrador de arrendatarios de Exchange hospedado para administrar objetos de contacto:

1.  El administrador de Exchange solicita números de teléfono para el acceso de objetos de contacto del operador automático y del suscriptor de mensajería unificada de Exchange.

2.  El administrador de Lync Server 2013 crea un objeto de contacto para cada número de teléfono y asigna una directiva de correo de voz hospedado a cada objeto de contacto.

3.  El administrador de Lync Server 2013 proporciona los números de teléfono al administrador de Exchange.

4.  El administrador de Exchange asigna los números de teléfono a los planes de marcado de mensajería unificada de Exchange para el acceso de suscriptores y operadores automáticos.


> [!NOTE]
> No hace falta preparar ninguna configuración de planes de marcado de Lync Server 2013 en los objetos de contacto, como sucede con las implementaciones locales.



## Configuración de objetos de contacto hospedados


> [!NOTE]
> Para poder habilitar objetos de contacto de Lync Server 2013 para la mensajería unificada de Exchange hospedada, debe implementarse una directiva de correo de voz hospedada que se aplique a dichos objetos. La directiva puede ser de ámbito global, de nivel de sitio o de ámbito de usuario, siempre y cuando se aplique al objeto de contacto que desea habilitar. Para más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">Directivas de correo de voz hospedado en Lync Server 2013</A>.



Para configurar objetos de contacto de acceso de suscriptor y operador automático en una implementación local, debe usar los cmdlets siguientes:

  - **New-CsExUmContact** crea un objeto de contacto para mensajería unificada hospedada.

  - **Set-CsExUmContact** modifica un objeto de contacto ya creado para mensajería unificada hospedada.

El ejemplo siguiente crea un objeto de contacto de operador automático.

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

Este ejemplo crea un objeto de contacto de mensajería unificada de Exchange con la dirección SIP sip:exumaa1@fabrikam.com. El nombre del grupo en el que se ejecuta el servicio Registrar de Lync Server 2013 es RedmondPool.litwareinc.com. La unidad organizativa de Active Directory donde se guardará esta información es OU=ExUmContacts,DC=litwareinc,DC=com. El número de teléfono del objeto de contacto es 2065554567. El parámetro opcional -AutoAttendant $True especifica que se trata de un objeto de contacto de operador automático. Si el parámetro -AutoAttendant se establece en False (valor predeterminado), se especifica un objeto de contacto con acceso de suscriptor.

Para ver los detalles sobre cómo usar los cmdlets New-CsExUmContact y Set-CsExUmContact, consulte la documentación de Shell de administración de Lync Server.

