---
title: 'Lync Server 2013: validación de la normalización y el enrutamiento de números de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1be8f09304ccf077eb24daf707e536e9c90f84dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="f5601-102">Validación de la normalización y el enrutamiento de números de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5601-102">Validating voice number normalization and routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5601-103">_**Última modificación del tema:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="f5601-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="f5601-104">Corregir la normalización de números y el enrutamiento es muy importante para un entorno funcional de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="f5601-104">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="f5601-105">Especialmente durante las migraciones desde la central de conmutación (PBX) a un entorno independiente de Lync Server, una de las claves para la migración correcta es mostrar y documentar todas las reglas de marcado existentes y crear reglas de normalización apropiadas, directivas de voz usos y rutas de teléfonos.</span><span class="sxs-lookup"><span data-stu-id="f5601-105">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="f5601-106">Validar la normalización de números y el enrutamiento es importante no solo durante las migraciones, sino también durante el funcionamiento normal y estable del sistema.</span><span class="sxs-lookup"><span data-stu-id="f5601-106">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="f5601-107">Se recomienda realizar esta validación diariamente con el panel de control de Lync Server, empezando por desarrollar un conjunto sólido de casos de prueba en comparación con el conjunto actual de reglas de normalización publicadas en la configuración global de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5601-107">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="f5601-108">Estos casos de prueba deben ejecutarse todos los días para resaltar los cambios no deseados que se hayan realizado y que se hayan confirmado en el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="f5601-108">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="f5601-109">El panel de control de Lync Server también le ayuda a visualizar, probar, cambiar, archivar y compartir información de configuración sobre el enrutamiento de voz y para cambiar las reglas de normalización de números de voz de empresa, los planes de marcado, la Directiva de voz y las rutas.</span><span class="sxs-lookup"><span data-stu-id="f5601-109">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="f5601-110">Tiene características adicionales para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f5601-110">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="f5601-111">Exportar e importar o realizar copias de seguridad de los datos de enrutamiento de voz entre sistemas.</span><span class="sxs-lookup"><span data-stu-id="f5601-111">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="f5601-112">Probar los cambios de configuración antes de cargarlos en un sistema en vivo.</span><span class="sxs-lookup"><span data-stu-id="f5601-112">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="f5601-113">Crear y ejecutar casos de pruebas de configuración para ayudar a garantizar la facilidad de uso de los datos de enrutamiento después de realizar cambios en ellos, pero antes de confirmarlos en un sistema implementado.</span><span class="sxs-lookup"><span data-stu-id="f5601-113">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="f5601-114">Crear y cambiar las reglas de normalización de números, los perfiles de ubicación, la Directiva de voz y los datos de enrutamiento sin escribir las expresiones regulares necesarias.</span><span class="sxs-lookup"><span data-stu-id="f5601-114">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="f5601-115">Analizar un perfil de ubicación para la compatibilidad con la edición telefónica de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5601-115">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="f5601-116">Puede encontrar más información sobre las pruebas de enrutamiento de voz en el [enrutamiento de voz de prueba en Lync Server 2013](lync-server-2013-test-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="f5601-116">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f5601-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5601-117">See Also</span></span>


[<span data-ttu-id="f5601-118">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5601-118">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

