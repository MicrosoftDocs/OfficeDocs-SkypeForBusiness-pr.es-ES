---
title: 'Lync Server 2013: incluir el Departamento de seguridad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99f35087d03b046fade741140dc3f5522e6c6d05
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="b73aa-102">Incluir el Departamento de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b73aa-102">Including the security desk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b73aa-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b73aa-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b73aa-p101">Puede que su compañía requiera que el departamento de seguridad participe en una llamada de emergencia. Para ayudarle a decidir cómo integrar el departamento de seguridad en la implementación de E9-1-1, deberá responder a las preguntas que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="b73aa-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="b73aa-106">**¿Desea que el departamento de seguridad reciba una notificación cuando haya una llamada de emergencia?**</span><span class="sxs-lookup"><span data-stu-id="b73aa-106">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="b73aa-107">Puede configurar la Directiva de ubicación para que Lync Server envíe alertas de mensajería instantánea (mi) a las direcciones SIP de Lync de uno o más personal de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b73aa-107">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="b73aa-108">Entonces el departamento de seguridad puede confirmar que hay una emergencia.</span><span class="sxs-lookup"><span data-stu-id="b73aa-108">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="b73aa-109">**¿Desea que el departamento de seguridad establezca una conferencia en todas las llamadas de emergencia?**</span><span class="sxs-lookup"><span data-stu-id="b73aa-109">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="b73aa-p103">En el caso de que el proveedor de servicios de emergencia lo permita, puede configurar la directiva de ubicación para incluir un número de devolución de llamada ante cada llamada de emergencia. Este número lo usa después el proveedor para que el personal de seguridad establezca una conferencia en cada llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="b73aa-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b73aa-p104">En caso necesario, puede configurar personal de emergencia diferente para cada directiva de ubicación. Esto permite personalizar la respuesta para las diferentes áreas de su empresa o crear un comportamiento diferente para llamadas de emergencia originadas en el interior en contraposición con las realizadas en el exterior de la red. Puede usar grupos de distribución para especificar el personal al que desea notificar.</span><span class="sxs-lookup"><span data-stu-id="b73aa-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

