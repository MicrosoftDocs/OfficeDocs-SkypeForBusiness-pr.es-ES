---
title: Cmdlet de informes y servicio Web REST de Skype empresarial online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a140ed48ac662daea14d602f0830b2fbc4bf1c05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Cmdlet de informes y servicio Web REST de Skype empresarial online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-09-05_

Junto con las características de informes, Skype empresarial online proporciona acceso a cinco cmdlets de Windows PowerShell que ayudan a generar esos informes y los administradores también pueden usarlos para devolver datos de informes personalizados. Skype empresarial online también incluye el resto (transferencia de estado representacional), que los desarrolladores pueden usar para recuperar información de informes personalizada.

Los cmdlets de informes disponibles para los administradores son:

  - Get-CsActiveUserReport, que proporciona información sobre el número de usuarios activos (es decir, usuarios que han iniciado sesión en Skype empresarial online y participaron como mínimo en una conferencia o en una sesión de comunicación punto a punto).

  - Get-CsAVConferenceTimeReport, que proporciona información acerca de la cantidad de tiempo (en minutos) que transcurren los usuarios en conferencias de audio o vídeo.

  - Get-CsConferenceReport, que proporciona información sobre el número y el tipo de conferencias en las que participaron los usuarios.

  - Get-CsP2PAVTimeReport, que proporciona información acerca de la cantidad de tiempo (en minutos) que los usuarios invirtieron en sesiones de punto a punto que incluían audio o vídeo.

  - Get-CsP2PSessionReport, que proporciona información sobre el número y el tipo de sesiones de punto a punto en las que participaron los usuarios.

La mayoría de los administradores usarán los informes disponibles en el centro de administración de Office 365: no solo se generan automáticamente esos informes, sino que también proporcionan una representación gráfica de los datos que a menudo es más fácil de interpretar que los valores de número sin formato devueltos por el cmdlets de informes. Sin embargo, los administradores familiarizados con Windows PowerShell pueden usar los cmdlets de informes para devolver datos que no se encuentran disponibles en los informes de Lync Online. Por ejemplo, los cmdlets de informes devuelven información sobre la duración de la sesión (la cantidad de tiempo, en minutos, que dura cada sesión). Las duraciones de las sesiones individuales no están disponibles con los informes de Lync Online. Del mismo modo, en la vista diaria los informes de Lync Online solo muestran información para los 14 días anteriores. Si desea revisar los totales diarios de un día diferente (por ejemplo, una fecha de hace cuatro meses) puede hacerlo usando los cmdlets de informes.

Los administradores también pueden estar interesados en el artículo [usar Excel para recuperar datos de informes de office 365](http://msdn.microsoft.com/en-us/library/dn781442.aspx), donde se explica cómo usar la característica de consulta de datos de oData en Microsoft Excel para crear un informe personalizado de Office 365. Los informes personalizados le ofrecen la posibilidad de dictar qué datos (y la cantidad de datos) se devuelven desde el servicio de informes de Office 365. Los informes personalizados también le permiten especificar cómo se deben ordenar y agrupar los datos, así como proporcionar acceso a la información que no se muestra en el centro de administración de Office 365.

Los administradores con un fondo de desarrollo pueden usar el servicio Web REST para obtener información que no se muestra en el centro de administración de Skype empresarial online. El servicio REST es similar al servicio SOAP, ya que cada tecnología proporciona una manera de transferir datos XML entre un cliente y un servidor. Sin embargo, el servicio REST tiene al menos dos ventajas en comparación con el servicio SOAP. En el caso de uno, REST realiza transferencias de datos XML con un formato estandarizado conocido como formato de sindicación ATOM. Por el contrario, SOAP usa un formato no estándar al transferir datos. Además, REST puede transferir datos a través de redes que bloqueen verbos HTTP distintos de GET y POST.

<div>

## <a name="see-also"></a>Vea también


[Informes de Lync Online](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))  


[El servicio Web de informes de Office 365](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[Información sobre el servicio Web de informes de Office 365](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
[Cmdlets de informes de Exchange Online](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)  
[Usar Excel para recuperar datos de informes de Office 365](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

