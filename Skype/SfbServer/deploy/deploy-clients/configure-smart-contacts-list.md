---
title: Configurar la lista de contactos inteligentes en clientes de Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Resumen: obtenga información sobre cómo activar la característica lista de contactos inteligentes en el cliente de Skype Empresarial.'
ms.openlocfilehash: 1f049493d591cd561b87611f8a34f9176ace165a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095804"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="dc503-103">Configurar la lista de contactos inteligentes en clientes de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="dc503-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="dc503-104">**Resumen:** Obtenga información sobre cómo activar la característica lista de contactos inteligentes en el cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="dc503-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="dc503-105">La característica lista de contactos inteligentes permite la población automática de listas de contactos para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="dc503-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="dc503-106">Al usar Primero Skype Empresarial, los usuarios verán automáticamente a su administrador y a otras personas de su equipo.</span><span class="sxs-lookup"><span data-stu-id="dc503-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="dc503-107">Esta característica está activada de forma predeterminada para los usuarios de Microsoft 365 y Office 365, pero debe habilitar explícitamente esta característica para los usuarios locales mediante la configuración de la directiva de cliente.</span><span class="sxs-lookup"><span data-stu-id="dc503-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="dc503-108">Tenga en cuenta lo siguiente al configurar esta característica:</span><span class="sxs-lookup"><span data-stu-id="dc503-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="dc503-109">Los usuarios, hasta 13, se agregan automáticamente a la lista de contactos inteligentes en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="dc503-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="dc503-110">Manager</span><span class="sxs-lookup"><span data-stu-id="dc503-110">Manager</span></span>

  2. <span data-ttu-id="dc503-111">Dirige en orden alfabético</span><span class="sxs-lookup"><span data-stu-id="dc503-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="dc503-112">Pares en orden alfabético</span><span class="sxs-lookup"><span data-stu-id="dc503-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="dc503-113">La primera vez que un usuario inicia sesión, se crea un nuevo grupo, denominado Mi grupo.</span><span class="sxs-lookup"><span data-stu-id="dc503-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="dc503-114">El grupo se rellena automáticamente con personas en la relación de grupo de AD del usuario en función del alias de usuario rellenado en el campo Administrador.</span><span class="sxs-lookup"><span data-stu-id="dc503-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="dc503-115">Tenga en cuenta que los cambios en la pertenencia a grupos de AD no provocan actualizaciones en Mi grupo después de rellenarla inicialmente.</span><span class="sxs-lookup"><span data-stu-id="dc503-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="dc503-116">Si un usuario elimina un contacto o el grupo, no se vuelve a crear el contacto ni el grupo.</span><span class="sxs-lookup"><span data-stu-id="dc503-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="dc503-117">Si el etiquetado automático está activado, los contactos de la lista se etiquetarán para los cambios de presencia.</span><span class="sxs-lookup"><span data-stu-id="dc503-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="dc503-118">El etiquetado automático está activado de forma predeterminada, pero puedes desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="dc503-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="dc503-119">Se informará a todos los nuevos usuarios del grupo de que se han agregado a la lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="dc503-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="dc503-120">Los usuarios pueden agregar manualmente nuevos miembros a su Mi grupo o a otros grupos de su elección.</span><span class="sxs-lookup"><span data-stu-id="dc503-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="dc503-121">Esta característica solo funciona para los usuarios que inician sesión por primera vez.</span><span class="sxs-lookup"><span data-stu-id="dc503-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="dc503-122">Si un usuario ha iniciado sesión previamente desde cualquier dispositivo (incluido, por ejemplo, cualquier dispositivo móvil o un Mac), la característica no está habilitada para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="dc503-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="dc503-123">Configurar la lista de contactos inteligentes</span><span class="sxs-lookup"><span data-stu-id="dc503-123">Configure Smart contacts list</span></span>

<span data-ttu-id="dc503-124">Para habilitar la característica lista de contactos inteligentes para los usuarios, deberá realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="dc503-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="dc503-125">Cree una nueva entrada CsClientPolicy y agrégrela a la directiva de cliente global.</span><span class="sxs-lookup"><span data-stu-id="dc503-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="dc503-126">Asegúrese de que la búsqueda de libreta de direcciones está configurada solo para la búsqueda web.</span><span class="sxs-lookup"><span data-stu-id="dc503-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="dc503-127">Crear una entrada de directiva para habilitar la lista de contactos inteligentes</span><span class="sxs-lookup"><span data-stu-id="dc503-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="dc503-128">Para crear una entrada de directiva para habilitar la característica lista de contactos inteligentes, use el cmdlet [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con la opción EnableClientAutoPopulateWithTeam de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="dc503-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="dc503-129">A continuación, use el cmdlet [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) para escribir los cambios en la directiva global de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="dc503-129">Next, use the [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="dc503-130">Opcionalmente, puede crear una directiva para desactivar el etiquetado automático de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="dc503-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="dc503-131">También debe establecer el parámetro AddressBookAvailability para la directiva correspondiente en WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="dc503-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="dc503-132">Para obtener más información, [vea Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="dc503-132">For more information, see [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="dc503-133">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="dc503-133">Troubleshoot</span></span>

<span data-ttu-id="dc503-134">Si la lista de contactos inteligentes no funciona como se esperaba, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc503-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="dc503-135">Validar la configuración.</span><span class="sxs-lookup"><span data-stu-id="dc503-135">Validate the configuration.</span></span> 

- <span data-ttu-id="dc503-136">Confirme que la información de la organización de AD está rellenada.</span><span class="sxs-lookup"><span data-stu-id="dc503-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="dc503-137">Recopilar los registros de cliente de Skype Empresarial en un nuevo usuario para su análisis posterior.</span><span class="sxs-lookup"><span data-stu-id="dc503-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="dc503-138">Confirme que la interfaz de usuario del cliente de Skype Empresarial no muestra un mensaje que no pueda conectarse a la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="dc503-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="dc503-139">Para confirmar la conectividad de la libreta de direcciones, realice una búsqueda de un usuario en la barra de búsqueda de cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="dc503-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="dc503-140">Los problemas de replicación de AD DS podrían hacer que los contactos no se resuelvan cuando un usuario inicia sesión por primera vez en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="dc503-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>