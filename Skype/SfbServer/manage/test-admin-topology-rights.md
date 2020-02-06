---
title: Probar los derechos de topología de administración en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cómo probar los derechos de topología en Skype empresarial Server
ms.openlocfilehash: 1664a7e7d2b202b596a882e4b393cc15220806c9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817316"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Probar los derechos de topología de administración en Skype empresarial Server

| | |
|--|--|
|Programación de verificación|Después de la implementación inicial de Skype empresarial Server. Según sea necesario, si surgen problemas relacionados con los permisos.|
|Herramienta de prueba|Windows PowerShell|
|Permisos necesarios|Al ejecutarse de forma local con el shell de administración de Skype empresarial Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.<br/><br/>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsSetupPermission. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:<br/><br/>Get-CsAdminRole \| -Object {$ _. Cmdlets: Match "test-CsSetupPermission"}|
|||

## <a name="description"></a>Descripción

De forma predeterminada, solo los administradores de dominio pueden habilitar una topología de servidor de Skype empresarial y realizar cambios importantes en la infraestructura de Skype empresarial Server. Esto no suponer un problema, siempre que los administradores de dominio y los administradores de Skype empresarial Server sean uno y el mismo. En muchas organizaciones, los administradores de Skype empresarial Server no mantienen derechos administrativos en todo el dominio. De forma predeterminada, esto significa que estos administradores (definidos como miembros del grupo RTCUniversalServerAdmins) no pueden hacer cambios en la topología de Skype empresarial Server. Para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de realizar cambios de topología, debe asignar los permisos necesarios de Active Directory mediante el cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) .
 
El cmdlet test-CsSetupPermission verifica que los permisos necesarios necesarios para instalar Skype empresarial Server o uno de sus componentes estén configurados en el contenedor de Active Directory especificado. Si no se asignan los permisos, puede ejecutar el cmdlet Grant-CsSetupPermission para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de instalar y habilitar Skype empresarial Server.

## <a name="running-the-test"></a>Ejecutar la prueba

Para determinar si los permisos de configuración se asignan a un contenedor de Active Directory, llame al cmdlet test-CsSetupPermission. Especifique el nombre distintivo del contenedor que se va a comprobar. Por ejemplo, este comando comprueba los permisos de configuración en el contenedor ou = CsServers, DC = litwareinc, DC = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Para obtener más información, vea el tema de ayuda para el cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si prueba-CsSetupPermission determina que los permisos necesarios ya se han establecido en un contenedor de Active Directory, el cmdlet devolverá el valor true:

Verdadero 

Si no se establecen permisos, test-CsSetupPermission devolverá el valor false. Ten en cuenta que este valor normalmente se incluirá en muchos mensajes de advertencia. Por ejemplo:

ADVERTENCIA: entrada de control de acceso (ACE) atl-cs-001\RTCUniversalServerAdmins; Permitir ExtendedRight; Nada Nada 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

ADVERTENCIA: las entradas de control de acceso (ACE) del objeto "CN = Computers, DC = litwareinc, DC = com" no están listas. 

Falso 

ADVERTENCIA: el procesamiento de "prueba-CsSetupPermission" se completó con advertencias. durante esta ejecución, se grabaron "2" advertencias. 

ADVERTENCIA: puede encontrar resultados detallados en "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Aunque hay raras excepciones, si test-CsSetupPermission da error, normalmente significa que los permisos de configuración no se asignan al contenedor de Active Directory especificado. Esos permisos se pueden asignar mediante el cmdlet Grant-CsSetupPermission. Por ejemplo, este comando concede permisos de configuración al contenedor Computers del dominio litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Para obtener más información, vea el tema de ayuda para el cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .
