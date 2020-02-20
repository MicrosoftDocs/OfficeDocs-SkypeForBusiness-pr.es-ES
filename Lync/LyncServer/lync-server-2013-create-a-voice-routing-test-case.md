---
title: 'Lync Server 2013: crear un caso de prueba de enrutamiento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8396a2e1cd13dd817d173f1285e9f25fd0be1ab9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="a8ce2-102">Crear un caso de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ce2-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8ce2-103">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="a8ce2-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="a8ce2-104">Para crear un caso de prueba</span><span class="sxs-lookup"><span data-stu-id="a8ce2-104">To create a test case</span></span>

1.  <span data-ttu-id="a8ce2-105">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a8ce2-106">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a8ce2-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a8ce2-107">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a8ce2-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a8ce2-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a8ce2-109">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Probar enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="a8ce2-110">En la página **Probar enrutamiento de voz**, haga clic en **Nuevo** para crear un nuevo caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="a8ce2-111">En **Nombre**, escriba un nombre único para el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="a8ce2-112">El nombre debe ser único entre todos los casos de prueba de enrutamiento de voz en la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="a8ce2-113">Puede tener hasta 32 caracteres de longitud y puede contener caracteres alfanuméricos, además de la barra diagonal inversa (\\), el punto (.) o el carácter de subrayado (\_).</span><span class="sxs-lookup"><span data-stu-id="a8ce2-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="a8ce2-p104">En **Número marcado para prueba**, escriba el número marcado que desea usar para probar la configuración de enrutamiento especificada para este caso de prueba. Según el plan de marcado, la ruta y la directiva de voz, este número se normalizará y se mostrará como resultado.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-p104">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case. Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="a8ce2-p105">En la lista **Plan de marcado**, seleccione el plan de marcado que se va a usar cuando se ejecute la prueba. El plan de marcado predeterminado es el plan de marcado Global.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-p105">In the **Dial Plan** list, select the dial plan to use when running the test. Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="a8ce2-p106">En la lista **Directiva de voz**, seleccione la directiva de voz que se va a usar cuando se ejecute la prueba. La directiva de voz predeterminada es la directiva de voz Global.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-p106">In the **Voice Policy** list, select the voice policy to use when running the test. Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="a8ce2-p107">En **Conversión prevista**, escriba el número de teléfono en el formato que desea que se muestre tras la conversión. Dicho número corresponde al valor del número de teléfono que se está probando tras la conversión de la primera regla de normalización que coincida con el plan de marcado seleccionado. Cuando ejecuta el caso de prueba, sabrá si ha fallo cuando el número que se está probando no se convierte en el valor especificado en **Conversión prevista**.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-p107">In **Expected translation**, type in the phone number in the format you expect to see it after translation. This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan. When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="a8ce2-p108">(Opcional) En la lista **Uso de RTC previsto**, puede seleccionar el registro de uso de la red telefónica conmutada (RTC) que espera que se use al ejecutar el caso de prueba, según el plan de marcado y la directiva de voz que se han especificado. Si se usa un registro de uso de RTC diferente significa que la prueba ha fallado.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-p108">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="a8ce2-p109">(Opcional) En la lista **Ruta prevista**, puede seleccionar la ruta de voz que espera que se use al ejecutar el caso de prueba, según el plan de marcado y la directiva de voz que se han especificado. Si se usa una ruta de voz diferente significa que la prueba ha fallado.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-p109">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="a8ce2-p110">(Opcional) Haga clic en **Ejecutar** para iniciar el caso de prueba. Los resultados se mostrarán en el panel que hay a la derecha de la página.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-p110">(Optional) Click **Run** to run the test case. The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="a8ce2-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-129">Click **OK**.</span></span>

14. <span data-ttu-id="a8ce2-130">Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a8ce2-131">Siempre que cree un caso de prueba de enrutamiento de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="a8ce2-132">Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="a8ce2-133">Si el plan de marcado que se usa en la prueba normaliza los números de teléfono que comienzan con un signo más (por ejemplo, + 12065551219), es posible que se produzca un error en la prueba de enrutamiento de voz.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="a8ce2-134">(El plan de marcado y la ruta de voz funcionarán; de hecho, test-CsDialPlan se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="a8ce2-135">Sin embargo, es posible que se produzca un error en la prueba de enrutamiento de voz. Esto es algo que se debe tener en cuenta al probar las rutas de voz.</span><span class="sxs-lookup"><span data-stu-id="a8ce2-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a8ce2-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8ce2-136">See Also</span></span>


[<span data-ttu-id="a8ce2-137">Exportar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ce2-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="a8ce2-138">Importar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ce2-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="a8ce2-139">Configurar planes de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ce2-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="a8ce2-140">Configurar directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8ce2-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

