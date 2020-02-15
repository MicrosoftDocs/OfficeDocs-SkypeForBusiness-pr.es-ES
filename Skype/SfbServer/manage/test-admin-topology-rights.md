---
title: Prueba de los derechos de topología de administración en Skype empresarial Server
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
ms.openlocfilehash: de2f5752bdcd9096a47595fd7ffd10a3ab799d9c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030153"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Prueba de los derechos de topología de administración en Skype empresarial Server

| | |
|--|--|
|Programación de comprobación|Después de la implementación inicial de Skype empresarial Server. Si es necesario, si surgen problemas relacionados con los permisos.|
|Herramienta de prueba|Windows PowerShell|
|Permisos necesarios|Cuando se ejecuta de forma local mediante el shell de administración de Skype empresarial Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.<br/><br/>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsSetupPermission. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlets-Match "test-CsSetupPermission"}|
|||

## <a name="description"></a>Descripción

De forma predeterminada, solo los administradores de dominio pueden habilitar una topología de Skype empresarial Server y realizar cambios importantes en la infraestructura de Skype empresarial Server. Esto no será un problema siempre que los administradores de dominio y los administradores de Skype empresarial Server sean uno y el mismo. En muchas organizaciones, los administradores de Skype empresarial Server no mantienen derechos administrativos en todo el dominio. De forma predeterminada, esto significa que estos administradores (definidos como miembros del grupo RTCUniversalServerAdmins) no pueden realizar cambios en la topología de Skype empresarial Server. Para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de realizar cambios en la topología, debe asignar los permisos necesarios de Active Directory mediante el cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .
 
El cmdlet test-CsSetupPermission comprueba que los permisos necesarios para instalar Skype empresarial Server o uno de sus componentes estén configurados en el contenedor de Active Directory especificado. Si no se asignan los permisos, puede ejecutar el cmdlet Grant-CsSetupPermission para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de instalar y habilitar Skype empresarial Server.

## <a name="running-the-test"></a>Ejecutar la prueba

Para determinar si se asignan permisos de configuración para un contenedor de Active Directory, llame al cmdlet test-CsSetupPermission. Especifique el nombre distintivo del contenedor que se va a comprobar. Por ejemplo, este comando comprueba los permisos de configuración en el contenedor ou = CsServers, DC = litwareinc, DC = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si test-CsSetupPermission determina que ya se han establecido los permisos necesarios en un contenedor de Active Directory, el cmdlet devolverá el valor true:

True 

Si no se establecen los permisos, test-CsSetupPermission devolverá el valor false. Tenga en cuenta que este valor normalmente se incluirá en muchos mensajes de advertencia. Por ejemplo:

ADVERTENCIA: entrada de control de acceso (ACE) atl-cs-001\RTCUniversalServerAdmins; Permita ExtendedRight; None None 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

ADVERTENCIA: las entradas de control de acceso (ACE) del objeto "CN = Computers, DC = litwareinc, DC = com" no están preparadas. 

False 

ADVERTENCIA: el procesamiento de "test-CsSetupPermission" se completó con advertencias. se han registrado advertencias de "2" durante esta ejecución. 

ADVERTENCIA: los resultados detallados se pueden encontrar en "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Aunque existen raras excepciones, si test-CsSetupPermission produce un error que suele significar que no se asignan permisos de configuración para el contenedor de Active Directory especificado. Estos permisos se pueden asignar mediante el cmdlet Grant-CsSetupPermission. Por ejemplo, este comando concede permisos de configuración al contenedor Computers del dominio litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .
