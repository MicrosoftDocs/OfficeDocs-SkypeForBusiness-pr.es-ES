---
title: 'Lync Server 2013: comprobar certificados de servidor de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af0a80df18a4fc6e27200d1ac04476fcea798b9b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>Comprobar certificados de servidor de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Programación de verificación</p></td>
<td><p>Cada mes</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet Get-CsCertificate. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet Get-CsCertificate le permite recuperar información acerca de cada uno de los certificados de Lync Server. Esto es especialmente importante porque los certificados tienen una fecha de expiración integrada. Por ejemplo, los certificados emitidos de forma privada normalmente vencen después de 12 meses. Si alguno de los certificados de Lync Server vence, perderá la funcionalidad correspondiente hasta que se renueve o se reemplace el certificado.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para obtener información sobre cada uno de los certificados de Lync Server, simplemente ejecute el siguiente comando:

`Get-CsCertificate`

O bien, puede filtrar la información del certificado devuelto según la fecha de expiración. Por ejemplo, este comando limita los datos devueltos a certificados que vencen (no se pueden usar después) 1 de junio de 2014:

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

Para obtener más información, consulte la documentación de ayuda del cmdlet Get-CsCertificate.

Tenga en cuenta que, aunque exista el cmdlet test-CsCertificateConfiguration, no es muy útil para los administradores. (En su lugar, el Asistente de certificados usa principalmente ese cmdlet). Aunque el cmdlet funcione, la información que devuelve es de un valor mínimo, tal y como se muestra en el siguiente ejemplo de salida:

Uso de la huella digital

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 predeterminado

</div>

<div>

## <a name="reviewing-the-output"></a>Revisar la salida

El cmdlet Get-CsCertificate devuelve información similar a la siguiente para cada uno de los certificados de Lync Server:

Emisor: CN = FabrikamCA

Nopérezer: 12/28/2015 3:35:41 PM

NotBefore: 1/2/2014 12:49:37 PM

SerialNumber: 611BB01200000000000C

Asunto: CN = LYNC-SE.fabrikam.com

AlternativeNames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,

meet.fabrikam.com, admin.fabrikam.com...}

Huella digital: A9D51A2911C74FABFF7F2A8A994B20857D399107

Uso: predeterminado

Como regla general, los principales problemas relacionados con los certificados de Lync Server incluyen fechas y horas, como cuando los certificados surten efecto (NotBefore) o cuando vencen (novalente). Como estas fechas y horas son tan importantes, es posible que desee limitar los datos devueltos a información como el uso de certificados, el número de serie del certificado y la fecha de expiración del certificado; después, puede revisar rápidamente todos los certificados y cuándo vencerán. Para obtener solo esa información, use el comando junto con las opciones que se muestran:

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

Ese comando devuelve datos similares a los siguientes, con los certificados ordenados por su fecha de expiración:

Usar SerialNumber alpérezer

\--- ------------ --------

611BB01200000000000C predeterminados 12/28/2015 3:35:41 P.M.

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

Si tiene problemas con el certificado, es posible que desee revisar el AlternativeNames configurado para un certificado. A primera vista, parece ser un problema. De forma predeterminada, y según el tamaño de la ventana de la consola, Get-CsCertificate podría no mostrar todos los nombres:

AlternativeNames: {sip.fabrikam.com, LYNC.fabrikam.com,

meet.fabrikam.com, admin. Fabrika...}

Para ver todos los nombres alternativos asignados a un certificado, use un comando similar a este:

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

Que le mostrarán todos los nombres alternativos en el certificado:

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>Vea también


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

