---
title: Establecer telefónico un usuario PIN en Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Resumen: Establecer telefónico un usuario PIN para Skype para Business Server.'
ms.openlocfilehash: e5d14af74c208aaf29fffe94937afc1253a032da
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009385"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="02c27-103">Establecer telefónico un usuario PIN en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="02c27-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="02c27-104">**Resumen:** Establecer telefónico un usuario PIN para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="02c27-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="02c27-105">Para unirse a una conferencia de acceso telefónico como un usuario autenticado, una Skype para usuario Business Server con las credenciales de los servicios de dominio de Active Directory (AD DS) requiere un número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="02c27-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="02c27-106">Si un usuario olvida la conferencia telefónico PIN o no ha establecido el PIN mediante el uso de Skype para Business Server, puede establecer el PIN del usuario de Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="02c27-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="02c27-107">Puede generar el PIN automáticamente o crear uno de forma manual.</span><span class="sxs-lookup"><span data-stu-id="02c27-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="02c27-p102">Las características específicas del PIN como, por ejemplo, su longitud mínima, pueden configurarse como una directiva. Además de la directiva global, puede configurar una directiva de PIN para sitios o usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="02c27-p102">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy. In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="02c27-110">Para establecer un PIN de usuario</span><span class="sxs-lookup"><span data-stu-id="02c27-110">To set a user's PIN</span></span>

1. <span data-ttu-id="02c27-111">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="02c27-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="02c27-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="02c27-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="02c27-113">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="02c27-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="02c27-114">Utilice uno de los métodos siguientes para encontrar a un usuario:</span><span class="sxs-lookup"><span data-stu-id="02c27-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="02c27-115">En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="02c27-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="02c27-116">Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="02c27-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="02c27-117">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="02c27-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="02c27-118">a.</span><span class="sxs-lookup"><span data-stu-id="02c27-118">a.</span></span> <span data-ttu-id="02c27-119">Haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="02c27-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="02c27-120">b.</span><span class="sxs-lookup"><span data-stu-id="02c27-120">b.</span></span> <span data-ttu-id="02c27-121">Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="02c27-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="02c27-122">c.</span><span class="sxs-lookup"><span data-stu-id="02c27-122">c.</span></span> <span data-ttu-id="02c27-123">En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).</span><span class="sxs-lookup"><span data-stu-id="02c27-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="02c27-124">d.</span><span class="sxs-lookup"><span data-stu-id="02c27-124">d.</span></span> <span data-ttu-id="02c27-125">En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="02c27-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="02c27-126">Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="02c27-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="02c27-127">e.</span><span class="sxs-lookup"><span data-stu-id="02c27-127">e.</span></span> <span data-ttu-id="02c27-128">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="02c27-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="02c27-p108">Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en **Acción** y en **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="02c27-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="02c27-131">Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Establecer PIN**.</span><span class="sxs-lookup"><span data-stu-id="02c27-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="02c27-132">En el cuadro de diálogo **Establecer PIN**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="02c27-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="02c27-133">Para permitir que Skype para Business Server generar el PIN del usuario, seleccione **generar automáticamente un PIN válido** (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="02c27-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="02c27-134">Para crear su propio PIN, haga clic en **Escribir manualmente un PIN específico**, haga clic en el cuadro de texto y escriba un PIN que cumpla los requisitos de PIN especificados en la configuración de la directiva de PIN.</span><span class="sxs-lookup"><span data-stu-id="02c27-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="02c27-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="02c27-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="02c27-136">En **Establecer PIN**, lleve a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="02c27-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="02c27-137">Active la casilla **Mostrar PIN** para ver el PIN y, a continuación, copie el PIN e informe del mismo al usuario mediante el método preferido en su organización.</span><span class="sxs-lookup"><span data-stu-id="02c27-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="02c27-p109">Haga clic en **Abrir mi aplicación de correo electrónico para enviar el nuevo PIN al usuario** para enviar el PIN por correo electrónico. Si su cliente de correo electrónico es Microsoft Office Outlook, el PIN se copia automáticamente en un mensaje de correo electrónico nuevo. Si usa un cliente de correo electrónico diferente, active la casilla **Mostrar PIN** para ver el PIN y cópielo en el mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="02c27-p109">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="02c27-141">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="02c27-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="02c27-142">Asignar un PIN de usuario mediante Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="02c27-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="02c27-143">Puede asignar números de PIN con el cmdlet Set-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="02c27-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="02c27-144">Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02c27-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="02c27-145">Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="02c27-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="02c27-146">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="02c27-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="02c27-147">Para asignar automáticamente un número de PIN a un usuario</span><span class="sxs-lookup"><span data-stu-id="02c27-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="02c27-148">El siguiente comando asigna un número PIN al usuario a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="02c27-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="02c27-149">Debido a que no se incluye el parámetro de Pin, Skype para Business Server generará automáticamente y asignar al número PIN.</span><span class="sxs-lookup"><span data-stu-id="02c27-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="02c27-150">Para asignar automáticamente un número de PIN específico a un usuario</span><span class="sxs-lookup"><span data-stu-id="02c27-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="02c27-151">Este comando usa el parámetro PIN para asignar el número PIN 121989 al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="02c27-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="02c27-152">Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="02c27-152">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
  

