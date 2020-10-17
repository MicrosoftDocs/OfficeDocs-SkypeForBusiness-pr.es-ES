---
title: Los cmdlets de informes de Skype empresarial online y el servicio Web REST
description: Los cmdlets de informes de Skype empresarial online y el servicio Web REST.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2160e0910d42f811ec8b03fa50450d5f73c59b1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567946"
---
# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="b58b8-103">Los cmdlets de informes de Skype empresarial online y el servicio Web REST</span><span class="sxs-lookup"><span data-stu-id="b58b8-103">The Skype for Business Online reporting cmdlets and REST web service</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b58b8-104">_**Última modificación del tema:** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="b58b8-104">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="b58b8-105">Junto con las características de informes, Skype empresarial online ofrece acceso a cinco cmdlets de Windows PowerShell que ayudan a generar esos informes y los administradores también pueden usarlos para devolver datos de informes personalizados.</span><span class="sxs-lookup"><span data-stu-id="b58b8-105">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="b58b8-106">Skype empresarial online también incluye el resto (transferencia de estado representacional), que los desarrolladores pueden usar para recuperar información de informes personalizada.</span><span class="sxs-lookup"><span data-stu-id="b58b8-106">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="b58b8-107">Los cmdlets de informes disponibles para los administradores incluyen:</span><span class="sxs-lookup"><span data-stu-id="b58b8-107">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="b58b8-108">Get-CsActiveUserReport, que proporciona información sobre el número de usuarios activos (es decir, los usuarios que han iniciado sesión en Skype empresarial online y que participaron como mínimo en una conferencia o en una sesión de comunicación punto a punto).</span><span class="sxs-lookup"><span data-stu-id="b58b8-108">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="b58b8-109">Get-CsAVConferenceTimeReport, que proporciona información sobre la cantidad de tiempo (en minutos) que dedican los usuarios a las conferencias de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="b58b8-109">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="b58b8-110">Get-CsConferenceReport, que proporciona información sobre el número y el tipo de conferencias en las que participaron los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b58b8-110">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="b58b8-111">Get-CsP2PAVTimeReport, que proporciona información sobre la cantidad de tiempo (en minutos) que dedican los usuarios a sesiones punto a punto que incluían audio o vídeo.</span><span class="sxs-lookup"><span data-stu-id="b58b8-111">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="b58b8-112">Get-CsP2PSessionReport, que proporciona información sobre el número y el tipo de sesiones de punto a punto en las que participaron los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b58b8-112">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="b58b8-113">La mayoría de los administradores usarán los informes disponibles en el centro de administración de Microsoft 365: no solo estos informes se generan automáticamente, sino que también proporcionan una representación gráfica de los datos que a menudo es más fácil de interpretar que los valores de número sin formato devueltos por los cmdlets de informes.</span><span class="sxs-lookup"><span data-stu-id="b58b8-113">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="b58b8-114">Sin embargo, los administradores familiarizados con Windows PowerShell pueden usar los cmdlets de informes para devolver datos que no están disponibles de forma legible desde los informes de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="b58b8-114">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="b58b8-115">Por ejemplo, los cmdlets de informes devuelven información sobre la duración de la sesión (la cantidad de tiempo, en minutos, que duró cada sesión).</span><span class="sxs-lookup"><span data-stu-id="b58b8-115">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="b58b8-116">Las duraciones de sesión individuales no están disponibles mediante los informes de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="b58b8-116">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="b58b8-117">Del mismo modo, en vista diaria los informes de Lync Online solo muestran información para los 14 días anteriores.</span><span class="sxs-lookup"><span data-stu-id="b58b8-117">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="b58b8-118">Si desea revisar los totales diarios de un día diferente (por ejemplo, una fecha de hace cuatro meses), puede hacerlo con los cmdlets de informes.</span><span class="sxs-lookup"><span data-stu-id="b58b8-118">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="b58b8-119">Los administradores también pueden estar interesados en el artículo [usar Excel para recuperar datos de informes de office 365](https://msdn.microsoft.com/library/dn781442.aspx), donde se explica cómo usar la característica de consulta de datos de oData en Microsoft Excel para crear un informe personalizado de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b58b8-119">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](https://msdn.microsoft.com/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="b58b8-120">Los informes personalizados le proporcionan la capacidad de dictar qué datos (y cuántos datos) se devuelven del servicio de informes de Office 365.</span><span class="sxs-lookup"><span data-stu-id="b58b8-120">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="b58b8-121">Los informes personalizados también le permiten especificar cómo deben ordenarse y agruparse los datos, así como proporcionar acceso a la información que no se muestra en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="b58b8-121">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="b58b8-122">Los administradores con un fondo de desarrollo pueden usar el servicio Web REST para obtener información que no se muestra en el centro de administración de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="b58b8-122">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="b58b8-123">El servicio REST es similar al servicio SOAP, en el que cada tecnología proporciona una forma de transferir datos XML entre un cliente y un servidor.</span><span class="sxs-lookup"><span data-stu-id="b58b8-123">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="b58b8-124">Sin embargo, el servicio REST tiene al menos dos ventajas sobre el servicio SOAP.</span><span class="sxs-lookup"><span data-stu-id="b58b8-124">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="b58b8-125">Para uno, REST realiza transferencias de datos XML con un formato estandarizado conocido como formato de sindicación ATOM.</span><span class="sxs-lookup"><span data-stu-id="b58b8-125">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="b58b8-126">Por el contrario, SOAP usa un formato no estándar al transferir datos.</span><span class="sxs-lookup"><span data-stu-id="b58b8-126">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="b58b8-127">Además, REST puede transferir datos a través de redes que bloquean verbos HTTP distintos de GET y POST.</span><span class="sxs-lookup"><span data-stu-id="b58b8-127">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b58b8-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b58b8-128">See Also</span></span>


<span data-ttu-id="b58b8-129">[Informes de Lync Online](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b58b8-129">[Lync Online reporting](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="b58b8-130">El servicio Web de informes de Office 365</span><span class="sxs-lookup"><span data-stu-id="b58b8-130">The Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[<span data-ttu-id="b58b8-131">Información sobre el servicio Web de informes de Office 365</span><span class="sxs-lookup"><span data-stu-id="b58b8-131">Learning About the Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984321.aspx)  
<span data-ttu-id="b58b8-132">[Cmdlets de informes de Exchange Online](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="b58b8-132">[The Exchange Online Reporting Cmdlets](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="b58b8-133">Uso de Excel para recuperar datos de informes de Office 365</span><span class="sxs-lookup"><span data-stu-id="b58b8-133">Using Excel to Retrieve Office 365 Reporting Data</span></span>](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

