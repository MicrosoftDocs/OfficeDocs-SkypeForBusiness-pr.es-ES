---
title: Probar permisos de administrador en Skype Empresarial Server
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
description: Cómo probar los permisos de administrador en Skype Empresarial Server
ms.openlocfilehash: 7dd9e1b95df35cb363617690cb9667c1a16ef904
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "58232625"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Probar permisos de administrador en Skype Empresarial Server

|&nbsp; |&nbsp; |
|--|--|
|Programación de comprobación|Después de la Skype Empresarial Server implementación inicial. Según sea necesario si surgen problemas relacionados con permisos.|
|Herramienta de prueba|Windows PowerShell|
|Permisos necesarios|Cuando se ejecuta localmente mediante Skype Empresarial Server Shell de administración, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.<br><br/>Cuando se ejecuta mediante una instancia remota de Windows PowerShell, se debe asignar a los usuarios un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsOUPermission usuario. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el Windows PowerShell solicitud:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Description

Al instalar Skype Empresarial Server, una de las tareas realizadas por el programa de instalación proporciona al grupo RTCUniversalUserAdmins los permisos de Active Directory necesarios para administrar usuarios, equipos, contactos, contactos de aplicaciones y personas de InetOrg. Si ha deshabilitado la herencia de permisos en Active Directory, el programa de instalación no podrá asignar esos permisos. Como resultado, los miembros del grupo RTCUniversalUserAdmins no podrán administrar Skype Empresarial Server entidades. Estos privilegios de administración solo estarán disponibles para los administradores de dominio. 

El cmdlet Test-CsOUPermission comprueba que los permisos necesarios para administrar usuarios, equipos y otros objetos se establecen en un contenedor de Active Directory. Si estos permisos no están establecidos, puede resolver este problema ejecutando el [cmdlet Grant-CsOUPermission](/powershell/module/skype/Grant-CsOUPermission). 

Tenga en cuenta Grant-CsOUPermission solo puede asignar permisos a los miembros del grupo RTCUniversalUserAdmins. No puede usar este cmdlet para conceder permisos a un usuario o grupo arbitrario. Si desea que otro usuario o grupo tenga permisos de administración de usuarios, debe agregar ese usuario (o grupo) al grupo RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Ejecución de la prueba

Para comprobar que los permisos de administración están establecidos en un contenedor, ejecute el cmdlet Test-CsOUPermission seguido del nombre distintivo del contenedor y del tipo de permisos que está comprobando. Por ejemplo, este comando comprueba si los permisos de usuario están establecidos en la OU ou=Redmond,dc=litwareinc,dc=com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Para comprobar varios permisos mediante un solo comando, escriba cada tipo de permiso entre comillas y, a continuación, separe esos tipos mediante comas. Por ejemplo, este comando comprueba los permisos de usuario, equipo y contacto:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Para obtener más información, vea el tema [de ayuda del cmdlet Test-CsOUPermission .](/powershell/module/skype/test-csoupermission)

## <a name="determining-success-or-failure"></a>Determinación del éxito o error

Si ya se han establecido los permisos necesarios, Test-CsOUPermission devolverá una respuesta de una palabra:

Verdadero

Si no se establecen los permisos necesarios, Test-CsOUPermission devolverá el valor False. Es posible que deba buscar un momento para encontrar este valor. Por lo general, se incrustará dentro de varias advertencias que lo acompañan. Por ejemplo:

ADVERTENCIA: entrada de control de acceso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendientes; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

ADVERTENCIA: Las entradas de control de acceso (ACE) del objeto "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" no están listas. 

Falso 

ADVERTENCIA: el procesamiento de "Test-CsOUPermission" se ha completado con advertencias. Durante esta ejecución se registraron advertencias "2". 

ADVERTENCIA: los resultados detallados se pueden encontrar en "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que la prueba pudo haber fallado

Si Test-CsOUPermission error, normalmente significa que el permiso especificado no se ha asignado al grupo RTCUniversalUserAdmins. Puede resolver este problema y asignar los permisos necesarios mediante el cmdlet Grant-CsOUPermission. Por ejemplo, este comando proporciona permisos ou para usuarios, contactos e inetOrgPersons al grupo RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Para obtener más información, vea el tema [de ayuda del cmdlet Test-CsOUPermission .](/powershell/module/skype/test-csoupermission)