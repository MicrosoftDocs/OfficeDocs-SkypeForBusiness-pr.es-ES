---
title: 'Lync Server 2013: crear un plan de marcado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8734ce4503ef62eb0fc04aab376f2819d1fc8fea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="23c3b-102">Crear un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23c3b-102">Create a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23c3b-103">_**Última modificación del tema:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="23c3b-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="23c3b-104">Para crear un nuevo plan de marcado, realice los pasos del procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="23c3b-104">To create a new dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="23c3b-105">Si desea editar un plan de marcado, vea [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="23c3b-105">If you want to edit a dial plan, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-create-a-dial-plan"></a><span data-ttu-id="23c3b-106">Para crear un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="23c3b-106">To create a dial plan</span></span>

1.  <span data-ttu-id="23c3b-107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="23c3b-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="23c3b-108">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="23c3b-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="23c3b-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23c3b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="23c3b-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="23c3b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="23c3b-111">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Plan de marcado**.</span><span class="sxs-lookup"><span data-stu-id="23c3b-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="23c3b-112">En la página **Plan de marcado**, haga clic en **Nuevo** y seleccione un ámbito para el plan de marcado:</span><span class="sxs-lookup"><span data-stu-id="23c3b-112">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
      - <span data-ttu-id="23c3b-p104">**Plan de marcado de sitio** se aplica a un sitio en su totalidad, salvo a los usuarios o grupos que estén asignados a un plan de marcado de usuario. Si selecciona **Sitio** para el ámbito de un plan de marcado, debe elegir el sitio en el cuadro de diálogo **Seleccionar un sitio**. Si ya se ha creado un plan de marcado, el sitio no aparece en el cuadro de diálogo **Seleccionar un sitio**.</span><span class="sxs-lookup"><span data-stu-id="23c3b-p104">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan. If you select **Site** for a dial plan’s scope, you must choose the site from the **Select a Site** dialog box. If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="23c3b-p105">**Plan de marcado de grupo** se puede aplicar a una puerta de enlace de red telefónica conmutada (RTC) o a un registrador. Si selecciona **Grupo** para el ámbito de un plan de marcado, elija la puerta de enlace de RTC o el registrador en el cuadro de diálogo **Seleccionar un servicio**. Si ya se ha creado un plan de marcado para un servicio (puerta de enlace de RTC o registrador), el servicio no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="23c3b-p105">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar. If you select **Pool** for a dial plan’s scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box. If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
      - <span data-ttu-id="23c3b-119">**Plan de marcado de usuario** se puede aplicar a usuarios o grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="23c3b-119">**User dial plan** can be applied to specified users or groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23c3b-120">Una vez seleccionado el ámbito del plan de marcado, no se podrá cambiar.</span><span class="sxs-lookup"><span data-stu-id="23c3b-120">After you select the dial plan scope, it cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="23c3b-p106">Si está creando un plan de marcado de usuario, escriba un nombre descriptivo en el campo **Nombre** en el cuadro de diálogo **Plan de marcado nuevo**. Una vez se haya guardado este nombre, no se podrá cambiar.</span><span class="sxs-lookup"><span data-stu-id="23c3b-p106">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box. After this name is saved, it cannot be changed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23c3b-123">En el caso de planes de marcado de sitio, el campo <STRONG>Nombre</STRONG> se rellena previamente con el nombre del sitio y no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="23c3b-123">For site dial plans, the <STRONG>Name</STRONG> field is prepopulated with the site name and cannot be changed.</span></span><BR><span data-ttu-id="23c3b-124">Respecto a los planes de marcado de grupo, el campo <STRONG>Nombre</STRONG> se cumplimenta previamente con la puerta de enlace de RTC o el registrador y no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="23c3b-124">For pool dial plans, the <STRONG>Name</STRONG> field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="23c3b-p107">El campo **Nombre simple** se cumplimenta previamente con el mismo nombre que aparece en el campo **Nombre**. Sil o desea, puede editar este campo para especificar un nombre más descriptivo que defina el sitio, servicio o usuario al que se aplica el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="23c3b-p107">The **Simple name** field is prepopulated with the same name that appears in the **Name** field. You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="23c3b-127">El <STRONG>nombre simple</STRONG> debe ser único entre todos los planes de marcado dentro de la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23c3b-127">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server deployment.</span></span> <span data-ttu-id="23c3b-128">No puede exceder los 256 caracteres Unicode, que pueden ser alfanuméricos o numéricos, un guión (-), un punto (.), o un guión bajo (_).</span><span class="sxs-lookup"><span data-stu-id="23c3b-128">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).</span></span><BR><span data-ttu-id="23c3b-129">Caracteres <STRONG>no admitidos</STRONG> incluyen espacios y caracteres reservados, tal y como sehttp://www.ietf.org/rfc/rfc3966.txt)definen en los documentos RFC 3966 (.</span><span class="sxs-lookup"><span data-stu-id="23c3b-129">Characters <STRONG>not supported</STRONG> include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="23c3b-130">Los caracteres reservados <STRONG>no admitidos</STRONG> en el campo <STRONG>Nombre simple</STRONG> son:</span><span class="sxs-lookup"><span data-stu-id="23c3b-130">Reserved characters that are <STRONG>not supported</STRONG> in the <STRONG>Simple Name</STRONG> include the following:</span></span><BR><span data-ttu-id="23c3b-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="23c3b-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

    
    </div>

7.  <span data-ttu-id="23c3b-132">(Opcional) En el campo **Descripción**, puede escribir información descriptiva adicional sobre el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="23c3b-132">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

8.  <span data-ttu-id="23c3b-p110">(Opcional) Si quiere usar este plan de marcado como región para los números de acceso telefónico local, especifique una **Región de conferencia de acceso telefónico local**. Si no quiere utilizar este plan de marcado para los números de acceso telefónico local, no rellene este campo.</span><span class="sxs-lookup"><span data-stu-id="23c3b-p110">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23c3b-135">Se requiere que en las regiones de conferencia de acceso telefónico local se asocien los números de acceso a conferencias de acceso telefónico local con uno o más planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="23c3b-135">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

9.  <span data-ttu-id="23c3b-136">(Opcional) En el campo **Prefijo de acceso externo**, especifique el valor únicamente si los usuarios necesitan marcar uno o más dígitos iniciales para tener acceso a una línea externa (por ejemplo, 9).</span><span class="sxs-lookup"><span data-stu-id="23c3b-136">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="23c3b-137">Puede escribir un valor de prefijo de hasta cuatro caracteres (\#, \*y 0-9).</span><span class="sxs-lookup"><span data-stu-id="23c3b-137">You can type in a prefix value of up to four characters (\#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23c3b-138">Si especifica un prefijo de acceso externo, no necesita crear una regla de normalización nueva para incluir el prefijo.</span><span class="sxs-lookup"><span data-stu-id="23c3b-138">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

10. <span data-ttu-id="23c3b-139">Asocie y configure reglas de normalización para el plan de marcado tal como sigue:</span><span class="sxs-lookup"><span data-stu-id="23c3b-139">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
      - <span data-ttu-id="23c3b-140">Para elegir una o más reglas de una lista de todas las reglas de normalización disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="23c3b-140">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="23c3b-141">En **Seleccionar reglas de normalización**, resalte las reglas que desee asociar al plan de marcado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="23c3b-141">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="23c3b-142">Para definir una regla de normalización nueva y asociarla con el plan de marcado, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="23c3b-142">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="23c3b-143">Para obtener más información sobre cómo definir una nueva regla, consulte [definir reglas de normalización en Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="23c3b-143">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="23c3b-144">Para editar una regla de normalización que ya esté asociada al plan de marcado, resalte el nombre de la regla y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="23c3b-144">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="23c3b-145">Para obtener más información sobre cómo editar la regla, consulte [definir reglas de normalización en Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="23c3b-145">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="23c3b-146">Para copiar una regla de normalización existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, resalte el nombre de la regla y haga clic en **Copiar** y, a continuación, en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="23c3b-146">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="23c3b-147">Para obtener más información sobre la edición de la copia, consulte [definición de reglas de normalización en Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="23c3b-147">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="23c3b-148">Para quitar una regla de normalización del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="23c3b-148">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23c3b-149">Cada plan de marcado debe tener al menos una regla de normalización asociada.</span><span class="sxs-lookup"><span data-stu-id="23c3b-149">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="23c3b-150">Para obtener información sobre cómo determinar todas las reglas de normalización de un plan de marcado, consulte <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planes de marcado y reglas de normalización en Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="23c3b-150">For information about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

11. <span data-ttu-id="23c3b-p117">Compruebe que las reglas de normalización del plan de marcado están dispuestas en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="23c3b-p117">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="23c3b-153">Lync Server recorre la lista de reglas de normalización de la parte superior hacia abajo y usa la primera regla que coincida con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="23c3b-153">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="23c3b-154">Si configura un plan de marcado de forma que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas.</span><span class="sxs-lookup"><span data-stu-id="23c3b-154">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="23c3b-155">La regla <STRONG></STRONG> predeterminada de normalización <STRONG>^ (\d{11}) $</STRONG> coincide con cualquier número de 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="23c3b-155">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="23c3b-156">Por ejemplo, si agrega una regla de normalización que coincide con los números de 11 dígitos que comienzan por 1425, asegúrese de que <STRONG>mantener todo</STRONG> se ordene debajo de la regla <STRONG>^ (1425 \{7}d) $</STRONG> más restrictiva.</span><span class="sxs-lookup"><span data-stu-id="23c3b-156">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

12. <span data-ttu-id="23c3b-p120">(Opcional) Especifique un número para probar el plan de marcado y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.</span><span class="sxs-lookup"><span data-stu-id="23c3b-p120">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23c3b-159">Puede guardar un plan de marcado que no haya pasado la prueba aún y volver a configurarlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="23c3b-159">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="23c3b-160">Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="23c3b-160">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="23c3b-161">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="23c3b-161">Click **OK**.</span></span>

14. <span data-ttu-id="23c3b-162">En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="23c3b-162">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23c3b-163">Cada vez que cree un plan de marcado, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="23c3b-163">Any time you create a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="23c3b-164">Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="23c3b-164">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="23c3b-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="23c3b-165">See Also</span></span>


[<span data-ttu-id="23c3b-166">Modificar un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23c3b-166">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="23c3b-167">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23c3b-167">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="23c3b-168">Definir las reglas de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23c3b-168">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

