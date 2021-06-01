---
title: Administrar cuentas de usuario
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Use el cmdlet Get-CsOnlineUser en Windows PowerShell para obtener información sobre los Skype Empresarial en línea de su organización.
ms.openlocfilehash: aec79f589f6b1fb0c9d38fd4bc70421b30f66a56
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238726"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="514d5-103">Administrar cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="514d5-103">Manage user accounts</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="manage-user-accounts"></a><span data-ttu-id="514d5-104">Administrar cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="514d5-104">Manage user accounts</span></span>

<span data-ttu-id="514d5-105">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="514d5-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="514d5-106">Obtener información sobre todos los usuarios de Lync Online</span><span class="sxs-lookup"><span data-stu-id="514d5-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="514d5-107">Devolver información para un usuario específico en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="514d5-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="514d5-108">Devolver información específica para usuarios específicos en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="514d5-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="514d5-109">Devolver una lista filtrada de usuarios en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="514d5-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="514d5-110">El cmdlet **Set-CsUser** también se incluye en el conjunto de cmdlets disponibles para Skype Empresarial en línea.</span><span class="sxs-lookup"><span data-stu-id="514d5-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="514d5-111">Sin embargo, **Set-CsUser** no se puede usar actualmente para administrar Skype Empresarial Online, excepto para establecer el _parámetro AudioVideoDisabled._</span><span class="sxs-lookup"><span data-stu-id="514d5-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="514d5-112">Si intenta ejecutar el cmdlet con cualquier otro parámetro, se producirá un error con un mensaje de error similar a este: No se puede establecer "SipAddress".</span><span class="sxs-lookup"><span data-stu-id="514d5-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="514d5-113">Este parámetro está restringido en PowerShell de inquilino remoto.</span><span class="sxs-lookup"><span data-stu-id="514d5-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="514d5-114">Obtener información sobre todos los usuarios de Lync Online</span><span class="sxs-lookup"><span data-stu-id="514d5-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="514d5-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="514d5-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span></span>

<span data-ttu-id="514d5-116">Para devolver información sobre todos los usuarios que se han habilitado para Skype Empresarial Online, llame al cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) sin ningún parámetro adicional.</span><span class="sxs-lookup"><span data-stu-id="514d5-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="514d5-117">Para devolver información para un único usuario seleccionado aleatoriamente (por ejemplo, para usar esta cuenta con fines de prueba), llame al cmdlet **Get-CsOnlineUser** y establezca el parámetro _ResultSize_ en 1.</span><span class="sxs-lookup"><span data-stu-id="514d5-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="514d5-118">Esto hace que el cmdlet **Get-CsOnlineUser** devuelva información solo para un usuario, independientemente de cuántos usuarios tenga en su organización.</span><span class="sxs-lookup"><span data-stu-id="514d5-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="514d5-119">Para devolver información para cinco usuarios, establezca el valor del parámetro _ResultSize_ en 5.</span><span class="sxs-lookup"><span data-stu-id="514d5-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="514d5-120">Devolver información para un usuario específico en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="514d5-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="514d5-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="514d5-121"><a name="BKMKReturnInfoSpecificUser"> </a></span></span>

<span data-ttu-id="514d5-122">Hay varias formas de hacer referencia a una cuenta de usuario específica al llamar al cmdlet [Get-CsOnlineUser.](/powershell/module/skype/Get-CsOnlineUser)</span><span class="sxs-lookup"><span data-stu-id="514d5-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet.</span></span> <span data-ttu-id="514d5-123">Puede usar el nombre para mostrar de servicios de dominio de Active Directory (AD DS) del usuario.</span><span class="sxs-lookup"><span data-stu-id="514d5-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="514d5-124">Puede usar la dirección SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="514d5-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="514d5-125">Puede usar el nombre principal de usuario (UPN) del usuario.</span><span class="sxs-lookup"><span data-stu-id="514d5-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="514d5-126">Devolver información específica para usuarios específicos en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="514d5-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="514d5-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="514d5-127"><a name="BKMKReturninfoSpecificUsers"> </a></span></span>

<span data-ttu-id="514d5-128">De forma predeterminada, el cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) devuelve una gran cantidad de información para cada Skype Empresarial cuenta de usuario en línea.</span><span class="sxs-lookup"><span data-stu-id="514d5-128">By default, the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="514d5-129">Si solo está interesado en un subconjunto de esa información, canalizar los datos devueltos al cmdlet **Select-Object.**</span><span class="sxs-lookup"><span data-stu-id="514d5-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="514d5-130">Por ejemplo, este comando devuelve todos los datos del usuario Ken Myer y, a continuación, usa el cmdlet **Select-Object** para limitar la información que se muestra en pantalla al nombre para mostrar y el plan de marcado de Ad DS de Ken.</span><span class="sxs-lookup"><span data-stu-id="514d5-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="514d5-131">El siguiente comando devuelve el nombre para mostrar y el plan de marcado para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="514d5-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="514d5-132">Para buscar las propiedades de una Skype Empresarial de usuario en línea, use el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="514d5-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="514d5-133">Devolver una lista filtrada de usuarios en Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="514d5-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="514d5-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="514d5-134"><a name="BKMKReturnFilteredListofUsers"> </a></span></span>

<span data-ttu-id="514d5-135">Con el cmdlet [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) y los parámetros _LdapFilter_ o _Filter,_ puede devolver fácilmente información sobre un conjunto de usuarios dirigido.</span><span class="sxs-lookup"><span data-stu-id="514d5-135">By using the [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="514d5-136">Por ejemplo, este comando devuelve todos los usuarios que trabajan en el departamento de Finanzas.</span><span class="sxs-lookup"><span data-stu-id="514d5-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="514d5-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="514d5-137">Related topics</span></span>
[<span data-ttu-id="514d5-138">Configurar el equipo para la administración en línea de Skype Empresarial con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="514d5-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
