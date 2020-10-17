---
title: 'Lync Server 2013: modificar una ruta de voz'
description: 'Lync Server 2013: modificar una ruta de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aa507f3d0f459dd200b9c772f3a330d7da36197
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546416"
---
# <a name="modify-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="e021d-103">Modificar una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e021d-103">Modify a voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e021d-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e021d-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e021d-105">En este tema se describe cómo editar una ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="e021d-105">This topic explains how to edit a voice route.</span></span> <span data-ttu-id="e021d-106">Para crear una ruta nueva, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="e021d-106">To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>

<div>

## <a name="to-modify-a-voice-route"></a><span data-ttu-id="e021d-107">Para modificar una ruta de voz</span><span class="sxs-lookup"><span data-stu-id="e021d-107">To modify a voice route</span></span>

1.  <span data-ttu-id="e021d-108">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e021d-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e021d-109">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e021d-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e021d-110">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e021d-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e021d-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e021d-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e021d-112">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Ruta**.</span><span class="sxs-lookup"><span data-stu-id="e021d-112">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>

4.  <span data-ttu-id="e021d-113">En la página **Ruta**, use uno de los métodos siguientes para modificar una ruta de voz:</span><span class="sxs-lookup"><span data-stu-id="e021d-113">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
      - <span data-ttu-id="e021d-114">Haga clic en el nombre de una ruta de voz, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="e021d-114">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="e021d-p104">Haga clic en el nombre de una ruta de voz, haga clic en **Editar**, en **Copiar** y, a continuación, en **Pegar**. Haga clic en la copia nueva de la ruta de voz que acaba de crear, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="e021d-p104">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e021d-117">En el campo **Nombre** en la página **Editar ruta de voz**, escriba un nombre descriptivo para la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="e021d-117">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>

6.  <span data-ttu-id="e021d-118">(Opcional) En el campo **Descripción**, escriba información descriptiva adicional para la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="e021d-118">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>

7.  <span data-ttu-id="e021d-119">Para especificar los patrones que desea que incluya esta ruta, puede utilizar la herramienta **Crear un patrón de coincidencia** para generar una expresión regular o escribirla manualmente.</span><span class="sxs-lookup"><span data-stu-id="e021d-119">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="e021d-p105">Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores de la forma siguiente: Puede especificar dos tipos de patrón de coincidencia:</span><span class="sxs-lookup"><span data-stu-id="e021d-p105">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="e021d-122">**Dígitos iniciales para los números que desea permitir:** Escriba los valores de prefijo que debe acomodar esta ruta (incluido el + inicial + si es necesario).</span><span class="sxs-lookup"><span data-stu-id="e021d-122">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="e021d-123">Por ejemplo, escriba **+425** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e021d-123">For example, type **+425** and then click **Add**.</span></span> <span data-ttu-id="e021d-124">Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.</span><span class="sxs-lookup"><span data-stu-id="e021d-124">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="e021d-125">**Excepciones:** Si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **excepciones**.</span><span class="sxs-lookup"><span data-stu-id="e021d-125">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="e021d-126">Escriba uno o más valores para los patrones coincidentes que *no* quiere que se incluyan en esta ruta.</span><span class="sxs-lookup"><span data-stu-id="e021d-126">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="e021d-127">Por ejemplo, para excluir números que empiecen por + 425237 de la ruta, escriba un valor de **+ 425237** en el campo **excepciones** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e021d-127">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="e021d-128">Para definir manualmente el patrón coincidente, haga clic en **Editar** en la herramienta **Crear un patrón de coincidencia** y, a continuación, escriba una expresión regular de .NET Framework para especificar el patrón coincidente correspondiente a los números de teléfono de destino a los que se va a aplicar la ruta.</span><span class="sxs-lookup"><span data-stu-id="e021d-128">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="e021d-129">Para obtener información sobre cómo escribir expresiones regulares, consulte "expresiones regulares de .NET Framework" en [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="e021d-129">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

8.  <span data-ttu-id="e021d-130">Seleccione **suprimir identificador de llamada** si no desea que el identificador del teléfono que hace la llamada saliente aparezca al destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e021d-130">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="e021d-131">Si selecciona esta opción, debe especificar un identificador de **llamada alternativo** que aparecerá en la presentación del identificador de llamada del destinatario.</span><span class="sxs-lookup"><span data-stu-id="e021d-131">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

9.  <span data-ttu-id="e021d-132">Para asociar uno o más troncos de red telefónica conmutada (RTC) con la ruta de voz, haga clic en **Agregar**y, a continuación, seleccione un tronco de la lista.</span><span class="sxs-lookup"><span data-stu-id="e021d-132">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e021d-133">Si la implementación incluye servidores de mediación de Microsoft Office Communications Server 2007 R2, también estarán disponibles en la lista.</span><span class="sxs-lookup"><span data-stu-id="e021d-133">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

10. <span data-ttu-id="e021d-134">Para asociar uno o más usos de RTC con la ruta de voz, haga clic en **seleccionar** y elija un registro de la lista de registros de uso de RTC que se han definido para la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="e021d-134">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e021d-135">Para ver las propiedades de cada uno de los registros de uso de RTC disponibles, consulte <A href="lync-server-2013-view-pstn-usage-records.md">Ver registros de uso de RTC en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e021d-135">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="e021d-136">Para crear o editar registros de uso de RTC, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">crear una directiva de voz y configurar registros de uso de RTC en Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar una directiva de voz y configurar registros de uso de RTC en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e021d-136">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="e021d-p110">Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro de la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="e021d-p110">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e021d-139">En contraste con una directiva de voz en la que el orden en que se enumeran los registros de uso de RTC es importante, el orden de los registros de uso de RTC en una ruta de voz es insignificante.</span><span class="sxs-lookup"><span data-stu-id="e021d-139">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="e021d-140">Sin embargo, se recomienda ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="e021d-140">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="e021d-141">(Lync Server recorre la lista de arriba abajo).</span><span class="sxs-lookup"><span data-stu-id="e021d-141">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

12. <span data-ttu-id="e021d-p112">(Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.</span><span class="sxs-lookup"><span data-stu-id="e021d-p112">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e021d-144">Puede guardar una ruta de voz que no haya pasado la prueba aún y volver a configurarla más adelante.</span><span class="sxs-lookup"><span data-stu-id="e021d-144">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="e021d-145">Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e021d-145">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="e021d-146">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e021d-146">Click **OK**.</span></span>

14. <span data-ttu-id="e021d-147">En la página **Ruta**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="e021d-147">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e021d-148">Siempre que cree o modifique una ruta de voz, debe ejecutar el comando <STRONG>confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="e021d-148">Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="e021d-149">Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="e021d-149">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e021d-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e021d-150">See Also</span></span>


[<span data-ttu-id="e021d-151">Crear una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e021d-151">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="e021d-152">Ver los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e021d-152">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="e021d-153">Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e021d-153">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="e021d-154">Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e021d-154">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="e021d-155">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e021d-155">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="e021d-156">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e021d-156">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

