---
title: Los cmdlets de informes de Skype empresarial online y el servicio Web REST
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9046bb075fba832f0ba7c83697c96a285988fcf7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Los cmdlets de informes de Skype empresarial online y el servicio Web REST

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-09-05_

Junto con las características de informes, Skype empresarial online ofrece acceso a cinco cmdlets de Windows PowerShell que ayudan a generar esos informes y los administradores también pueden usarlos para devolver datos de informes personalizados. Skype empresarial online también incluye el resto (transferencia de estado representacional), que los desarrolladores pueden usar para recuperar información de informes personalizada.

Los cmdlets de informes disponibles para los administradores incluyen:

  - Get-CsActiveUserReport, que proporciona información sobre el número de usuarios activos (es decir, los usuarios que han iniciado sesión en Skype empresarial online y que participaron como mínimo en una conferencia o en una sesión de comunicación punto a punto).

  - Get-CsAVConferenceTimeReport, que proporciona información sobre la cantidad de tiempo (en minutos) que dedican los usuarios a las conferencias de audio y vídeo.

  - Get-CsConferenceReport, que proporciona información sobre el número y el tipo de conferencias en las que participaron los usuarios.

  - Get-CsP2PAVTimeReport, que proporciona información sobre la cantidad de tiempo (en minutos) que dedican los usuarios a sesiones punto a punto que incluían audio o vídeo.

  - Get-CsP2PSessionReport, que proporciona información sobre el número y el tipo de sesiones de punto a punto en las que participaron los usuarios.

La mayoría de los administradores usarán los informes disponibles en el centro de administración de 365 de Microsoft: no solo esos informes se generan automáticamente, sino que también proporcionan una representación gráfica de los datos que a menudo es más fácil de interpretar que los valores de número sin formato devueltos por el cmdlets de informes. Sin embargo, los administradores familiarizados con Windows PowerShell pueden usar los cmdlets de informes para devolver datos que no están disponibles de forma legible desde los informes de Lync Online. Por ejemplo, los cmdlets de informes devuelven información sobre la duración de la sesión (la cantidad de tiempo, en minutos, que duró cada sesión). Las duraciones de sesión individuales no están disponibles mediante los informes de Lync Online. Del mismo modo, en vista diaria los informes de Lync Online solo muestran información para los 14 días anteriores. Si desea revisar los totales diarios de un día diferente (por ejemplo, una fecha de hace cuatro meses), puede hacerlo con los cmdlets de informes.

Los administradores también pueden estar interesados en el artículo [usar Excel para recuperar datos de informes de office 365](http://msdn.microsoft.com/library/dn781442.aspx), donde se explica cómo usar la característica de consulta de datos de oData en Microsoft Excel para crear un informe personalizado de Office 365. Los informes personalizados le proporcionan la capacidad de dictar qué datos (y cuántos datos) se devuelven del servicio de informes de Office 365. Los informes personalizados también le permiten especificar cómo deben ordenarse y agruparse los datos, así como proporcionar acceso a la información que no se muestra en el centro de administración.

Los administradores con un fondo de desarrollo pueden usar el servicio Web REST para obtener información que no se muestra en el centro de administración de Skype empresarial online. El servicio REST es similar al servicio SOAP, en el que cada tecnología proporciona una forma de transferir datos XML entre un cliente y un servidor. Sin embargo, el servicio REST tiene al menos dos ventajas sobre el servicio SOAP. Para uno, REST realiza transferencias de datos XML con un formato estandarizado conocido como formato de sindicación ATOM. Por el contrario, SOAP usa un formato no estándar al transferir datos. Además, REST puede transferir datos a través de redes que bloquean verbos HTTP distintos de GET y POST.

<div>

## <a name="see-also"></a>Vea también


[Informes de Lync Online](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))  


[El servicio Web de informes de Office 365](http://msdn.microsoft.com/library/office/jj984325.aspx)  
[Información sobre el servicio Web de informes de Office 365](http://msdn.microsoft.com/library/office/jj984321.aspx)  
[Cmdlets de informes de Exchange Online](http://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)  
[Uso de Excel para recuperar datos de informes de Office 365](http://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

