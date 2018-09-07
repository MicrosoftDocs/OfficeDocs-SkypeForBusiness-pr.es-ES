---
title: Administrar cuentas de usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use el cmdlet Get-CsOnlineUser en Windows PowerShell para obtener información acerca de Skype la organización para usuarios profesionales en línea.
ms.openlocfilehash: 90f928fa6cd546dabc0cbb5d3f4f84aa7f00f202
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858485"
---
# <a name="manage-user-accounts"></a><span data-ttu-id="e8ad9-103">Administrar cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="e8ad9-103">Manage user accounts</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="e8ad9-104">Administrar cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="e8ad9-104">Manage user accounts</span></span>

<span data-ttu-id="e8ad9-105">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e8ad9-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="e8ad9-106">Obtener información sobre todos los usuarios de Lync Online</span><span class="sxs-lookup"><span data-stu-id="e8ad9-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts.md#BKMKReturnInfoAboutAllUsers)

- [<span data-ttu-id="e8ad9-107">Devolver información para un usuario específico de Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="e8ad9-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturnInfoSpecificUser)

- [<span data-ttu-id="e8ad9-108">Devolver información específica para usuarios específicos en Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="e8ad9-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts.md#BKMKReturninfoSpecificUsers)

- [<span data-ttu-id="e8ad9-109">Devolver una lista filtrada de usuarios de Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="e8ad9-109">Return a filtered list of users in Skype for Business Online </span></span>](manage-user-accounts.md#BKMKReturnFilteredListofUsers)

> [!NOTE]
> <span data-ttu-id="e8ad9-110">El cmdlet **Set-CsUser** también se incluye en el conjunto de cmdlets disponibles para Skype para los administradores de negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="e8ad9-111">Sin embargo, **Set-CsUser** actualmente no puede usarse para administrar Skype para en línea de negocio, excepto si se establece el parámetro _AudioVideoDisabled_ .</span><span class="sxs-lookup"><span data-stu-id="e8ad9-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="e8ad9-112">Si intenta ejecutar el cmdlet con otros parámetros, producirá un error con un mensaje de error similar al siguiente: no se puede establecer "SipAddress".</span><span class="sxs-lookup"><span data-stu-id="e8ad9-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="e8ad9-113">Este parámetro está restringido dentro de PowerShell remoto de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="e8ad9-114">Obtener información sobre todos los usuarios de Lync Online</span><span class="sxs-lookup"><span data-stu-id="e8ad9-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="e8ad9-115"><a name="BKMKReturnInfoAboutAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ad9-115"></span></span>

<span data-ttu-id="e8ad9-116">Para devolver información acerca de todos los usuarios que han sido habilitados para Skype para profesionales en línea, llame al cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sin ningún parámetro adicional.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```
Get-CsOnlineUser
```

<span data-ttu-id="e8ad9-117">Para devolver información de un usuario único, seleccionada al azar (por ejemplo, para usar esta cuenta para realizar pruebas), llamar al cmdlet **Get-CsOnlineUser** y establezca el parámetro _ResultSize_ en 1.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="e8ad9-118">Que hace que el cmdlet **Get-CsOnlineUser** devolver información de un solo usuario, independientemente de cuántos usuarios tiene en la organización.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="e8ad9-119">Para devolver información de cinco usuarios, establezca el valor del parámetro _ResultSize_ en 5.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="e8ad9-120">Devolver información para un usuario específico de Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="e8ad9-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="e8ad9-121"><a name="BKMKReturnInfoSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ad9-121"></span></span>

<span data-ttu-id="e8ad9-122">Hay varias maneras de hacer referencia a una cuenta de usuario específica cuando se llama al cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) .</span><span class="sxs-lookup"><span data-stu-id="e8ad9-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="e8ad9-123">Puede usar el nombre para mostrar del usuario los servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="e8ad9-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="e8ad9-124">Puede usar la dirección SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-124">You can use the user's SIP address.</span></span>

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="e8ad9-125">Puede usar el nombre principal de usuario (UPN) del usuario.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-125">You can use the user's user principal name (UPN).</span></span>

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="e8ad9-126">Devolver información específica para usuarios específicos en Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="e8ad9-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="e8ad9-127"><a name="BKMKReturninfoSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ad9-127"></span></span>

<span data-ttu-id="e8ad9-128">De forma predeterminada, el cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) devuelve una gran cantidad de información para cada Skype para la cuenta de usuario en línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="e8ad9-129">Si está interesado en sólo un subconjunto de esa información, canalizar los datos devueltos al cmdlet **Select-Object** .</span><span class="sxs-lookup"><span data-stu-id="e8ad9-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="e8ad9-130">Por ejemplo, este comando devuelve todos los datos para el usuario Ken Myer y, a continuación, utiliza el cmdlet **Select-Object** para limitar la información que se muestra en la pantalla para el nombre para mostrar de Ken AD DS y el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="e8ad9-131">El siguiente comando devuelve el nombre para mostrar y marcado planeación para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-131">The following command returns the display name and dial plan for all your users.</span></span>

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="e8ad9-132">Para buscar las propiedades de un Skype para la cuenta de usuario de negocio en línea, use el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="e8ad9-133">Devolver una lista filtrada de usuarios de Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="e8ad9-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="e8ad9-134"><a name="BKMKReturnFilteredListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="e8ad9-134"></span></span>

<span data-ttu-id="e8ad9-135">Mediante el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) y los parámetros _LdapFilter_ o _filtro_ , fácilmente puede devolver información acerca de un conjunto concreto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="e8ad9-136">Por ejemplo, este comando devuelve todos los usuarios que trabajan en el departamento de finanzas.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-136">For example, this command returns all the users who work in the Finance department.</span></span>

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="e8ad9-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e8ad9-137">Related topics</span></span>
[<span data-ttu-id="e8ad9-138">Configurar el equipo para Skype para la administración en línea de negocio con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8ad9-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


