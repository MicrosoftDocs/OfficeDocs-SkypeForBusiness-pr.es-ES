---
title: Probar los derechos de topología de administración en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Cómo probar los derechos de topología en Skype Empresarial Server
ms.openlocfilehash: 6f4eed0271d9dd6d099d19287f7caa37148f6026
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861317"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Probar los derechos de topología de administración en Skype Empresarial Server

|&nbsp; |&nbsp; |
|--|--|
|Programación de comprobación|Después de la Skype Empresarial Server implementación inicial. Según sea necesario si surgen problemas relacionados con permisos.|
|Herramienta de prueba|Windows PowerShell|
|Permisos necesarios|Cuando se ejecuta localmente mediante Skype Empresarial Server Shell de administración, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.<br/><br/>Cuando se ejecuta mediante una instancia remota de Windows PowerShell, se debe asignar a los usuarios un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsSetupPermission usuario. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el Windows PowerShell solicitud:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Descripción

De forma predeterminada, solo los administradores de dominio pueden habilitar una topología Skype Empresarial Server y realizar grandes cambios en la infraestructura Skype Empresarial Server dominio. Esto no será un problema mientras los administradores de dominio y los administradores de Skype Empresarial Server sean uno y los mismos. En muchas organizaciones, Skype Empresarial Server administradores no tienen derechos administrativos en todo el dominio. De forma predeterminada, esto significa que estos administradores (definidos como miembros del grupo RTCUniversalServerAdmins) no pueden realizar cambios Skype Empresarial Server topología. Para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de realizar cambios en la topología, debe asignar los permisos de Active Directory necesarios mediante el cmdlet [Grant-CsSetupPermission.](/powershell/module/skype/Grant-CsSetupPermission)
 
El cmdlet Test-CsSetupPermission comprueba que los permisos necesarios para instalar Skype Empresarial Server o uno de sus componentes estén configurados en el contenedor de Active Directory especificado. Si no se asignan los permisos, puede ejecutar el cmdlet Grant-CsSetupPermission para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de instalar y habilitar Skype Empresarial Server.

## <a name="running-the-test"></a>Ejecución de la prueba

Para determinar si se asignan permisos de instalación para un contenedor de Active Directory, llame al cmdlet Test-CsSetupPermission configuración. Especifique el nombre distintivo del contenedor que se va a comprobar. Por ejemplo, este comando comprueba los permisos de instalación en el contenedor ou=CsServers,dc=litwareinc,dc=com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Para obtener más información, vea el tema de ayuda del cmdlet [Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)

## <a name="determining-success-or-failure"></a>Determinación del éxito o error

Si Test-CsSetupPermission determina que los permisos necesarios ya se han establecido en un contenedor de Active Directory, el cmdlet devolverá el valor True:

Verdadero 

Si no se establecen permisos, Test-CsSetupPermission devolverá el valor False. Tenga en cuenta que este valor normalmente se incluye en muchos mensajes de advertencia. Por ejemplo:

ADVERTENCIA: Entrada de control de acceso (ACE) atl-cs-001\RTCUniversalServerAdmins; Permitir; ExtendedRight; Ninguno; Ninguno; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

ADVERTENCIA: Las entradas de control de acceso (ACE) del objeto "CN=Computers,DC=litwareinc,DC=com" no están listas. 

Falso 

ADVERTENCIA: el procesamiento de "Test-CsSetupPermission" se ha completado con advertencias. Durante esta ejecución se registraron advertencias "2". 

ADVERTENCIA: Los resultados detallados se pueden encontrar en "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que la prueba pudo haber fallado

Aunque hay excepciones raras, si Test-CsSetupPermission error, normalmente significa que los permisos de instalación no están asignados para el contenedor de Active Directory especificado. Estos permisos se pueden asignar mediante el cmdlet Grant-CsSetupPermission. Por ejemplo, este comando concede permisos de instalación al contenedor Equipos del dominio litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Para obtener más información, vea el tema de ayuda del cmdlet [Test-CsSetupPermission.](/powershell/module/skype/Test-CsSetupPermission)