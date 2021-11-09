---
title: Skype Consideraciones de unión a dominios del sistema de sala
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Lea este tema para obtener información sobre cómo unirse a un equipo Skype de sistema de sala a su dominio.
ms.openlocfilehash: d3c94a4983bddb051bda29badf5c569eeef635a3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844873"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype Consideraciones de unión a dominios del sistema de sala
 
Lea este tema para obtener información sobre cómo unirse a un equipo Skype de sistema de sala a su dominio.
  
## <a name="domain-joining-considerations"></a>Consideraciones de unión de dominio

Puede unir el equipo del Skype del sistema de sala al dominio de Active Directory o dejarlo en un grupo de trabajo. Tenga en cuenta los siguientes puntos antes de tomar esta decisión:
  
- La unión de dominio Skype equipo del dispositivo del sistema de sala ayuda a importar automáticamente la cadena de certificados raíz privada de la organización.
    
- La unión a un dominio Skype equipo del sistema de sala le permite conceder derechos administrativos a los usuarios y grupos de dominio. Al hacerlo, no tendrá que recordar la contraseña de la cuenta de administrador de nivel de equipo local.
    
- Cuando se une un equipo de aplicación del sistema de sala de Skype al dominio, es necesario que cree una unidad organizativa (OU) independiente, de modo que pueda proporcionar exclusiones de objetos de directiva de grupo (GPO) a la unidad organizativa donde residen todos los objetos del equipo del sistema de sala de Skype. Al hacerlo, cree objetos de máquina en la unidad organizativa antes de unir Skype equipo del dispositivo del sistema de sala al dominio.
    
- Muchas organizaciones tienen los siguientes GPO, que afectan Skype funciones del equipo del dispositivo del sistema de sala. Asegúrese de invalidar o bloquear la herencia de estos GPO en la unidad organizativa Skype room system: 
    
  - Tiempo de espera de las sesiones de inicio de sesión (bloqueo automático)
    
  - Directivas relacionadas con la administración de energía
    
  - Requerir pasos de autenticación adicionales
    
  - Denegar el acceso a unidades locales
    
  - Solicitar a los usuarios conexiones de red lentas
    
  - Iniciar un programa determinado al iniciar sesión
    
  - Cree otra cuenta de usuario de dominio en todos los equipos unidos a un dominio.
    
  - Push Windows Update to Skype Room System
    
- Como alternativa, puede decidir dejar el equipo del dispositivo en el grupo de trabajo. Al igual que con el Skype Empresarial de escritorio, esto requiere que importe manualmente la cadena de certificados raíz en el equipo del Skype sistema de sala. No es necesario importar la cadena de certificados raíz si la implementación de Skype Empresarial usa un certificado público (por ejemplo, Entrust, VeriSign, y así sucesivamente). 
    
Si tiene previsto unirse Skype máquinas del sistema de sala al dominio, para evitar unirse Skype una máquina del sistema de sala de forma involuntaria a una unidad organizativa no intencionada, que puede no estar libre de GPO, asegúrese de unirse a la OU correcta. Puede usar el siguiente cmdlet de la máquina Skype Room System para unirse a la OU correcta y no recibe GPO que puedan bloquear la funcionalidad de LRS. Póngase en contacto con el administrador del sistema o con el partner OEM para ejecutar estos cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Incluso si crea una OU independiente y bloquea la herencia, hay algunas directivas que podrían causar problemas en un nivel superior. Una configuración de directiva de grupo sin invalidación supera a una OU con una configuración de herencia de directivas de bloqueo. Para obtener más información, consulte el artículo [No override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) en la documentación de la directiva de grupo.
  
Es posible que tenga varios enfoques para resolver estos problemas. Le recomendamos que consulte con los expertos de Active Directory para asegurarse de que se le proporciona una OU que tenga la configuración de GPO adecuada, o al menos una OU en la que no existan las directivas descritas anteriormente. Se recomienda habilitar la calidad del servicio (QoS) para Skype del sistema de sala.

## <a name="see-also"></a>Consulte también
  
[Configuración de dispositivo: Crear nueva o editar existente](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Administración de la calidad del servicio](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)