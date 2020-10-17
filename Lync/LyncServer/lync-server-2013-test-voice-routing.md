---
title: 'Lync Server 2013: probar el enrutamiento de voz'
description: 'Lync Server 2013: probar el enrutamiento de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e641e68ccecfe7d1d0e64dc9eb1b1f5016e68e22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567246"
---
# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="11f93-103">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11f93-103">Test voice routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11f93-104">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="11f93-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="11f93-105">Puede usar la ficha probar el enrutamiento de **voz** del panel de control de Lync Server para configurar escenarios de casos de prueba.</span><span class="sxs-lookup"><span data-stu-id="11f93-105">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="11f93-106">Para definir un caso de prueba, se especifica el plan de marcado, la directiva de voz, el uso de la RTC y la ruta de voz que se van a usar para probar un número de teléfono específico.</span><span class="sxs-lookup"><span data-stu-id="11f93-106">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="11f93-107">Antes de implementar realmente la configuración de enrutamiento de voz, le recomendamos que la pruebe con varios números de teléfono para asegurarse de que los resultados son lo que esperaba.</span><span class="sxs-lookup"><span data-stu-id="11f93-107">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="11f93-108">Puede usar los comandos <STRONG>Exportar casos de prueba</STRONG> e <STRONG>Importar casos de prueba</STRONG> para guardar los casos de prueba de enrutamiento de voz e importarlos para su uso en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="11f93-108">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="11f93-109">Si ha eliminado cualquier parte de la configuración del enrutamiento de voz, como un plan de marcado, directiva de voz, ruta de voz o uso de un teléfono, debe comprobar y actualizar los casos de prueba del enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="11f93-109">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="11f93-110">El panel de control de Lync Server no le avisará de los casos de prueba que ya no son válidos debido a configuraciones modificadas.</span><span class="sxs-lookup"><span data-stu-id="11f93-110">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="11f93-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="11f93-111">In This Section</span></span>

  - [<span data-ttu-id="11f93-112">Crear un caso de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11f93-112">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="11f93-113">Exportar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11f93-113">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="11f93-114">Importar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11f93-114">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="11f93-115">Ejecución de pruebas de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11f93-115">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

