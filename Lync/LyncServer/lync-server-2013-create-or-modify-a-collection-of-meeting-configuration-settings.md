---
title: Crear o modificar una colección de opciones de configuración de reuniones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb7f5df9a734fc248afbe0bf21739b95ecfba285
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516907"
---
# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b5c8d-102">Crear o modificar una colección de opciones de configuración de reuniones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5c8d-102">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5c8d-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b5c8d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b5c8d-p101">Use la configuración de la página Configuración de reunión para definir diversas características de la experiencia de participar en una reunión. Normalmente, la participación se rige por la configuración global. También puede crear configuraciones de participación en reuniones en el nivel de sitio y en el nivel de grupo de servidores. Si crea una configuración en el nivel de grupo de servidores, esa configuración se aplicará a todas las reuniones que ese grupo de servidores hospeda. Si no crea ninguna configuración en el nivel de grupo de servidores, se aplicará la configuración del nivel de sitio, si existe. Si no define la configuración en el nivel de sitio, se aplicará la configuración global a todas las reuniones.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-p101">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience. By default, the global settings define the join experience. You can also create site-level and pool-level meeting join settings. If you create pool-level settings, those settings apply to all meetings hosted by that pool. If you do not create pool-level settings, site-level settings apply, if they exist. If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="b5c8d-110">Para crear nuevas configuraciones de participación en reuniones</span><span class="sxs-lookup"><span data-stu-id="b5c8d-110">To create new meeting join settings</span></span>

1.  <span data-ttu-id="b5c8d-111">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b5c8d-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b5c8d-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b5c8d-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b5c8d-114">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-114">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="b5c8d-115">En la página **Configuración de reunión**, haga clic en **Nueva** y después realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b5c8d-115">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="b5c8d-p103">Para crear una directiva de nivel de sitio, haga clic en **Configuración de sitio**. En el campo de búsqueda **Seleccionar un sitio**, escriba el nombre, o parte del nombre, del sitio para el que desee definir la configuración de participación en reuniones. En la lista de sitios resultante, haga clic en el sitio que desee y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-p103">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="b5c8d-p104">Para crear una directiva de nivel de grupo de servidores, haga clic en **Configuración del grupo de servidores**. En el campo de búsqueda **Seleccionar un servicio**, escriba el nombre, o parte del nombre, del servicio del grupo de servidores para el que desee definir la configuración de participación en reuniones. En la lista de servicios resultante, haga clic en el grupo de servidores que desee y después en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-p104">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="b5c8d-p105">Para redirigir a los participantes que realizaron la llamada desde una red telefónica conmutada (RTC) a través de la sala de espera, desactive la casilla **Los autores de llamadas RTC no pasan por la sala de espera**. Normalmente, los participantes que efectúen la llamada desde la RTC obtendrán acceso directamente a la reunión.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-p105">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="b5c8d-124">Para configurar quién puede ser moderador en una reunión, en **Designar como moderador**, lleve a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5c8d-124">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="b5c8d-125">Para que solo sea moderador el organizador, haga clic en **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-125">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="b5c8d-p106">Para que solo sean moderadores los participantes que pertenezcan a la organización, haga clic en **Compañía**. Esta es la configuración que se aplica normalmente.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-p106">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
      - <span data-ttu-id="b5c8d-128">Para que cualquier participante sea moderador, haga clic en **Todos**.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-128">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="b5c8d-p107">Para que el moderador pueda seleccionar un tipo de conferencia cuando se programe una reunión, desactive la casilla **Tipo de conferencia asignada de forma predeterminada**. Normalmente, el tipo de conferencia se asigna automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-p107">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="b5c8d-p108">Para evitar que se admitan automáticamente a usuarios anónimos (sin autenticar), desactive la casilla **Admitir usuarios anónimos de forma predeterminada**. Normalmente, los usuarios anónimos se admiten automáticamente en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-p108">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="b5c8d-133">Para personalizar la invitación a la reunión que se envía a los participantes, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-133">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="b5c8d-134">Recuerde que la longitud máxima de las direcciones URL y el texto de pie de página personalizado es de 1 KB.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-134">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="b5c8d-135">Salvo en el caso de la **Dirección URL de la Ayuda**, si no especifica un valor para las personalizaciones, no se incluirán en la reunión.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-135">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="b5c8d-136">Si no incluye una dirección URL de ayuda personalizada, la dirección URL de la ayuda predeterminada para Lync se mostrará en la invitación.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-136">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="b5c8d-137">Para personalizar el logotipo que aparece en la invitación de la reunión, en **Dirección URL del logotipo**, especifique la ubicación del logotipo.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-137">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="b5c8d-138">El logotipo debe ser una imagen GIF o JPG con un tamaño de 188 por 30 píxeles.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-138">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="b5c8d-139">Para personalizar el texto de ayuda que aparece en la invitación a la reunión, en la **Dirección URL de la Ayuda**, especifique la ubicación del texto de ayuda.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-139">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="b5c8d-140">Para personalizar el texto legal que aparece en la invitación de la reunión, en **Dirección URL del texto legal**, especifique la ubicación del logotipo.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-140">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="b5c8d-141">Para personalizar el texto del pie de página que aparece en la invitación a la reunión, en **Texto de pie de página personalizado**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-141">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="b5c8d-142">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="b5c8d-143">Para modificar una colección de configuraciones de reunión existente</span><span class="sxs-lookup"><span data-stu-id="b5c8d-143">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="b5c8d-144">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b5c8d-145">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b5c8d-146">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b5c8d-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b5c8d-147">En la barra de navegación izquierda, haga clic en **Conferencia** y después en **Configuración de reunión**.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-147">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="b5c8d-148">En la lista de configuraciones de reunión, haga clic en la configuración que desee cambiar, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-148">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b5c8d-149">En **Editar configuración de reunión**, modifique cualquiera de las configuraciones de participación en reuniones, excepto el nombre, que no se puede modificar.
</span><span class="sxs-lookup"><span data-stu-id="b5c8d-149">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="b5c8d-150">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-150">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b5c8d-151">Crear nuevas opciones de configuración de reuniones con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5c8d-151">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b5c8d-152">Se pueden crear opciones de configuración de reunión (solo en el ámbito del sitio) mediante Windows PowerShell y el cmdlet New-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-152">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="b5c8d-153">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-153">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b5c8d-154">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="b5c8d-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="b5c8d-155">Para crear opciones de configuración de reunión que usen los valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="b5c8d-155">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="b5c8d-156">Este comando crea un conjunto de configuraciones de reunión nuevo para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="b5c8d-156">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="b5c8d-157">Como no se especificó ningún parámetro (salvo el parámetro de identidad obligatorio) en el comando anterior, la configuración de reunión nueva usará los valores habituales para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="b5c8d-157">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="b5c8d-158">Para cambiar el valor de una propiedad al crear una configuración de reunión</span><span class="sxs-lookup"><span data-stu-id="b5c8d-158">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="b5c8d-p112">Para crear configuraciones que usen valores de propiedad diferentes, solo tiene que incluir el parámetro y el valor de parámetro adecuado. Por ejemplo, para crear una colección de configuraciones de reunión que admitan siempre a todos los participantes de una reunión como moderadores, use un comando como este:</span><span class="sxs-lookup"><span data-stu-id="b5c8d-p112">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="b5c8d-161">Para cambiar varios valores de propiedad al crear opciones de configuración de reunión</span><span class="sxs-lookup"><span data-stu-id="b5c8d-161">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="b5c8d-p113">Puede cambiar varios valores de propiedad incluyendo varios parámetros. Por ejemplo, este comando admite a todos los participantes de la reunión como moderadores y también obliga a los usuarios de RTC a permanecer en la sala de espera hasta que se les admita formalmente a la reunión:</span><span class="sxs-lookup"><span data-stu-id="b5c8d-p113">Multiple property values can be modified by including multiple parameters. For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="b5c8d-164">Para obtener más información, consulte el tema de ayuda del cmdlet [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="b5c8d-164">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

