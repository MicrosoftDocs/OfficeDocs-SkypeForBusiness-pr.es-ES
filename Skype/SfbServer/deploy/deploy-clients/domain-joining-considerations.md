---
title: Consideraciones de unión a dominio del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Lea este tema para obtener información sobre cómo unirse a un equipo PC de la aplicación de Sistema de salas de Skype para su dominio.
ms.openlocfilehash: 93aa983080ee93f38143224b6c74bdcd6490842c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-domain-joining-considerations"></a>Consideraciones de unión a dominio del Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo unirse a un equipo PC de la aplicación de Sistema de salas de Skype para su dominio.
  
## <a name="domain-joining-considerations"></a>Consideraciones de unión a dominio

Puede unir el dispositivo de sistema de sala de Skype PC al dominio de Active Directory o dejarlo en un grupo de trabajo. Considere los siguientes puntos antes de realizar esta decisión:
  
- El dispositivo de sistema de sala de Skype PC la unión de dominio ayuda a importar la cadena de certificados de raíz privada de la organización automáticamente.
    
- El dispositivo de sistema de sala de Skype PC la unión de dominio le permite conceder derechos administrativos de grupos y de usuarios de dominio. Al hacer esto, no tendrá que acordarse de la contraseña de la cuenta de administrador de nivel de máquina local.
    
- Cuando se une a un dispositivo de sistema de sala de Skype PC al dominio, es necesario crear un independiente unidad organizativa (OU), por lo que puede proporcionar exclusiones de objeto de directiva de grupo (GPO) a la unidad organizativa donde residen los objetos de equipo de sistema del sitio de Skype. Al hacerlo, crear objetos de equipo en la unidad organizativa antes de unir el dispositivo de sistema de sala de Skype PC al dominio.
    
- Muchas organizaciones tienen los siguientes GPO, que afectan a las funciones del dispositivo PC de sistema de sala de Skype. Asegúrese de reemplazar o bloquear la herencia de los GPO en la OU de sistema de sala de Skype: 
    
  - Tiempo de espera de sesiones de inicio de sesión (bloqueo automático)
    
  - Directivas relacionadas de administración de energía
    
  - Requerir pasos de autenticación adicionales
    
  - Negar el acceso a las unidades locales
    
  - Avisar a los usuarios de conexiones de red lentas
    
  - Iniciar un programa determinado en el inicio de sesión
    
  - Crear otra cuenta de usuario de dominio en todas las máquinas con unión a dominio.
    
  - Insertar la actualización de Windows al sistema de sala de Skype
    
- De forma alternativa, puede decidir dejar el equipo PC de aplicación en el grupo de trabajo. Como con el escritorio Skype para cliente de empresa, esto requiere importar manualmente la cadena de certificados de raíz en el dispositivo de sistema de sala de Skype PC. No es necesario importar la cadena de certificados de raíz si tu Skype para la implementación de la empresa está utilizando un certificado público (por ejemplo, Entrust, VeriSign etc.). 
    
Si va a unir equipos con un sistema de sala de Skype al dominio, para evitar unirse a sistema de sala de Skype máquina inadvertidamente a una unidad organizativa no deseada, que puede no estar libre de los GPO, asegúrese se une a la unidad organizativa correcta. Puede usar el cmdlet siguiente desde el equipo de sistema del sitio de Skype se unen en la unidad organizativa correcta y no recibe los GPO que puedan bloquear la funcionalidad LRS. Póngase en contacto con su administrador de sistema o socio OEM para ejecutar estos cmdlets:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"

```

Aunque cree un OU independiente y bloqueo de herencia, existen algunas directivas que podrían ocasionar problemas en un nivel superior. Una directiva de grupo con una configuración de no invalidación supera a un OU con una configuración de herencia de directiva de bloqueo. Para obtener más información, consulte el artículo "No reemplazar en comparación en bloquear la herencia de directivas" en la documentación de directiva de grupo en http://technet.microsoft.com/en-us/library/cc978255.aspx.
  
Puede tener varios enfoques para solucionar estos problemas. Le aconsejamos que consulte con los expertos de Active Directory para asegurarse de que obtiene un OU que tiene una configuración de GPO adecuada, o al menos un OU en el que las directivas descritas anteriormente no existan. Es recomendable habilitar calidad de servicio (QoS) para el sistema del sitio de Skype.
  

