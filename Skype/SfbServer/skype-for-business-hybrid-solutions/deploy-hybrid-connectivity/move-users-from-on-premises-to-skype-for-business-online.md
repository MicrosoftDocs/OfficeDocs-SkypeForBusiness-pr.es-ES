---
title: Mover usuarios de local a Skype Empresarial Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/12/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
description: 'Resumen: Conozca cómo migrar la configuración de usuario y mover usuarios a Skype para los negocios en línea.'
ms.openlocfilehash: dada94d1bc198a86a06c468dc959fa0684e706d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="0bb9e-103">Mover usuarios de local a Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0bb9e-103">Move users from on premises to Skype for Business Online</span></span>
 
<span data-ttu-id="0bb9e-104">**Resumen:** Aprenda cómo migrar la configuración de usuario y mover usuarios a Skype para los negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-104">**Summary:** Learn how to migrate user settings and move users to Skype for Business Online.</span></span>
  
<span data-ttu-id="0bb9e-p101">Antes de mover el usuario a Office 365, debería confirmar primero que las cuentas de usuario están sincronizados con la nube y asígneles una licencia. Para hacerlo, use el Centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-p101">Before actually moving the user to Office 365, you should first confirm that the user accounts are synchronized to the cloud, and assign them a license. To do this, you use the Office 365 Admin Center.</span></span>
  
### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a><span data-ttu-id="0bb9e-107">Para confirmar que se ha sincronizado una cuenta de usuario local con Office 365</span><span class="sxs-lookup"><span data-stu-id="0bb9e-107">To confirm that an on-premises user account has been synchronized with Office 365</span></span>

1. <span data-ttu-id="0bb9e-108">Con una cuenta de administrador de inquilinos, abra el [Centro de administración de Office 365](https://portal.office.com/) para el arrendatario.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-108">Using an tenant admin account, open the [Office 365 admin center](https://portal.office.com/) for your tenant.</span></span>
    
2. <span data-ttu-id="0bb9e-109">En el panel de navegación izquierdo, haga clic en **Usuarios** y, después, en **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-109">On the left navigation pane, click **Users** and then **Active Users**.</span></span>
    
3. <span data-ttu-id="0bb9e-110">Haga clic en **Buscar un usuario** y escriba el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-110">Click **Search for a User**, and type the name of the user.</span></span>
    
4. <span data-ttu-id="0bb9e-111">Confirme que puede ver el usuario y que su estado es **Sincronizado con Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-111">Confirm that you see the user, and that their status is **Synched with Active Directory**.</span></span>
    
    <span data-ttu-id="0bb9e-112">Si el usuario todavía no está sincronizado, la siguiente sincronización automática debería producirse en tres horas.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-112">If the user is not yet synchronized, the next automatic synchronization should happen within three hours.</span></span> <span data-ttu-id="0bb9e-113">También puede forzar la sincronización para que se produzca antes.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-113">You can also force a synchronization sooner.</span></span> <span data-ttu-id="0bb9e-114">Para obtener más información, vea [Forzar la sincronización de directorios](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span><span class="sxs-lookup"><span data-stu-id="0bb9e-114">For more information, see [Force Directory Synchronization](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span></span>
    
<span data-ttu-id="0bb9e-115">Para asignar la licencia de Office 365, consulte [asignación de licencias para Office 365 para el negocio](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="0bb9e-115">To assign the license in Office 365, see [Assign licenses for Office 365 for Business](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
## <a name="migrate-user-settings-to-skype-for-business-online"></a><span data-ttu-id="0bb9e-116">Migrar la configuración de usuario Skype para los negocios en línea</span><span class="sxs-lookup"><span data-stu-id="0bb9e-116">Migrate user settings to Skype for Business Online</span></span>

<span data-ttu-id="0bb9e-117">Antes de empezar a migrar los usuarios a Skype para los negocios en línea, debe copia de seguridad los datos de usuario asociados a las cuentas que desea mover.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-117">Before you start migrating users to Skype for Business Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="0bb9e-118">No todos los datos de usuario se mueve con la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-118">Not all user data is moved with the user account.</span></span> <span data-ttu-id="0bb9e-119">Para obtener información, consulte [requerimientos de Backup y restauración: datos](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span><span class="sxs-lookup"><span data-stu-id="0bb9e-119">For information, see [Backup and Restoration Requirements: Data](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span></span>
  
<span data-ttu-id="0bb9e-p104">La configuración de usuario se mueve con la cuenta de usuario. Algunos valores de configuración locales no se mueven con la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-p104">User settings are moved with the user account. Some on-premises settings are not moved with the user account.</span></span>
  
## <a name="move-pilot-users-to-skype-for-business-online"></a><span data-ttu-id="0bb9e-122">Trasladar a usuarios piloto a Skype para los negocios en línea</span><span class="sxs-lookup"><span data-stu-id="0bb9e-122">Move pilot users to Skype for Business Online</span></span>

<span data-ttu-id="0bb9e-123">Antes de empezar a mover los usuarios a Skype para los negocios en línea, es aconsejable mover algunos usuarios piloto para confirmar que su entorno está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-123">Before you begin to move users to Skype for Business Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="0bb9e-124">Después puede verificar que las características y los servicios de Lync funcionan del modo esperado antes de intentar mover más usuarios.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-124">You can then verify that the features and services function as expected before attempting to move additional users.</span></span>
  
<span data-ttu-id="0bb9e-125">Para mover un usuario local a su Skype para inquilinos de negocios en línea, ejecute los siguientes cmdlets en el Skype para el Shell de administración de servidor de negocios, utilizando las credenciales de administrador para los clientes de Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-125">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="0bb9e-126">Sustituya “username@contoso.com” por la información del usuario que quiera mover.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-126">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds 
```

## <a name="move-users-to-skype-for-business-online"></a><span data-ttu-id="0bb9e-127">Mover usuarios a Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0bb9e-127">Move users to Skype for Business Online</span></span>

<span data-ttu-id="0bb9e-128">Puede mover varios usuarios mediante el cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) -el parámetro Filter para seleccionar los usuarios con una propiedad específica asignada a las cuentas de usuario, como RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-128">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet with the -Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="0bb9e-129">A continuación, puede canalizar los usuarios devueltos al cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-129">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) cmdlet, as shown in the following example.</span></span>
  
```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds 
```

<span data-ttu-id="0bb9e-130">También puede utilizar el parámetro - OU para recuperar todos los usuarios de la unidad organizativa especificada, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-130">You can also use the -OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>
  
```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds 
```

## <a name="verify-online-user-settings-and-features"></a><span data-ttu-id="0bb9e-131">Comprobar las características y configuración de usuario en línea</span><span class="sxs-lookup"><span data-stu-id="0bb9e-131">Verify online user settings and features</span></span>

<span data-ttu-id="0bb9e-132">Puede comprobar que el usuario se ha movido correctamente de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="0bb9e-132">You can verify that the user was moved successfully in the following ways:</span></span>
  
- <span data-ttu-id="0bb9e-p108">Vea el estado del usuario en el Panel de Control de Skype Empresarial Online. El indicador visual de los usuarios locales y los usuarios en línea es diferente.</span><span class="sxs-lookup"><span data-stu-id="0bb9e-p108">View the status of the user in the Skype for Business Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>
    
- <span data-ttu-id="0bb9e-135">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0bb9e-135">Run the following cmdlet:</span></span>
    
  ```
  Get-CsUser -Identity
  ```


