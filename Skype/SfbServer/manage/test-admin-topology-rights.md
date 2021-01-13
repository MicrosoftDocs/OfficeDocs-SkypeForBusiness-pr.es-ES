---
title: Probar los derechos de topología de administración en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cómo probar los derechos de topología en Skype Empresarial Server
ms.openlocfilehash: a6bbebd44387911fdb69679a16ab052c673f0b10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832850"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Probar los derechos de topología de administración en Skype Empresarial Server

| | |
|--|--|
|Programación de comprobación|Después de la implementación inicial de Skype Empresarial Server. Según sea necesario si surgen problemas relacionados con permisos.|
|Herramienta de pruebas|Windows PowerShell|
|Permisos necesarios|Cuando se ejecuta localmente con el Shell de administración de Skype Empresarial Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.<br/><br/>Cuando se ejecuta mediante una instancia remota de Windows PowerShell, se debe asignar a los usuarios un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsSetupPermission remoto. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el Windows PowerShell siguiente:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Descripción

De forma predeterminada, solo los administradores de dominio pueden habilitar una topología de Skype Empresarial Server y realizar cambios grandes en la infraestructura de Skype Empresarial Server. This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same. En muchas organizaciones, los administradores de Skype Empresarial Server no tienen derechos administrativos en todo el dominio. De forma predeterminada, esto significa que estos administradores (definidos como miembros del grupo RTCUniversalServerAdmins) no pueden realizar cambios en la topología de Skype Empresarial Server. Para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de realizar cambios en la topología, debe asignar los permisos de Active Directory necesarios mediante el cmdlet [Grant-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)
 
El cmdlet Test-CsSetupPermission comprueba que los permisos necesarios para instalar Skype Empresarial Server o uno de sus componentes están configurados en el contenedor de Active Directory especificado. Si los permisos no están asignados, puede ejecutar el cmdlet Grant-CsSetupPermission para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de instalar y habilitar Skype Empresarial Server.

## <a name="running-the-test"></a>Ejecución de la prueba

Para determinar si se asignan permisos de instalación para un contenedor de Active Directory, llame al cmdlet Test-CsSetupPermission configuración. Especifique el nombre distintivo del contenedor que se va a comprobar. Por ejemplo, este comando comprueba los permisos de instalación en el contenedor ou=CsServers,dc=litwareinc,dc=com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)

## <a name="determining-success-or-failure"></a>Determinar el éxito o el error

Si Test-CsSetupPermission determina que los permisos necesarios ya se han establecido en un contenedor de Active Directory, el cmdlet devolverá el valor True:

Verdadero 

Si no se establecen los permisos, Test-CsSetupPermission devolverá el valor False. Tenga en cuenta que este valor normalmente se incluye en muchos mensajes de advertencia. Por ejemplo:

ADVERTENCIA: Entrada de control de acceso (ACE) atl-cs-001\RTCUniversalServerAdmins; Permitir; ExtendedRight; Ninguno; Ninguno; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

ADVERTENCIA: Las entradas de control de acceso (ACE) en el objeto "CN=Computers,DC=litwareinc,DC=com" no están listas. 

False 

ADVERTENCIA: el procesamiento de "Test-CsSetupPermission" se ha completado con advertencias. Durante esta ejecución se registraron advertencias de "2". 

ADVERTENCIA: Encontrará resultados detallados en "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se pudo haber fallado la prueba

Aunque hay excepciones raras, si Test-CsSetupPermission error, normalmente significa que no se asignan permisos de configuración para el contenedor de Active Directory especificado. Estos permisos se pueden asignar mediante el cmdlet Grant-CsSetupPermission usuario. Por ejemplo, este comando concede permisos de configuración al contenedor Equipos del dominio litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)
