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
description: El administrador puede obtener información sobre cómo unirse a un equipo de Skype de sistema de sala a un dominio de Active Directory, junto con las consideraciones para hacerlo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c322819fb765e05cead793c95b5e3b6af2d2a180
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117558"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Consideraciones de unión a dominio del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo unirse a un equipo PC de la aplicación de Sistema de salas de Skype para su dominio.
  
## <a name="domain-joining-considerations"></a>Consideraciones de unión a dominio

Puede unirse al equipo Skype room system al dominio de Active Directory o dejarlo en un grupo de trabajo. Considere los siguientes puntos antes de realizar esta decisión:
  
- Unirse al dominio Skype equipo del sistema de sala ayuda a importar automáticamente la cadena de certificados raíz privada de su organización.
- Unirse al dominio Skype equipo de sistema de sala le permite conceder derechos administrativos a usuarios y grupos de dominios. Al hacer esto, no tendrá que acordarse de la contraseña de la cuenta de administrador de nivel de máquina local.
- Cuando se une a un equipo del dispositivo del sistema de salón de Skype al dominio, es necesario que cree una unidad organizativa (OU) independiente, de modo que pueda proporcionar exclusiones de objetos de directiva de grupo (GPO) a la unidad organizativa donde residen todos los objetos del equipo del sistema de salón de Skype. Al hacerlo, cree objetos de máquina en la unidad organizativa antes de unirse al Skype equipo del sistema de sala al dominio.
- Muchas organizaciones tienen los siguientes GPO, que afectan a Skype de pc del dispositivo Room System. Asegúrese de invalidar o bloquear la herencia de estos GPO en la unidad organizativa Skype room system:

  - Tiempo de espera de sesiones de inicio de sesión (bloqueo automático)
  - Directivas relacionadas con la administración de energía
  - Requerir pasos de autenticación adicionales
  - Negar el acceso a las unidades locales
  - Avisar a los usuarios de conexiones de red lentas
  - Iniciar un programa determinado en el inicio de sesión
  - Crear otra cuenta de usuario de dominio en todas las máquinas con unión a dominio.
  - Insertar Windows actualizar a Skype room system
    
- De forma alternativa, puede decidir dejar el equipo PC de aplicación en el grupo de trabajo. Al igual que con el Microsoft Teams o Skype Empresarial de escritorio, esto requiere que importe manualmente la cadena de certificados raíz en el equipo de Skype de room system. No es necesario importar la cadena de certificados raíz si la implementación usa un certificado público (por ejemplo, Entrust, VeriSign, entre otros). 
    
Si tiene previsto unirse Skype los equipos del sistema de sala al dominio, para evitar unirse Skype un equipo del sistema de sala de forma involuntaria a una unidad organizativa no deseada, que puede no estar libre de GPO, asegúrese de unirse a la unidad organizativa correcta. Puede usar el siguiente cmdlet desde el equipo Skype Room System para unirse a la unidad organizativa correcta y no recibe GPO que puedan bloquear la funcionalidad de LRS. Póngase en contacto con el administrador del sistema o con el partner OEM para ejecutar estos cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Incluso si crea una unidad organizativa independiente y bloquea la herencia, hay algunas directivas que podrían causar problemas en un nivel superior. Una directiva de grupo con una configuración de no invalidación supera a un OU con una configuración de herencia de directiva de bloqueo. Para obtener más información, vea [Ninguna invalidación en comparación](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) con bloquear la herencia de directivas en la documentación de directiva de grupo.
  
Puede tener varios enfoques para solucionar estos problemas. Le recomendamos que consulte con sus expertos de Active Directory para asegurarse de que se le proporciona una unidad organizativa que tiene la configuración de GPO adecuada o al menos una unidad organizativa en la que no existen las directivas descritas anteriormente. Recomendamos habilitar calidad de servicio (QoS) para Skype de room system.

## <a name="related-topics"></a>Temas relacionados
  
[Configuración de dispositivo: Crear nueva o editar existente](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Administración de la Calidad de servicio (QoS)](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)