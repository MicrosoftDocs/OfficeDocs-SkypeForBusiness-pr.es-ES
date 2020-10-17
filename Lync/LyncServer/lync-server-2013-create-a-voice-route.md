---
title: 'Lync Server 2013: crear una ruta de voz'
description: 'Lync Server 2013: crear una ruta de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a9becac8b35967d7b7ff05014bd6b6600f62a06
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562436"
---
# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="dce7c-103">Crear una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dce7c-103">Create a voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dce7c-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dce7c-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dce7c-105">El siguiente procedimiento explica cómo crear una nueva ruta de voz mediante el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dce7c-105">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="dce7c-106">Para editar una ruta existente, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md) para obtener el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="dce7c-106">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="dce7c-107">Para crear una ruta de voz con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="dce7c-107">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="dce7c-108">Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro de la función administrativa **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="dce7c-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="dce7c-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dce7c-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dce7c-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dce7c-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dce7c-111">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="dce7c-111">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="dce7c-112">Haga clic en **Ruta**.</span><span class="sxs-lookup"><span data-stu-id="dce7c-112">Click **Route**.</span></span>

5.  <span data-ttu-id="dce7c-113">Haga clic en **Nueva** para mostrar el cuadro de diálogo **Ruta de voz nueva**.</span><span class="sxs-lookup"><span data-stu-id="dce7c-113">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="dce7c-114">En **nombre**, escriba un nombre descriptivo para la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="dce7c-114">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="dce7c-115">Opcional En **Descripción**, escriba información descriptiva adicional para la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="dce7c-115">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="dce7c-116">Para especificar los patrones que desea que el enrutamiento admita, puede usar la herramienta **crear un patrón para hacer coincidir** para generar una expresión regular o escribir la expresión regular manualmente.</span><span class="sxs-lookup"><span data-stu-id="dce7c-116">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="dce7c-p103">Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores de la forma siguiente: Puede especificar dos tipos de patrón de coincidencia:</span><span class="sxs-lookup"><span data-stu-id="dce7c-p103">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="dce7c-119">**Dígitos iniciales para los números que desea permitir:** Escriba los valores de prefijo que debe acomodar esta ruta (incluido el + inicial + si es necesario).</span><span class="sxs-lookup"><span data-stu-id="dce7c-119">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="dce7c-120">Por ejemplo, escriba **+ 425**y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="dce7c-120">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="dce7c-121">Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.</span><span class="sxs-lookup"><span data-stu-id="dce7c-121">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="dce7c-122">**Excepciones:** Si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **excepciones**.</span><span class="sxs-lookup"><span data-stu-id="dce7c-122">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="dce7c-123">Escriba uno o más valores para los patrones coincidentes que *no* quiere que se incluyan en esta ruta.</span><span class="sxs-lookup"><span data-stu-id="dce7c-123">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="dce7c-124">Por ejemplo, para excluir números que empiecen por + 425237 de la ruta, escriba un valor de **+ 425237** en el campo **excepciones** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dce7c-124">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="dce7c-125">Para definir manualmente el patrón coincidente, haga clic en **Editar** en la herramienta **Crear un patrón de coincidencia** y, a continuación, escriba una expresión regular de .NET Framework para especificar el patrón coincidente correspondiente a los números de teléfono de destino a los que se va a aplicar la ruta.</span><span class="sxs-lookup"><span data-stu-id="dce7c-125">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="dce7c-126">Para obtener más información sobre cómo escribir expresiones regulares, consulte "expresiones regulares de .NET Framework" en [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="dce7c-126">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="dce7c-p107">Seleccione **Suprimir Id. de autor de llamada** si no desea que el Id. del teléfono desde donde se efectúa la llamada saliente se muestre al receptor de la llamada. Si selecciona esta opción, es preciso que especifique un **Id. de autor de llamada alternativo** que aparecerá en la pantalla que contiene el Id. del autor de la llamada del destinatario.</span><span class="sxs-lookup"><span data-stu-id="dce7c-p107">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="dce7c-129">Para asociar uno o más troncos con la ruta de voz, haga clic en **Agregar** y, a continuación, seleccione un tronco de la lista.</span><span class="sxs-lookup"><span data-stu-id="dce7c-129">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dce7c-130">Si la implementación incluye servidores de mediación de Microsoft Office Communications Server 2007 R2, también estarán disponibles en la lista.</span><span class="sxs-lookup"><span data-stu-id="dce7c-130">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="dce7c-131">Para asociar uno o varios usos de red telefónica conmutada (RTC) con la ruta de voz, haga clic en **seleccionar** y elija un registro de la lista de registros de uso de RTC que se han definido para la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="dce7c-131">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dce7c-132">Para ver las propiedades de cada uno de los registros de uso de RTC disponibles, consulte <A href="lync-server-2013-view-pstn-usage-records.md">Ver registros de uso de RTC en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dce7c-132">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="dce7c-133">Para crear o editar registros de uso de RTC, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">crear una directiva de voz y configurar registros de uso de RTC en Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar una directiva de voz y configurar registros de uso de RTC en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dce7c-133">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="dce7c-p108">Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro de la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="dce7c-p108">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dce7c-136">A diferencia de una directiva de voz, en la que el orden en que se enumeran los registros de uso de RTC es importante, el orden en el que se enumeran los registros de uso de RTC en la ruta de voz no es significativo.</span><span class="sxs-lookup"><span data-stu-id="dce7c-136">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="dce7c-137">Sin embargo, se recomienda que organice la lista por frecuencia de uso.</span><span class="sxs-lookup"><span data-stu-id="dce7c-137">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="dce7c-138">Por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="dce7c-138">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="dce7c-139">(Lync Server recorre la lista de arriba abajo).</span><span class="sxs-lookup"><span data-stu-id="dce7c-139">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="dce7c-p110">(Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.</span><span class="sxs-lookup"><span data-stu-id="dce7c-p110">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dce7c-142">Puede guardar una ruta de voz que no haya pasado la prueba aún y volver a configurarla más adelante.</span><span class="sxs-lookup"><span data-stu-id="dce7c-142">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="dce7c-143">Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dce7c-143">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="dce7c-144">Haga clic en **Aceptar** para guardar la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="dce7c-144">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dce7c-145">Siempre que cree una ruta de voz, debe ejecutar el comando <STRONG>confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="dce7c-145">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="dce7c-146">Para obtener información detallada, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dce7c-146">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dce7c-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dce7c-147">See Also</span></span>


[<span data-ttu-id="dce7c-148">Modificar una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dce7c-148">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="dce7c-149">Ver los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dce7c-149">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="dce7c-150">Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dce7c-150">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="dce7c-151">Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dce7c-151">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="dce7c-152">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dce7c-152">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="dce7c-153">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dce7c-153">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

