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
# <a name="skype-room-system-domain-joining-considerations"></a>Consideraciones de unión de dominio del sistema de salón de Skype
 
Lea este tema para obtener información sobre cómo unirse a un equipo de aplicación del sistema de salón de Skype a su dominio.
  
## <a name="domain-joining-considerations"></a>Consideraciones de unión de dominio

Puede unir el equipo del dispositivo del sistema de salón de Skype al dominio de Active Directory o dejarlo en un grupo de trabajo. Tenga en cuenta los siguientes puntos antes de tomar esta decisión:
  
- La unión a un dominio del equipo del dispositivo del sistema de salón de Skype ayuda a importar automáticamente la cadena de certificados raíz privada de su organización.
    
- La unión a un dominio del equipo del dispositivo del sistema de salón de Skype permite conceder derechos administrativos a usuarios de dominio y grupos. Al hacerlo, no tendrá que recordar la contraseña de la cuenta de administrador de nivel de equipo local.
    
- Cuando se une un equipo de aplicación del sistema de salón de Skype al dominio, es necesario crear una unidad organizativa (OU) independiente, de modo que pueda proporcionar exclusiones de objetos de directiva de grupo (GPO) a la OU donde residen todos los objetos de máquina del sistema de salón de Skype. Al hacerlo, cree objetos de máquina en la OU antes de unir el equipo del dispositivo del sistema de salón de Skype al dominio.
    
- Muchas organizaciones tienen los siguientes GPO, que afectan a las funciones del equipo del dispositivo del sistema de sala de Skype. Asegúrese de invalidar o bloquear la herencia de estos GPO en la OU del sistema de salón de Skype: 
    
  - Tiempo de espera de las sesiones de inicio de sesión (bloqueo automático)
    
  - Directivas relacionadas con la administración de energía
    
  - Requerir pasos de autenticación adicionales
    
  - Denegar el acceso a unidades locales
    
  - Solicitar a los usuarios conexiones de red lentas
    
  - Iniciar un programa determinado al iniciar sesión
    
  - Cree otra cuenta de usuario de dominio en todos los equipos unidos a un dominio.
    
  - Insertar Windows Update en el sistema de sala de Skype
    
- Como alternativa, puede decidir dejar el equipo del dispositivo en el grupo de trabajo. Al igual que con el cliente de Skype Empresarial de escritorio, esto requiere que importe manualmente la cadena de certificados raíz en el equipo del dispositivo sistema de salón de Skype. No es necesario importar la cadena de certificados raíz si la implementación de Skype Empresarial usa un certificado público (por ejemplo, Entrust, VeriSign, entre otros). 
    
Si planea unir máquinas del sistema de sala de Skype al dominio, para evitar unirse accidentalmente a una máquina del sistema de sala de Skype a una OU no intencionada, que puede no estar libre de GPO, asegúrese de unirse a la OU correcta. Puede usar el siguiente cmdlet de la máquina sistema de salón de Skype para unirse a la OU correcta y no recibe GPO que puedan bloquear la funcionalidad de LRS. Póngase en contacto con el administrador del sistema o con el partner OEM para ejecutar estos cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Incluso si crea una OU independiente y bloquea la herencia, hay algunas directivas que podrían causar problemas en un nivel superior. Una configuración de directiva de grupo sin invalidación supera a una OU con una configuración de herencia de directivas de bloqueo. Para obtener más información, consulte el artículo [No override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) en la documentación de la directiva de grupo.
  
Es posible que tenga varios enfoques para resolver estos problemas. Le recomendamos que consulte con los expertos de Active Directory para asegurarse de que se le proporciona una OU que tenga la configuración de GPO adecuada, o al menos una OU en la que no existan las directivas descritas anteriormente. Se recomienda habilitar la calidad del servicio (QoS) para dispositivos del sistema de sala de Skype.

## <a name="see-also"></a>Ver también
  
[Configuración de dispositivo: Crear nueva o editar existente](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Administración de la calidad del servicio](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)