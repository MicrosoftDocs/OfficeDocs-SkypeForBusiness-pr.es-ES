---
title: 'Lync Server 2013: Administración de usuarios de Hosted Exchange'
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
ms.openlocfilehash: 23289399e4eee4a654b41f2978191a6329739b4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Administración de usuarios de Hosted Exchange en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

Para proporcionar servicios de correo de voz para los usuarios de Lync Server 2013 cuyos buzones se encuentran en un servicio de Exchange hospedado, debe habilitar sus cuentas de usuario para el correo de voz hospedado.

<div>


> [!NOTE]  
> Para que un usuario de Lync Server 2013 pueda estar habilitado para el correo de voz hospedado, debe implementarse una directiva de correo de voz hospedada que se aplique a la cuenta de usuario correspondiente. La Directiva puede ser global, de sitio o por usuario en ámbito, siempre que se aplique al usuario que desea habilitar. Para obtener más información, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">directivas de correo de voz hospedado en Lync Server 2013</A>.



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>El atributo msExchUCVoiceMailSettings

Lync Server 2013 introduce un nuevo atributo de usuario denominado **msExchUCVoiceMailSettings**, que se crea como parte de la preparación del esquema de Active Directory de Lync Server 2013. Este atributo multivalor tiene la configuración del correo de voz compartida por Lync Server 2013 y el servicio hospedado de Exchange.

En algunos casos, el servicio hospedado de Exchange puede establecer el valor del atributo msExchUCVoiceMailSettings en el proceso de habilitar la mensajería unificada de Exchange o durante el proceso de transferencia de buzones a un servidor de Exchange hospedado. Si Exchange no establece este atributo, el administrador de Lync Server 2013 debe establecerlo ejecutando el cmdlet Set-CsUser, tal y como se describió anteriormente en este tema.

En la tabla siguiente se muestran los pares de clave y valor del atributo y sus autores.

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>Pares clave/valor de atributo msExchUCVoiceMailSettings

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valor</th>
<th>Autorización</th>
<th>Significado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>El usuario ha habilitado el acceso a UM hospedado en el servidor de Exchange. La aplicación de enrutamiento de mensajería unificada de Exchange verificará la Directiva de correo de voz hospedada del usuario para ver los detalles de enrutamiento.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>El usuario ha deshabilitado el acceso a UM hospedado por parte de Exchange Server.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>El usuario ha sido habilitado para el acceso a UM hospedado por Lync Server 2013. La aplicación de enrutamiento ExUM de Lync Server 2013 verificará la Directiva de correo de voz hospedada del usuario para ver los detalles de enrutamiento.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013 ha deshabilitado al usuario para el acceso a mensajería unificada hospedada.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Si el atributo ya tiene valores distintos de uno de los pares de clave y valor de Lync Server 2013 (CSHostedVoiceMail = 0 o CSHostedVoiceMail = 1), una advertencia indicará que el atributo puede ser administrado por otra aplicación distinta. Por ejemplo, se muestra una advertencia si el par clave/valor ExchangeHostedVoiceMail = 0 o ExchangeHostedVoiceMail = 1 ya está presente. En ese caso, puede cambiar el valor editándolo en Active Directory o ejecutar el cmdlet siguiente para establecer el valor en NULL:<BR>Set-CsUser-Identity User-HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>Habilitar usuarios para el correo de voz hospedado

Para permitir que las llamadas de correo de voz de un usuario se enruten a la mensajería unificada de Exchange hospedada, debe ejecutar el cmdlet Set-CsUser para establecer el valor del parámetro *HostedVoiceMail* . Este parámetro también indica Lync Server 2013 para que se ilumine el indicador "llamar al correo de voz".

  - En el siguiente ejemplo se habilita la cuenta de usuario de Pilar Ackerman para el correo de voz hospedado:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    El cmdlet verifica que se aplica una directiva de correo de voz hospedada (global, de sitio o por usuario) a este usuario. Si no se aplica ninguna directiva, se produce un error en el cmdlet.

  - En el ejemplo siguiente se deshabilita la cuenta de usuario de Pilar Ackerman para el correo de voz hospedado:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    El cmdlet verifica que no se aplica ninguna directiva de correo de voz hospedada (global, de sitio o por usuario) a este usuario. Si se aplica una directiva, se produce un error en el cmdlet.

Para obtener más información sobre cómo usar el cmdlet Set-CsUser, consulte la documentación del shell de administración de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

