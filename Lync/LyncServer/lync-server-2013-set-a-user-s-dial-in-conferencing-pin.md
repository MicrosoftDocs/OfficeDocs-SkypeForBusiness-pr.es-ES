---
title: 'Lync Server 2013: establecer el PIN de conferencia de acceso telefónico local de un usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c344a848050d53027c094ad549f0285fbae09489
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a><span data-ttu-id="8c0e9-102">Establecer el PIN de conferencia de acceso telefónico local de un usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c0e9-102">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c0e9-103">_**Última modificación del tema:** 2014-06-10_</span><span class="sxs-lookup"><span data-stu-id="8c0e9-103">_**Topic Last Modified:** 2014-06-10_</span></span>

<span data-ttu-id="8c0e9-104">Para unirse a una conferencia de acceso telefónico local como usuario autenticado, un usuario de Lync Server 2013 con credenciales de servicios de dominio de Active Directory (AD DS) requiere un número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="8c0e9-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="8c0e9-105">Si un usuario olvida el PIN de conferencia de acceso telefónico local o no ha establecido el PIN con Lync Server, puede establecer el PIN del usuario desde el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-105">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Lync Server, you can set the user’s PIN from Lync Server Control Panel.</span></span> <span data-ttu-id="8c0e9-106">Puede generar el PIN automáticamente o crear uno de forma manual.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-106">You can automatically generate the PIN or create one manually.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c0e9-107">Las características específicas del PIN como, por ejemplo, su longitud mínima, pueden configurarse como una directiva.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-107">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="8c0e9-108">Además de la directiva global, puede configurar una directiva de PIN para sitios o usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-108">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> <span data-ttu-id="8c0e9-109">Para obtener más información sobre cómo configurar una directiva de PIN, vea <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">configurar las reglas de número de identificación personal (PIN) de conferencia de acceso telefónico local en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-109">For details about configuring a PIN policy, see <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-set-a-users-pin"></a><span data-ttu-id="8c0e9-110">Para definir el PIN de un usuario</span><span class="sxs-lookup"><span data-stu-id="8c0e9-110">To set a user’s PIN</span></span>

1.  <span data-ttu-id="8c0e9-111">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8c0e9-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8c0e9-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8c0e9-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8c0e9-114">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8c0e9-115">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="8c0e9-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="8c0e9-116">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="8c0e9-117">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="8c0e9-118">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="8c0e9-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="8c0e9-119">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="8c0e9-120">Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="8c0e9-121">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="8c0e9-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="8c0e9-122">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-122">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="8c0e9-123">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="8c0e9-124">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-124">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c0e9-p104">Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en <STRONG>Acción</STRONG> y en <STRONG>Desbloquear PIN</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="8c0e9-127">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Establecer PIN**.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-127">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>

7.  <span data-ttu-id="8c0e9-128">En el cuadro de diálogo **Establecer PIN**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8c0e9-128">In the **Set PIN** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="8c0e9-129">Para permitir que Lync Server 2013 genere el PIN del usuario, seleccione **generar automáticamente un PIN válido** (opción predeterminada).</span><span class="sxs-lookup"><span data-stu-id="8c0e9-129">To allow Lync Server 2013 to generate the user’s PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
      - <span data-ttu-id="8c0e9-130">Para crear su propio PIN, haga clic en **Introducir manualmente un PIN específico**, haga clic en el cuadro de texto y escriba un PIN que cumpla los requisitos de PIN especificados en la configuración de la directiva de PIN.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-130">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>

8.  <span data-ttu-id="8c0e9-131">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-131">Click **OK**.</span></span>

9.  <span data-ttu-id="8c0e9-132">En **Establecer PIN**, lleve a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8c0e9-132">In **Set PIN**, do one of the following:</span></span>
    
      - <span data-ttu-id="8c0e9-133">Active la casilla **Mostrar PIN** para ver el PIN y, a continuación, copie el PIN e informe del mismo al usuario mediante el método preferido en su organización.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-133">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
      - <span data-ttu-id="8c0e9-p105">Haga clic en **Abrir mi aplicación de correo electrónico para enviar el nuevo PIN al usuario** para enviar el PIN por correo electrónico. Si su cliente de correo electrónico es Microsoft Office Outlook, el PIN se copia automáticamente en un mensaje de correo electrónico nuevo. Si usa un cliente de correo electrónico diferente, active la casilla **Mostrar PIN** para ver el PIN y cópielo en el mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-p105">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>

10. <span data-ttu-id="8c0e9-137">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-137">Click **Close**.</span></span>

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8c0e9-138">Asignación de un PIN de usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c0e9-138">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8c0e9-139">Puede asignar números de PIN que también se pueden asignar mediante el cmdlet Set-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-139">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="8c0e9-140">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-140">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8c0e9-141">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-141">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="8c0e9-142">Para asignar automáticamente un número de PIN a un usuario</span><span class="sxs-lookup"><span data-stu-id="8c0e9-142">To auto-assign a PIN number to a user</span></span>

  - <span data-ttu-id="8c0e9-143">El siguiente comando asigna a un número PIN al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-143">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="8c0e9-144">Debido a que no se incluye el parámetro PIN, Lync Server generará y asignará automáticamente el número PIN.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-144">Because the Pin parameter is not included, Lync Server will automatically generate and assign the PIN number.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="8c0e9-145">Para asignar un número de PIN específico a un usuario</span><span class="sxs-lookup"><span data-stu-id="8c0e9-145">To assign a specific PIN number to a user</span></span>

  - <span data-ttu-id="8c0e9-146">Este comando usa el parámetro PIN para asignar el número PIN 121989 al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="8c0e9-146">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

<span data-ttu-id="8c0e9-147">Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .</span><span class="sxs-lookup"><span data-stu-id="8c0e9-147">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c0e9-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c0e9-148">See Also</span></span>


<span data-ttu-id="8c0e9-149">[Número de acceso telefónico local](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8c0e9-149">[Dial-in Access Number](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))</span></span>  


[<span data-ttu-id="8c0e9-150">Configurar reglas de número de identificación personal (PIN) de conferencia de acceso telefónico en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c0e9-150">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

