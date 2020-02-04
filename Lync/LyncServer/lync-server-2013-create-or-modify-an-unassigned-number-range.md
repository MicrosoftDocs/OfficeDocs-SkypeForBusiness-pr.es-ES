---
title: 'Lync Server 2013: crear o modificar un intervalo de números sin asignar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90b6068de77a1a32f45afbc34604dc70a4daf58e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="f89ff-102">Crear o modificar un intervalo numérico sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f89ff-102">Create or modify an unassigned number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f89ff-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f89ff-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f89ff-104">Use uno de los procedimientos siguientes para configurar intervalos numéricos no asignados para la aplicación de anuncios.</span><span class="sxs-lookup"><span data-stu-id="f89ff-104">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f89ff-105">Antes de configurar la tabla de números sin asignar, debe haber definido uno o más anuncios o configurar un operador automático de mensajería unificada (UM) de Exchange.</span><span class="sxs-lookup"><span data-stu-id="f89ff-105">Before you configure the unassigned number table, you must have already defined one or more announcements or set up an Exchange Unified Messaging (UM) Auto Attendant.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="f89ff-106">Para usar el panel de control de Lync Server para configurar números de teléfono no asignados</span><span class="sxs-lookup"><span data-stu-id="f89ff-106">To use Lync Server Control Panel to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="f89ff-107">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f89ff-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f89ff-108">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f89ff-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f89ff-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f89ff-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f89ff-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f89ff-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f89ff-111">En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Número sin asignar**.</span><span class="sxs-lookup"><span data-stu-id="f89ff-111">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="f89ff-112">En la página **Número sin asignar**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="f89ff-112">On the **Unassigned Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f89ff-p103">Para crear un nuevo intervalo de números, haga clic en **Nuevo**. En **Nombre**, escriba un nombre identificativo para este intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="f89ff-p103">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f89ff-115">Una vez que haya confirmado el nuevo intervalo de números sin asignar para la base de datos, no podrá cambiar este nombre.</span><span class="sxs-lookup"><span data-stu-id="f89ff-115">After you commit the new unassigned number range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="f89ff-p104">Para modificar un intervalo de números existente, escriba en el campo de búsqueda todo el intervalo de números o parte de él. En la lista de intervalos numéricos resultante, haga clic en el nombre que desee, en **Editar** y, por último, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="f89ff-p104">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f89ff-118">En el primer campo **Intervalo numérico**, escriba el número inicial del intervalo y, en el segundo campo **Intervalo numérico**, escriba el número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="f89ff-118">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="f89ff-119">El número inicial del intervalo debe ser menor o igual al número final.</span><span class="sxs-lookup"><span data-stu-id="f89ff-119">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f89ff-120">Si el número inicial o final del intervalo incluye un número de extensión, ambos números del intervalo deben incluir la extensión y el número de extensión debe ser igual al número inicial y final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="f89ff-120">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f89ff-121">El número debe coincidir con la expresión regular (Tel:)? ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?.</span><span class="sxs-lookup"><span data-stu-id="f89ff-121">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="f89ff-122">Esto significa que el número puede comenzar con la cadena de caracteres tel: (si no especifica la cadena de caracteres, se agregará automáticamente), un signo más (+) y un dígito del 1 al 9.</span><span class="sxs-lookup"><span data-stu-id="f89ff-122">This means the number may begin with the string tel: (if you don’t specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="f89ff-123">El número de teléfono puede tener hasta 17 dígitos y puede estar seguido de una extensión en formato ext= y el número de extensión.</span><span class="sxs-lookup"><span data-stu-id="f89ff-123">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="f89ff-124">En **Servicio de anuncio**, lleve a cabo uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="f89ff-124">In **Announcement service**, do one of the following:</span></span>
    
      - <span data-ttu-id="f89ff-125">Haga clic en **Anuncio**.</span><span class="sxs-lookup"><span data-stu-id="f89ff-125">Click **Announcement**.</span></span>
    
      - <span data-ttu-id="f89ff-126">Haga clic en **Mensajería unificada de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="f89ff-126">Click **Exchange UM**.</span></span>

7.  <span data-ttu-id="f89ff-127">Si en el paso anterior ha hecho clic en **Anuncio**, proceda de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f89ff-127">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    1.  <span data-ttu-id="f89ff-128">En **FQDN del servidor de destino**, haga clic en **seleccionar**, haga clic en el identificador de servicio del servicio de aplicación que ejecuta la aplicación de anuncio que controlará las llamadas entrantes a este rango de números sin asignar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f89ff-128">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    2.  <span data-ttu-id="f89ff-129">En **Anuncio**, haga clic en el anuncio que se va a reproducir para este intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="f89ff-129">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>

8.  <span data-ttu-id="f89ff-130">Si en el paso anterior hizo clic en **Mensajería unificada de Exchange**, en **Número de teléfono del operador automático**, haga clic en **Seleccionar**, haga clic en el número de teléfono que se va a utilizar para este intervalo de números sin asignar y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f89ff-130">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>

9.  <span data-ttu-id="f89ff-131">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f89ff-131">Click **OK**.</span></span>

10. <span data-ttu-id="f89ff-p106">En la página **Número sin asignar**, asegúrese de que los intervalos de números sin asignar se disponen según el orden que le interesa. Para cambiar la posición de un intervalo en la tabla, haga clic en uno o más nombres consecutivos en la lista de intervalos y, a continuación, haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="f89ff-p106">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f89ff-134">Lync Server busca la tabla de números sin asignar de arriba a abajo y usa el primer rango que coincida con el número sin asignar.</span><span class="sxs-lookup"><span data-stu-id="f89ff-134">Lync Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="f89ff-135">Si tiene intervalos superpuestos y un intervalo especifica una acción de último recurso, asegúrese de que ese intervalo se encuentra en último lugar en la lista.</span><span class="sxs-lookup"><span data-stu-id="f89ff-135">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

    
    </div>

11. <span data-ttu-id="f89ff-136">Cuando haya ordenado el intervalo de números sin asignar según su conveniencia, haga clic en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="f89ff-136">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="f89ff-137">Para usar Windows PowerShell para configurar números de teléfono sin asignar</span><span class="sxs-lookup"><span data-stu-id="f89ff-137">To use Windows PowerShell to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="f89ff-138">Inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f89ff-138">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f89ff-139">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f89ff-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f89ff-140">Use **New-CsUnassignedNumber** para crear un nuevo intervalo de números no asignados.</span><span class="sxs-lookup"><span data-stu-id="f89ff-140">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="f89ff-141">Use **Set-CsUnassignedNumber** para modificar un intervalo de números no asignados existente.</span><span class="sxs-lookup"><span data-stu-id="f89ff-141">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f89ff-p109">Si tiene intervalos solapados y desea que se apliquen en un orden específico, incluya el parámetro Prioridad. Se aplicará a la llamada el intervalo con la máxima prioridad.</span><span class="sxs-lookup"><span data-stu-id="f89ff-p109">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter. The range with the highest priority will be applied to the call.</span></span>

    
    </div>
    
    <span data-ttu-id="f89ff-144">En la línea de comandos, realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f89ff-144">At the command line, do one of the following:</span></span>
    
      - <span data-ttu-id="f89ff-145">Si desea crear un intervalo de números para un servicio de anuncio, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f89ff-145">To create a number range for an Announcement service, run:</span></span>
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - <span data-ttu-id="f89ff-146">O, si desea crear un intervalo de números para el Operador automático de mensajería unificada de Exchange, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f89ff-146">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    <span data-ttu-id="f89ff-147">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f89ff-147">For example:</span></span>
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    <span data-ttu-id="f89ff-148">O bien</span><span class="sxs-lookup"><span data-stu-id="f89ff-148">Or</span></span>
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    <span data-ttu-id="f89ff-149">El siguiente ejemplo muestra cómo modificar los números de un intervalo de números no asignados existente:</span><span class="sxs-lookup"><span data-stu-id="f89ff-149">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f89ff-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="f89ff-150">See Also</span></span>


[<span data-ttu-id="f89ff-151">Eliminar un intervalo numérico sin asignar en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f89ff-151">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)  


[<span data-ttu-id="f89ff-152">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="f89ff-152">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[<span data-ttu-id="f89ff-153">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="f89ff-153">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[<span data-ttu-id="f89ff-154">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="f89ff-154">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

