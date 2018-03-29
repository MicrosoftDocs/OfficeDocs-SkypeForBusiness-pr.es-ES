---
title: Administrar cuentas de usuario de Skype para Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Las secciones de este artículo describen cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype para Business Server 2015.
ms.openlocfilehash: bd09687a6a2d2f3d1e8dcfe13b7f8aa64648e56b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-user-accounts-for-skype-for-business-server-2015"></a><span data-ttu-id="4c584-103">Administrar cuentas de usuario de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4c584-103">Manage user accounts for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4c584-104">Las secciones de este artículo describen cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4c584-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4c584-105">Para obtener información sobre cómo habilitar a un usuario de Active Directory, vea [crear una nueva cuenta de usuario](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="4c584-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="4c584-106">Para obtener información sobre cómo eliminar un usuario de Active Directory, vea [Eliminar una cuenta de usuario](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="4c584-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>
  
<span data-ttu-id="4c584-107">Estos procedimientos deben realizarse durante un período de mantenimiento, cuando Skype para uso comercial es el más bajo.</span><span class="sxs-lookup"><span data-stu-id="4c584-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="4c584-108">Si esto se realiza en una programación diaria o semanal determinará las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="4c584-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span> 
  
<span data-ttu-id="4c584-109">Este artículo contiene los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="4c584-109">This article contains the following procedures:</span></span>
  
- [<span data-ttu-id="4c584-110">Para buscar uno o más usuarios</span><span class="sxs-lookup"><span data-stu-id="4c584-110">To search for one or more users</span></span>](user-accounts.md#Search)
    
- [<span data-ttu-id="4c584-111">Agregar y habilitar un nuevo Skype para usuario Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4c584-111">Add and enable a new Skype for Business Server 2015 user</span></span>](user-accounts.md#Add)
    
- [<span data-ttu-id="4c584-112">Deshabilitar o volver a habilitar una cuenta de usuario habilitada previamente para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="4c584-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)
    
- [<span data-ttu-id="4c584-113">Deshabilitar a un usuario de Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="4c584-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)
    
- [<span data-ttu-id="4c584-114">Quitar una cuenta de usuario con el Skype para el Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="4c584-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)
    
## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="4c584-115">Para buscar uno o más usuarios</span><span class="sxs-lookup"><span data-stu-id="4c584-115">To search for one or more users</span></span>
<span data-ttu-id="4c584-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="4c584-116"></span></span>

<span data-ttu-id="4c584-117">Puede utilizar los resultados de una consulta de búsqueda para configurar usuarios de Active Directory para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4c584-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server 2015.</span></span> <span data-ttu-id="4c584-118">Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el nombre de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.</span><span class="sxs-lookup"><span data-stu-id="4c584-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>
  
<span data-ttu-id="4c584-119">Puede buscar usuarios utilizando el Skype para el Panel de Control de Business Server o Active Directory Users y complemento equipos.</span><span class="sxs-lookup"><span data-stu-id="4c584-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="4c584-120">El procedimiento siguiente describe cómo usar Skype para Business Server Control Panel para buscar usuarios.</span><span class="sxs-lookup"><span data-stu-id="4c584-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c584-121">En un entorno con una topología de bosque central, resultados de búsqueda podrían no ser exactos al buscar un usuario por su dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="4c584-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="4c584-122">En su lugar, puede buscar los usuarios especificando un prefijo de dirección SIP, por ejemplo, sip: nombre, agregar un filtro de búsqueda y seleccione una dirección SIP que contiene una dirección de correo electrónico parcial o usar el cmdlet **Get-Csusuario** .</span><span class="sxs-lookup"><span data-stu-id="4c584-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>
  
1. <span data-ttu-id="4c584-123">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4c584-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4c584-124">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4c584-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4c584-125">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="4c584-125">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4c584-126">En el cuadro de **búsqueda usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, apellido, nombre de cuenta SAM, dirección SIP o línea de URI de la cuenta de usuario que desea buscar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="4c584-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>
    
5. <span data-ttu-id="4c584-127">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="4c584-127">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="4c584-128">a.</span><span class="sxs-lookup"><span data-stu-id="4c584-128">a.</span></span> <span data-ttu-id="4c584-129">Haga clic en el botón de flecha de expansión en la esquina superior derecha de la pantalla situada por encima de los **resultados de la búsqueda**y, a continuación, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="4c584-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
   <span data-ttu-id="4c584-130">b.</span><span class="sxs-lookup"><span data-stu-id="4c584-130">b.</span></span> <span data-ttu-id="4c584-131">Especifique la propiedad de usuario escribiéndola o haciendo clic en la flecha de la lista desplegable para seleccionar una propiedad de usuario.</span><span class="sxs-lookup"><span data-stu-id="4c584-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
   <span data-ttu-id="4c584-132">c.</span><span class="sxs-lookup"><span data-stu-id="4c584-132">c.</span></span> <span data-ttu-id="4c584-133">En la lista **igual a** , haga clic en **igual a** o **no igual a**.</span><span class="sxs-lookup"><span data-stu-id="4c584-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
   <span data-ttu-id="4c584-134">d.</span><span class="sxs-lookup"><span data-stu-id="4c584-134">d.</span></span> <span data-ttu-id="4c584-135">En el cuadro de texto, escriba los criterios de búsqueda que desee utilizar para filtrar los resultados de la búsqueda y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="4c584-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>
    
6. <span data-ttu-id="4c584-136">Resultados de la búsqueda aparecen en los **Resultados de la búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="4c584-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="4c584-137">Puede seleccionar alguno o todos los usuarios en la lista y realizar tareas de configuración de los usuarios que seleccione.</span><span class="sxs-lookup"><span data-stu-id="4c584-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>
    
## <a name="add-and-enable-a-new-skype-for-business-server-2015-user"></a><span data-ttu-id="4c584-138">Agregar y habilitar un nuevo Skype para usuario Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4c584-138">Add and enable a new Skype for Business Server 2015 user</span></span>
<span data-ttu-id="4c584-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="4c584-139"></span></span>

<span data-ttu-id="4c584-140">Después de habilitar una cuenta de usuario en Active Directory Users and Computers, puede utilizar Skype para Business Server Control Panel para crear y habilitar el nuevo Skype para cuentas de usuario de Business Server 2015 agregando un usuario de Active Directory a Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4c584-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server 2015 user accounts by adding an Active Directory user to Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4c584-141">También puede utilizar un cmdlet, específicamente [Habilitar Csusuario](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4c584-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>
  
1. <span data-ttu-id="4c584-142">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4c584-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4c584-143">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4c584-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4c584-144">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="4c584-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4c584-145">Haga clic en **Permitir a los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="4c584-145">Click **Enable users**.</span></span>
    
5. <span data-ttu-id="4c584-146">En el cuadro de diálogo **Nuevo usuario de Lync Server** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4c584-146">On the **New Lync Server User** dialog, click **Add**.</span></span>
    
6. <span data-ttu-id="4c584-147">En el cuadro de **búsqueda usuarios** , escriba todo o la primera parte del nombre, Mostrar nombre, nombre, apellido, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección de correo electrónico, nombre Principal de usuario (UPN) o número de teléfono de la cuenta de usuario de Active Directory que desee y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="4c584-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>
    
7. <span data-ttu-id="4c584-148">En la tabla, seleccione la cuenta que desea agregar a Skype para Business Server 2015 y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4c584-148">In the table, select the account you want to add to Skype for Business Server 2015, and then click **OK**.</span></span>
    
8. <span data-ttu-id="4c584-149">Asignar al usuario a un grupo, especifique detalles adicionales y asignar las directivas para el usuario que desee y, a continuación, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="4c584-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>
    
## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="4c584-150">Deshabilitar o volver a habilitar una cuenta de usuario habilitada previamente para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="4c584-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="4c584-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="4c584-151"></span></span>

<span data-ttu-id="4c584-152">Puede utilizar el procedimiento siguiente para deshabilitar una cuenta de usuario previamente habilitado en Skype para Business Server sin perder la Skype para la configuración del servidor de la empresa que ha configurado para la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="4c584-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="4c584-153">Porque no se pierden el Skype para la configuración de cuentas de usuario de Business Server, se puede volver a habilitar una cuenta de usuario previamente habilitado otra vez sin tener que volver a configurar la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="4c584-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span> 
  
1. <span data-ttu-id="4c584-154">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4c584-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4c584-155">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4c584-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4c584-156">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="4c584-156">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4c584-157">En el cuadro de **búsqueda usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, apellido, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de Uniform Resource Identifier (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar, y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="4c584-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="4c584-158">En la tabla, haga clic en la cuenta de usuario que desea volver a habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="4c584-158">In the table, click the user account that you want to disable or re-enable.</span></span>
    
6. <span data-ttu-id="4c584-159">En el menú **acción** , siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="4c584-159">On the **Action** menu, do one of the following:</span></span>
    
   - <span data-ttu-id="4c584-160">Para deshabilitar temporalmente la cuenta de usuario de Skype para Business Server, haga clic en **deshabilitar temporalmente para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4c584-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>
    
   - <span data-ttu-id="4c584-161">Para habilitar la cuenta de usuario de Skype para Business Server, haga clic en **volver a habilitar para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4c584-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>
    
### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="4c584-162">Usar Windows Powershell para deshabilitar o volver a habilitar las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="4c584-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="4c584-163">Las cuentas de usuario pueden temporalmente deshabilitadas y posteriormente volver a habilitarla después, mediante el cmdlet **Set-Csusuario** .</span><span class="sxs-lookup"><span data-stu-id="4c584-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="4c584-164">Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c584-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4c584-165">Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="4c584-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="4c584-166">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="4c584-166">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-disable-a-user-account"></a><span data-ttu-id="4c584-167">Para deshabilitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="4c584-167">To disable a user account</span></span>

- <span data-ttu-id="4c584-168">Para deshabilitar temporalmente una cuenta de usuario, establezca el valor de la propiedad Enabled en False ($False).</span><span class="sxs-lookup"><span data-stu-id="4c584-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="4c584-169">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4c584-169">For example:</span></span>
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="4c584-170">Para volver a habilitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="4c584-170">To re-enable a user account</span></span>

- <span data-ttu-id="4c584-171">Para volver a habilitar una cuenta de usuario deshabilitada, establezca el valor de la propiedad Enabled en True ($True).</span><span class="sxs-lookup"><span data-stu-id="4c584-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="4c584-172">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4c584-172">For example:</span></span>
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="4c584-173">Para obtener más información, vea el tema de ayuda para el cmdlet [Set-Csusuario](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="4c584-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>
  
## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="4c584-174">Deshabilitar a un usuario de Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="4c584-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="4c584-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="4c584-175"></span></span>

<span data-ttu-id="4c584-176">Utilice el procedimiento siguiente para deshabilitar la Telefonía IP empresarial en una cuenta de usuario está habilitada para Skype en Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4c584-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server 2015.</span></span>
  
### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="4c584-177">Para deshabilitar una cuenta de usuario para Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="4c584-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="4c584-178">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4c584-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4c584-179">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4c584-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4c584-180">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="4c584-180">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4c584-181">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="4c584-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="4c584-182">En la tabla, haga clic en la cuenta de usuario que desea habilitar para Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="4c584-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="4c584-183">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="4c584-183">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="4c584-184">En la página **Modificar usuario de Lync Server** , **telefonía**, haga clic en cualquier opción excepto **Telefonía IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="4c584-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c584-185">Para impedir que un usuario realizar llamadas de audio o vídeo utilizando Lync en **telefonía**, haga clic en **deshabilitado de Audio y vídeo**.</span><span class="sxs-lookup"><span data-stu-id="4c584-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span> 
  
8. <span data-ttu-id="4c584-186">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4c584-186">Click **Commit**.</span></span>
    
<span data-ttu-id="4c584-187">El usuario es ahora no puede utilizar la característica de Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="4c584-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="4c584-188">Información relacionada:</span><span class="sxs-lookup"><span data-stu-id="4c584-188">Related information:</span></span> <br/>[<span data-ttu-id="4c584-189">Movilidad y Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="4c584-189">Enterprise Voice and mobility</span></span>](http://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="4c584-190">Permitir que los usuarios de Telefonía IP empresarial en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4c584-190">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="4c584-191">Skype para el Shell de administración de negocio servidor 2015</span><span class="sxs-lookup"><span data-stu-id="4c584-191">Skype for Business Server 2015 Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="4c584-192">Quitar una cuenta de usuario con el Skype para el Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="4c584-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="4c584-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="4c584-193"></span></span>

<span data-ttu-id="4c584-194">Puede utilizar el siguiente procedimiento para quitar una cuenta de usuario previamente agregado de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4c584-194">You can use the following procedure to remove a previously added user account in Skype for Business Server 2015.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4c584-195">Quitar un usuario hará que pierda cualquier configuración de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="4c584-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="4c584-196">Si desea deshabilitar temporalmente una cuenta de usuario en su lugar, vea [Deshabilitar o volver a habilitar una cuenta de usuario habilitada previamente para Skype para Business Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="4c584-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span> 
  
1. <span data-ttu-id="4c584-197">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4c584-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4c584-198">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4c584-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4c584-199">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="4c584-199">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4c584-200">En el cuadro de **búsqueda usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, apellido, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de Uniform Resource Identifier (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar, y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="4c584-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="4c584-201">En la tabla, haga clic en la cuenta de usuario que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="4c584-201">In the table, click the user account that you want to remove.</span></span>
    
6. <span data-ttu-id="4c584-202">En el menú **acción** , seleccione **quitar de Lync Server**y un cuadro de diálogo aparecerá el cuadro de.</span><span class="sxs-lookup"><span data-stu-id="4c584-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>
    
7. <span data-ttu-id="4c584-203">En el cuadro de diálogo, seleccione **Aceptar** para eliminar el usuario.</span><span class="sxs-lookup"><span data-stu-id="4c584-203">From the dialog box, select **OK** to remove the user.</span></span>
    
### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="4c584-204">Quitar cuentas de usuario con los cmdlets de Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="4c584-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="4c584-205">Puede quitar cuentas de usuario mediante el cmdlet Disable-Csusuario.</span><span class="sxs-lookup"><span data-stu-id="4c584-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="4c584-206">Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c584-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="4c584-207">Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="4c584-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="4c584-208">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="4c584-208">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-user-account"></a><span data-ttu-id="4c584-209">Para quitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="4c584-209">To remove a user account</span></span>
<span data-ttu-id="4c584-210">Para quitar una cuenta de usuario, utilice el cmdlet Disable-Csusuario.</span><span class="sxs-lookup"><span data-stu-id="4c584-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="4c584-211">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4c584-211">For example:</span></span>
    
  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.
    
<span data-ttu-id="4c584-212">Para obtener más información, vea el tema de ayuda para el cmdlet [Disable-Csusuario](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="4c584-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4c584-213">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c584-213">See also</span></span>
<span data-ttu-id="4c584-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="4c584-214"></span></span>

#### 

[<span data-ttu-id="4c584-215">Habilitar CsUser</span><span class="sxs-lookup"><span data-stu-id="4c584-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)
  
[<span data-ttu-id="4c584-216">Deshabilitar CsUser</span><span class="sxs-lookup"><span data-stu-id="4c584-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

