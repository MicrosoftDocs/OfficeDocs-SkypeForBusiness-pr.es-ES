---
title: 'Lync Server 2013: modificar un plan de marcado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e20b05a85daa50003ca0062ea427473eae1bf95
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="7b2cd-102">Modificar un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b2cd-102">Modify a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b2cd-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7b2cd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7b2cd-104">Para modificar un plan de marcado existente, siga los pasos del procedimiento a continuación.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-104">To modify an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="7b2cd-105">Si desea crear un nuevo plan de marcado, consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="7b2cd-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-modify-a-dial-plan"></a><span data-ttu-id="7b2cd-106">Para modificar un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="7b2cd-106">To modify a dial plan</span></span>

1.  <span data-ttu-id="7b2cd-107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7b2cd-108">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="7b2cd-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="7b2cd-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7b2cd-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7b2cd-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7b2cd-111">En la barra de navegación izquierda, haga clic en  \*\*Enrutamiento de voz \*\* y, a continuación, en  \*\*Plan de marcado \*\*.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="7b2cd-112">En la página **Plan de marcado**, haga doble clic en el nombre del plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b2cd-p104">El ámbito y el nombre del plan de marcado se establecieron cuando se creó el plan de marcado. No pueden modificarse.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-p104">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="7b2cd-115">(Opcional) En **Editar plan de marcado**, edite el campo **Nombre simple**, el cual se ha cumplimentado previamente con el mismo nombre que aparece en el campo **Nombre** para especificar un nombre más descriptivo que refleje el sitio, el servicio o el usuario a quien se aplica el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-115">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7b2cd-116">El <STRONG>nombre simple</STRONG> debe ser único entre todos los planes de marcado de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-116">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="7b2cd-117">No puede exceder de 256 caracteres Unicode, donde cada uno de los cuales puede ser alfanumérico o numérico, un guión (-), un punto (.), un signo más (+) o un guión bajo (_).</span><span class="sxs-lookup"><span data-stu-id="7b2cd-117">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).</span></span><BR><span data-ttu-id="7b2cd-118">No se permiten espacios en el campo <STRONG>Nombre simple</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-118">Spaces are not allowed in the <STRONG>Simple name</STRONG> field.</span></span>

    
    </div>

6.  <span data-ttu-id="7b2cd-119">(Opcional) En el campo **Descripción**, escriba información descriptiva sobre el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-119">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7.  <span data-ttu-id="7b2cd-p106">(Opcional) Si quiere usar este plan de marcado como región para los números de acceso telefónico local, especifique una **Región de conferencia de acceso telefónico local**. Si no quiere utilizar este plan de marcado para los números de acceso telefónico local, no rellene este campo.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b2cd-122">Se requiere que en las regiones de conferencia de acceso telefónico local se asocien los números de acceso a conferencias de acceso telefónico local con uno o más planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-122">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

8.  <span data-ttu-id="7b2cd-123">(Opcional) En el campo **Prefijo de acceso externo**, especifique el valor únicamente si los usuarios necesitan marcar uno o más dígitos iniciales para tener acceso a una línea externa (por ejemplo, 9).</span><span class="sxs-lookup"><span data-stu-id="7b2cd-123">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="7b2cd-124">Puede escribir un valor de prefijo de hasta cuatro caracteres (es decir, \# \*, y 0-9).</span><span class="sxs-lookup"><span data-stu-id="7b2cd-124">You can type in a prefix value of up to four characters (that is, \#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b2cd-125">Si especifica un prefijo de acceso externo, no necesita crear una regla de normalización nueva para incluir el prefijo.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-125">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

9.  <span data-ttu-id="7b2cd-126">Asocie y configure reglas de normalización para el plan de marcado:</span><span class="sxs-lookup"><span data-stu-id="7b2cd-126">Associate and configure normalization rules for the dial plan:</span></span>
    
      - <span data-ttu-id="7b2cd-127">Para elegir una o más reglas de una lista de todas las reglas de normalización disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-127">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="7b2cd-128">En el cuadro de diálogo **Seleccionar reglas de normalización**, resalte las reglas que desee asociar al plan de marcado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-128">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="7b2cd-129">Para definir una regla de normalización nueva y asociarla con el plan de marcado, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-129">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="7b2cd-130">Para obtener más información sobre cómo definir una regla nueva, consulte [Defining Normalization Rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="7b2cd-130">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="7b2cd-131">Para editar una regla de normalización que ya esté asociada al plan de marcado, resalte el nombre de la regla y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-131">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="7b2cd-132">Para obtener más información sobre cómo editar la regla, consulte [Defining Normalization Rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="7b2cd-132">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="7b2cd-133">Para copiar una regla de normalización existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, resalte el nombre de la regla y haga clic en **Copiar** y, a continuación, en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-133">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="7b2cd-134">Para obtener más información sobre cómo editar la copia, consulte [Defining Normalization Rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="7b2cd-134">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="7b2cd-135">Para quitar una regla de normalización del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-135">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b2cd-136">Cada plan de marcado debe tener al menos una regla de normalización asociada.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-136">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="7b2cd-137">Para obtener más información sobre cómo determinar todas las reglas de normalización que necesita un plan de marcado, consulte <A href="lync-server-2013-dial-plans-and-normalization-rules.md">planes de marcado y reglas de normalización en Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-137">For details about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

10. <span data-ttu-id="7b2cd-p113">Compruebe que las reglas de normalización del plan de marcado están dispuestas en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-p113">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7b2cd-140">Lync Server recorre la lista de reglas de normalización de arriba abajo y usa la primera regla que coincide con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-140">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="7b2cd-141">Si configura un plan de marcado de forma que un número marcado pueda coincidir con más de una regla de normalización, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-141">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="7b2cd-142">La regla de normalización predeterminada de <STRONG>guardar todas</STRONG> las reglas de normalización <STRONG>^ ({11}\d) $</STRONG> coincide con cualquier número de 11 dígitos.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-142">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="7b2cd-143">Si, por ejemplo, agrega una regla de normalización que coincide con los números de 11 dígitos que comienzan por 1425, asegúrese de que la regla <STRONG>mantener todos</STRONG> está ordenada por debajo de la regla <STRONG>^ ({7}1425 \ d) $</STRONG> más restrictiva.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-143">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

11. <span data-ttu-id="7b2cd-p116">(Opcional) Especifique un número para probar el plan de marcado y, a continuación, haga clic en **Ir**. Los resultados de la prueba se muestran en **Introducir un número para probarlo**.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-p116">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b2cd-146">Puede guardar un plan de marcado que no haya pasado la prueba aún y volver a configurarlo más adelante.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-146">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="7b2cd-147">Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-147">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="7b2cd-148">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-148">Click **OK**.</span></span>

13. <span data-ttu-id="7b2cd-149">En la página **Plan de marcado**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-149">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b2cd-150">Siempre que cree o modifique un plan de marcado, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-150">Any time you create or modify a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="7b2cd-151">Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="7b2cd-151">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7b2cd-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b2cd-152">See Also</span></span>


[<span data-ttu-id="7b2cd-153">Crear un plan de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b2cd-153">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="7b2cd-154">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b2cd-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="7b2cd-155">Definición de reglas de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b2cd-155">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

