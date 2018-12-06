---
title: 'Lync Server 2013: Administración de usuarios de Hosted Exchange'
TOCTitle: Administración de usuarios de Hosted Exchange
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48277025
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administración de usuarios de Hosted Exchange en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Para proporcionar servicios de correo de voz para usuarios de Lync Server 2013 cuyos buzones de correo se encuentren en un servicio de Exchange hospedado, habilite sus cuentas de usuario para el correo de voz hospedado.


> [!NOTE]
> Antes de habilitar a un usuario de Lync Server 2013 para correo de voz hospedado, implemente una directiva de correo de voz hospedada que se aplique a la cuenta de usuario correspondiente. La directiva puede ser de ámbito global, de sitio o de usuario, siempre y cuando se aplique al usuario que desea habilitar. Para más información, vea <A href="lync-server-2013-hosted-voice-mail-policies.md">Directivas de correo de voz hospedado en Lync Server 2013</A>.



## El atributo msExchUCVoiceMailSettings

Lync Server 2013 incorpora un nuevo atributo de usuario denominado **msExchUCVoiceMailSettings**, que se crea como parte de la preparación del esquema de Active Directory de Lync Server 2013. Este atributo de varios valores contiene parámetros de correo de voz que comparten Lync Server 2013 y el servicio de Exchange hospedado.

En algunos casos, el servicio de Exchange hospedado puede definir el valor del atributo msExchUCVoiceMailSettings durante el proceso de habilitación de la mensajería unificada de Exchange, o bien durante el proceso de transferencia de buzones de correo a un servidor hospedado de Exchange Server. Si Exchange no define este atributo, tendrá que definirlo el administrador de Lync Server 2013 ejecutando el cmdlet Set-CsUser, tal y como se ha descrito anteriormente en este tema.

En la tabla a continuación se muestran los pares clave/valor del atributo y sus autores.

### Los pares clave/valor del atributo msExchUCVoiceMailSettings

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
<td><p>ExchangeHostedVoiceMail=1</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server ha habilitado al usuario para el acceso a la mensajería unificada hospedada. La aplicación de enrutamiento Mensajería unificada de Exchange examinará la directiva de correo de voz hospedado del usuario en busca de detalles de enrutamiento.</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail=0</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server ha deshabilitado al usuario para el acceso a la mensajería unificada hospedada.</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail=1</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013 ha habilitado al usuario para el acceso a la mensajería unificada hospedada. La aplicación Lync Server 2013 ExUM Routing examinará la directiva de correo de voz hospedado del usuario en busca de detalles de enrutamiento.</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail=0</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013 ha deshabilitado al usuario para el acceso a la mensajería unificada hospedada.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Si el atributo ya tiene valores distintos a uno de los pares clave/valor de Lync Server 2013 (CSHostedVoiceMail=0 o CSHostedVoiceMail=1), aparecerá una advertencia indicando que es posible que el atributo sea administrado por otra aplicación. Por ejemplo, se muestra una advertencia si el par clave/valor ExchangeHostedVoiceMail=0 o ExchangeHostedVoiceMail=1 ya está presente. En tal caso, puede cambiar el valor editándolo en Active Directory, o bien ejecute el cmdlet siguiente para definir el valor como nulo:<BR>Set-CsUser –identity user –HostedVoicemail $null



## Habilitación de usuarios para correo de voz hospedado

Para habilitar las llamadas de correo de voz de un usuario para que se redirijan a la mensajería unificada hospedada de Exchange, ejecute el cmdlet Set-CsUser para definir el valor del parámetro *HostedVoiceMail* . Este parámetro también indica a Lync Server 2013 que encienda el indicador de “Llamar al correo de voz”.

  - En el ejemplo siguiente se habilita la cuenta de usuario de Pilar Ackerman para correo de voz hospedado:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    El cmdlet comprueba que una directiva de correo de voz hospedado (global, de nivel de sitio o por usuario) se aplique al usuario. Si no se aplica ninguna directiva, el cmdlet no se completará correctamente.

  - En el ejemplo siguiente se deshabilita la cuenta de usuario de Pilar Ackerman para correo de voz hospedado:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    El cmdlet comprueba que ninguna directiva de correo de voz hospedado (global, de nivel de sitio o por usuario) se aplique al usuario. Si se aplica alguna directiva, el cmdlet no se completará correctamente.

Para ver los detalles sobre cómo usar el cmdlet Set-CsUser, vea la documentación del Shell de administración de Lync Server.

