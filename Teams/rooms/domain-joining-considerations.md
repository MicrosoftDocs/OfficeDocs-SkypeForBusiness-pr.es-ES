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
description: El administrador puede obtener información sobre cómo unirse a un equipo de aplicación de Sistema de sala de Skype a un dominio de Active Directory, junto con las consideraciones para hacerlo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfcee1421c25903a5ec8deb2f66871ed1d57ef1c
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905442"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="050d8-103">Consideraciones de unión a dominio del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="050d8-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="050d8-104">Lea este tema para obtener información sobre cómo unirse a un equipo PC de la aplicación de Sistema de salas de Skype para su dominio.</span><span class="sxs-lookup"><span data-stu-id="050d8-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="050d8-105">Consideraciones de unión a dominio</span><span class="sxs-lookup"><span data-stu-id="050d8-105">Domain joining considerations</span></span>

<span data-ttu-id="050d8-106">Puede unirse al equipo del dispositivo de Sistema de sala de Skype al dominio de Active Directory o dejarlo en un grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="050d8-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="050d8-107">Considere los siguientes puntos antes de realizar esta decisión:</span><span class="sxs-lookup"><span data-stu-id="050d8-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="050d8-108">Unirse a un dominio en el equipo del dispositivo de Skype Room System le ayuda a importar automáticamente la cadena de certificados raíz privados de su organización.</span><span class="sxs-lookup"><span data-stu-id="050d8-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="050d8-109">Unirse a un dominio en el equipo del dispositivo de Skype Room System le permite conceder derechos administrativos a los usuarios y grupos del dominio.</span><span class="sxs-lookup"><span data-stu-id="050d8-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="050d8-110">Al hacer esto, no tendrá que acordarse de la contraseña de la cuenta de administrador de nivel de máquina local.</span><span class="sxs-lookup"><span data-stu-id="050d8-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="050d8-111">Cuando se une a un equipo del dispositivo de Sistema de salón de Skype en el dominio, es necesario que cree una unidad organizativa (OU) independiente, de modo que pueda proporcionar exclusiones de objeto de directiva de grupo (GPO) a la unidad organizativa en la que residen todos los objetos del equipo de Sistema de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="050d8-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="050d8-112">Al hacerlo, cree objetos de equipo en la UO antes de unirse al equipo del dispositivo de Sistema de sala de Skype con el dominio.</span><span class="sxs-lookup"><span data-stu-id="050d8-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="050d8-113">Muchas organizaciones tienen los siguientes GPO, que afectan a las funciones de pc de aplicación de Sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="050d8-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="050d8-114">Asegúrese de invalidar o bloquear la herencia de estos GPO en la UO de Sistema de salón de Skype:</span><span class="sxs-lookup"><span data-stu-id="050d8-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="050d8-115">Tiempo de espera de sesiones de inicio de sesión (bloqueo automático)</span><span class="sxs-lookup"><span data-stu-id="050d8-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="050d8-116">Directivas relacionadas de administración de energía</span><span class="sxs-lookup"><span data-stu-id="050d8-116">Power management related policies</span></span>
  - <span data-ttu-id="050d8-117">Requerir pasos de autenticación adicionales</span><span class="sxs-lookup"><span data-stu-id="050d8-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="050d8-118">Negar el acceso a las unidades locales</span><span class="sxs-lookup"><span data-stu-id="050d8-118">Denying access to local drives</span></span>
  - <span data-ttu-id="050d8-119">Avisar a los usuarios de conexiones de red lentas</span><span class="sxs-lookup"><span data-stu-id="050d8-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="050d8-120">Iniciar un programa determinado en el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="050d8-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="050d8-121">Crear otra cuenta de usuario de dominio en todas las máquinas con unión a dominio.</span><span class="sxs-lookup"><span data-stu-id="050d8-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="050d8-122">Actualizar Windows Update al sistema de sala de Skype</span><span class="sxs-lookup"><span data-stu-id="050d8-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="050d8-123">De forma alternativa, puede decidir dejar el equipo PC de aplicación en el grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="050d8-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="050d8-124">Al igual que con el cliente de escritorio de Microsoft Teams o Skype Empresarial, esto requiere que importe manualmente la cadena de certificados raíz en el equipo de aplicación de Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="050d8-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="050d8-125">No es necesario importar la cadena de certificados raíz si su implementación está usando un certificado público (por ejemplo, Entrust, VeriSign, y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="050d8-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="050d8-126">Si planea unirse a equipos de Sistema de sala de Skype en el dominio, para evitar que se una accidentalmente a un equipo de Sistema de sala de Skype con una UO no intencionada, que puede no estar libre de GPO, asegúrese de unirse a la unidad organizativa correcta.</span><span class="sxs-lookup"><span data-stu-id="050d8-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="050d8-127">Puede usar el siguiente cmdlet de la máquina de Sistema de salón de Skype para unirse a la unidad organizativa correcta y no recibe GPO que puedan bloquear la funcionalidad del LRS.</span><span class="sxs-lookup"><span data-stu-id="050d8-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="050d8-128">Póngase en contacto con su administrador de sistema o socio OEM para ejecutar estos cmdlets:</span><span class="sxs-lookup"><span data-stu-id="050d8-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="050d8-129">Aunque cree un OU independiente y bloqueo de herencia, existen algunas directivas que podrían ocasionar problemas en un nivel superior.</span><span class="sxs-lookup"><span data-stu-id="050d8-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="050d8-130">Una directiva de grupo con una configuración de no invalidación supera a un OU con una configuración de herencia de directiva de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="050d8-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="050d8-131">Para obtener más información, vea el artículo ["No](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) invalidar en comparación con bloquear la herencia de directivas" en la documentación de la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="050d8-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="050d8-132">Puede tener varios enfoques para solucionar estos problemas.</span><span class="sxs-lookup"><span data-stu-id="050d8-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="050d8-133">Le aconsejamos que consulte con los expertos de Active Directory para asegurarse de que obtiene un OU que tiene una configuración de GPO adecuada, o al menos un OU en el que las directivas descritas anteriormente no existan.</span><span class="sxs-lookup"><span data-stu-id="050d8-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="050d8-134">Se recomienda habilitar la Calidad de servicio (QoS) para los dispositivos de Sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="050d8-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="050d8-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="050d8-135">Related topics</span></span>
  
[<span data-ttu-id="050d8-136">Configuración de dispositivo: Crear nueva o editar existente</span><span class="sxs-lookup"><span data-stu-id="050d8-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="050d8-137">Administración de la Calidad de servicio (QoS)</span><span class="sxs-lookup"><span data-stu-id="050d8-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
