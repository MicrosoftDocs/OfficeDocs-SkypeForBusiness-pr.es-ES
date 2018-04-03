---
title: Administrar cuentas de usuario mediante el conector en línea
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Para obtener información acerca Skype de su organización para usuarios de negocios en línea, use el cmdlet Get-CsOnlineUser en Windows PowerShell.
ms.openlocfilehash: 1583e808cc489bb19f51acd6f52c900772138efe
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="1f6a3-103">Administrar cuentas de usuario mediante el conector en línea</span><span class="sxs-lookup"><span data-stu-id="1f6a3-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="1f6a3-104">Administrar cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="1f6a3-104">Manage user accounts</span></span>

<span data-ttu-id="1f6a3-105">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f6a3-105">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="1f6a3-106">Devuelven información acerca de todos los Skype para usuarios de negocios en línea</span><span class="sxs-lookup"><span data-stu-id="1f6a3-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)
    
- [<span data-ttu-id="1f6a3-107">Devolver información de un usuario específico en Skype para los negocios en línea</span><span class="sxs-lookup"><span data-stu-id="1f6a3-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)
    
- [<span data-ttu-id="1f6a3-108">Devolver información específica para usuarios específicos en Skype para los negocios en línea</span><span class="sxs-lookup"><span data-stu-id="1f6a3-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)
    
- [<span data-ttu-id="1f6a3-109">Devolver una lista filtrada de usuarios de Skype para los negocios en línea</span><span class="sxs-lookup"><span data-stu-id="1f6a3-109">Return a filtered list of users in Skype for Business Online </span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)
    
> [!NOTE]
> <span data-ttu-id="1f6a3-110">El cmdlet **Set-CsUser** también se incluye en el conjunto de cmdlets de Skype disponibles para los administradores de negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="1f6a3-111">Sin embargo, **Conjunto CsUser** actualmente no puede utilizarse para administrar Skype para los negocios en línea, excepto si el parámetro _AudioVideoDisabled_ .</span><span class="sxs-lookup"><span data-stu-id="1f6a3-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="1f6a3-112">Si intenta ejecutar el cmdlet con ningún otro parámetro, se producirá un mensaje de error similar al siguiente: no se puede establecer en "SipAddress".</span><span class="sxs-lookup"><span data-stu-id="1f6a3-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="1f6a3-113">Este parámetro es restringido en PowerShell remoto de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>
  
### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="1f6a3-114">Obtener información sobre todos los usuarios de Lync Online</span><span class="sxs-lookup"><span data-stu-id="1f6a3-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="1f6a3-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="1f6a3-115"></span></span>

<span data-ttu-id="1f6a3-116">Para obtener información acerca de todos los usuarios que han sido habilitados para Skype para los negocios en línea, llame el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sin ningún parámetro adicional.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>
  
```
Get-CsOnlineUser
```

<span data-ttu-id="1f6a3-117">Para devolver información de un usuario único, seleccionado aleatoriamente (por ejemplo, para utilizar esta cuenta para fines de prueba), llame el cmdlet **Get-CsOnlineUser** y establezca el parámetro _ResultSize_ en 1.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>
  
```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="1f6a3-118">Que hace que el cmdlet **Get-CsOnlineUser** devolver información de un solo usuario, independientemente de cuántos usuarios hay en su organización.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="1f6a3-119">Para devolver información de cinco usuarios, establezca el valor del parámetro _ResultSize_ a 5.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>
  
```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="1f6a3-120">Devolver información de un usuario específico en Skype para los negocios en línea</span><span class="sxs-lookup"><span data-stu-id="1f6a3-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="1f6a3-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="1f6a3-121"></span></span>

<span data-ttu-id="1f6a3-122">Hay varias maneras de hacer referencia a una cuenta de usuario específica cuando se llama el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) .</span><span class="sxs-lookup"><span data-stu-id="1f6a3-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="1f6a3-123">Puede utilizar el nombre para mostrar del usuario los servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="1f6a3-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>
  
```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="1f6a3-124">Puede utilizar la dirección del usuario SIP.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-124">You can use the user's SIP address.</span></span>
  
```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="1f6a3-125">Puede utilizar el nombre principal de usuario (UPN) del usuario.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-125">You can use the user's user principal name (UPN).</span></span>
  
```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="1f6a3-126">Devolver información específica para usuarios específicos en Skype para los negocios en línea</span><span class="sxs-lookup"><span data-stu-id="1f6a3-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="1f6a3-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="1f6a3-127"></span></span>

<span data-ttu-id="1f6a3-128">De forma predeterminada, el cmdlet [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) devuelve una gran cantidad de información para cada Skype para cuenta de usuario de negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-128">By default, the [Get-CsOnlineUser](http://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="1f6a3-129">Si estás interesado en sólo un subconjunto de la información, canalizar los datos devueltos al cmdlet **Select-Object** .</span><span class="sxs-lookup"><span data-stu-id="1f6a3-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="1f6a3-130">Por ejemplo, este comando restablece todos los datos para el usuario Ken Myer y usa el cmdlet **Select-Object** para limitar la información que aparece en la pantalla nombre para mostrar de Ken AD DS y el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>
  
```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="1f6a3-131">El comando siguiente se devuelve el nombre para mostrar y el dial plan para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-131">The following command returns the display name and dial plan for all your users.</span></span>
  
```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="1f6a3-132">Para buscar las propiedades de un Skype para cuenta de usuario de negocios en línea, utilice el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>
  
```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="1f6a3-133">Devolver una lista filtrada de usuarios de Skype para los negocios en línea</span><span class="sxs-lookup"><span data-stu-id="1f6a3-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="1f6a3-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="1f6a3-134"></span></span>

<span data-ttu-id="1f6a3-135">Mediante el cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) y los parámetros _filtroLDAP_ o _filtro_ , podrá volver fácilmente información sobre un conjunto concreto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="1f6a3-136">Por ejemplo, este comando devuelve todos los usuarios que trabajan en el departamento de finanzas.</span><span class="sxs-lookup"><span data-stu-id="1f6a3-136">For example, this command returns all the users who work in the Finance department.</span></span>
  
```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="1f6a3-137">See also</span><span class="sxs-lookup"><span data-stu-id="1f6a3-137">Related topics</span></span>
[<span data-ttu-id="1f6a3-138">Configurar el equipo de Skype para la administración de negocios en línea mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f6a3-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 