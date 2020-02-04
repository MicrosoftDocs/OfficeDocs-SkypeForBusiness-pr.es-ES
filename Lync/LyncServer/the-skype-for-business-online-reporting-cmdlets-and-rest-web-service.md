---
title: Cmdlet de informes y servicio Web REST de Skype empresarial online
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
ms.openlocfilehash: bf02e845acc35ff4381b43beb91d798ec49f58d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="69a7c-102">Cmdlet de informes y servicio Web REST de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="69a7c-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69a7c-103">_**Última modificación del tema:** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="69a7c-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="69a7c-104">Junto con las características de informes, Skype empresarial online proporciona acceso a cinco cmdlets de Windows PowerShell que ayudan a generar esos informes y los administradores también pueden usarlos para devolver datos de informes personalizados.</span><span class="sxs-lookup"><span data-stu-id="69a7c-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="69a7c-105">Skype empresarial online también incluye el resto (transferencia de estado representacional), que los desarrolladores pueden usar para recuperar información de informes personalizada.</span><span class="sxs-lookup"><span data-stu-id="69a7c-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="69a7c-106">Los cmdlets de informes disponibles para los administradores son:</span><span class="sxs-lookup"><span data-stu-id="69a7c-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="69a7c-107">Get-CsActiveUserReport, que proporciona información sobre el número de usuarios activos (es decir, usuarios que han iniciado sesión en Skype empresarial online y participaron como mínimo en una conferencia o en una sesión de comunicación punto a punto).</span><span class="sxs-lookup"><span data-stu-id="69a7c-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="69a7c-108">Get-CsAVConferenceTimeReport, que proporciona información acerca de la cantidad de tiempo (en minutos) que transcurren los usuarios en conferencias de audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="69a7c-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="69a7c-109">Get-CsConferenceReport, que proporciona información sobre el número y el tipo de conferencias en las que participaron los usuarios.</span><span class="sxs-lookup"><span data-stu-id="69a7c-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="69a7c-110">Get-CsP2PAVTimeReport, que proporciona información acerca de la cantidad de tiempo (en minutos) que los usuarios invirtieron en sesiones de punto a punto que incluían audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="69a7c-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="69a7c-111">Get-CsP2PSessionReport, que proporciona información sobre el número y el tipo de sesiones de punto a punto en las que participaron los usuarios.</span><span class="sxs-lookup"><span data-stu-id="69a7c-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="69a7c-112">La mayoría de los administradores usarán los informes disponibles en el centro de administración de Microsoft 365: no solo se generan automáticamente esos informes, sino que también proporcionan una representación gráfica de los datos que a menudo es más fácil de interpretar que los valores de número sin formato devueltos por el cmdlets de informes.</span><span class="sxs-lookup"><span data-stu-id="69a7c-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="69a7c-113">Sin embargo, los administradores familiarizados con Windows PowerShell pueden usar los cmdlets de informes para devolver datos que no se encuentran disponibles en los informes de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="69a7c-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="69a7c-114">Por ejemplo, los cmdlets de informes devuelven información sobre la duración de la sesión (la cantidad de tiempo, en minutos, que dura cada sesión).</span><span class="sxs-lookup"><span data-stu-id="69a7c-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="69a7c-115">Las duraciones de las sesiones individuales no están disponibles con los informes de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="69a7c-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="69a7c-116">Del mismo modo, en la vista diaria los informes de Lync Online solo muestran información para los 14 días anteriores.</span><span class="sxs-lookup"><span data-stu-id="69a7c-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="69a7c-117">Si desea revisar los totales diarios de un día diferente (por ejemplo, una fecha de hace cuatro meses) puede hacerlo usando los cmdlets de informes.</span><span class="sxs-lookup"><span data-stu-id="69a7c-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="69a7c-118">Los administradores también pueden estar interesados en el artículo [usar Excel para recuperar datos de informes de office 365](http://msdn.microsoft.com/en-us/library/dn781442.aspx), donde se explica cómo usar la característica de consulta de datos de oData en Microsoft Excel para crear un informe personalizado de Office 365.</span><span class="sxs-lookup"><span data-stu-id="69a7c-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](http://msdn.microsoft.com/en-us/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="69a7c-119">Los informes personalizados le ofrecen la posibilidad de dictar qué datos (y la cantidad de datos) se devuelven desde el servicio de informes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="69a7c-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="69a7c-120">Los informes personalizados también le permiten especificar cómo se deben ordenar y agrupar los datos, así como proporcionar acceso a la información que no se muestra en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="69a7c-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="69a7c-121">Los administradores con un fondo de desarrollo pueden usar el servicio Web REST para obtener información que no se muestra en el centro de administración de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="69a7c-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="69a7c-122">El servicio REST es similar al servicio SOAP, ya que cada tecnología proporciona una manera de transferir datos XML entre un cliente y un servidor.</span><span class="sxs-lookup"><span data-stu-id="69a7c-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="69a7c-123">Sin embargo, el servicio REST tiene al menos dos ventajas en comparación con el servicio SOAP.</span><span class="sxs-lookup"><span data-stu-id="69a7c-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="69a7c-124">En el caso de uno, REST realiza transferencias de datos XML con un formato estandarizado conocido como formato de sindicación ATOM.</span><span class="sxs-lookup"><span data-stu-id="69a7c-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="69a7c-125">Por el contrario, SOAP usa un formato no estándar al transferir datos.</span><span class="sxs-lookup"><span data-stu-id="69a7c-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="69a7c-126">Además, REST puede transferir datos a través de redes que bloqueen verbos HTTP distintos de GET y POST.</span><span class="sxs-lookup"><span data-stu-id="69a7c-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="69a7c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="69a7c-127">See Also</span></span>


<span data-ttu-id="69a7c-128">[Informes de Lync Online](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="69a7c-128">[Lync Online reporting](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="69a7c-129">El servicio Web de informes de Office 365</span><span class="sxs-lookup"><span data-stu-id="69a7c-129">The Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[<span data-ttu-id="69a7c-130">Información sobre el servicio Web de informes de Office 365</span><span class="sxs-lookup"><span data-stu-id="69a7c-130">Learning About the Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
<span data-ttu-id="69a7c-131">[Cmdlets de informes de Exchange Online](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="69a7c-131">[The Exchange Online Reporting Cmdlets](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="69a7c-132">Usar Excel para recuperar datos de informes de Office 365</span><span class="sxs-lookup"><span data-stu-id="69a7c-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

