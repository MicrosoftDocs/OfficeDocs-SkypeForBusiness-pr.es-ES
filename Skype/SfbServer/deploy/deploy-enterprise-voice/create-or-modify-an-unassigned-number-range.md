---
title: Crear o modificar un intervalo de números sin asignar en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Crear, modificar o eliminar rangos numéricos no asignados para la aplicación de anuncios en Skype empresarial Server Enterprise Voice. Esto afecta a cómo se administran las llamadas a números sin asignar.
ms.openlocfilehash: 5b9afa463d6eaff2f6ba3ed283d11556bd95bc03
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286186"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="ebcb6-104">Crear o modificar un intervalo de números sin asignar en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ebcb6-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="ebcb6-105">Crear, modificar o eliminar rangos numéricos no asignados para la aplicación de anuncios en Skype empresarial Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="ebcb6-106">Esto afecta a cómo se administran las llamadas a números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="ebcb6-107">Skype empresarial Server le permite decir lo que sucede con las llamadas entrantes a números de teléfono que son válidos para su organización, pero que no están asignados a un usuario o un teléfono.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="ebcb6-108">Para administrar las llamadas de este tipo, deberá configurar una tabla de números no asignados.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="ebcb6-109">Puede usar la tabla para enrutar las llamadas a una aplicación de anuncio o a un servidor de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="ebcb6-p104">La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar o bien con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en esos momentos. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="ebcb6-116">Configuración de números de teléfono sin asignar</span><span class="sxs-lookup"><span data-stu-id="ebcb6-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="ebcb6-117">Use uno de los procedimientos siguientes para configurar intervalos numéricos no asignados para la aplicación de anuncios.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ebcb6-118">Antes de configurar la tabla de números sin asignar, el sistema ya debe tener anuncios definidos o un operador automático de mensajería unificada (UM) de Exchange configurado.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="ebcb6-119">Cuando alguien llama a un número no asignado, Skype empresarial Server busca la tabla de números sin asignar de arriba abajo y usa el primer intervalo coincidente.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="ebcb6-120">Por consiguiente, si quiere que se lleve a cabo una acción determinada como último recurso, deberá especificarla para el último intervalo en la tabla.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="ebcb6-121">Para usar el panel de control de Skype empresarial Server para configurar números de teléfono no asignados</span><span class="sxs-lookup"><span data-stu-id="ebcb6-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="ebcb6-p106">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-p106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ebcb6-124">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ebcb6-125">En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Número sin asignar**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="ebcb6-126">En la página **Número sin asignar**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="ebcb6-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="ebcb6-p107">Para crear un nuevo intervalo de números, haga clic en **Nuevo**. En **Nombre**, escriba un nombre identificativo para este intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-p107">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="ebcb6-129">Una vez que haya confirmado el nuevo intervalo de números sin asignar para la base de datos, no podrá cambiar este nombre.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="ebcb6-p108">Para modificar un intervalo de números existente, escriba en el campo de búsqueda todo el intervalo de números o parte de él. En la lista de intervalos numéricos resultante, haga clic en el nombre que desee, en **Editar** y, por último, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-p108">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ebcb6-132">En el primer campo **Intervalo numérico**, escriba el número inicial del intervalo y, en el segundo campo **Intervalo numérico**, escriba el número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="ebcb6-133">El número inicial del intervalo debe ser menor o igual al número final.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="ebcb6-134">Si el número inicial o final del intervalo incluye un número de extensión, ambos números del intervalo deben incluir la extensión y el número de extensión debe ser igual al número inicial y final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="ebcb6-135">El número debe coincidir con la expresión regular (Tel:)\+? () ? [1-9{0,17}] \d (; ext = [1-9{0,9}] \d) ?.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="ebcb6-136">Esto significa que el número puede comenzar con la cadena Tel: (si no especifica esa cadena, se agregará automáticamente), un signo más (+) y un dígito de 1 a 9.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="ebcb6-137">El número de teléfono puede tener hasta 17 dígitos y puede estar seguido de una extensión en formato ext= y el número de extensión.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="ebcb6-138">En **Servicio de anuncio**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="ebcb6-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="ebcb6-139">Haga clic en **Anuncio**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="ebcb6-140">Haga clic en **Mensajería unificada de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="ebcb6-141">Si en el paso anterior ha hecho clic en **Anuncio**, proceda de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ebcb6-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="ebcb6-142">a.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-142">a.</span></span> <span data-ttu-id="ebcb6-143">En **FQDN del servidor de destino**, haga clic en **seleccionar**, haga clic en el identificador de servicio del servicio de aplicación que ejecuta la aplicación de anuncio que controlará las llamadas entrantes a este rango de números sin asignar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="ebcb6-144">b.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-144">b.</span></span> <span data-ttu-id="ebcb6-145">En **Anuncio**, haga clic en el anuncio que se va a reproducir para este intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="ebcb6-146">Si en el paso anterior hizo clic en **Mensajería unificada de Exchange**, en **Número de teléfono del operador automático**, haga clic en **Seleccionar**, haga clic en el número de teléfono que se va a utilizar para este intervalo de números sin asignar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="ebcb6-147">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="ebcb6-p112">En la página **Número sin asignar**, asegúrese de que los intervalos de números sin asignar se disponen según el orden que le interesa. Para cambiar la posición de un intervalo en la tabla, haga clic en uno o más nombres consecutivos en la lista de intervalos y, a continuación, haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-p112">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ebcb6-150">Skype empresarial Server busca la tabla de números sin asignar de arriba a abajo y usa el primer rango que coincida con el número sin asignar.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="ebcb6-151">Si tiene intervalos superpuestos y un intervalo especifica una acción de último recurso, asegúrese de que ese intervalo se encuentra en último lugar en la lista.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="ebcb6-152">Cuando haya ordenado el intervalo de números sin asignar según su conveniencia, haga clic en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="ebcb6-153">Para usar el shell de administración de Skype empresarial Server para configurar números de teléfono sin asignar</span><span class="sxs-lookup"><span data-stu-id="ebcb6-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="ebcb6-154">Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, como se describe en **permisos de configuración de delegado**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ebcb6-155">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ebcb6-156">Use **New-CsUnassignedNumber** para crear un nuevo intervalo de números no asignados.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="ebcb6-157">Use **Set-CsUnassignedNumber** para modificar un intervalo de números no asignados existente.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ebcb6-158">Si tiene intervalos solapados y desea que se apliquen en un orden específico, incluya el parámetro Prioridad.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="ebcb6-159">Se aplicará a la llamada el intervalo con la máxima prioridad.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="ebcb6-160">El valor 0 representa la prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="ebcb6-161">En la línea de comandos, realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ebcb6-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="ebcb6-162">Si desea crear un intervalo de números para un servicio de anuncio, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ebcb6-162">To create a number range for an Announcement service, run:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="ebcb6-163">O, si desea crear un intervalo de números para el Operador automático de mensajería unificada de Exchange, ejecute:</span><span class="sxs-lookup"><span data-stu-id="ebcb6-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="ebcb6-164">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ebcb6-164">For example:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="ebcb6-165">O bien</span><span class="sxs-lookup"><span data-stu-id="ebcb6-165">Or</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="ebcb6-166">El siguiente ejemplo muestra cómo modificar los números de un intervalo de números no asignados existente:</span><span class="sxs-lookup"><span data-stu-id="ebcb6-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="ebcb6-167">Eliminar un intervalo de números sin asignar</span><span class="sxs-lookup"><span data-stu-id="ebcb6-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="ebcb6-168">Para usar el panel de control de Skype empresarial Server para eliminar un intervalo de números no asignado</span><span class="sxs-lookup"><span data-stu-id="ebcb6-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="ebcb6-p116">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para más información, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-p116">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ebcb6-171">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ebcb6-172">En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Número sin asignar**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="ebcb6-173">En la página **Número sin asignar**, en el campo de búsqueda, escriba la totalidad o parte del nombre del intervalo del número sin asignar que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="ebcb6-174">En la lista resultante de intervalos numéricos, haga clic en el nombre, en **Editar** y, a continuación, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="ebcb6-175">Haga clic en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="ebcb6-176">Para usar el shell de administración de Skype empresarial Server para eliminar un intervalo de números sin asignar</span><span class="sxs-lookup"><span data-stu-id="ebcb6-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="ebcb6-177">Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, como se describe en **permisos de configuración de delegado**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ebcb6-178">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="ebcb6-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ebcb6-179">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebcb6-179">At the command line, type:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="ebcb6-180">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ebcb6-180">For example:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="ebcb6-181">Para obtener más información sobre más opciones, consulte [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ebcb6-181">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ebcb6-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebcb6-182">See also</span></span>

[<span data-ttu-id="ebcb6-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="ebcb6-183">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="ebcb6-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="ebcb6-184">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="ebcb6-185">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="ebcb6-185">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
