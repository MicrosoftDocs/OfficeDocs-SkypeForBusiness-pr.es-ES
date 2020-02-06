---
title: Administrar cuentas de usuario de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: En las secciones de este artículo se describe cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype empresarial Server.
ms.openlocfilehash: 33af0305fe25b9d7a272e89ae196923e97c4cfd3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817060"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="e1ec7-103">Administrar cuentas de usuario de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e1ec7-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="e1ec7-104">En las secciones de este artículo se describe cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="e1ec7-105">Para obtener información sobre cómo habilitar un usuario de Active Directory, consulte [crear una nueva cuenta de usuario](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e1ec7-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="e1ec7-106">Para obtener información sobre cómo eliminar un usuario de Active Directory, vea [eliminar una cuenta de usuario](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e1ec7-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="e1ec7-107">Estos procedimientos deben realizarse durante una ventana de mantenimiento, cuando el uso de Skype empresarial es el más bajo.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="e1ec7-108">El hecho de que se lleve a cabo con una programación diaria o semanal dependerá de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="e1ec7-109">Este artículo contiene los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e1ec7-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="e1ec7-110">Para buscar uno o más usuarios</span><span class="sxs-lookup"><span data-stu-id="e1ec7-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="e1ec7-111">Agregar y habilitar un nuevo usuario de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e1ec7-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="e1ec7-112">Deshabilitar o volver a habilitar una cuenta de usuario habilitada previamente para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e1ec7-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="e1ec7-113">Deshabilitar un usuario para telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="e1ec7-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="e1ec7-114">Quitar una cuenta de usuario con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e1ec7-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="e1ec7-115">Para buscar uno o más usuarios</span><span class="sxs-lookup"><span data-stu-id="e1ec7-115">To search for one or more users</span></span>
<span data-ttu-id="e1ec7-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="e1ec7-116"><a name="Search"> </a></span></span>

<span data-ttu-id="e1ec7-117">Puede usar los resultados de una consulta de búsqueda para configurar usuarios de Active Directory para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="e1ec7-118">Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el nombre de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="e1ec7-119">Puede buscar usuarios mediante el panel de control de Skype empresarial Server o el complemento usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="e1ec7-120">En el procedimiento siguiente se describe cómo usar el panel de control de Skype empresarial Server para buscar usuarios.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="e1ec7-121">En un entorno con una topología de bosque central, los resultados de la búsqueda podrían no ser exactos al buscar un usuario por la dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="e1ec7-122">En su lugar, puede buscar usuarios especificando un prefijo de dirección SIP, por ejemplo, SIP: Name, agregar un filtro de búsqueda y seleccionar una dirección SIP que contenga una dirección de correo electrónico parcial o usar el cmdlet **Get-CSUser** .</span><span class="sxs-lookup"><span data-stu-id="e1ec7-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="e1ec7-123">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="e1ec7-124">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e1ec7-125">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="e1ec7-126">En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta SAM, la dirección SIP o el URI de línea de la cuenta de usuario que desea buscar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="e1ec7-127">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="e1ec7-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="e1ec7-128">a.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-128">a.</span></span> <span data-ttu-id="e1ec7-129">Haga clic en el botón de flecha Expandir situado en la esquina superior derecha de la pantalla, encima de resultados de la **búsqueda**, y haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="e1ec7-130">b.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-130">b.</span></span> <span data-ttu-id="e1ec7-131">Escriba la propiedad de usuario escribiéndola o haciendo clic en la flecha de la lista desplegable para seleccionar una propiedad de usuario.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="e1ec7-132">c.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-132">c.</span></span> <span data-ttu-id="e1ec7-133">En la lista **igual a** , haga clic en **igual a** o **no es igual a**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="e1ec7-134">d.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-134">d.</span></span> <span data-ttu-id="e1ec7-135">En el cuadro de texto, escriba los criterios de búsqueda que desea usar para filtrar los resultados de la búsqueda y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="e1ec7-136">Los resultados de la búsqueda aparecen en resultados de la **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="e1ec7-137">Puede seleccionar cualquiera de los usuarios de la lista o todos ellos y realizar tareas de configuración en los usuarios que seleccione.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="e1ec7-138">Agregar y habilitar un nuevo usuario de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e1ec7-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="e1ec7-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="e1ec7-139"><a name="Add"> </a></span></span>

<span data-ttu-id="e1ec7-140">Tras habilitar una cuenta de usuario en usuarios y equipos de Active Directory, puede usar el panel de control de Skype empresarial Server para crear y habilitar nuevas cuentas de usuario de Skype empresarial Server agregando un usuario de Active Directory a Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="e1ec7-141">También puedes usar un cmdlet, específicamente [enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e1ec7-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="e1ec7-142">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="e1ec7-143">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e1ec7-144">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="e1ec7-145">Haga clic en **Habilitar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="e1ec7-146">En el cuadro de diálogo **nuevo usuario de Lync Server** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="e1ec7-147">En el cuadro **Buscar usuarios** , escriba toda o la primera parte del nombre, nombre para mostrar, nombre, apellido, nombre de cuenta de administrador de cuentas de seguridad (SAM), dirección de correo electrónico, nombre principal de usuario (UPN) o número de teléfono de la cuenta de usuario de Active Directory que desee y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="e1ec7-148">En la tabla, seleccione la cuenta que desea agregar a Skype empresarial Server y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="e1ec7-149">Asigne el usuario a un grupo, especifique los detalles adicionales, asigne las directivas al usuario que desee y, a continuación, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="e1ec7-150">Deshabilitar o volver a habilitar una cuenta de usuario habilitada previamente para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e1ec7-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="e1ec7-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="e1ec7-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="e1ec7-152">Puede usar el siguiente procedimiento para deshabilitar una cuenta de usuario habilitada previamente en Skype empresarial Server sin perder la configuración de Skype empresarial Server que ha configurado para la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="e1ec7-153">Como no pierde la configuración de la cuenta de usuario de Skype empresarial Server, puede volver a habilitar otra cuenta de usuario habilitada previamente sin tener que volver a configurar la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="e1ec7-154">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="e1ec7-155">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e1ec7-156">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="e1ec7-157">En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="e1ec7-158">En la tabla, haga clic en la cuenta de usuario que desea deshabilitar o volver a habilitar.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="e1ec7-159">En el menú **acción** , siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="e1ec7-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="e1ec7-160">Para deshabilitar temporalmente la cuenta de usuario de Skype empresarial Server, haga clic en **deshabilitar temporalmente para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="e1ec7-161">Para habilitar la cuenta de usuario de Skype empresarial Server, haga clic en **volver a habilitar para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="e1ec7-162">Usar Windows PowerShell para deshabilitar o volver a habilitar cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="e1ec7-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="e1ec7-163">Las cuentas de usuario se pueden deshabilitar temporalmente y, después, volverlas a habilitar más tarde mediante el cmdlet **set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="e1ec7-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="e1ec7-164">Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e1ec7-165">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="e1ec7-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e1ec7-166">El proceso es el mismo en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="e1ec7-167">Para deshabilitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="e1ec7-167">To disable a user account</span></span>

- <span data-ttu-id="e1ec7-168">Para deshabilitar temporalmente una cuenta de usuario, establezca el valor de la propiedad Enabled en false ($False).</span><span class="sxs-lookup"><span data-stu-id="e1ec7-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="e1ec7-169">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e1ec7-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="e1ec7-170">Para volver a habilitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="e1ec7-170">To re-enable a user account</span></span>

- <span data-ttu-id="e1ec7-171">Para volver a habilitar una cuenta de usuario deshabilitada, establezca el valor de la propiedad Enabled en true ($True).</span><span class="sxs-lookup"><span data-stu-id="e1ec7-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="e1ec7-172">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e1ec7-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="e1ec7-173">Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e1ec7-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="e1ec7-174">Deshabilitar un usuario para telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="e1ec7-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="e1ec7-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="e1ec7-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="e1ec7-176">Use el siguiente procedimiento para deshabilitar Enterprise Voice para una cuenta de usuario habilitada para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="e1ec7-177">Para deshabilitar una cuenta de usuario para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="e1ec7-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="e1ec7-178">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="e1ec7-179">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e1ec7-180">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="e1ec7-181">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="e1ec7-182">En la tabla, haga clic en la cuenta de usuario que desea habilitar para la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="e1ec7-183">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="e1ec7-184">En la página **Editar usuario de Lync Server** , en **telefonía**, haga clic en cualquier opción excepto telefonía **IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1ec7-185">Para impedir que un usuario realice llamadas de audio o vídeo mediante Lync, en **telefonía**, haga clic en **audio/vídeo deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="e1ec7-186">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-186">Click **Commit**.</span></span>

<span data-ttu-id="e1ec7-187">El usuario ahora no puede usar la característica de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="e1ec7-188">Información relacionada:</span><span class="sxs-lookup"><span data-stu-id="e1ec7-188">Related information:</span></span> <br/>[<span data-ttu-id="e1ec7-189">Telefonía y movilidad empresarial</span><span class="sxs-lookup"><span data-stu-id="e1ec7-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="e1ec7-190">Habilitar usuarios para telefonía IP empresarial en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e1ec7-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="e1ec7-191">Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e1ec7-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="e1ec7-192">Quitar una cuenta de usuario con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e1ec7-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="e1ec7-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="e1ec7-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="e1ec7-194">Puede usar el siguiente procedimiento para quitar una cuenta de usuario agregada anteriormente en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="e1ec7-195">Si quita un usuario, perderá la configuración que haya configurado para la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="e1ec7-196">Si desea deshabilitar temporalmente una cuenta de usuario, consulte deshabilitar [o volver a habilitar una cuenta de usuario habilitada previamente para Skype empresarial Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="e1ec7-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="e1ec7-197">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="e1ec7-198">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e1ec7-199">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="e1ec7-200">En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="e1ec7-201">En la tabla, haga clic en la cuenta de usuario que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="e1ec7-202">En el menú **acción** , seleccione **quitar de Lync Server**y aparecerá un cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="e1ec7-203">En el cuadro de diálogo, seleccione **Aceptar** para quitar el usuario.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="e1ec7-204">Quitar cuentas de usuario con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1ec7-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="e1ec7-205">Puede quitar cuentas de usuario mediante el cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="e1ec7-206">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="e1ec7-207">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="e1ec7-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e1ec7-208">El proceso es el mismo en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="e1ec7-209">Para quitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="e1ec7-209">To remove a user account</span></span>
<span data-ttu-id="e1ec7-210">Para quitar una cuenta de usuario, use el cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="e1ec7-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="e1ec7-211">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e1ec7-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="e1ec7-212">Para obtener más información, vea el tema de ayuda sobre el cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e1ec7-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1ec7-213">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1ec7-213">See also</span></span>
<span data-ttu-id="e1ec7-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="e1ec7-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="e1ec7-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="e1ec7-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="e1ec7-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="e1ec7-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
