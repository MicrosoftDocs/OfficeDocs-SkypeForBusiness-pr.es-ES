---
title: Administrar cuentas de usuario con el conector en línea
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
f1keywords: None
ms.custom:
- PowerShell
description: Use el cmdlet Get-CsOnlineUser en Windows PowerShell para obtener información sobre los usuarios de Skype empresarial online de su organización.
ms.openlocfilehash: 143f7934564caf4e2c00b5b4a40bc6f2e597950d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990995"
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="e26f6-103">Administrar cuentas de usuario con el conector en línea</span><span class="sxs-lookup"><span data-stu-id="e26f6-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="e26f6-104">Administrar cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="e26f6-104">Manage user accounts</span></span>

<span data-ttu-id="e26f6-105">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e26f6-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="e26f6-106">Obtener información sobre todos los usuarios de Lync Online</span><span class="sxs-lookup"><span data-stu-id="e26f6-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [<span data-ttu-id="e26f6-107">Devolver información para un usuario específico en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="e26f6-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [<span data-ttu-id="e26f6-108">Devolver información específica para usuarios específicos de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="e26f6-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [<span data-ttu-id="e26f6-109">Devolver una lista filtrada de usuarios en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="e26f6-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> <span data-ttu-id="e26f6-110">El cmdlet **set-CsUser** también está incluido en el conjunto de cmdlets disponibles para administradores de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="e26f6-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="e26f6-111">Sin embargo, **set-CsUser** no puede usarse para administrar Skype empresarial online, excepto para establecer el parámetro _AudioVideoDisabled_ .</span><span class="sxs-lookup"><span data-stu-id="e26f6-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="e26f6-112">Si intenta ejecutar el cmdlet con cualquier otro parámetro, se producirá un error con un mensaje similar al siguiente: no se puede establecer "SipAddress".</span><span class="sxs-lookup"><span data-stu-id="e26f6-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="e26f6-113">Este parámetro está restringido en PowerShell remoto de inquilino.</span><span class="sxs-lookup"><span data-stu-id="e26f6-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="e26f6-114">Obtener información sobre todos los usuarios de Lync Online</span><span class="sxs-lookup"><span data-stu-id="e26f6-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="e26f6-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="e26f6-115"></span></span>

<span data-ttu-id="e26f6-116">Para obtener información sobre todos los usuarios que se han habilitado para Skype empresarial online, llame al cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sin ningún parámetro adicional.</span><span class="sxs-lookup"><span data-stu-id="e26f6-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```PowerShell
Get-CsOnlineUser
```

<span data-ttu-id="e26f6-117">Para devolver información de un único usuario seleccionado aleatoriamente (por ejemplo, para usar esta cuenta con fines de prueba), llame al cmdlet **Get-CsOnlineUser** y establezca el parámetro de _los resultados_ en 1.</span><span class="sxs-lookup"><span data-stu-id="e26f6-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="e26f6-118">Esto hace que el cmdlet **Get-CsOnlineUser** devuelva información para un solo usuario, independientemente del número de usuarios que tenga en su organización.</span><span class="sxs-lookup"><span data-stu-id="e26f6-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="e26f6-119">Para devolver información para cinco usuarios, establezca el valor del parámetro de los _resultados_ en 5.</span><span class="sxs-lookup"><span data-stu-id="e26f6-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="e26f6-120">Devolver información para un usuario específico en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="e26f6-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="e26f6-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="e26f6-121"></span></span>

<span data-ttu-id="e26f6-122">Hay varias maneras de hacer referencia a una cuenta de usuario específica al llamar al cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) .</span><span class="sxs-lookup"><span data-stu-id="e26f6-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="e26f6-123">Puede usar el nombre para mostrar de los servicios de dominio de Active Directory (AD DS) del usuario.</span><span class="sxs-lookup"><span data-stu-id="e26f6-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="e26f6-124">Puede usar la dirección SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="e26f6-124">You can use the user's SIP address.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="e26f6-125">Puede usar el nombre principal de usuario (UPN) del usuario.</span><span class="sxs-lookup"><span data-stu-id="e26f6-125">You can use the user's user principal name (UPN).</span></span>

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="e26f6-126">Devolver información específica para usuarios específicos de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="e26f6-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="e26f6-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="e26f6-127"></span></span>

<span data-ttu-id="e26f6-128">De forma predeterminada, el cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) devuelve una gran cantidad de información para cada cuenta de usuario de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="e26f6-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="e26f6-129">Si solo le interesa un subconjunto de esa información, canalice los datos devueltos al cmdlet **Select-Object** .</span><span class="sxs-lookup"><span data-stu-id="e26f6-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="e26f6-130">Por ejemplo, este comando devuelve todos los datos del usuario Ken Myer y, a continuación, usa el cmdlet **Select-Object** para limitar la información que se muestra en la pantalla al nombre para mostrar de Ken AD DS y el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="e26f6-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="e26f6-131">El siguiente comando devuelve el nombre para mostrar y el plan de marcado de todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e26f6-131">The following command returns the display name and dial plan for all your users.</span></span>

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="e26f6-132">Para buscar las propiedades de una cuenta de usuario de Skype empresarial online, use el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="e26f6-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="e26f6-133">Devolver una lista filtrada de usuarios en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="e26f6-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="e26f6-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="e26f6-134"></span></span>

<span data-ttu-id="e26f6-135">Al usar el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) y los parámetros _LdapFilter_ o _Filter_ , puede devolver fácilmente información acerca de un conjunto de usuarios de destino.</span><span class="sxs-lookup"><span data-stu-id="e26f6-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="e26f6-136">Por ejemplo, este comando devuelve todos los usuarios que trabajan en el Departamento de finanzas.</span><span class="sxs-lookup"><span data-stu-id="e26f6-136">For example, this command returns all the users who work in the Finance department.</span></span>

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="e26f6-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e26f6-137">Related topics</span></span>
[<span data-ttu-id="e26f6-138">Configurar el equipo para la administración de Skype empresarial online con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e26f6-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


