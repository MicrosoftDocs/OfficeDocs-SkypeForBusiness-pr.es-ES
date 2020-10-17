---
title: 'Lync Server 2013: validación de la normalización y el enrutamiento de números de voz'
description: 'Lync Server 2013: validación de la normalización y el enrutamiento de los números de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating voice number normalization and routing
ms:assetid: a6a825c7-6928-4e80-b7e9-803b7f7ebd13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720922(v=OCS.15)
ms:contentKeyID: 63969633
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f28f679cbb991bdb90362eb61c9c7b68879791e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547146"
---
# <a name="validating-voice-number-normalization-and-routing-in-lync-server-2013"></a><span data-ttu-id="551ed-103">Validación de la normalización y el enrutamiento de los números de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="551ed-103">Validating voice number normalization and routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="551ed-104">_**Última modificación del tema:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="551ed-104">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="551ed-105">La normalización y el enrutamiento de los números son muy importantes para el entorno funcional de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="551ed-105">Correct number normalization and routing is very important for functional Enterprise Voice environment.</span></span> <span data-ttu-id="551ed-106">Especialmente durante las migraciones desde una central de conmutación (PBX) a un entorno independiente de Lync Server, una de las claves para una migración correcta es mostrar y documentar todas las reglas de marcado existentes y crear reglas de normalización apropiadas, directivas de voz, usos de teléfono y rutas.</span><span class="sxs-lookup"><span data-stu-id="551ed-106">Especially during migrations from private branch exchange (PBX) to stand-alone Lync Server environment, one of the keys to successful migration is to reveal and document all existing dialing rules, and create appropriate normalization rules, voice policies, phone usages and routes.</span></span>

<span data-ttu-id="551ed-107">Validar la normalización y el enrutamiento de números es importante no solo durante las migraciones, sino también durante el funcionamiento normal y estable del sistema.</span><span class="sxs-lookup"><span data-stu-id="551ed-107">Validating number normalization and routing is important not only during migrations but also during normal, stable operation of the system.</span></span>

<span data-ttu-id="551ed-108">Se recomienda realizar esta validación diariamente mediante el panel de control de Lync Server, comenzando con el desarrollo de un conjunto sólido de casos de prueba en comparación con el conjunto actual de reglas de normalización que se publicaron en la configuración global de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="551ed-108">We recommend conducting this validation daily by using the Lync Server Control Panel, starting with developing a robust set of test cases against the current set of normalization rules that were published in the Lync Server global settings.</span></span> <span data-ttu-id="551ed-109">Estos casos de prueba deben ejecutarse diariamente para resaltar los cambios no deseados que se han realizado y confirmado en el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="551ed-109">These test cases should be run daily to highlight any unwanted changes that were made and committed to the dial plan.</span></span>

<span data-ttu-id="551ed-110">El panel de control de Lync Server también le ayuda a visualizar, probar, cambiar, archivar y compartir información de configuración sobre el enrutamiento de voz y el cambio de reglas de normalización de números de telefonía IP empresarial, planes de marcado, Directiva de voz y rutas.</span><span class="sxs-lookup"><span data-stu-id="551ed-110">Lync Server Control Panel also helps you visualize, test, change, archive, and share configuration information about voice routing and in changing Enterprise Voice number normalization rules, dial plans, voice policy, and routes.</span></span> <span data-ttu-id="551ed-111">Tiene características adicionales para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="551ed-111">It has additional features for doing the following:</span></span>

  - <span data-ttu-id="551ed-112">Exportar e importar o realizar copias de seguridad de datos de enrutamiento de voz entre sistemas.</span><span class="sxs-lookup"><span data-stu-id="551ed-112">Exporting and importing or backing up voice routing data between systems.</span></span>

  - <span data-ttu-id="551ed-113">Probar los cambios de configuración antes de cargarlos en un sistema activo.</span><span class="sxs-lookup"><span data-stu-id="551ed-113">Testing configuration changes before uploading them to a live system.</span></span>

  - <span data-ttu-id="551ed-114">Crear y ejecutar casos de prueba de configuración para ayudar a garantizar la facilidad de uso de los datos de enrutamiento después de realizar cambios en él, pero antes de confirmarlos en un sistema implementado.</span><span class="sxs-lookup"><span data-stu-id="551ed-114">Creating and running configuration test cases to help ensure the usability of routing data after you make changes to it, but before committing them the changes to a deployed system.</span></span>

  - <span data-ttu-id="551ed-115">Crear y cambiar las reglas de normalización de números, los perfiles de ubicación, la Directiva de voz y los datos de enrutamiento sin escribir las expresiones regulares necesarias.</span><span class="sxs-lookup"><span data-stu-id="551ed-115">Creating and changing number normalization rules, location profiles, voice policy, and routing data without writing the necessary regular expressions.</span></span>

  - <span data-ttu-id="551ed-116">Analizar un perfil de ubicación para que sea compatible con Lync Server Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="551ed-116">Analyzing a location profile for compatibility with the Lync Server Phone Edition.</span></span>

  - <span data-ttu-id="551ed-117">Puede encontrar más información sobre las pruebas de enrutamiento de voz en [probar el enrutamiento de voz en Lync Server 2013](lync-server-2013-test-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="551ed-117">More information about voice routing tests can be found at [Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="551ed-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="551ed-118">See Also</span></span>


[<span data-ttu-id="551ed-119">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="551ed-119">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

