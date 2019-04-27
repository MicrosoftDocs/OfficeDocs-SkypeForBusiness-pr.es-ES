---
title: Consideraciones de unión a dominio del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Lea este tema para obtener información sobre cómo unirse a un equipo PC de la aplicación de Sistema de salas de Skype para su dominio.
ms.openlocfilehash: 675074cc61b60432e68317d139b20b727073961f
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33363007"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="479bc-103">Consideraciones de unión a dominio del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="479bc-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="479bc-104">Lea este tema para obtener información sobre cómo unirse a un equipo PC de la aplicación de Sistema de salas de Skype para su dominio.</span><span class="sxs-lookup"><span data-stu-id="479bc-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="479bc-105">Consideraciones de unión a dominio</span><span class="sxs-lookup"><span data-stu-id="479bc-105">Domain joining considerations</span></span>

<span data-ttu-id="479bc-106">Puede participar en el dispositivo del sistema de salas de Skype PC para el dominio de Active Directory o dejarla en un grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="479bc-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="479bc-107">Considere los siguientes puntos antes de realizar esta decisión:</span><span class="sxs-lookup"><span data-stu-id="479bc-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="479bc-108">El dispositivo del sistema de salas de Skype PC la unión de dominio ayuda a importar la cadena de certificados raíz privado de la organización automáticamente.</span><span class="sxs-lookup"><span data-stu-id="479bc-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="479bc-109">El dispositivo del sistema de salas de Skype PC la unión de dominio le permite conceder a los usuarios de dominio y derechos administrativos de grupos.</span><span class="sxs-lookup"><span data-stu-id="479bc-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="479bc-110">Al hacer esto, no tendrá que acordarse de la contraseña de la cuenta de administrador de nivel de máquina local.</span><span class="sxs-lookup"><span data-stu-id="479bc-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="479bc-111">Cuando se une a un dispositivo de sistema de salas de Skype PC al dominio, es necesario crear un independiente unidad organizativa (OU), por lo que puede proporcionar las exclusiones de objeto de directiva de grupo (GPO) para la unidad organizativa donde residen todos los objetos de equipo del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="479bc-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="479bc-112">En este caso, crear objetos de equipo en la unidad organizativa antes de unirse al dispositivo del sistema de salas de Skype PC al dominio.</span><span class="sxs-lookup"><span data-stu-id="479bc-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="479bc-113">Muchas organizaciones tienen los GPO siguientes, que afectan a las funciones del sistema de salas de Skype dispositivo PC.</span><span class="sxs-lookup"><span data-stu-id="479bc-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="479bc-114">Asegúrese de que reemplazar o bloquear la herencia de estos GPO en la unidad organizativa de Skype salón del sistema:</span><span class="sxs-lookup"><span data-stu-id="479bc-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="479bc-115">Tiempo de espera de sesiones de inicio de sesión (bloqueo automático)</span><span class="sxs-lookup"><span data-stu-id="479bc-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="479bc-116">Directivas relacionadas de administración de energía</span><span class="sxs-lookup"><span data-stu-id="479bc-116">Power management related policies</span></span>
    
  - <span data-ttu-id="479bc-117">Requerir pasos de autenticación adicionales</span><span class="sxs-lookup"><span data-stu-id="479bc-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="479bc-118">Negar el acceso a las unidades locales</span><span class="sxs-lookup"><span data-stu-id="479bc-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="479bc-119">Avisar a los usuarios de conexiones de red lentas</span><span class="sxs-lookup"><span data-stu-id="479bc-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="479bc-120">Iniciar un programa determinado en el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="479bc-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="479bc-121">Crear otra cuenta de usuario de dominio en todas las máquinas con unión a dominio.</span><span class="sxs-lookup"><span data-stu-id="479bc-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="479bc-122">Inserción de Windows Update al sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="479bc-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="479bc-123">De forma alternativa, puede decidir dejar el equipo PC de aplicación en el grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="479bc-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="479bc-124">Como con el escritorio Microsoft Teams o Skype para clientes empresariales, esto requiere importar manualmente la cadena de certificados raíz en el dispositivo del sistema de salas de Skype PC.</span><span class="sxs-lookup"><span data-stu-id="479bc-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="479bc-125">No es necesario para importar la cadena de certificados raíz si la implementación usa un certificado público (por ejemplo, Entrust, VeriSign etc.).</span><span class="sxs-lookup"><span data-stu-id="479bc-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="479bc-126">Si planea unirse a equipos con un sistema de salas de Skype para el dominio, para evitar que se unen a máquina del sistema de salas de Skype sin darse cuenta a una unidad organizativa no deseada, que puede no estar libre de los GPO, asegúrese de unirse a la unidad organizativa correcta.</span><span class="sxs-lookup"><span data-stu-id="479bc-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="479bc-127">Puede usar el cmdlet siguiente desde el equipo del sistema de salas de Skype a participar en la unidad organizativa correcta y no recibe los GPO que podrían bloquear la funcionalidad LRS.</span><span class="sxs-lookup"><span data-stu-id="479bc-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="479bc-128">Póngase en contacto con su administrador de sistema o socio OEM para ejecutar estos cmdlets:</span><span class="sxs-lookup"><span data-stu-id="479bc-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="479bc-129">Aunque cree un OU independiente y bloqueo de herencia, existen algunas directivas que podrían ocasionar problemas en un nivel superior.</span><span class="sxs-lookup"><span data-stu-id="479bc-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="479bc-130">Una directiva de grupo con una configuración de no invalidación supera a un OU con una configuración de herencia de directiva de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="479bc-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="479bc-131">Para obtener más información, vea el artículo [No reemplazar con respecto a bloquear la herencia de directiva](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) en la documentación de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="479bc-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="479bc-132">Puede tener varios enfoques para solucionar estos problemas.</span><span class="sxs-lookup"><span data-stu-id="479bc-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="479bc-133">Le aconsejamos que consulte con los expertos de Active Directory para asegurarse de que obtiene un OU que tiene una configuración de GPO adecuada, o al menos un OU en el que las directivas descritas anteriormente no existan.</span><span class="sxs-lookup"><span data-stu-id="479bc-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="479bc-134">Se recomienda habilitar la calidad de servicio (QoS) para dispositivos de sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="479bc-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="479bc-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="479bc-135">See also</span></span>
  
[<span data-ttu-id="479bc-136">Configuración de dispositivo: Crear nueva o editar existente</span><span class="sxs-lookup"><span data-stu-id="479bc-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="479bc-137">Administración de la Calidad de servicio (QoS)</span><span class="sxs-lookup"><span data-stu-id="479bc-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
