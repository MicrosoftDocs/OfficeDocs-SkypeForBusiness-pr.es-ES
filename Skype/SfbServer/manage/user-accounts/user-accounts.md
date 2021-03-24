---
title: Administrar cuentas de usuario para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: En las secciones de este artículo se describe cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype Empresarial Server.
ms.openlocfilehash: 0cf78b4ebe7023bc5a0f1b4af75c5d9e5a45db1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103126"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="5e5fc-103">Administrar cuentas de usuario para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5e5fc-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="5e5fc-104">En las secciones de este artículo se describe cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="5e5fc-105">Para obtener información sobre cómo habilitar un usuario de Active Directory, vea [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-105">For information on how to enable an Active Directory user, see [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)).</span></span> <span data-ttu-id="5e5fc-106">Para obtener información sobre cómo eliminar un usuario de Active Directory, vea [Eliminar una cuenta de usuario](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-106">For information on how to delete an Active Directory user, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>

<span data-ttu-id="5e5fc-107">Estos procedimientos deben realizarse durante una ventana de mantenimiento, cuando el uso de Skype Empresarial sea el más bajo.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="5e5fc-108">Si esto se realiza en una programación diaria o semanal, se determinará según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="5e5fc-109">Este artículo contiene los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="5e5fc-110">Para buscar uno o más usuarios</span><span class="sxs-lookup"><span data-stu-id="5e5fc-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="5e5fc-111">Agregar y habilitar un nuevo usuario de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5e5fc-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="5e5fc-112">Deshabilitar o volver a habilitar una cuenta de usuario habilitada anteriormente para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5e5fc-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="5e5fc-113">Deshabilitar un usuario para Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="5e5fc-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="5e5fc-114">Quitar una cuenta de usuario con el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5e5fc-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="5e5fc-115">Para buscar uno o más usuarios</span><span class="sxs-lookup"><span data-stu-id="5e5fc-115">To search for one or more users</span></span>
<span data-ttu-id="5e5fc-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="5e5fc-116"><a name="Search"> </a></span></span>

<span data-ttu-id="5e5fc-117">Puede usar los resultados de una consulta de búsqueda para configurar usuarios de Active Directory para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="5e5fc-118">Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el número de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="5e5fc-119">Puede buscar usuarios mediante el Panel de control de Skype Empresarial Server o el complemento Usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="5e5fc-120">En el siguiente procedimiento se describe cómo usar el Panel de control de Skype Empresarial Server para buscar usuarios.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="5e5fc-121">En un entorno con una topología de bosque central, es posible que los resultados de la búsqueda no sean precisos al buscar un usuario por la dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="5e5fc-122">En su lugar, puede buscar usuarios especificando un prefijo de dirección SIP, por ejemplo, sip:name, agregar un filtro de búsqueda y seleccionar una dirección SIP que contenga una dirección de correo electrónico parcial, o usar el cmdlet **Get-CSUser**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="5e5fc-123">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="5e5fc-124">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="5e5fc-125">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="5e5fc-126">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee buscar y después haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="5e5fc-127">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="5e5fc-128">a.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-128">a.</span></span> <span data-ttu-id="5e5fc-129">Haga clic en la flecha para expandir de la esquina superior derecha de la pantalla que hay sobre **Resultados de la búsqueda** y después haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="5e5fc-130">b.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-130">b.</span></span> <span data-ttu-id="5e5fc-131">Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="5e5fc-132">c.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-132">c.</span></span> <span data-ttu-id="5e5fc-133">En la lista **Igual a**, haga clic en **Igual a** o **No igual a**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="5e5fc-134">d.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-134">d.</span></span> <span data-ttu-id="5e5fc-135">En el cuadro de texto, escriba los criterios de búsqueda que desea usar para filtrar los resultados y después haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="5e5fc-p110">Los resultados de búsqueda aparecerán en el cuadro **Resultados de búsqueda**. Puede seleccionar uno, varios o todos los usuarios de la lista y realizar tareas de configuración en los usuarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-p110">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="5e5fc-138">Agregar y habilitar un nuevo usuario de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5e5fc-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="5e5fc-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="5e5fc-139"><a name="Add"> </a></span></span>

<span data-ttu-id="5e5fc-140">Después de habilitar una cuenta de usuario en Usuarios y equipos de Active Directory, puede usar el Panel de control de Skype Empresarial Server para crear y habilitar nuevas cuentas de usuario de Skype Empresarial Server agregando un usuario de Active Directory a Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="5e5fc-141">También puede usar un cmdlet, específicamente [Enable-CsUser](/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-141">You can also use a cmdlet, specifically [Enable-CsUser](/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="5e5fc-142">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="5e5fc-143">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="5e5fc-144">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="5e5fc-145">Haga clic en **Habilitar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="5e5fc-146">En el cuadro de diálogo **Nuevo usuario de Lync Server**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="5e5fc-147">En el cuadro **Buscar usuarios**, escriba el nombre completo o parcial, el nombre para mostrar, el apellido, el nombre de la cuenta del Administrador de cuentas de seguridad, la dirección de correo electrónico, el nombre principal del usuario (UPN) o el número de teléfono del usuario de Active Directory que está buscando y después haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="5e5fc-148">En la tabla, seleccione la cuenta que desea agregar a Skype Empresarial Server y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="5e5fc-149">Asigne el usuario a un grupo de servidores, especifique datos adicionales si lo considera necesario y asigne las directivas al usuario que desee; luego haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="5e5fc-150">Deshabilitar o volver a habilitar una cuenta de usuario habilitada anteriormente para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5e5fc-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="5e5fc-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="5e5fc-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="5e5fc-152">Puede usar el siguiente procedimiento para deshabilitar una cuenta de usuario habilitada anteriormente en Skype Empresarial Server sin perder la configuración de Skype Empresarial Server que configuró para la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="5e5fc-153">Dado que no pierde la configuración de la cuenta de usuario de Skype Empresarial Server, puede volver a habilitar una cuenta de usuario habilitada previamente sin tener que volver a configurar la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="5e5fc-154">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="5e5fc-155">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="5e5fc-156">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="5e5fc-157">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee deshabilitar o volver a habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="5e5fc-158">En la tabla, haga clic en la cuenta de usuario que desea deshabilitar o volver a habilitar.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="5e5fc-159">En el **menú** Acción, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="5e5fc-160">Para deshabilitar temporalmente la cuenta de usuario de Skype Empresarial Server, haga clic en Deshabilitar **temporalmente para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="5e5fc-161">Para habilitar la cuenta de usuario de Skype Empresarial Server, haga clic **en Volver a habilitar para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="5e5fc-162">Usar Windows Powershell para deshabilitar o volver a habilitar cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="5e5fc-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="5e5fc-163">Las cuentas de usuario se pueden deshabilitar temporalmente y, posteriormente, volver a habilitarse mediante el cmdlet **Set-CsUser.**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="5e5fc-164">Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5e5fc-165">Para obtener más información acerca del Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="5e5fc-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5e5fc-166">El proceso es el mismo en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="5e5fc-167">Para deshabilitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="5e5fc-167">To disable a user account</span></span>

- <span data-ttu-id="5e5fc-168">Para deshabilitar temporalmente una cuenta de usuario, establezca el valor de la propiedad Enabled en False ($False).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="5e5fc-169">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="5e5fc-170">Para volver a habilitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="5e5fc-170">To re-enable a user account</span></span>

- <span data-ttu-id="5e5fc-171">Para volver a habilitar una cuenta de usuario deshabilitada, establezca el valor de la propiedad Enabled en True ($True).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="5e5fc-172">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="5e5fc-173">Para obtener más información, vea el tema de ayuda del cmdlet [Set-CsUser.](/powershell/module/skype/set-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="5e5fc-173">For more information, see the help topic for the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="5e5fc-174">Deshabilitar un usuario para Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="5e5fc-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="5e5fc-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="5e5fc-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="5e5fc-176">Use el siguiente procedimiento para deshabilitar Telefonía IP empresarial una cuenta de usuario habilitada para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="5e5fc-177">Para deshabilitar una cuenta de usuario para Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="5e5fc-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="5e5fc-178">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="5e5fc-179">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="5e5fc-180">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="5e5fc-181">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="5e5fc-182">En la tabla, haga clic en la cuenta de usuario que desea habilitar para Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="5e5fc-183">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="5e5fc-184">En la página **Editar usuario de Lync Server**, en **Telefonía**, haga clic en cualquier opción excepto **Telefonía IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e5fc-185">Para restringir que un usuario haga llamadas de audio o vídeo mediante Lync, en **Telefonía,** haga clic en **Audio/vídeo deshabilitado.**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="5e5fc-186">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-186">Click **Commit**.</span></span>

<span data-ttu-id="5e5fc-187">El usuario ahora no puede usar la característica Telefonía IP empresarial usuario.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="5e5fc-188">Información relacionada:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-188">Related information:</span></span> <br/>[<span data-ttu-id="5e5fc-189">Telefonía IP empresarial y movilidad</span><span class="sxs-lookup"><span data-stu-id="5e5fc-189">Enterprise Voice and mobility</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [<span data-ttu-id="5e5fc-190">Habilitar usuarios para Telefonía IP empresarial en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5e5fc-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="5e5fc-191">Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5e5fc-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="5e5fc-192">Quitar una cuenta de usuario con el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5e5fc-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="5e5fc-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="5e5fc-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="5e5fc-194">Puede usar el siguiente procedimiento para quitar una cuenta de usuario agregada anteriormente en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="5e5fc-195">Eliminar un usuario provocará que pierda los parámetros que haya configurado para la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="5e5fc-196">Si desea deshabilitar temporalmente una cuenta de usuario en su lugar, vea [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="5e5fc-197">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="5e5fc-198">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="5e5fc-199">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="5e5fc-200">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee deshabilitar o volver a habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="5e5fc-201">En la tabla, haga clic en la cuenta de usuario que desee quitar.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="5e5fc-202">En el menú **Acción**, seleccione **Quitar de Lync Server** y, a continuación, aparecerá un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="5e5fc-203">En el cuadro de diálogo, seleccione **Aceptar** para quitar el usuario.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="5e5fc-204">Quitar cuentas de usuario con cmdlets de Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="5e5fc-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="5e5fc-205">Puede quitar cuentas de usuario mediante el cmdlet Disable-CsUser usuario.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="5e5fc-206">Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="5e5fc-207">Para obtener más información acerca del Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="5e5fc-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5e5fc-208">El proceso es el mismo en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="5e5fc-209">Para quitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="5e5fc-209">To remove a user account</span></span>
<span data-ttu-id="5e5fc-210">Para quitar una cuenta de usuario, utilice el cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="5e5fc-211">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="5e5fc-212">Para obtener más información, vea el tema de ayuda del cmdlet [Disable-CsUser.](/powershell/module/skype/disable-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="5e5fc-212">For more information, see the help topic for the [Disable-CsUser](/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e5fc-213">Ver también</span><span class="sxs-lookup"><span data-stu-id="5e5fc-213">See also</span></span>
<span data-ttu-id="5e5fc-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="5e5fc-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="5e5fc-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="5e5fc-215">Enable-CsUser</span></span>](/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="5e5fc-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="5e5fc-216">Disable-CsUser</span></span>](/powershell/module/skype/disable-csuser?view=skype-ps)