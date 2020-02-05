---
title: Configurar la lista Smart Contacts en clientes de Skype empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Resumen: Obtenga información sobre cómo activar la característica lista de contactos inteligente en el cliente de Skype empresarial.'
ms.openlocfilehash: 9db4e6616aa4c11be3ad2f9ee1cd92a0587b4e51
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768873"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="26ed5-103">Configurar la lista Smart Contacts en clientes de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="26ed5-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="26ed5-104">**Resumen:** Obtenga información sobre cómo activar la característica lista de contactos inteligente en el cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="26ed5-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="26ed5-105">La característica Lista de contactos inteligentes permite rellenar automáticamente las listas de contactos de los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="26ed5-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="26ed5-106">La primera vez que use Skype empresarial, los usuarios verán automáticamente a su jefe y a otras personas de su equipo.</span><span class="sxs-lookup"><span data-stu-id="26ed5-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="26ed5-107">Esta característica está activada de forma predeterminada para los usuarios de Office 365, pero debe habilitarla de forma explícita para los usuarios locales mediante la configuración de la Directiva de cliente.</span><span class="sxs-lookup"><span data-stu-id="26ed5-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="26ed5-108">Tenga en cuenta lo siguiente al configurar esta característica:</span><span class="sxs-lookup"><span data-stu-id="26ed5-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="26ed5-109">Los usuarios, hasta 13, se agregan automáticamente a la lista de contactos inteligente en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="26ed5-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="26ed5-110">Administrador</span><span class="sxs-lookup"><span data-stu-id="26ed5-110">Manager</span></span>

  2. <span data-ttu-id="26ed5-111">Directos en orden alfabético</span><span class="sxs-lookup"><span data-stu-id="26ed5-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="26ed5-112">Compañeros en orden alfabético</span><span class="sxs-lookup"><span data-stu-id="26ed5-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="26ed5-113">La primera vez que un usuario inicia sesión, se crea un grupo llamado Mi grupo.</span><span class="sxs-lookup"><span data-stu-id="26ed5-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="26ed5-114">El grupo se rellena automáticamente con las personas de la relación de grupo de AD del usuario en función del alias de usuario rellenado en el campo administrador.</span><span class="sxs-lookup"><span data-stu-id="26ed5-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="26ed5-115">Tenga en cuenta que los cambios realizados en la pertenencia a un grupo de AD no se actualizan en Mi grupo después de haberse rellenado inicialmente.</span><span class="sxs-lookup"><span data-stu-id="26ed5-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="26ed5-116">Si un usuario elimina un contacto o el grupo, ni el contacto ni el grupo se volverán a crear.</span><span class="sxs-lookup"><span data-stu-id="26ed5-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="26ed5-117">Si el etiquetado automático está activado, los contactos de la lista estarán etiquetados para cambios de presencia.</span><span class="sxs-lookup"><span data-stu-id="26ed5-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="26ed5-118">El etiquetado automático está activado de forma predeterminada, pero puede elegir desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="26ed5-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="26ed5-119">Se informará a todos los nuevos usuarios del grupo que han sido agregados a la lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="26ed5-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="26ed5-120">Los usuarios pueden agregar de forma manual nuevos miembros a su instancia de Mi grupo o a otros grupos que elijan.</span><span class="sxs-lookup"><span data-stu-id="26ed5-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="26ed5-121">Esta característica solo funciona con usuarios que inician sesión la primera vez.</span><span class="sxs-lookup"><span data-stu-id="26ed5-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="26ed5-122">Si un usuario ha iniciado sesión anteriormente desde cualquier dispositivo (por ejemplo, un dispositivo móvil o un equipo Mac), esta característica no estará habilitada para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="26ed5-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="26ed5-123">Configurar la lista de contactos inteligentes</span><span class="sxs-lookup"><span data-stu-id="26ed5-123">Configure Smart contacts list</span></span>

<span data-ttu-id="26ed5-124">Para habilitar la lista de contactos inteligentes para los usuarios, tendrá que completar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="26ed5-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="26ed5-125">Cree una nueva entrada de ClientPolicy y agréguela a la Directiva de cliente global.</span><span class="sxs-lookup"><span data-stu-id="26ed5-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="26ed5-126">Asegúrese de que la opción Búsqueda de la Libreta de direcciones esté configurada solo para búsqueda en la web.</span><span class="sxs-lookup"><span data-stu-id="26ed5-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="26ed5-127">Crear una entrada de directiva para habilitar la lista de contactos inteligentes</span><span class="sxs-lookup"><span data-stu-id="26ed5-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="26ed5-128">Para crear una entrada de directiva para habilitar la característica de lista de contactos inteligente, use el cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con la opción EnableClientAutoPopulateWithTeam de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="26ed5-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="26ed5-129">A continuación, use el cmdlet [set-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) para escribir los cambios en la directiva global de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="26ed5-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="26ed5-130">De manera opcional, puede crear una directiva para desactivar el etiquetado automático, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="26ed5-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="26ed5-131">Además, tiene que configurar el parámetro AddressBookAvailability para la directiva correspondiente en WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="26ed5-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="26ed5-132">Para obtener más información, consulte [set-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="26ed5-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="26ed5-133">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="26ed5-133">Troubleshoot</span></span>

<span data-ttu-id="26ed5-134">Si la lista de contactos inteligentes no funciona según lo esperado, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="26ed5-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="26ed5-135">Valide la configuración.</span><span class="sxs-lookup"><span data-stu-id="26ed5-135">Validate the configuration.</span></span> 

- <span data-ttu-id="26ed5-136">Confirme que la información de la organización de AD está rellenada.</span><span class="sxs-lookup"><span data-stu-id="26ed5-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="26ed5-137">Recopilar registros de clientes de Skype empresarial en un nuevo usuario para analizarlos más.</span><span class="sxs-lookup"><span data-stu-id="26ed5-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="26ed5-138">Confirme que la interfaz de usuario del cliente de Skype empresarial no muestra un mensaje que indica que no se puede conectar con la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="26ed5-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="26ed5-139">Para confirmar la conectividad de la libreta de direcciones, busque un usuario en la barra de búsqueda del cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="26ed5-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="26ed5-140">Los problemas de replicación de AD DS pueden provocar que los contactos no se resuelvan cuando un usuario inicia sesión en Skype empresarial por primera vez.</span><span class="sxs-lookup"><span data-stu-id="26ed5-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


