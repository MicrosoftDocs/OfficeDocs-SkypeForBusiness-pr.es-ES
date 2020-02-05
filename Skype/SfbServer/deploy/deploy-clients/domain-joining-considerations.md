---
title: Consideraciones de unión a dominio del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Lea este tema para obtener información sobre cómo unirse a un equipo PC de la aplicación de Sistema de salas de Skype para su dominio.
ms.openlocfilehash: 49e8c89ed9ddbbd579e7ed30fec6b98a933e3a3f
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768933"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Consideraciones de unión a dominio del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo unirse a un equipo PC de la aplicación de Sistema de salas de Skype para su dominio.
  
## <a name="domain-joining-considerations"></a>Consideraciones de unión a dominio

Puedes unirte al equipo de Skype Room System Appliance al dominio de Active Directory o dejarlo en un grupo de trabajo. Considere los siguientes puntos antes de realizar esta decisión:
  
- Unirse al dominio con el equipo de Skype Room System Appliance le ayuda a importar la cadena de certificados raíz privada de su organización automáticamente.
    
- Unirse al dominio: el equipo del sistema de Skype Room le permite conceder derechos administrativos a usuarios y grupos del dominio. Al hacer esto, no tendrá que acordarse de la contraseña de la cuenta de administrador de nivel de máquina local.
    
- Cuando se une a un equipo de un sistema de salas de Skype en el dominio, es necesario que cree una unidad organizativa (Uo) independiente, de modo que pueda proporcionar exclusiones de objeto de directiva de grupo (GPO) a la uo donde se encuentran todos los objetos de la máquina del sistema de salas de Skype. Cuando lo haga, cree objetos de equipo en la OU antes de unirse al dominio del equipo del sistema de salas de Skype.
    
- Muchas organizaciones tienen los siguientes GPO, que afectan a las funciones de equipo de Skype Room System Appliance. Asegúrate de invalidar o bloquear la herencia de estos GPO en la unidad organizativa del sistema de salas de Skype: 
    
  - Tiempo de espera de sesiones de inicio de sesión (bloqueo automático)
    
  - Directivas relacionadas de administración de energía
    
  - Requerir pasos de autenticación adicionales
    
  - Negar el acceso a las unidades locales
    
  - Avisar a los usuarios de conexiones de red lentas
    
  - Iniciar un programa determinado en el inicio de sesión
    
  - Crear otra cuenta de usuario de dominio en todas las máquinas con unión a dominio.
    
  - Insertar Windows Update en el sistema de salas de Skype
    
- De forma alternativa, puede decidir dejar el equipo PC de aplicación en el grupo de trabajo. Al igual que con el cliente de escritorio de Skype empresarial, debe importar manualmente la cadena de certificados raíz en el equipo del sistema de salas de Skype. No es necesario importar la cadena de certificados raíz si su implementación de Skype empresarial usa un certificado público (por ejemplo, Entrust, VeriSign, etc.). 
    
Si planeas unir las máquinas del sistema de salas de Skype con el dominio, para evitar que se unan al equipo del sistema de salas de Skype accidentalmente a una OU no deseada, que puede no estar exenta de GPO, asegúrate de unirte a la unidad organizativa correcta. Puede usar el siguiente cmdlet de la máquina del sistema de salas de Skype para unirse a la OU correcta y no recibe GPO que puedan bloquear la funcionalidad de LRS. Póngase en contacto con su administrador de sistema o socio OEM para ejecutar estos cmdlets:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Aunque cree un OU independiente y bloqueo de herencia, existen algunas directivas que podrían ocasionar problemas en un nivel superior. Una directiva de grupo con una configuración de no invalidación supera a un OU con una configuración de herencia de directiva de bloqueo. Para obtener más información, vea el artículo [no reemplazar en comparación con bloquear la herencia de directivas](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) en la documentación de directiva de grupo.
  
Puede tener varios enfoques para solucionar estos problemas. Le aconsejamos que consulte con los expertos de Active Directory para asegurarse de que obtiene un OU que tiene una configuración de GPO adecuada, o al menos un OU en el que las directivas descritas anteriormente no existan. Se recomienda habilitar la calidad de servicio (QoS) para los dispositivos de sistema de la sala de Skype.

## <a name="see-also"></a>Vea también
  
[Configuración de dispositivo: Crear nueva o editar existente](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Administración de la Calidad de servicio (QoS)](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
