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
ms.openlocfilehash: d995d2addf8b774ebad9945b3f35f07ddb431855
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805780"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="53de1-103">Configurar la lista de contactos inteligentes en clientes de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="53de1-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="53de1-104">**Resumen:** Obtenga información sobre cómo activar la característica lista de contactos inteligentes en el cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="53de1-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="53de1-105">La característica lista de contactos inteligentes permite la población automática de listas de contactos para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="53de1-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="53de1-106">Una vez que use Skype Empresarial, los usuarios verán automáticamente a su administrador y a otras personas de su equipo.</span><span class="sxs-lookup"><span data-stu-id="53de1-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="53de1-107">Esta característica está activada de forma predeterminada para los usuarios de Microsoft 365 y Office 365, pero debe habilitar explícitamente esta característica para los usuarios locales mediante la configuración de la directiva de cliente.</span><span class="sxs-lookup"><span data-stu-id="53de1-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="53de1-108">Tenga en cuenta lo siguiente al configurar esta característica:</span><span class="sxs-lookup"><span data-stu-id="53de1-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="53de1-109">Los usuarios, hasta 13, se agregan automáticamente a la lista de contactos inteligentes en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="53de1-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="53de1-110">Manager</span><span class="sxs-lookup"><span data-stu-id="53de1-110">Manager</span></span>

  2. <span data-ttu-id="53de1-111">Dirige en orden alfabético</span><span class="sxs-lookup"><span data-stu-id="53de1-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="53de1-112">Sistemas del mismo nivel en orden alfabético</span><span class="sxs-lookup"><span data-stu-id="53de1-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="53de1-113">La primera vez que un usuario inicia sesión, se crea un nuevo grupo, denominado Mi grupo.</span><span class="sxs-lookup"><span data-stu-id="53de1-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="53de1-114">El grupo se rellena automáticamente con las personas de la relación de grupo de AD del usuario en función del alias de usuario rellenado en el campo Administrador.</span><span class="sxs-lookup"><span data-stu-id="53de1-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="53de1-115">Ten en cuenta que los cambios en la pertenencia a grupos de AD no provocan actualizaciones en Mi grupo después de rellenarse inicialmente.</span><span class="sxs-lookup"><span data-stu-id="53de1-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="53de1-116">Si un usuario elimina un contacto o el grupo, no se vuelve a crear ni el contacto ni el grupo.</span><span class="sxs-lookup"><span data-stu-id="53de1-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="53de1-117">Si el etiquetado automático está activado, los contactos de la lista se etiquetarán para los cambios de presencia.</span><span class="sxs-lookup"><span data-stu-id="53de1-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="53de1-118">El etiquetado automático está activado de forma predeterminada, pero puedes elegir desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="53de1-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="53de1-119">Se informará a todos los nuevos usuarios del grupo de que se han agregado a la lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="53de1-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="53de1-120">Los usuarios pueden agregar manualmente nuevos miembros a su Mi grupo o a otros grupos de su elección.</span><span class="sxs-lookup"><span data-stu-id="53de1-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="53de1-121">Esta característica solo funciona para los usuarios que inician sesión por primera vez.</span><span class="sxs-lookup"><span data-stu-id="53de1-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="53de1-122">Si un usuario ha iniciado sesión previamente desde cualquier dispositivo (incluido, por ejemplo, cualquier dispositivo móvil o un Equipo Mac), la característica no está habilitada para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="53de1-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="53de1-123">Configurar la lista de contactos inteligentes</span><span class="sxs-lookup"><span data-stu-id="53de1-123">Configure Smart contacts list</span></span>

<span data-ttu-id="53de1-124">Para habilitar la característica lista de contactos inteligentes para los usuarios, deberá realizar los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="53de1-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="53de1-125">Crear una nueva entrada de CsClientPolicy y agregarla a la directiva de cliente global.</span><span class="sxs-lookup"><span data-stu-id="53de1-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="53de1-126">Asegúrese de que la búsqueda de la libreta de direcciones está configurada solo para la búsqueda web.</span><span class="sxs-lookup"><span data-stu-id="53de1-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="53de1-127">Crear una entrada de directiva para habilitar la lista de contactos inteligentes</span><span class="sxs-lookup"><span data-stu-id="53de1-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="53de1-128">Para crear una entrada de directiva para habilitar la característica lista de contactos inteligentes, use el cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con la opción EnableClientAutoPopulateWithTeam de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="53de1-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="53de1-129">A continuación, use el cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) para escribir los cambios en la directiva global de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="53de1-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="53de1-130">Opcionalmente, puede crear una directiva para desactivar el etiquetado automático de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="53de1-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="53de1-131">También debe establecer el parámetro AddressBookAvailability para la directiva correspondiente en WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="53de1-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="53de1-132">Para obtener más información, [vea Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="53de1-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="53de1-133">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="53de1-133">Troubleshoot</span></span>

<span data-ttu-id="53de1-134">Si la lista de contactos inteligentes no funciona como se esperaba, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53de1-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="53de1-135">Valide la configuración.</span><span class="sxs-lookup"><span data-stu-id="53de1-135">Validate the configuration.</span></span> 

- <span data-ttu-id="53de1-136">Confirme que se ha rellenado la información de la organización de AD.</span><span class="sxs-lookup"><span data-stu-id="53de1-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="53de1-137">Recopilar los registros de cliente de Skype Empresarial en un nuevo usuario para un análisis posterior.</span><span class="sxs-lookup"><span data-stu-id="53de1-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="53de1-138">Confirme que la interfaz de usuario del cliente de Skype Empresarial no muestra un mensaje que indica que no se puede conectar a la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="53de1-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="53de1-139">Para confirmar la conectividad de la libreta de direcciones, realice una búsqueda para un usuario en la barra de búsqueda del cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="53de1-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="53de1-140">Los problemas de replicación de AD DS podrían hacer que los contactos no se resuelvan cuando un usuario inicia sesión por primera vez en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="53de1-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


