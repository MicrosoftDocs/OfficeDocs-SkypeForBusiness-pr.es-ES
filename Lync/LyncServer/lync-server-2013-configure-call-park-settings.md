---
title: 'Lync Server 2013: configurar la configuración de estacionamiento de llamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee4f12ccf614816e27262f8b393cdc1dac4a7a5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a>Configurar la configuración de estacionamiento de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Si no desea usar la configuración de Parque de llamadas predeterminada, puede personalizarla. Al instalar la aplicación de estacionamiento de llamadas, la configuración global se configura de forma predeterminada. Puede modificar esta configuración global y, además, puede especificar opciones de configuración específicas del sitio. Use el cmdlet **New-CsCpsConfiguration** para crear una nueva configuración específica del sitio. Use cmdlet **Set-CsCpsConfiguration** para modificar la configuración existente.

<div>


> [!NOTE]  
> Como mínimo, se recomienda configurar la opción <STRONG>OnTimeoutURI</STRONG> para el destino de reserva que se usará cuando el tiempo de espera de una llamada estacionada se agote y deje de sonar.



</div>

Use el cmdlet **New-CsCpsConfiguration** o el cmdlet **Set-CsCpsConfiguration** para configurar cualquiera de las opciones siguientes:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Esta opción:</th>
<th>Especifica:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallPickupTimeoutThreshold</strong></p></td>
<td><p>El tiempo que transcurre después de estacionar la llamada hasta que vuelve a sonar en el teléfono en el que se respondió.</p>
<p>El valor debe introducirse con el formato hh:mm:ss para especificar las horas, los minutos y los segundos. El valor mínimo es 10 segundos y el máximo, 10 minutos. El valor predeterminado es 00:01:30.</p></td>
</tr>
<tr class="even">
<td><p><strong>EnableMusicOnHold</strong></p></td>
<td><p>Si la persona que llama escuchará música mientras la llamada está estacionada.</p>
<p>Los valores son True o False. El valor predeterminado es True.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCallPickupAttempts</strong></p></td>
<td><p>El número de veces que una llamada estacionada vuelve a sonar en el teléfono en que se respondió antes de transferirla al identificador uniforme de recursos (URI) de reserva que se especifique para <strong>OnTimeoutURI</strong>. El valor predeterminado es 1.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnTimeoutURI</strong></p></td>
<td><p>La dirección SIP del usuario o grupo de respuesta al que se enruta una llamada estacionada que no se responda cuando se supera el valor de <strong>MaxCallPickupAttempts</strong>.</p>
<p>El valor debe ser un URI de SIP que comience por sip:. Por ejemplo, sip:bob@contoso.com. El valor predeterminado corresponde a sin dirección de transferencia.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a>Para configurar la configuración del parque de llamadas

1.  Inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > Use el cmdlet <STRONG>Get-CsSite</STRONG> para identificar el sitio. Para obtener más información, consulte la documentación del shell de administración de Lync Server.

    
    </div>
    
    Por ejemplo:
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a>Vea también


[Personalizar la música de estacionamiento de llamadas en espera en Lync Server 2013](lync-server-2013-customize-call-park-music-on-hold.md)  


[Nuevo: CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

