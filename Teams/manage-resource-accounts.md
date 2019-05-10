---
title: Administrar cuentas de recursos en Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Obtenga información acerca de cómo administrar las cuentas de recursos en Microsoft Teams
ms.openlocfilehash: dea4a154e25c719ddabc572ba26ddb7d25c43d71
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835421"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="f68b7-103">Administrar cuentas de recursos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f68b7-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="f68b7-104">Una cuenta de recursos es también conocida como un objeto de usuario deshabilitado en Azure Active Directory y puede usarse para representar los recursos en general.</span><span class="sxs-lookup"><span data-stu-id="f68b7-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="f68b7-105">En Exchange pueden usarse para representar salas de conferencias, por ejemplo y permitir que tengan un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="f68b7-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="f68b7-106">Una cuenta de recursos puede estar alojada en Microsoft 365 o local mediante Skype para Business server, y estas cuentas se crean utilizando los comandos de Powershell.</span><span class="sxs-lookup"><span data-stu-id="f68b7-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="f68b7-107">En Microsoft Teams o Skype para profesionales en línea, cada llamada de cola o auto attendant se requiere para tienen una cuenta de recurso asociado.</span><span class="sxs-lookup"><span data-stu-id="f68b7-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="f68b7-108">Si una cuenta de recursos necesita un número de teléfono asignado se dependen el uso intencionado de la cola de llamada asociada o el operador automático.</span><span class="sxs-lookup"><span data-stu-id="f68b7-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="f68b7-109">Hacer referencia a los artículos en las colas de llamadas y automáticos vinculado en la parte inferior de este artículo antes de asignar a un número de teléfono a una cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="f68b7-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="f68b7-110">En este artículo se aplica a Microsoft Teams y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="f68b7-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="f68b7-111">Requisitos previos para asignar a un número de teléfono a una cuenta de recurso</span><span class="sxs-lookup"><span data-stu-id="f68b7-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="f68b7-112">Para empezar a es importante recordar algunas cosas:</span><span class="sxs-lookup"><span data-stu-id="f68b7-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="f68b7-113">Una cola de llamada o de operador automático es necesario tener una cuenta de recurso asociado.</span><span class="sxs-lookup"><span data-stu-id="f68b7-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="f68b7-114">Para obtener información detallada sobre las cuentas de recursos, vea [Administrar cuentas de recursos en los equipos](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="f68b7-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="f68b7-115">Si tiene previsto asignar un número de enrutamiento directa, debe adquirir y asignar las siguientes licencias para las cuentas de recursos \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico\).</span><span class="sxs-lookup"><span data-stu-id="f68b7-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="f68b7-116">Si se asigna un número de servicio de Microsoft en su lugar, debe adquirir y asignar las licencias siguientes a la cuenta del recurso \(Office 365 Enterprise E1, E3 o E5, con el complemento de sistema telefónico y un Plan de llamar a\).</span><span class="sxs-lookup"><span data-stu-id="f68b7-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="f68b7-117">Sólo debe obtener licencia para las cuentas de recursos con un número de teléfono que se les haya asignado.</span><span class="sxs-lookup"><span data-stu-id="f68b7-117">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="f68b7-118">En una cola de llamada o de operador automático anidados, no es necesario para el resto de los operadores automáticos de licencia o colas de llamadas si no tienen números de teléfono asociados con ellos</span><span class="sxs-lookup"><span data-stu-id="f68b7-118">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them</span></span>

> [!NOTE] 
> <span data-ttu-id="f68b7-119">Números de servicio de enrutamiento directo para colas de operador y llamada automático es compatible con los usuarios de Microsoft Teams y sólo los agentes.</span><span class="sxs-lookup"><span data-stu-id="f68b7-119">Direct Routing service numbers for auto attendant and call queues is supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE] 
> <span data-ttu-id="f68b7-120">Microsoft está trabajando en un modelo de licencias adecuado para aplicaciones como automáticos en la nube y las colas de llamadas, para ahora tiene que usar el modelo de licencias de usuario.</span><span class="sxs-lookup"><span data-stu-id="f68b7-120">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f68b7-121">Para redirigir las llamadas a personas de la organización que están en línea, deben tener una licencia de **Sistema telefónico** y estar habilitados para Enterprise Voice o tienen planes de llamada de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f68b7-121">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="f68b7-122">Vea [las licencias de asignar los equipos de Microsoft](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="f68b7-122">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="f68b7-123">Para habilitar la Telefonía IP empresarial para sus usuarios, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f68b7-123">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="f68b7-124">Por ejemplo, ejecute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="f68b7-124">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="f68b7-125">Puede asignar a un número de híbrido de enrutamiento directa a la cuenta del recurso.</span><span class="sxs-lookup"><span data-stu-id="f68b7-125">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="f68b7-126">Para obtener información detallada, vea [Planear el enrutamiento directo](direct-routing-plan.md) .</span><span class="sxs-lookup"><span data-stu-id="f68b7-126">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="f68b7-127">Planes de llamada de Microsoft, puede asignar sólo números de pago y los números de teléfono de un servicio gratuito que obtuvo en el **Centro de administración de equipos de Microsoft** o trasladado desde otro proveedor de servicios a una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="f68b7-127">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="f68b7-128">Para obtener y usar números de servicio gratuitos, debe configurar Créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="f68b7-128">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="f68b7-129">Los números de teléfono del usuario (suscriptor) no se pueden asignar a una cuenta de recurso.</span><span class="sxs-lookup"><span data-stu-id="f68b7-129">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="f68b7-130">Se pueden usar solo números de pago de servicio o números de teléfono gratuito.</span><span class="sxs-lookup"><span data-stu-id="f68b7-130">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="f68b7-131">Para asignar un número de teléfono a una cuenta de recurso, necesitará obtener o su teléfono de pago existente o un servicio gratuito de puerto números.</span><span class="sxs-lookup"><span data-stu-id="f68b7-131">To assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="f68b7-132">Después de obtener el teléfono de pago o números de teléfono gratuito de servicio, se mostrarán en el **Centro de administración de equipos de Microsoft** > **voz** > **los números de teléfono**y la ya se encuentra el **tipo de número de** aparecer como **servicio - gratuito**.</span><span class="sxs-lookup"><span data-stu-id="f68b7-132">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="f68b7-133">Para obtener sus números de servicio, vea [los números de teléfono del servicio de obtención](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) o si desea transferir un número de servicio existente, vea [los números de teléfono de transferencia a Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f68b7-133">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f68b7-134">Si está fuera de los Estados Unidos, no puede usar el centro de administración de Microsoft Teams para obtener números de servicio.</span><span class="sxs-lookup"><span data-stu-id="f68b7-134">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="f68b7-135">Vaya a [administrar los números de teléfono para su organización](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) en su lugar para ver cómo hacerlo desde fuera de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="f68b7-135">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="f68b7-136">Crear una cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f68b7-136">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="f68b7-137">En el centro de administración de Microsoft Teams, vaya a **configuración de toda la organización** > **las cuentas de recursos**.</span><span class="sxs-lookup"><span data-stu-id="f68b7-137">In Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**.</span></span> 

![ASD](media/r-a-master.png)

![número 1](media/sfbcallout1.png)

<span data-ttu-id="f68b7-140">Para crear un nuevo recurso cuenta haga clic en **+ nueva cuenta**.</span><span class="sxs-lookup"><span data-stu-id="f68b7-140">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="f68b7-141">En el menú emergente, rellene el nombre para mostrar y nombre de usuario para la cuenta del recurso (el nombre de dominio debe rellenar automáticamente), a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f68b7-141">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![cuenta de recurso](media/res-acct.png)

<span data-ttu-id="f68b7-143">A continuación, deberá aplicar una licencia a la cuenta del recurso, tal como se describe en [asignar licencias a los usuarios de Office 365 para profesionales](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="f68b7-143">Next, you will  need to apply a license to the resource account, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

<span data-ttu-id="f68b7-144">![número 3](media/sfbcallout3.png) una vez que se ha creado la cuenta del recurso y asigna la licencia, puede hacer clic en **Asignar o Cancelar asignación** para asignar un número de servicio de planeación de la llamada a la cuenta del recurso, o asignar la cuenta de recurso a una cola de llamada o de operador automático que ya existe.</span><span class="sxs-lookup"><span data-stu-id="f68b7-144">![number 3](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a Calling Plan service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="f68b7-145">Asignación de un número de enrutamiento directo puede realizarse con sólo los Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f68b7-145">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="f68b7-146">Si la cola de llamadas u operador automático aún debe crearse, puede vincular la cuenta del recurso al crearlo.</span><span class="sxs-lookup"><span data-stu-id="f68b7-146">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="f68b7-147">Cuando haya terminado, haga clic en **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="f68b7-147">Click **Save** when you are done.</span></span>

![asignar la cuenta de recurso](media/r-a-assign.png)

<span data-ttu-id="f68b7-149">![número 2](media/sfbcallout2.png) puede editar el nombre para mostrar recursos cuenta con la opción de **Editar** .</span><span class="sxs-lookup"><span data-stu-id="f68b7-149">![number 2](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="f68b7-150">Cuando haya terminado, haga clic en **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="f68b7-150">Click **Save** when you are done.</span></span>
<span data-ttu-id="f68b7-151">![editar la cuenta de recurso](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="f68b7-151">![edit resource account](media/r-a-edit.png)</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="f68b7-152">Crear una cuenta de recursos en Powershell</span><span class="sxs-lookup"><span data-stu-id="f68b7-152">Create a resource account in Powershell</span></span>

<span data-ttu-id="f68b7-153">Planes de llamada de Microsoft, puede asignar sólo números de pago y los números de teléfono de un servicio gratuito que obtuvo en el **Centro de administración de equipos de Microsoft** o trasladado desde otro proveedor de servicios a una cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="f68b7-153">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="f68b7-154">Para obtener y usar números de servicio gratuitos, debe configurar Créditos de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="f68b7-154">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

<span data-ttu-id="f68b7-155">Dependiendo de si la cuenta del recurso se encuentra en línea o local, sería necesario para conectarse a la adecuada símbolo del sistema Powershell con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="f68b7-155">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span> 
- <span data-ttu-id="f68b7-156">El siguiente Powershell cmdlet ejemplos suponen que la cuenta del recurso está hospeda en línea utilizando [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para crear una cuenta de recurso que se hospeda en línea.</span><span class="sxs-lookup"><span data-stu-id="f68b7-156">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="f68b7-157">Para recursos cuentas alojarse en local en Skype para 2019 de Business Server que se pueden usar con colas de llamadas en la nube y en la nube operadores automáticos, consulte [Configurar colas de llamadas en la nube](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) o [Configurar operadores automáticos de la nube](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="f68b7-157">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="f68b7-158">Las implementaciones de híbrido (números hospedados en el enrutamiento directo) se utilizará [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f68b7-158">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="f68b7-159">La aplicación de ID que necesita utilizarlo durante la creación de la aplicación de instancias son:</span><span class="sxs-lookup"><span data-stu-id="f68b7-159">The application ID's that you need to use while creating the application instances are:</span></span>
- <span data-ttu-id="f68b7-160">**Operadores automáticos:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="f68b7-160">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="f68b7-161">**Cola de llamadas:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="f68b7-161">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="f68b7-162">Si desea que la cola de llamadas u operador para que pueda buscarse por usuarios locales automático, debe crear los recursos cuentas locales, ya que las cuentas de recursos en línea no están sincronizadas hacia abajo a Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f68b7-162">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="f68b7-163">Para crear una cuenta de recursos en línea para usar con el uso auto attendant, el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="f68b7-163">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="f68b7-164">No podrá usar la cuenta del recurso hasta que se aplican una licencia a ella.</span><span class="sxs-lookup"><span data-stu-id="f68b7-164">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="f68b7-165">Cómo aplicar una licencia a una cuenta en el centro de administración de Office 365, vea [asignar licencias a los usuarios de Office 365 para la empresa](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) , así como [Asignar Skype para licencias de negocio](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="f68b7-165">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="f68b7-166">(Opcional) Una vez que la licencia correcta se aplica a la cuenta del recurso puede establecer un número de teléfono a la cuenta del recurso, tal y como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="f68b7-166">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="f68b7-167">No todas las cuentas de recursos requerirá un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="f68b7-167">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="f68b7-168">Si no aplicó una licencia para la cuenta del recurso, se producirá un error en la asignación de números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="f68b7-168">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="f68b7-169">Para obtener más información acerca de este comando, vea [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f68b7-169">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="f68b7-170">Es más fácil de establecer el número de teléfono en línea mediante el centro de administración de Microsoft Teams, tal y como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f68b7-170">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="f68b7-171">Administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f68b7-171">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="f68b7-172">Para administrar la configuración de la cuenta de recursos en el centro de administración de Microsoft Teams, vaya a **configuración de toda la organización**  > **las cuentas de recursos**, seleccione la cuenta de recursos que necesita para cambiar la configuración para y, a continuación, haga clic en el botón **Editar** .</span><span class="sxs-lookup"><span data-stu-id="f68b7-172">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="f68b7-173">en la pantalla **Editar la cuenta del recurso** , podrá cambiar esta configuración:</span><span class="sxs-lookup"><span data-stu-id="f68b7-173">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="f68b7-174">**Nombre para mostrar** para la cuenta</span><span class="sxs-lookup"><span data-stu-id="f68b7-174">**Display name** for the account</span></span>
- <span data-ttu-id="f68b7-175">Cola de llamadas u operadores automáticos que usa la cuenta</span><span class="sxs-lookup"><span data-stu-id="f68b7-175">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="f68b7-176">Número de teléfono asignado a la cuenta</span><span class="sxs-lookup"><span data-stu-id="f68b7-176">Phone number assigned to the account</span></span>

<span data-ttu-id="f68b7-177">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f68b7-177">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="f68b7-178">Eliminar una cuenta de recurso</span><span class="sxs-lookup"><span data-stu-id="f68b7-178">Delete a resource account</span></span>

<span data-ttu-id="f68b7-179">Asegúrese de que disociar el número de teléfono de la cuenta del recurso antes de eliminarlo, para evitar la introducción de su número de servicio se bloquee en pendiente de modo.</span><span class="sxs-lookup"><span data-stu-id="f68b7-179">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="f68b7-180">Puede hacerlo mediante el commandlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="f68b7-180">You can do that using the following commandlet:</span></span> 

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```
                
<span data-ttu-id="f68b7-181">Una vez que lo, puede eliminar la cuenta del recurso desde el portal de administración de Office 365, en la ficha de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f68b7-181">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>


## <a name="related-information"></a><span data-ttu-id="f68b7-182">Información relacionada</span><span class="sxs-lookup"><span data-stu-id="f68b7-182">Related Information</span></span>

<span data-ttu-id="f68b7-183">Para las implementaciones que son híbrida con Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="f68b7-183">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="f68b7-184">Planear los operadores automáticos en la nube</span><span class="sxs-lookup"><span data-stu-id="f68b7-184">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="f68b7-185">Configurar los operadores automáticos en la nube</span><span class="sxs-lookup"><span data-stu-id="f68b7-185">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="f68b7-186">Para las implementaciones en los equipos o Skype para empresarial en línea:</span><span class="sxs-lookup"><span data-stu-id="f68b7-186">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="f68b7-187">¿Qué son los operadores automáticos en la nube?</span><span class="sxs-lookup"><span data-stu-id="f68b7-187">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="f68b7-188">Configurar un operador automático en la nube</span><span class="sxs-lookup"><span data-stu-id="f68b7-188">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="f68b7-189">Ejemplo de pequeña empresa: configurar un operador automático</span><span class="sxs-lookup"><span data-stu-id="f68b7-189">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="f68b7-190">Crear una cola de llamadas en la nube</span><span class="sxs-lookup"><span data-stu-id="f68b7-190">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="f68b7-191">Nueva CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="f68b7-191">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="f68b7-192">Nueva CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="f68b7-192">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
