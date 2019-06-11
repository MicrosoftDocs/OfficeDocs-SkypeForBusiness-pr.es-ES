---
title: 'Lync Server 2013: ejecutar la ruta de voz casos de prueba'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cded8f3bf44388103ccf5a33507973817de45ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="cbf42-102">Ejecutar los casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbf42-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbf42-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="cbf42-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="cbf42-104">Puede ejecutar todos los casos de prueba en el conjunto de casos de prueba de enrutamiento de voz, o bien puede ejecutar uno o varios casos de prueba seleccionados.</span><span class="sxs-lookup"><span data-stu-id="cbf42-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="cbf42-105">Para ejecutar todos los casos de prueba de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="cbf42-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="cbf42-106">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cbf42-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="cbf42-107">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cbf42-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="cbf42-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cbf42-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cbf42-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cbf42-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cbf42-110">En la barra de navegación izquierda, haga clic en **enrutamiento de voz** y luego en **probar enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="cbf42-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="cbf42-111">En la página **probar enrutamiento de voz** , haga clic en **acción** y, a continuación, en **ejecutar todo**.</span><span class="sxs-lookup"><span data-stu-id="cbf42-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="cbf42-112">El estado de paso o error de cada caso de prueba se muestra en la columna **correcto o error** .</span><span class="sxs-lookup"><span data-stu-id="cbf42-112">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="cbf42-113">Si aún no se ha ejecutado un caso de prueba, se muestra N/A en la columna **correcto o error** .</span><span class="sxs-lookup"><span data-stu-id="cbf42-113">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="cbf42-114">Faculta Para ver los resultados detallados de cada caso de prueba, haga doble clic en el nombre del caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="cbf42-114">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="cbf42-115">Los resultados se muestran en el área sombreada en el lado derecho de la página **Editar caso de prueba** :</span><span class="sxs-lookup"><span data-stu-id="cbf42-115">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="cbf42-116">**Resultado de la prueba:** Estado general de paso o error de la ejecución del caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="cbf42-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="cbf42-117">**Regla de normalización:** La primera regla de normalización seleccionada en el plan de marcado para este caso de prueba que coincide con el número marcado (el valor del campo **número para probar** ).</span><span class="sxs-lookup"><span data-stu-id="cbf42-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="cbf42-118">**Número normalizado:** El valor del número marcado después de que la regla de normalización la haya traducido.</span><span class="sxs-lookup"><span data-stu-id="cbf42-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="cbf42-119">**Primer uso de la RTC:** El primer registro de uso de la red telefónica conmutada (RTC) en la Directiva de voz seleccionada para este caso de prueba que coincide con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="cbf42-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="cbf42-120">**Primera ruta:** La primera ruta de voz del primer registro de uso de RTC que coincide con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="cbf42-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cbf42-121">El <STRONG>registro de uso de RTC esperado</STRONG> y los campos de <STRONG>ruta</STRONG> previstos son opcionales en la configuración del caso de prueba de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="cbf42-121">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="cbf42-122">Si el caso de prueba no especifica estos valores, el campo correspondiente en los resultados de la prueba estará vacío.</span><span class="sxs-lookup"><span data-stu-id="cbf42-122">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="cbf42-123">Para ejecutar uno o varios casos de prueba de enrutamiento de voz seleccionados</span><span class="sxs-lookup"><span data-stu-id="cbf42-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="cbf42-124">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cbf42-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="cbf42-125">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cbf42-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="cbf42-126">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cbf42-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cbf42-127">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cbf42-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cbf42-128">En la barra de navegación izquierda, haga clic en **enrutamiento de voz**y, a continuación, en **probar enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="cbf42-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="cbf42-129">En la página **probar enrutamiento de voz** , haga clic en los nombres de los casos de prueba que desee ejecutar.</span><span class="sxs-lookup"><span data-stu-id="cbf42-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="cbf42-130">En el menú **acción** , haga clic en **Ejecutar seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="cbf42-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="cbf42-131">El estado de paso o error de cada caso de prueba se muestra en la columna **correcto o error** .</span><span class="sxs-lookup"><span data-stu-id="cbf42-131">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="cbf42-132">Si aún no se ha ejecutado un caso de prueba, se muestra N/A en la columna **correcto o error** .</span><span class="sxs-lookup"><span data-stu-id="cbf42-132">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="cbf42-133">Faculta Para ver los resultados detallados de cada caso de prueba, haga doble clic en el nombre del caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="cbf42-133">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="cbf42-134">Los resultados se muestran en el área sombreada en el lado derecho de la página **Editar caso de prueba** :</span><span class="sxs-lookup"><span data-stu-id="cbf42-134">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="cbf42-135">**Resultado de la prueba:** Estado general de paso o error de la ejecución del caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="cbf42-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="cbf42-136">**Regla de normalización:** La primera regla de normalización seleccionada en el plan de marcado para este caso de prueba que coincide con el número marcado (el valor del campo **número para probar** ).</span><span class="sxs-lookup"><span data-stu-id="cbf42-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="cbf42-137">**Número normalizado:** El valor del número marcado después de que la regla de normalización la haya traducido.</span><span class="sxs-lookup"><span data-stu-id="cbf42-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="cbf42-138">**Primer uso de la RTC:** El primer registro de uso de RTC de la Directiva de voz seleccionada para este caso de prueba que coincide con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="cbf42-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="cbf42-139">**Primera ruta:** La primera ruta de voz del primer registro de uso de RTC que coincide con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="cbf42-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cbf42-140">El <STRONG>registro de uso de RTC esperado</STRONG> y los campos de <STRONG>ruta</STRONG> previstos son opcionales en la configuración del caso de prueba de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="cbf42-140">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="cbf42-141">Si el caso de prueba no especifica estos valores, el campo correspondiente en los resultados de la prueba estará vacío.</span><span class="sxs-lookup"><span data-stu-id="cbf42-141">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cbf42-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbf42-142">See Also</span></span>


[<span data-ttu-id="cbf42-143">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbf42-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="cbf42-144">Ejecución de pruebas de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbf42-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

