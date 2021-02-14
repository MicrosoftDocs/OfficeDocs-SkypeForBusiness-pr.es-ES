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

# <a name="skype-room-system-domain-joining-considerations"></a>Consideraciones de unión a dominio del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo unirse a un equipo PC de la aplicación de Sistema de salas de Skype para su dominio.
  
## <a name="domain-joining-considerations"></a>Consideraciones de unión a dominio

Puede unirse al equipo del dispositivo de Sistema de sala de Skype al dominio de Active Directory o dejarlo en un grupo de trabajo. Considere los siguientes puntos antes de realizar esta decisión:
  
- Unirse a un dominio en el equipo del dispositivo de Skype Room System le ayuda a importar automáticamente la cadena de certificados raíz privados de su organización.
- Unirse a un dominio en el equipo del dispositivo de Skype Room System le permite conceder derechos administrativos a los usuarios y grupos del dominio. Al hacer esto, no tendrá que acordarse de la contraseña de la cuenta de administrador de nivel de máquina local.
- Cuando se une a un equipo del dispositivo de Sistema de salón de Skype en el dominio, es necesario que cree una unidad organizativa (OU) independiente, de modo que pueda proporcionar exclusiones de objeto de directiva de grupo (GPO) a la unidad organizativa en la que residen todos los objetos del equipo de Sistema de salón de Skype. Al hacerlo, cree objetos de equipo en la UO antes de unirse al equipo del dispositivo de Sistema de sala de Skype con el dominio.
- Muchas organizaciones tienen los siguientes GPO, que afectan a las funciones de pc de aplicación de Sistema de sala de Skype. Asegúrese de invalidar o bloquear la herencia de estos GPO en la UO de Sistema de salón de Skype:

  - Tiempo de espera de sesiones de inicio de sesión (bloqueo automático)
  - Directivas relacionadas de administración de energía
  - Requerir pasos de autenticación adicionales
  - Negar el acceso a las unidades locales
  - Avisar a los usuarios de conexiones de red lentas
  - Iniciar un programa determinado en el inicio de sesión
  - Crear otra cuenta de usuario de dominio en todas las máquinas con unión a dominio.
  - Actualizar Windows Update al sistema de sala de Skype
    
- De forma alternativa, puede decidir dejar el equipo PC de aplicación en el grupo de trabajo. Al igual que con el cliente de escritorio de Microsoft Teams o Skype Empresarial, esto requiere que importe manualmente la cadena de certificados raíz en el equipo de aplicación de Skype Room System. No es necesario importar la cadena de certificados raíz si su implementación está usando un certificado público (por ejemplo, Entrust, VeriSign, y así sucesivamente). 
    
Si planea unirse a equipos de Sistema de sala de Skype en el dominio, para evitar que se una accidentalmente a un equipo de Sistema de sala de Skype con una UO no intencionada, que puede no estar libre de GPO, asegúrese de unirse a la unidad organizativa correcta. Puede usar el siguiente cmdlet de la máquina de Sistema de salón de Skype para unirse a la unidad organizativa correcta y no recibe GPO que puedan bloquear la funcionalidad del LRS. Póngase en contacto con su administrador de sistema o socio OEM para ejecutar estos cmdlets:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Aunque cree un OU independiente y bloqueo de herencia, existen algunas directivas que podrían ocasionar problemas en un nivel superior. Una directiva de grupo con una configuración de no invalidación supera a un OU con una configuración de herencia de directiva de bloqueo. Para obtener más información, vea el artículo ["No](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) invalidar en comparación con bloquear la herencia de directivas" en la documentación de la directiva de grupo.
  
Puede tener varios enfoques para solucionar estos problemas. Le aconsejamos que consulte con los expertos de Active Directory para asegurarse de que obtiene un OU que tiene una configuración de GPO adecuada, o al menos un OU en el que las directivas descritas anteriormente no existan. Se recomienda habilitar la Calidad de servicio (QoS) para los dispositivos de Sistema de sala de Skype.

## <a name="related-topics"></a>Temas relacionados
  
[Configuración de dispositivo: Crear nueva o editar existente](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Administración de la Calidad de servicio (QoS)](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
