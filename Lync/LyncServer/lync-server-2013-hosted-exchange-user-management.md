---
title: 'Lync Server 2013: administración de usuarios hospedados de Exchange'
description: 'Lync Server 2013: administración de usuarios hospedados de Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ceda9352fc627fc7b762b5995d788ffafa159ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550116"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Administración de usuarios de Exchange hospedada en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Para proporcionar servicios de correo de voz para Lync Server 2013 usuarios cuyos buzones se encuentran en un servicio de Exchange hospedado, debe habilitar sus cuentas de usuario para el correo de voz hospedado.

<div>


> [!NOTE]  
> Antes de que un usuario de Lync Server 2013 pueda estar habilitado para el correo de voz hospedado, debe implementarse una directiva de correo de voz hospedada que se aplique a la cuenta de usuario correspondiente. La directiva puede ser de ámbito global, de sitio o de usuario, siempre y cuando se aplique al usuario que desea habilitar. Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>El atributo msExchUCVoiceMailSettings

Lync Server 2013 presenta un nuevo atributo de usuario denominado **msExchUCVoiceMailSettings**, que se crea como parte de la preparación del esquema de Active Directory de Lync Server 2013. Este atributo multivalor contiene la configuración del correo de voz que se comparte con Lync Server 2013 y el servicio de Exchange hospedado.

En algunos casos, el servicio de Exchange hospedado puede definir el valor del atributo msExchUCVoiceMailSettings durante el proceso de habilitación de la mensajería unificada de Exchange, o bien durante el proceso de transferencia de buzones de correo a un servidor hospedado de Exchange Server. Si Exchange no establece este atributo, el administrador de Lync Server 2013 debe establecerlo ejecutando el cmdlet Set-CsUser, tal y como se ha descrito anteriormente en este tema.

En la tabla a continuación se muestran los pares clave/valor del atributo y sus autores.

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>Los pares clave/valor del atributo msExchUCVoiceMailSettings

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valor</th>
<th>Autor</th>
<th>Significado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server ha habilitado al usuario para el acceso a la mensajería unificada hospedada. La aplicación de enrutamiento de mensajería unificada de Exchange comprobará la Directiva de correo de voz hospedado del usuario para ver los detalles de enrutamiento.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server ha deshabilitado al usuario para el acceso a la mensajería unificada hospedada.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013 ha habilitado al usuario para el acceso a la mensajería unificada hospedada. La aplicación Lync Server 2013 ExUM Routing comprobará la Directiva de correo de voz hospedado del usuario para obtener detalles de enrutamiento.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013 ha deshabilitado al usuario para el acceso a la mensajería unificada hospedada.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Si el atributo ya tiene valores distintos de uno de los pares de clave/valor de Lync Server 2013 (CSHostedVoiceMail = 0 o CSHostedVoiceMail = 1), una advertencia indicará que el atributo puede ser administrado por una aplicación diferente. Por ejemplo, se muestra una advertencia si el par clave/valor ExchangeHostedVoiceMail=0 o ExchangeHostedVoiceMail=1 ya está presente. En tal caso, puede cambiar el valor editándolo en Active Directory, o bien ejecute el cmdlet siguiente para definir el valor como nulo:<BR>Set-CsUser –identity user –HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>Habilitación de usuarios para correo de voz hospedado

Para habilitar las llamadas de correo de voz de un usuario para que se redirijan a la mensajería unificada hospedada de Exchange, ejecute el cmdlet Set-CsUser para definir el valor del parámetro *HostedVoiceMail*. Este parámetro también indica a Lync Server 2013 que debe aclarar el indicador "llamar al correo de voz".

  - En el ejemplo siguiente se habilita la cuenta de usuario de Pilar Ackerman para correo de voz hospedado:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    El cmdlet comprueba que una directiva de correo de voz hospedado (global, de nivel de sitio o por usuario) se aplique al usuario. Si no se aplica ninguna directiva, el cmdlet no se completará correctamente.

  - En el ejemplo siguiente se deshabilita la cuenta de usuario de Pilar Ackerman para correo de voz hospedado:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    El cmdlet comprueba que ninguna directiva de correo de voz hospedado (global, de nivel de sitio o por usuario) se aplique al usuario. Si se aplica alguna directiva, el cmdlet no se completará correctamente.

Para obtener información detallada sobre cómo usar el cmdlet Set-CsUser, consulte la documentación del shell de administración de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

