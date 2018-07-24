---
title: Consideraciones de unión a dominio del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Lea este tema para obtener información sobre cómo unirse a un equipo PC de la aplicación de Sistema de salas de Skype para su dominio.
ms.openlocfilehash: b89ca5c5619c8d090aa765d0be1765b0b13900de
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20972481"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Consideraciones de unión a dominio del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo unirse a un equipo PC de la aplicación de Sistema de salas de Skype para su dominio.
  
## <a name="domain-joining-considerations"></a>Consideraciones de unión a dominio

Puede participar en el dispositivo del sistema de salas de Skype PC para el dominio de Active Directory o dejarla en un grupo de trabajo. Considere los siguientes puntos antes de realizar esta decisión:
  
- El dispositivo del sistema de salas de Skype PC la unión de dominio ayuda a importar la cadena de certificados raíz privado de la organización automáticamente.
    
- El dispositivo del sistema de salas de Skype PC la unión de dominio le permite conceder a los usuarios de dominio y derechos administrativos de grupos. Al hacer esto, no tendrá que acordarse de la contraseña de la cuenta de administrador de nivel de máquina local.
    
- Cuando se une a un dispositivo de sistema de salas de Skype PC al dominio, es necesario crear un independiente unidad organizativa (OU), por lo que puede proporcionar las exclusiones de objeto de directiva de grupo (GPO) para la unidad organizativa donde residen todos los objetos de equipo del sistema de salas de Skype. En este caso, crear objetos de equipo en la unidad organizativa antes de unirse al dispositivo del sistema de salas de Skype PC al dominio.
    
- Muchas organizaciones tienen los GPO siguientes, que afectan a las funciones del sistema de salas de Skype dispositivo PC. Asegúrese de que reemplazar o bloquear la herencia de estos GPO en la unidad organizativa de Skype salón del sistema: 
    
  - Tiempo de espera de sesiones de inicio de sesión (bloqueo automático)
    
  - Directivas relacionadas de administración de energía
    
  - Requerir pasos de autenticación adicionales
    
  - Negar el acceso a las unidades locales
    
  - Avisar a los usuarios de conexiones de red lentas
    
  - Iniciar un programa determinado en el inicio de sesión
    
  - Crear otra cuenta de usuario de dominio en todas las máquinas con unión a dominio.
    
  - Inserción de Windows Update al sistema de salas de Skype
    
- De forma alternativa, puede decidir dejar el equipo PC de aplicación en el grupo de trabajo. Como con el escritorio Skype para clientes empresariales, esto requiere importar manualmente la cadena de certificados raíz en el dispositivo del sistema de salas de Skype PC. No es necesario para importar la cadena de certificados raíz si su Skype para la implementación de la empresa está usando un certificado público (por ejemplo, Entrust, VeriSign etc.). 
    
Si planea unirse a equipos con un sistema de salas de Skype para el dominio, para evitar que se unen a máquina del sistema de salas de Skype sin darse cuenta a una unidad organizativa no deseada, que puede no estar libre de los GPO, asegúrese de unirse a la unidad organizativa correcta. Puede usar el cmdlet siguiente desde el equipo del sistema de salas de Skype a participar en la unidad organizativa correcta y no recibe los GPO que podrían bloquear la funcionalidad LRS. Póngase en contacto con su administrador de sistema o socio OEM para ejecutar estos cmdlets:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Aunque cree un OU independiente y bloqueo de herencia, existen algunas directivas que podrían ocasionar problemas en un nivel superior. Una directiva de grupo con una configuración de no invalidación supera a un OU con una configuración de herencia de directiva de bloqueo. Para obtener más información, vea el artículo [No reemplazar con respecto a bloquear la herencia de directiva](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) en la documentación de directiva de grupo.
  
Puede tener varios enfoques para solucionar estos problemas. Le aconsejamos que consulte con los expertos de Active Directory para asegurarse de que obtiene un OU que tiene una configuración de GPO adecuada, o al menos un OU en el que las directivas descritas anteriormente no existan. Se recomienda habilitar la calidad de servicio (QoS) para dispositivos de sistema de salas de Skype.

## <a name="see-also"></a>Vea también
  
[Configuración de dispositivo: Crear nueva o editar existente](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Administración de la Calidad de servicio (QoS)](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
