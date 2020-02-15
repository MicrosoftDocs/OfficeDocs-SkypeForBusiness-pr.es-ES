---
title: 'Lync Server 2013: ejecutar pruebas de enrutamiento de voz informal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8edac9a9bd955165a2e20197fd340ea80c2e27a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="afae2-102">Ejecutar pruebas de enrutamiento de voz informal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afae2-102">Run informal voice routing tests in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afae2-103">_**Última modificación del tema:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="afae2-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="afae2-p101">Puede usar el cuadro de diálogo **Crear información de caso de prueba de enrutamiento de voz** para ejecutar pruebas informales antes de crear un caso de prueba real. Cuando esté satisfecho con el resultado de una prueba, dispone de la opción de guardarlo como caso de prueba formal.</span><span class="sxs-lookup"><span data-stu-id="afae2-p101">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case. When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="afae2-106">Para ejecutar una prueba de enrutamiento de voz informal</span><span class="sxs-lookup"><span data-stu-id="afae2-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="afae2-107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="afae2-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="afae2-108">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="afae2-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="afae2-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afae2-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="afae2-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="afae2-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="afae2-111">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Probar enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="afae2-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="afae2-112">En la página **Probar enrutamiento de voz**, haga clic en **Crear información de caso de prueba de enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="afae2-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="afae2-p104">En el campo **Número marcado**, escriba el número de teléfono que desee usar para esta prueba. El número se normalizará y se mostrará en el campo **Número normalizado** del panel **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="afae2-p104">In the **Dialed number** field, type in the phone number you want to use for this test. This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="afae2-p105">En la lista **Plan de marcado**, seleccione el plan de marcado que se usará para probar el número marcado. El plan de marcado predeterminado es el plan de marcado Global.</span><span class="sxs-lookup"><span data-stu-id="afae2-p105">In the **Dial plan** list, select the dial plan to use for testing the dialed number. Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="afae2-117">Cuando ejecute la prueba, la primera regla de normalización del plan de marcado que coincida con el número marcado aparecerá en el campo **Regla de normalización** del panel **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="afae2-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="afae2-p106">En la lista **Directiva de voz**, seleccione la directiva de voz que se usará para probar el número marcado. La directiva de voz predeterminada es la directiva de voz Global.</span><span class="sxs-lookup"><span data-stu-id="afae2-p106">In the **Voice Policy** list, select the voice policy to use for testing the dialed number. Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="afae2-p107">Cuando ejecute la prueba, el primer registro de uso de RTC coincidente en esta directiva de voz se mostrará en el campo **Primer uso de RTC** del panel **Resultados**. Asimismo, la primera ruta de voz coincidente que se asocie con este registro de uso de RTC se mostrará en el campo **Primera ruta**.</span><span class="sxs-lookup"><span data-stu-id="afae2-p107">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="afae2-122">(Opcional) Active la casilla **Rellenar con usuario** si desea probar el número marcado con la directiva de voz asignada a un usuario en concreto.</span><span class="sxs-lookup"><span data-stu-id="afae2-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="afae2-123">Haga clic en **Examinar** para mostrar el cuadro de diálogo **Seleccionar usuarios de Telefonía IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="afae2-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="afae2-124">Haga clic en **Buscar** para visualizar la lista de usuarios habilitados para Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="afae2-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="afae2-p108">Haga doble clic en el nombre del usuario cuya directiva de voz asignada desee usar para esta prueba. A continuación, el campo **Directiva** se rellenará con la directiva de voz asignada al usuario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="afae2-p108">Double-click the user name whose assigned voice policy you want to use for this test. The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="afae2-p109">Cuando ejecute la prueba, el primer registro de uso de RTC coincidente en esta directiva de voz se mostrará en el campo **Primer uso de RTC** del panel **Resultados**. Asimismo, la primera ruta de voz coincidente que se asocie con este registro de uso de RTC se mostrará en el campo **Primera ruta**.</span><span class="sxs-lookup"><span data-stu-id="afae2-p109">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="afae2-p110">Haga clic en **Ejecutar** para ejecutar el caso de prueba. Los resultados se mostrarán en el panel derecho del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="afae2-p110">Click **Run** to run the test case. The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="afae2-131">(Opcional) Haga clic en **Guardar como** si desea guardar la configuración de la prueba como caso de prueba formal.</span><span class="sxs-lookup"><span data-stu-id="afae2-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="afae2-132">En el campo **Nombre** del cuadro de diálogo **Guardar información de caso de prueba de enrutamiento de voz**, escriba un nombre único para el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="afae2-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="afae2-133">El nombre debe ser único entre todos los casos de prueba de enrutamiento de voz en la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="afae2-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="afae2-134">Puede tener hasta 32 caracteres de longitud y puede contener caracteres alfanuméricos, además de la barra diagonal inversa (\\), el punto (.) o el carácter de subrayado (\_).</span><span class="sxs-lookup"><span data-stu-id="afae2-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="afae2-p112">No olvide que los demás campos del cuadro de diálogo **Guardar información de caso de prueba de enrutamiento de voz** son de solo lectura, y se rellenan automáticamente con la configuración de la prueba informal *y* sus resultados. Compruebe que es la configuración que desea guardar para el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="afae2-p112">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results. Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="afae2-137">Los valores de los resultados de la prueba se usan para rellenar automáticamente los campos del cuadro de diálogo <STRONG>Guardar información de caso de prueba de enrutamiento de voz</STRONG>, como sigue:</span><span class="sxs-lookup"><span data-stu-id="afae2-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="afae2-138"><STRONG>Conversión prevista</STRONG> se rellena automáticamente con el valor del campo <STRONG>Número normalizado</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="afae2-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="afae2-139"><STRONG>Ruta prevista</STRONG> se rellena automáticamente con el valor del campo <STRONG>Primera ruta</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="afae2-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="afae2-140"><STRONG>Registro de uso de RTC previsto</STRONG> se rellena automáticamente con el valor del campo <STRONG>Primer uso de RTC</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="afae2-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="afae2-p113">Si no se han encontrado coincidencias con estos valores durante la ejecución de la prueba, el campo correspondiente estará vacío en el cuadro de diálogo <STRONG>Guardar información de caso de prueba de enrutamiento de voz</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="afae2-p113">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.   </span></span></div>
    
    3.  <span data-ttu-id="afae2-142">Haga clic en **Aceptar** para guardar el caso de prueba o en **Cancelar** para volver al cuadro de diálogo **ver información de caso de prueba de enrutamiento de voz** para seguir desarrollando la prueba antes de guardarla.</span><span class="sxs-lookup"><span data-stu-id="afae2-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="afae2-143">Haga clic en **Confirmar** y, a continuación en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="afae2-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afae2-144">Cada vez que cree un caso de prueba de enrutamiento de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="afae2-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="afae2-145">Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="afae2-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="afae2-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="afae2-146">See Also</span></span>


[<span data-ttu-id="afae2-147">Crear un caso de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afae2-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="afae2-148">Ejecutar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afae2-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="afae2-149">Exportar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afae2-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="afae2-150">Importar casos de prueba de enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afae2-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="afae2-151">Configurar planes de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afae2-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="afae2-152">Configurar directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afae2-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

