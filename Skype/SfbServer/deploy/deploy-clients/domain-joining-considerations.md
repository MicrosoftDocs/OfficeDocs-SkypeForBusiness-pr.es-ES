---
title: Consideraciones de unión de dominio del sistema de salón de Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Lea este tema para obtener información sobre cómo unirse a un equipo de aplicación del sistema de salón de Skype a su dominio.
ms.openlocfilehash: cf98f98a7294ead0920b3d6b07b00879cbfe15f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093574"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="94a13-103">Consideraciones de unión de dominio del sistema de salón de Skype</span><span class="sxs-lookup"><span data-stu-id="94a13-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="94a13-104">Lea este tema para obtener información sobre cómo unirse a un equipo de aplicación del sistema de salón de Skype a su dominio.</span><span class="sxs-lookup"><span data-stu-id="94a13-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="94a13-105">Consideraciones de unión de dominio</span><span class="sxs-lookup"><span data-stu-id="94a13-105">Domain joining considerations</span></span>

<span data-ttu-id="94a13-106">Puede unir el equipo del dispositivo del sistema de salón de Skype al dominio de Active Directory o dejarlo en un grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="94a13-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="94a13-107">Tenga en cuenta los siguientes puntos antes de tomar esta decisión:</span><span class="sxs-lookup"><span data-stu-id="94a13-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="94a13-108">La unión a un dominio del equipo del dispositivo del sistema de salón de Skype ayuda a importar automáticamente la cadena de certificados raíz privada de su organización.</span><span class="sxs-lookup"><span data-stu-id="94a13-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="94a13-109">La unión a un dominio del equipo del dispositivo del sistema de salón de Skype permite conceder derechos administrativos a usuarios de dominio y grupos.</span><span class="sxs-lookup"><span data-stu-id="94a13-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="94a13-110">Al hacerlo, no tendrá que recordar la contraseña de la cuenta de administrador de nivel de equipo local.</span><span class="sxs-lookup"><span data-stu-id="94a13-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="94a13-111">Cuando se une un equipo de aplicación del sistema de salón de Skype al dominio, es necesario crear una unidad organizativa (OU) independiente, de modo que pueda proporcionar exclusiones de objetos de directiva de grupo (GPO) a la OU donde residen todos los objetos de máquina del sistema de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="94a13-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="94a13-112">Al hacerlo, cree objetos de máquina en la OU antes de unir el equipo del dispositivo del sistema de salón de Skype al dominio.</span><span class="sxs-lookup"><span data-stu-id="94a13-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="94a13-113">Muchas organizaciones tienen los siguientes GPO, que afectan a las funciones del equipo del dispositivo del sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="94a13-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="94a13-114">Asegúrese de invalidar o bloquear la herencia de estos GPO en la OU del sistema de salón de Skype:</span><span class="sxs-lookup"><span data-stu-id="94a13-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="94a13-115">Tiempo de espera de las sesiones de inicio de sesión (bloqueo automático)</span><span class="sxs-lookup"><span data-stu-id="94a13-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="94a13-116">Directivas relacionadas con la administración de energía</span><span class="sxs-lookup"><span data-stu-id="94a13-116">Power management related policies</span></span>
    
  - <span data-ttu-id="94a13-117">Requerir pasos de autenticación adicionales</span><span class="sxs-lookup"><span data-stu-id="94a13-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="94a13-118">Denegar el acceso a unidades locales</span><span class="sxs-lookup"><span data-stu-id="94a13-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="94a13-119">Solicitar a los usuarios conexiones de red lentas</span><span class="sxs-lookup"><span data-stu-id="94a13-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="94a13-120">Iniciar un programa determinado al iniciar sesión</span><span class="sxs-lookup"><span data-stu-id="94a13-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="94a13-121">Cree otra cuenta de usuario de dominio en todos los equipos unidos a un dominio.</span><span class="sxs-lookup"><span data-stu-id="94a13-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="94a13-122">Insertar Windows Update en el sistema de sala de Skype</span><span class="sxs-lookup"><span data-stu-id="94a13-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="94a13-123">Como alternativa, puede decidir dejar el equipo del dispositivo en el grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="94a13-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="94a13-124">Al igual que con el cliente de Skype Empresarial de escritorio, esto requiere que importe manualmente la cadena de certificados raíz en el equipo del dispositivo sistema de salón de Skype.</span><span class="sxs-lookup"><span data-stu-id="94a13-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="94a13-125">No es necesario importar la cadena de certificados raíz si la implementación de Skype Empresarial usa un certificado público (por ejemplo, Entrust, VeriSign, entre otros).</span><span class="sxs-lookup"><span data-stu-id="94a13-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="94a13-126">Si planea unir máquinas del sistema de sala de Skype al dominio, para evitar unirse accidentalmente a una máquina del sistema de sala de Skype a una OU no intencionada, que puede no estar libre de GPO, asegúrese de unirse a la OU correcta.</span><span class="sxs-lookup"><span data-stu-id="94a13-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="94a13-127">Puede usar el siguiente cmdlet de la máquina sistema de salón de Skype para unirse a la OU correcta y no recibe GPO que puedan bloquear la funcionalidad de LRS.</span><span class="sxs-lookup"><span data-stu-id="94a13-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="94a13-128">Póngase en contacto con el administrador del sistema o con el partner OEM para ejecutar estos cmdlets:</span><span class="sxs-lookup"><span data-stu-id="94a13-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="94a13-129">Incluso si crea una OU independiente y bloquea la herencia, hay algunas directivas que podrían causar problemas en un nivel superior.</span><span class="sxs-lookup"><span data-stu-id="94a13-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="94a13-130">Una configuración de directiva de grupo sin invalidación supera a una OU con una configuración de herencia de directivas de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="94a13-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="94a13-131">Para obtener más información, consulte el artículo [No override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) en la documentación de la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="94a13-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="94a13-132">Es posible que tenga varios enfoques para resolver estos problemas.</span><span class="sxs-lookup"><span data-stu-id="94a13-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="94a13-133">Le recomendamos que consulte con los expertos de Active Directory para asegurarse de que se le proporciona una OU que tenga la configuración de GPO adecuada, o al menos una OU en la que no existan las directivas descritas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="94a13-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="94a13-134">Se recomienda habilitar la calidad del servicio (QoS) para dispositivos del sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="94a13-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="94a13-135">Ver también</span><span class="sxs-lookup"><span data-stu-id="94a13-135">See also</span></span>
  
[<span data-ttu-id="94a13-136">Configuración de dispositivo: Crear nueva o editar existente</span><span class="sxs-lookup"><span data-stu-id="94a13-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="94a13-137">Administración de la calidad del servicio</span><span class="sxs-lookup"><span data-stu-id="94a13-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)