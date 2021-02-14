---
title: Consideraciones de unión a un dominio del Sistema de sala de Skype
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
description: Lea este tema para obtener información sobre cómo unir un equipo de dispositivo del Sistema de sala de Skype a su dominio.
ms.openlocfilehash: 6d6decf689b1a38615851911b42676050a823e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805920"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Consideraciones de unión a un dominio del Sistema de sala de Skype
 
Lea este tema para obtener información sobre cómo unir un equipo de dispositivo del Sistema de sala de Skype a su dominio.
  
## <a name="domain-joining-considerations"></a>Consideraciones de unión de dominio

Puede unir el equipo del dispositivo del Sistema de sala de Skype al dominio de Active Directory o dejarlo en un grupo de trabajo. Tenga en cuenta los siguientes puntos antes de tomar esta decisión:
  
- Unirse a un dominio al equipo de dispositivo del Sistema de sala de Skype ayuda a importar automáticamente la cadena de certificados raíz privada de su organización.
    
- La unión a un dominio del equipo de aplicación del Sistema de sala de Skype le permite conceder derechos administrativos de usuarios y grupos de dominio. Al hacerlo, no tendrá que recordar la contraseña de la cuenta de administrador de nivel de equipo local.
    
- Cuando se une un equipo de dispositivo del Sistema de sala de Skype al dominio, es necesario que cree una unidad organizativa (OU) independiente, de modo que pueda proporcionar exclusiones de objetos de directiva de grupo (GPO) a la unidad organizativa donde residen todos los objetos del equipo del Sistema de sala de Skype. Al hacerlo, cree objetos de máquina en la unidad organizativa antes de unir el equipo de dispositivo del Sistema de sala de Skype al dominio.
    
- Muchas organizaciones tienen los siguientes GPO, que afectan a las funciones de equipo del dispositivo del Sistema de sala de Skype. Asegúrese de invalidar o bloquear la herencia de estos GPO en la unidad organizativa del sistema de sala de Skype: 
    
  - Tiempo de espera de sesiones de inicio de sesión (bloqueo automático)
    
  - Directivas relacionadas con la administración de energía
    
  - Requerir pasos de autenticación adicionales
    
  - Denegar el acceso a unidades locales
    
  - Solicitar a los usuarios conexiones de red lentas
    
  - Iniciar un determinado programa al iniciar sesión
    
  - Crea otra cuenta de usuario de dominio en todos los equipos unidos a un dominio.
    
  - Insertar Windows Update en el sistema de sala de Skype
    
- Como alternativa, puede decidir dejar el equipo del dispositivo en el grupo de trabajo. Al igual que con el cliente de Skype Empresarial de escritorio, esto requiere que importe manualmente la cadena de certificados raíz en el equipo de dispositivo del Sistema de sala de Skype. You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on). 
    
Si planea unir máquinas del Sistema de sala de Skype al dominio, para evitar unirse accidentalmente a una unidad organizativa no intencionada, que puede no estar libre de GPO, asegúrese de unirse a la unidad organizativa correcta. Puede usar el siguiente cmdlet desde el equipo del Sistema de sala de Skype para unirse a la unidad organizativa correcta y no recibe GPO que puedan bloquear la funcionalidad LRS. Póngase en contacto con el administrador del sistema o con el partner oem para ejecutar estos cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Incluso si crea una unidad organizativa independiente y bloquea la herencia, hay algunas directivas que podrían causar problemas en un nivel superior. Una configuración de directiva de grupo sin invalidación supera a una unidad organizativa con una configuración de herencia de directiva de bloqueo. Para obtener más información, consulte el artículo Sin invalidación en comparación con bloquear la herencia [de directivas](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) en la documentación de directiva de grupo.
  
Es posible que tenga varios enfoques para resolver estos problemas. Le recomendamos que consulte con los expertos de Active Directory para asegurarse de que se le proporciona una UO que tenga la configuración de GPO adecuada o al menos una OU en la que no existan las directivas descritas anteriormente. Se recomienda habilitar la calidad de servicio (QoS) para los dispositivos del Sistema de sala de Skype.

## <a name="see-also"></a>Vea también
  
[Configuración de dispositivo: Crear nueva o editar existente](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Administración de la calidad de servicio](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
