---
title: Consideraciones de unión a dominio del Sistema de salas de Skype
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: Administrador puede aprender a unirse a un equipo del sistema de salas de Skype en un dominio de Active Directory, junto con las consideraciones para hacerlo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfcee1421c25903a5ec8deb2f66871ed1d57ef1c
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905442"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="7f00b-103">Consideraciones de unión a dominio del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="7f00b-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="7f00b-104">Lea este tema para obtener información sobre cómo unirse a un equipo PC de la aplicación de Sistema de salas de Skype para su dominio.</span><span class="sxs-lookup"><span data-stu-id="7f00b-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="7f00b-105">Consideraciones de unión a dominio</span><span class="sxs-lookup"><span data-stu-id="7f00b-105">Domain joining considerations</span></span>

<span data-ttu-id="7f00b-106">Puedes unirte al equipo de Skype Room System Appliance al dominio de Active Directory o dejarlo en un grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7f00b-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="7f00b-107">Considere los siguientes puntos antes de realizar esta decisión:</span><span class="sxs-lookup"><span data-stu-id="7f00b-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="7f00b-108">Unirse al dominio con el equipo de Skype Room System Appliance le ayuda a importar la cadena de certificados raíz privada de su organización automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7f00b-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="7f00b-109">Unirse al dominio: el equipo del sistema de Skype Room le permite conceder derechos administrativos a usuarios y grupos del dominio.</span><span class="sxs-lookup"><span data-stu-id="7f00b-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="7f00b-110">Al hacer esto, no tendrá que acordarse de la contraseña de la cuenta de administrador de nivel de máquina local.</span><span class="sxs-lookup"><span data-stu-id="7f00b-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="7f00b-111">Cuando se une a un equipo de un sistema de salas de Skype en el dominio, es necesario que cree una unidad organizativa (Uo) independiente, de modo que pueda proporcionar exclusiones de objeto de directiva de grupo (GPO) a la uo donde se encuentran todos los objetos de la máquina del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="7f00b-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="7f00b-112">Cuando lo haga, cree objetos de equipo en la OU antes de unirse al dominio del equipo del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="7f00b-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="7f00b-113">Muchas organizaciones tienen los siguientes GPO, que afectan a las funciones de equipo de Skype Room System Appliance.</span><span class="sxs-lookup"><span data-stu-id="7f00b-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="7f00b-114">Asegúrate de invalidar o bloquear la herencia de estos GPO en la unidad organizativa del sistema de salas de Skype:</span><span class="sxs-lookup"><span data-stu-id="7f00b-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="7f00b-115">Tiempo de espera de sesiones de inicio de sesión (bloqueo automático)</span><span class="sxs-lookup"><span data-stu-id="7f00b-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="7f00b-116">Directivas relacionadas de administración de energía</span><span class="sxs-lookup"><span data-stu-id="7f00b-116">Power management related policies</span></span>
  - <span data-ttu-id="7f00b-117">Requerir pasos de autenticación adicionales</span><span class="sxs-lookup"><span data-stu-id="7f00b-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="7f00b-118">Negar el acceso a las unidades locales</span><span class="sxs-lookup"><span data-stu-id="7f00b-118">Denying access to local drives</span></span>
  - <span data-ttu-id="7f00b-119">Avisar a los usuarios de conexiones de red lentas</span><span class="sxs-lookup"><span data-stu-id="7f00b-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="7f00b-120">Iniciar un programa determinado en el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="7f00b-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="7f00b-121">Crear otra cuenta de usuario de dominio en todas las máquinas con unión a dominio.</span><span class="sxs-lookup"><span data-stu-id="7f00b-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="7f00b-122">Insertar Windows Update en el sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="7f00b-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="7f00b-123">De forma alternativa, puede decidir dejar el equipo PC de aplicación en el grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7f00b-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="7f00b-124">Al igual que con el cliente de Microsoft Teams o Skype empresarial, necesita importar manualmente la cadena de certificados raíz en el equipo del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="7f00b-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="7f00b-125">No es necesario importar la cadena de certificados raíz si su implementación usa un certificado público (por ejemplo, Entrust, VeriSign, etc.).</span><span class="sxs-lookup"><span data-stu-id="7f00b-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="7f00b-126">Si planeas unir las máquinas del sistema de salas de Skype con el dominio, para evitar que se unan al equipo del sistema de salas de Skype accidentalmente a una OU no deseada, que puede no estar exenta de GPO, asegúrate de unirte a la unidad organizativa correcta.</span><span class="sxs-lookup"><span data-stu-id="7f00b-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="7f00b-127">Puede usar el siguiente cmdlet de la máquina del sistema de salas de Skype para unirse a la OU correcta y no recibe GPO que puedan bloquear la funcionalidad de LRS.</span><span class="sxs-lookup"><span data-stu-id="7f00b-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="7f00b-128">Póngase en contacto con su administrador de sistema o socio OEM para ejecutar estos cmdlets:</span><span class="sxs-lookup"><span data-stu-id="7f00b-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="7f00b-129">Aunque cree un OU independiente y bloqueo de herencia, existen algunas directivas que podrían ocasionar problemas en un nivel superior.</span><span class="sxs-lookup"><span data-stu-id="7f00b-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="7f00b-130">Una directiva de grupo con una configuración de no invalidación supera a un OU con una configuración de herencia de directiva de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7f00b-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="7f00b-131">Para obtener más información, vea el artículo [no reemplazar en comparación con bloquear la herencia de directivas](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) en la documentación de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="7f00b-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="7f00b-132">Puede tener varios enfoques para solucionar estos problemas.</span><span class="sxs-lookup"><span data-stu-id="7f00b-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="7f00b-133">Le aconsejamos que consulte con los expertos de Active Directory para asegurarse de que obtiene un OU que tiene una configuración de GPO adecuada, o al menos un OU en el que las directivas descritas anteriormente no existan.</span><span class="sxs-lookup"><span data-stu-id="7f00b-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="7f00b-134">Se recomienda habilitar la calidad de servicio (QoS) para los dispositivos de sistema de la sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="7f00b-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7f00b-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7f00b-135">Related topics</span></span>
  
[<span data-ttu-id="7f00b-136">Configuración de dispositivo: Crear nueva o editar existente</span><span class="sxs-lookup"><span data-stu-id="7f00b-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="7f00b-137">Administración de la Calidad de servicio (QoS)</span><span class="sxs-lookup"><span data-stu-id="7f00b-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
