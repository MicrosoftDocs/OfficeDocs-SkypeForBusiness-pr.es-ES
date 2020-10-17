---
title: 'Lync Server 2013: ejecutar los casos de prueba de enrutamiento de voz'
description: 'Lync Server 2013: ejecutar los casos de prueba de enrutamiento de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e521216a12fba6b78913e7f4a79432809bb6e252
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566796"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="c2eca-103">Ejecutar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2eca-103">Run voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2eca-104">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c2eca-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="c2eca-105">Puede ejecutar todos los casos de prueba en el conjunto de casos de prueba de enrutamiento de voz, o bien puede ejecutar uno o varios casos de prueba seleccionados.</span><span class="sxs-lookup"><span data-stu-id="c2eca-105">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="c2eca-106">Para ejecutar todos los casos de prueba de enrutamiento de voz</span><span class="sxs-lookup"><span data-stu-id="c2eca-106">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="c2eca-107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c2eca-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c2eca-108">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c2eca-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c2eca-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2eca-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c2eca-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c2eca-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c2eca-111">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Probar enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="c2eca-111">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="c2eca-112">En la página **Probar enrutamiento de voz**, haga clic en **Acción** y, a continuación, en **Ejecutar todo**.</span><span class="sxs-lookup"><span data-stu-id="c2eca-112">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="c2eca-p103">El estado de superado o no superado con respecto a cada caso de prueba se muestra en la columna **Superado/no superado**. Si no se ha ejecutado aún ningún caso de prueba, aparecerá N/A en la columna **Superado/no superado**.</span><span class="sxs-lookup"><span data-stu-id="c2eca-p103">The pass or fail status of each test case is shown in the **Pass/fail** column. If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="c2eca-p104">(Opcional) Para ver los resultados detallados de cada caso de prueba, haga doble clic en el nombre del caso de prueba que desee. Los resultados se muestran en la zona sombreada a la derecha de la página **Editar caso de prueba**.</span><span class="sxs-lookup"><span data-stu-id="c2eca-p104">(Optional) To see detailed results for each test case, double-click the test case name. Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="c2eca-117">**Resultado de la prueba:** Estado general de Pass o Fail del caso de prueba ejecutado.</span><span class="sxs-lookup"><span data-stu-id="c2eca-117">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="c2eca-118">**Regla de normalización:** La primera regla de normalización del plan de marcado seleccionado para este caso de prueba que coincide con el número marcado (el valor del campo **número que se va a probar** ).</span><span class="sxs-lookup"><span data-stu-id="c2eca-118">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="c2eca-119">**Número normalizado:** El valor del número marcado después de que la regla de normalización la haya traducido.</span><span class="sxs-lookup"><span data-stu-id="c2eca-119">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="c2eca-120">**Primer uso de RTC:** El primer registro de uso de RTC (red telefónica conmutada) en la Directiva de voz seleccionada para este caso de prueba que coincide con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="c2eca-120">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="c2eca-121">**Primera ruta:** La primera ruta de voz del primer registro de uso de RTC que coincide con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="c2eca-121">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c2eca-p105">Los campos <STRONG>Registro de uso de RTC previsto</STRONG> y <STRONG>Ruta prevista</STRONG> son opcionales en la configuración del caso de prueba de enrutamiento de voz. Si el caso de prueba no especifica estos valores, el campo correspondiente en los resultados de la prueba estará vacío.</span><span class="sxs-lookup"><span data-stu-id="c2eca-p105">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration. If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="c2eca-124">Para ejecutar uno o varios casos de prueba de enrutamiento de voz seleccionados</span><span class="sxs-lookup"><span data-stu-id="c2eca-124">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="c2eca-125">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c2eca-125">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c2eca-126">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c2eca-126">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c2eca-127">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2eca-127">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c2eca-128">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c2eca-128">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c2eca-129">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Probar enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="c2eca-129">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="c2eca-130">En la página **Probar enrutamiento de voz**, haga clic en los nombres de los casos de prueba que desee ejecutar.</span><span class="sxs-lookup"><span data-stu-id="c2eca-130">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="c2eca-131">En el menú **Acción**, haga clic en **Ejecutar seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="c2eca-131">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="c2eca-p108">El estado de superado o no superado con respecto a cada caso de prueba se muestra en la columna **Superado/no superado**. Si no se ha ejecutado aún ningún caso de prueba, aparecerá N/A en la columna **Superado/no superado**.</span><span class="sxs-lookup"><span data-stu-id="c2eca-p108">The pass or fail status of each test case is shown in the **Pass/fail** column. If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="c2eca-p109">(Opcional) Para ver los resultados detallados de cada caso de prueba, haga doble clic en el nombre del caso de prueba que desee. Los resultados se muestran en la zona sombreada a la derecha de la página **Editar caso de prueba**.</span><span class="sxs-lookup"><span data-stu-id="c2eca-p109">(Optional) To see detailed results for each test case, double-click the test case name. Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="c2eca-136">**Resultado de la prueba:** Estado general de Pass o Fail del caso de prueba ejecutado.</span><span class="sxs-lookup"><span data-stu-id="c2eca-136">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="c2eca-137">**Regla de normalización:** La primera regla de normalización del plan de marcado seleccionado para este caso de prueba que coincide con el número marcado (el valor del campo **número que se va a probar** ).</span><span class="sxs-lookup"><span data-stu-id="c2eca-137">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="c2eca-138">**Número normalizado:** El valor del número marcado después de que la regla de normalización la haya traducido.</span><span class="sxs-lookup"><span data-stu-id="c2eca-138">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="c2eca-139">**Primer uso de RTC:** El primer registro de uso de RTC en la Directiva de voz que se ha seleccionado para este caso de prueba que coincide con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="c2eca-139">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="c2eca-140">**Primera ruta:** La primera ruta de voz del primer registro de uso de RTC que coincide con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="c2eca-140">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c2eca-p110">Los campos <STRONG>Registro de uso de RTC previsto</STRONG> y <STRONG>Ruta prevista</STRONG> son opcionales en la configuración del caso de prueba de enrutamiento de voz. Si el caso de prueba no especifica estos valores, el campo correspondiente en los resultados de la prueba estará vacío.</span><span class="sxs-lookup"><span data-stu-id="c2eca-p110">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration. If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c2eca-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2eca-143">See Also</span></span>


[<span data-ttu-id="c2eca-144">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2eca-144">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="c2eca-145">Ejecución de pruebas de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2eca-145">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

