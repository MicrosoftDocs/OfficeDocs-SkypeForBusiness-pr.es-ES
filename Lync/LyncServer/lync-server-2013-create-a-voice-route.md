---
title: 'Lync Server 2013: crear una ruta de voz'
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
ms.openlocfilehash: 30a25f9d070c81d45ffc966be49560dc67c292c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="d1035-102">Crear una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1035-102">Create a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1035-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d1035-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d1035-104">En el procedimiento siguiente se explica cómo crear una nueva ruta de voz con el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1035-104">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="d1035-105">Para editar una ruta existente, vea el procedimiento sobre cómo [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md) .</span><span class="sxs-lookup"><span data-stu-id="d1035-105">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="d1035-106">Para crear una ruta de voz con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d1035-106">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d1035-107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="d1035-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="d1035-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d1035-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d1035-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d1035-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d1035-110">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="d1035-110">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="d1035-111">Haga clic en **Ruta**.</span><span class="sxs-lookup"><span data-stu-id="d1035-111">Click **Route**.</span></span>

5.  <span data-ttu-id="d1035-112">Haga clic en **Nueva** para mostrar el cuadro de diálogo **Ruta de voz nueva**.</span><span class="sxs-lookup"><span data-stu-id="d1035-112">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="d1035-113">En el campo **Nombre**, escriba un nombre descriptivo para la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="d1035-113">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="d1035-114">(Opcional) En el campo **Descripción**, escriba información descriptiva adicional para la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="d1035-114">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="d1035-115">Para especificar los patrones que desea que incluya esta ruta, puede usar la herramienta **Crear un patrón de coincidencia** para generar una expresión regular o escribirla manualmente.</span><span class="sxs-lookup"><span data-stu-id="d1035-115">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="d1035-p103">Para usar la herramienta **Crear un patrón de coincidencia** con el fin de generar una expresión regular, especifique valores como se indica a continuación. Puede especificar dos tipos de patrón de coincidencia:</span><span class="sxs-lookup"><span data-stu-id="d1035-p103">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="d1035-118">**Dígitos iniciales para los números que desea permitir:** Escriba los valores de prefijo que esta ruta debe acomodar (incluido el +, si es necesario).</span><span class="sxs-lookup"><span data-stu-id="d1035-118">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="d1035-119">Por ejemplo, escriba **+425** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d1035-119">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="d1035-120">Repita el procedimiento para cada valor de prefijo que desee incluir en la ruta.</span><span class="sxs-lookup"><span data-stu-id="d1035-120">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="d1035-121">**Excepciones:** Si desea especificar una o más excepciones para un valor de prefijo, resalte el prefijo y haga clic en **excepciones**.</span><span class="sxs-lookup"><span data-stu-id="d1035-121">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="d1035-122">Escriba uno o más valores para los patrones coincidentes que *no* quiere que se incluyan en esta ruta.</span><span class="sxs-lookup"><span data-stu-id="d1035-122">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="d1035-123">Por ejemplo, para excluir los números que comiencen por de la ruta, escriba el valor **+425237** campo **Excepciones** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1035-123">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="d1035-124">Para definir manualmente el patrón coincidente, haga clic en **Editar** en la herramienta **Crear un patrón de coincidencia** y, a continuación, escriba una expresión regular de .NET Framework para especificar el patrón coincidente correspondiente a los números de teléfono de destino a los que se va a aplicar la ruta.</span><span class="sxs-lookup"><span data-stu-id="d1035-124">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="d1035-125">Para obtener más información sobre cómo escribir expresiones regulares, vea "expresiones regulares de .NET Framework [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)" en.</span><span class="sxs-lookup"><span data-stu-id="d1035-125">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="d1035-p107">Seleccione **Suprimir Id. de autor de llamada** si no desea que el Id. del teléfono desde donde se efectúa la llamada saliente se muestre al receptor de la llamada. Si selecciona esta opción, es preciso que especifique un **Id. de autor de llamada alternativo** que aparecerá en la pantalla que contiene el Id. del autor de la llamada del destinatario.</span><span class="sxs-lookup"><span data-stu-id="d1035-p107">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="d1035-128">Para asociar uno o más troncos a la ruta de voz, haga clic en **Agregar** y, a continuación, seleccione una puerta de enlace o un tronco SIP en la lista.</span><span class="sxs-lookup"><span data-stu-id="d1035-128">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1035-129">Si su implementación incluye servidores de mediación de Microsoft Office Communications Server 2007 R2, también estarán disponibles en la lista.</span><span class="sxs-lookup"><span data-stu-id="d1035-129">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="d1035-130">Para asociar uno o varios usos de la red telefónica conmutada (RTC) con la ruta de voz, haga clic en **seleccionar** y elija un registro de la lista de registros de uso de RTC que se han definido para la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d1035-130">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1035-131">Para ver las propiedades de cada uno de los registros de uso de RTC disponibles, consulte <A href="lync-server-2013-view-pstn-usage-records.md">Ver registros de uso de RTC en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d1035-131">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="d1035-132">Para crear o editar registros de uso de RTC, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">crear una directiva de voz y configurar los registros de uso de RTC en Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d1035-132">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="d1035-p108">Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="d1035-p108">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1035-135">En contraste con una directiva de voz, donde el orden en el que se muestran los registros de uso de RTC es importante, el orden en que aparecen los registros de uso de RTC en la ruta de voz es inimportante.</span><span class="sxs-lookup"><span data-stu-id="d1035-135">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="d1035-136">Sin embargo, le recomendamos que organice la lista según la frecuencia de uso.</span><span class="sxs-lookup"><span data-stu-id="d1035-136">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="d1035-137">Por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="d1035-137">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="d1035-138">(Lync Server recorre la lista desde el principio).</span><span class="sxs-lookup"><span data-stu-id="d1035-138">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="d1035-p110">(Opcional) Escriba un valor en el campo **Introducir un número para probarlo** y haga clic en **Ir**. Los resultados de la prueba se muestran en el campo.</span><span class="sxs-lookup"><span data-stu-id="d1035-p110">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1035-141">Puede guardar una ruta de voz que aún no pase la prueba y, a continuación, volver a configurarla más tarde.</span><span class="sxs-lookup"><span data-stu-id="d1035-141">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="d1035-142">Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d1035-142">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="d1035-143">Haga clic en **Aceptar** para guardar la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="d1035-143">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d1035-144">Al crear una ruta de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="d1035-144">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="d1035-145">Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d1035-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1035-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1035-146">See Also</span></span>


[<span data-ttu-id="d1035-147">Modificar una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1035-147">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="d1035-148">Ver los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1035-148">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="d1035-149">Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1035-149">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="d1035-150">Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1035-150">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="d1035-151">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1035-151">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="d1035-152">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1035-152">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

