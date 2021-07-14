---
title: Implementar Teams teléfonos y Teams pantallas con Intune
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: En este artículo se proporciona información general sobre las características compatibles con Microsoft Teams pantallas.
ms.openlocfilehash: ee5b536aaadaf458b6edf9b32dea299a3ecad9a0
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420825"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="16fbd-103">Implementar Teams teléfonos y Teams pantallas con Intune</span><span class="sxs-lookup"><span data-stu-id="16fbd-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="16fbd-104">En este artículo se ofrece información general sobre cómo implementar.</span><span class="sxs-lookup"><span data-stu-id="16fbd-104">This article gives you an overview of how to deploy.</span></span> <span data-ttu-id="16fbd-105">Teams teléfonos y Teams pantalla con Intune.</span><span class="sxs-lookup"><span data-stu-id="16fbd-105">Teams phones and Teams display using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="16fbd-106">Acceso condicional</span><span class="sxs-lookup"><span data-stu-id="16fbd-106">Conditional Access</span></span>

<span data-ttu-id="16fbd-107">El acceso condicional es una característica Azure Active Directory (Azure AD) que le ayuda a garantizar que los dispositivos que obtienen acceso Office 365 los recursos se administran correctamente y son seguros.</span><span class="sxs-lookup"><span data-stu-id="16fbd-107">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="16fbd-108">Si aplica directivas de acceso condicional al servicio Teams, los dispositivos Android (incluidos los teléfonos Teams y las pantallas Teams) que accedan Teams deben estar inscritos en Intune y su configuración debe cumplir con las directivas.</span><span class="sxs-lookup"><span data-stu-id="16fbd-108">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams needs to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="16fbd-109">Si el dispositivo no está inscrito en Intune o si está inscrito, pero su configuración no cumple con las directivas, Acceso condicional impedirá que un usuario inicie sesión en o use la aplicación Teams en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="16fbd-109">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="16fbd-110">Normalmente, las directivas de cumplimiento definidas en Intune se asignan a grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="16fbd-110">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="16fbd-111">Esto significa que, si asigna una directiva de cumplimiento de Android a user@contoso.com, dicha directiva se aplicará por igual a su smartphone Android y a cualquier dispositivo de Teams basado en Android en el que user@contoso.com sesión.</span><span class="sxs-lookup"><span data-stu-id="16fbd-111">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="16fbd-112">Si usa acceso condicional, que requiere que se aplique la inscripción de Intune, en su organización, hay un par de cosas que debe configurar para permitir una inscripción correcta de Intune:</span><span class="sxs-lookup"><span data-stu-id="16fbd-112">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="16fbd-113">**Licencia de Intune** El usuario que inicia sesión en Teams dispositivo debe tener licencia para Intune.</span><span class="sxs-lookup"><span data-stu-id="16fbd-113">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="16fbd-114">Siempre que el dispositivo Teams haya iniciado sesión en una cuenta de usuario que tenga una licencia válida de Intune, el dispositivo se inscribirá automáticamente en Microsoft Intune como parte del proceso de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="16fbd-114">As long as the Teams device is signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="16fbd-115">**Configurar Intune** Debe tener un espacio empresarial de Intune configurado correctamente para la inscripción del administrador de dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="16fbd-115">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="16fbd-116">Configurar Intune para inscribir Teams dispositivos basados en Android</span><span class="sxs-lookup"><span data-stu-id="16fbd-116">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="16fbd-117">Teams Intune administra los dispositivos basados en Android a través de la administración del administrador de dispositivos Android (DA).</span><span class="sxs-lookup"><span data-stu-id="16fbd-117">Teams Android-based devices are managed by Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="16fbd-118">Antes de que los dispositivos se puedan inscribir en Intune, hay algunos pasos básicos para realizar.</span><span class="sxs-lookup"><span data-stu-id="16fbd-118">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="16fbd-119">Si ya está administrando dispositivos con Intune hoy, es probable que ya haya hecho todas estas cosas.</span><span class="sxs-lookup"><span data-stu-id="16fbd-119">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="16fbd-120">Si no es así, esto es lo que debe hacer:</span><span class="sxs-lookup"><span data-stu-id="16fbd-120">If not, here’s what to do:</span></span>

> [!NOTE]
> - <span data-ttu-id="16fbd-121">Si los administradores de inquilinos quieren que los teléfonos de área común se inscriba en Intune, deben agregar una licencia de Intune a la cuenta y seguir los pasos para la inscripción de Intune.</span><span class="sxs-lookup"><span data-stu-id="16fbd-121">If tenant admins want common area phones to be enrolled into Intune, they need to add an Intune license to the account and follow the steps for Intune enrollment.</span></span>
> - <span data-ttu-id="16fbd-122">Si la cuenta de usuario usada para iniciar sesión en un dispositivo Teams no tiene licencia para Intune, las directivas de cumplimiento de Intune y las restricciones de inscripción deben deshabilitarse para la cuenta.</span><span class="sxs-lookup"><span data-stu-id="16fbd-122">If the user account used to sign into a Teams device isn't licensed for Intune, Intune compliance policies and enrollment restrictions need to be disabled for the account.</span></span>



1. <span data-ttu-id="16fbd-123">Establecer Intune MDM (administración de dispositivos móviles) Autoridad.</span><span class="sxs-lookup"><span data-stu-id="16fbd-123">Set Intune MDM (mobile device management) Authority.</span></span>  

   <span data-ttu-id="16fbd-124">Si nunca ha usado Intune antes, debe establecer la autoridad mdma antes de poder inscribir dispositivos.</span><span class="sxs-lookup"><span data-stu-id="16fbd-124">If you’ve never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="16fbd-125">Para obtener más información, vea Establecer la autoridad de administración [de dispositivos móviles.](/intune/fundamentals/mdm-authority-set)</span><span class="sxs-lookup"><span data-stu-id="16fbd-125">For more information, see [Set the mobile device management authority](/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="16fbd-126">Este es un paso único que debe realizarse al crear un nuevo inquilino de Intune.</span><span class="sxs-lookup"><span data-stu-id="16fbd-126">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
1. <span data-ttu-id="16fbd-127">Habilitar la inscripción del administrador de dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="16fbd-127">Enable Android device administrator enrollment.</span></span>
  
   <span data-ttu-id="16fbd-128">Los dispositivos Teams basados en Android se administran como dispositivos de administrador de dispositivos con Intune.</span><span class="sxs-lookup"><span data-stu-id="16fbd-128">Android-based Teams devices are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="16fbd-129">La inscripción del administrador de dispositivos está desactivada de forma predeterminada para los inquilinos recién creados.</span><span class="sxs-lookup"><span data-stu-id="16fbd-129">Device administrator enrollment is off by default for newly created tenants.</span></span> <span data-ttu-id="16fbd-130">Consulte Inscripción [del administrador de dispositivos Android.](/intune/enrollment/android-enroll-device-administrator)</span><span class="sxs-lookup"><span data-stu-id="16fbd-130">See [Android device administrator enrollment](/intune/enrollment/android-enroll-device-administrator).</span></span>
1. <span data-ttu-id="16fbd-131">Asignar licencias a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="16fbd-131">Assign licenses to users.</span></span> 
 
   <span data-ttu-id="16fbd-132">Los usuarios Teams dispositivos que se inscriban en Intune deben tener asignada una licencia válida de Intune.</span><span class="sxs-lookup"><span data-stu-id="16fbd-132">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="16fbd-133">Para obtener más información, vea Asignar licencias a los usuarios [para que puedan inscribir dispositivos en Intune.](/intune/fundamentals/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="16fbd-133">For more information, see [Assign licenses to users so they can enroll devices in Intune](/intune/fundamentals/licenses-assign).</span></span>
1. <span data-ttu-id="16fbd-134">Asignar directivas de cumplimiento del administrador de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="16fbd-134">Assign Device Administrator compliance policies.</span></span>  

   <span data-ttu-id="16fbd-135">a.</span><span class="sxs-lookup"><span data-stu-id="16fbd-135">a.</span></span> <span data-ttu-id="16fbd-136">Crear una directiva de cumplimiento del administrador de dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="16fbd-136">Create an Android Device Administrator compliance policy.</span></span>

   <span data-ttu-id="16fbd-137">b.</span><span class="sxs-lookup"><span data-stu-id="16fbd-137">b.</span></span> <span data-ttu-id="16fbd-138">Asígnelo al grupo Azure Active Directory que contiene los usuarios que iniciarán sesión en los Teams dispositivos.</span><span class="sxs-lookup"><span data-stu-id="16fbd-138">Assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="16fbd-139">Vea [Usar directivas de cumplimiento para establecer reglas para los dispositivos que administra con Intune.](/mem/intune/protect/device-compliance-get-started)</span><span class="sxs-lookup"><span data-stu-id="16fbd-139">See [Use compliance policies to set rules for devices you manage with Intune](/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="16fbd-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="16fbd-140">See also</span></span>

[<span data-ttu-id="16fbd-141">Teléfonos para Teams</span><span class="sxs-lookup"><span data-stu-id="16fbd-141">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="16fbd-142">Teléfonos IP certificados para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16fbd-142">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="16fbd-143">Teams pantallas</span><span class="sxs-lookup"><span data-stu-id="16fbd-143">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="16fbd-144">Administrar los dispositivos en Teams</span><span class="sxs-lookup"><span data-stu-id="16fbd-144">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="16fbd-145">Teams Marketplace</span><span class="sxs-lookup"><span data-stu-id="16fbd-145">Teams Marketplace</span></span>](https://office.com/teamsdevices)