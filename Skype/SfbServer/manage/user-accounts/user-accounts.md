---
title: Administrar cuentas de usuario de Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Las secciones de este artículo describen cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype para Business Server.
ms.openlocfilehash: 8aeebafc0e221cd51df76233f6dce1f1e53fb429
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897320"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="dc92e-103">Administrar cuentas de usuario de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="dc92e-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="dc92e-104">Las secciones de este artículo describen cómo habilitar, deshabilitar temporalmente o quitar usuarios de Active Directory de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc92e-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="dc92e-105">Para obtener información acerca de cómo habilitar a un usuario de Active Directory, vea [crear una nueva cuenta de usuario](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="dc92e-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="dc92e-106">Para obtener información sobre cómo eliminar un usuario de Active Directory, vea [Eliminar una cuenta de usuario](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="dc92e-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="dc92e-107">Estos procedimientos se deben realizar durante un período de mantenimiento, cuando Skype para uso empresarial es más bajo.</span><span class="sxs-lookup"><span data-stu-id="dc92e-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="dc92e-108">Si esto se realiza en una programación diaria o semanal vendrá determinada por las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="dc92e-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="dc92e-109">Este artículo contiene los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="dc92e-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="dc92e-110">Para buscar uno o varios usuarios</span><span class="sxs-lookup"><span data-stu-id="dc92e-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="dc92e-111">Agregar y habilitar un nuevo Skype para usuario Business Server</span><span class="sxs-lookup"><span data-stu-id="dc92e-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="dc92e-112">Deshabilitar o volver a habilitar una cuenta de usuario habilitada anteriormente para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="dc92e-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="dc92e-113">Deshabilitar a un usuario para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="dc92e-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="dc92e-114">Quitar una cuenta de usuario con el Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="dc92e-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="dc92e-115">Para buscar uno o varios usuarios</span><span class="sxs-lookup"><span data-stu-id="dc92e-115">To search for one or more users</span></span>
<span data-ttu-id="dc92e-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="dc92e-116"></span></span>

<span data-ttu-id="dc92e-117">Puede usar los resultados de una consulta de búsqueda para configurar usuarios de Active Directory para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc92e-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="dc92e-118">Puede buscar usuarios según el nombre para mostrar, el nombre, los apellidos, el nombre de cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea.</span><span class="sxs-lookup"><span data-stu-id="dc92e-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="dc92e-119">Puede buscar los usuarios mediante el Skype para Panel de Control de servidor empresarial o los usuarios de Active Directory y complemento de equipos.</span><span class="sxs-lookup"><span data-stu-id="dc92e-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="dc92e-120">El siguiente procedimiento describe cómo usar Skype para el Panel de Control de servidor empresarial para buscar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="dc92e-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="dc92e-121">En un entorno con una topología de bosque central, los resultados de búsqueda podrían no ser exactos al buscar un usuario por dirección de correo electrónico del usuario.</span><span class="sxs-lookup"><span data-stu-id="dc92e-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="dc92e-122">En su lugar, puede buscar los usuarios mediante la especificación de un prefijo de dirección SIP, por ejemplo, sip: nombre, agregar un filtro de búsqueda y seleccione una dirección SIP que contiene una dirección de correo electrónico parcial o use el cmdlet **Get-CSUser** .</span><span class="sxs-lookup"><span data-stu-id="dc92e-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="dc92e-123">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="dc92e-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="dc92e-124">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="dc92e-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="dc92e-125">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="dc92e-126">En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, apellidos, nombre de cuenta SAM, la dirección SIP o URI de la cuenta de usuario que desea buscar y, a continuación, haga clic en **Buscar**de línea.</span><span class="sxs-lookup"><span data-stu-id="dc92e-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="dc92e-127">(Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:</span><span class="sxs-lookup"><span data-stu-id="dc92e-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="dc92e-128">a.</span><span class="sxs-lookup"><span data-stu-id="dc92e-128">a.</span></span> <span data-ttu-id="dc92e-129">Haga clic en la flecha para expandir en la esquina superior derecha de la pantalla por encima de **los resultados de búsqueda**y, a continuación, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="dc92e-130">b.</span><span class="sxs-lookup"><span data-stu-id="dc92e-130">b.</span></span> <span data-ttu-id="dc92e-131">Especifique la propiedad de usuario escribe en él o haciendo clic en la flecha de la lista desplegable para seleccionar una propiedad de usuario.</span><span class="sxs-lookup"><span data-stu-id="dc92e-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="dc92e-132">c.</span><span class="sxs-lookup"><span data-stu-id="dc92e-132">c.</span></span> <span data-ttu-id="dc92e-133">En la lista **igual a** , haga clic en **igual a** o **no igual a**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="dc92e-134">d.</span><span class="sxs-lookup"><span data-stu-id="dc92e-134">d.</span></span> <span data-ttu-id="dc92e-135">En el cuadro de texto, escriba los criterios de búsqueda que desea usar para filtrar los resultados de búsqueda y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="dc92e-136">En **Los resultados de búsqueda**, aparecerán los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dc92e-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="dc92e-137">Puede seleccionar cualquier o todos los usuarios en la lista y realizar tareas de configuración en los usuarios que seleccione.</span><span class="sxs-lookup"><span data-stu-id="dc92e-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="dc92e-138">Agregar y habilitar un nuevo Skype para usuario Business Server</span><span class="sxs-lookup"><span data-stu-id="dc92e-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="dc92e-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="dc92e-139"></span></span>

<span data-ttu-id="dc92e-140">Después de habilitar una cuenta de usuario en usuarios y equipos de usuarios de Active Directory, puede usar Skype para el Panel de Control de Business Server para crear y habilitar nuevas Skype Business Server las cuentas de usuario mediante la adición de un usuario de Active Directory a Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc92e-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="dc92e-141">También puede usar un cmdlet, específicamente [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="dc92e-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="dc92e-142">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="dc92e-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="dc92e-143">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="dc92e-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="dc92e-144">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="dc92e-145">Haga clic en **Permitir a los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="dc92e-146">En el cuadro de diálogo **Nuevo usuario de Lync Server** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="dc92e-147">En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre, Mostrar nombre, nombre, apellidos, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección de correo electrónico, nombre Principal del usuario (UPN) o número de teléfono de la cuenta de usuario de Active Directory que desee y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="dc92e-148">En la tabla, seleccione la cuenta que desea agregar a Skype para Business Server y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="dc92e-149">Asigne al usuario a un grupo de servidores, especificar detalles adicionales y asigne las directivas al usuario que desee y, a continuación, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="dc92e-150">Deshabilitar o volver a habilitar una cuenta de usuario habilitada anteriormente para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="dc92e-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="dc92e-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="dc92e-151"></span></span>

<span data-ttu-id="dc92e-152">Puede usar el siguiente procedimiento para deshabilitar una cuenta de usuario habilitada anteriormente en Skype para Business Server sin perder el Skype para la configuración del servidor de negocio que ha configurado para la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="dc92e-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="dc92e-153">Debido a que no se pierde la Skype para la configuración de cuenta de usuario de Business Server, puede volver a habilitar una cuenta de usuario habilitada anteriormente nuevo sin tener que volver a configurar la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="dc92e-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="dc92e-154">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="dc92e-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="dc92e-155">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="dc92e-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="dc92e-156">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="dc92e-157">En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, apellidos, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de identificador uniforme de recursos (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar, y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="dc92e-158">En la tabla, haga clic en la cuenta de usuario que desea deshabilitar o volver a habilitar.</span><span class="sxs-lookup"><span data-stu-id="dc92e-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="dc92e-159">En el menú **acción** , realice una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="dc92e-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="dc92e-160">Para deshabilitar temporalmente la cuenta de usuario de Skype para Business Server, haga clic en **deshabilitar temporalmente para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="dc92e-161">Para habilitar la cuenta de usuario de Skype para Business Server, haga clic en **volver a habilitar para Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="dc92e-162">Usar Windows Powershell para deshabilitar o volver a habilitar cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="dc92e-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="dc92e-163">Las cuentas de usuario pueden deshabilitadas temporalmente y, a continuación, más adelante volver a habilitarse, mediante el cmdlet **Set-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="dc92e-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="dc92e-164">Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc92e-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dc92e-165">Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="dc92e-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="dc92e-166">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc92e-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="dc92e-167">Para deshabilitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="dc92e-167">To disable a user account</span></span>

- <span data-ttu-id="dc92e-168">Para deshabilitar temporalmente una cuenta de usuario, establezca el valor de la propiedad Enabled en False ($False).</span><span class="sxs-lookup"><span data-stu-id="dc92e-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="dc92e-169">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dc92e-169">For example:</span></span>

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="dc92e-170">Para volver a habilitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="dc92e-170">To re-enable a user account</span></span>

- <span data-ttu-id="dc92e-171">Para volver a habilitar una cuenta de usuario deshabilitada, establezca el valor de la propiedad Enabled en True ($True).</span><span class="sxs-lookup"><span data-stu-id="dc92e-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="dc92e-172">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dc92e-172">For example:</span></span>

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="dc92e-173">Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="dc92e-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="dc92e-174">Deshabilitar a un usuario para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="dc92e-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="dc92e-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="dc92e-175"></span></span>

<span data-ttu-id="dc92e-176">Use el procedimiento siguiente para deshabilitar Enterprise Voice para una cuenta de usuario que está habilitada para Skype en Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc92e-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="dc92e-177">Para deshabilitar una cuenta de usuario para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="dc92e-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="dc92e-178">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="dc92e-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="dc92e-179">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="dc92e-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="dc92e-180">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="dc92e-181">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="dc92e-182">En la tabla, haga clic en la cuenta de usuario que desea habilitar para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="dc92e-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="dc92e-183">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="dc92e-184">En la página **Editar usuario de Lync Server** , en **telefonía**, haga clic en cualquier opción excepto **Telefonía IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc92e-185">Para restringir la capacidad de un usuario realizar llamadas de audio o vídeos mediante el uso de Lync, en **telefonía**, haga clic en **Audio y vídeo deshabilitados**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="dc92e-186">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-186">Click **Commit**.</span></span>

<span data-ttu-id="dc92e-187">El usuario es ahora no se puede usar la característica de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="dc92e-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="dc92e-188">Información relacionada:</span><span class="sxs-lookup"><span data-stu-id="dc92e-188">Related information:</span></span> <br/>[<span data-ttu-id="dc92e-189">Enterprise Voice y movilidad</span><span class="sxs-lookup"><span data-stu-id="dc92e-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="dc92e-190">Habilitar a usuarios para Enterprise Voice en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="dc92e-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="dc92e-191">Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="dc92e-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="dc92e-192">Quitar una cuenta de usuario con el Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="dc92e-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="dc92e-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="dc92e-193"></span></span>

<span data-ttu-id="dc92e-194">Puede usar el siguiente procedimiento para quitar una cuenta de usuario agregada anteriormente en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc92e-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="dc92e-195">Eliminación de un usuario hará que perder cualquier configuración establecida para la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="dc92e-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="dc92e-196">Si desea deshabilitar temporalmente una cuenta de usuario en su lugar, vea [Deshabilitar o volver a habilitar una cuenta de usuario habilitada anteriormente para Skype para Business Server](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="dc92e-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="dc92e-197">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="dc92e-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="dc92e-198">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="dc92e-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="dc92e-199">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="dc92e-200">En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, apellidos, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de identificador uniforme de recursos (URI) de la cuenta de usuario que desea deshabilitar o volver a habilitar, y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="dc92e-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="dc92e-201">En la tabla, haga clic en la cuenta de usuario que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="dc92e-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="dc92e-202">En el menú **acción** , seleccione **quitar de Lync Server**y un cuadro de diálogo aparecerá el cuadro.</span><span class="sxs-lookup"><span data-stu-id="dc92e-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="dc92e-203">En el cuadro de diálogo, seleccione **Aceptar** para quitar el usuario.</span><span class="sxs-lookup"><span data-stu-id="dc92e-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="dc92e-204">Quitar cuentas de usuario con los cmdlets de Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="dc92e-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="dc92e-205">Puede quitar cuentas de usuario mediante el cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="dc92e-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="dc92e-206">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc92e-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="dc92e-207">Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="dc92e-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="dc92e-208">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc92e-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="dc92e-209">Para quitar una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="dc92e-209">To remove a user account</span></span>
<span data-ttu-id="dc92e-210">Para quitar una cuenta de usuario, use el cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="dc92e-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="dc92e-211">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dc92e-211">For example:</span></span>

  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="dc92e-212">Para obtener más información, vea el tema de ayuda para el cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="dc92e-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc92e-213">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc92e-213">See also</span></span>
<span data-ttu-id="dc92e-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="dc92e-214"></span></span>

[<span data-ttu-id="dc92e-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="dc92e-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="dc92e-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="dc92e-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
