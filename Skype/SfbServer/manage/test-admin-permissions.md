---
title: Probar los permisos de administrador en Skype empresarial Server
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
description: Cómo probar los permisos de administrador en Skype empresarial Server
ms.openlocfilehash: 1e06c87dcf0e436d72c510a2bc8d9f2aa2051620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030163"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Probar los permisos de administrador en Skype empresarial Server

| | |
|--|--|
|Programación de comprobación|Después de la implementación inicial de Skype empresarial Server. Si es necesario, si surgen problemas relacionados con los permisos.|
|Herramienta de prueba|Windows PowerShell|
|Permisos necesarios|Cuando se ejecuta de forma local mediante el shell de administración de Skype empresarial Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.<br><br/>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsOUPermission. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlets-Match "test-CsOUPermission"}|
|||

## <a name="description"></a>Descripción

Al instalar Skype empresarial Server, una de las tareas realizadas por el programa de instalación proporciona al grupo RTCUniversalUserAdmins los permisos de Active Directory que se necesitan para administrar usuarios, equipos, contactos, contactos de aplicaciones y InetOrg ajena. Si ha deshabilitado la herencia de permisos en Active Directory, el programa de instalación no podrá asignar esos permisos. Como resultado, los miembros del grupo RTCUniversalUserAdmins no podrán administrar las entidades de Skype empresarial Server. Estos privilegios de administración solo estarán disponibles para los administradores de dominio. 

El cmdlet test-CsOUPermission comprueba que los permisos necesarios para administrar usuarios, equipos y otros objetos se establecen en un contenedor de Active Directory. Si estos permisos no están establecidos, puede resolver este problema mediante la ejecución del [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission). 

Tenga en cuenta que Grant-CsOUPermission solo puede asignar permisos a miembros del grupo RTCUniversalUserAdmins. No puede usar este cmdlet para conceder permisos a un usuario o grupo arbitrario. Si desea que un usuario o grupo diferente tenga permisos de administración de usuarios, debe agregar el usuario (o grupo) al grupo RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Ejecutar la prueba

Para comprobar que los permisos de administración están establecidos en un contenedor, ejecute el cmdlet test-CsOUPermission seguido por el nombre distintivo del contenedor y por el tipo de permisos que está comprobando. Por ejemplo, este comando comprueba si los permisos de usuario están establecidos en ou ou = Redmond, DC = litwareinc, DC = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Para comprobar varios permisos mediante un solo comando, encierre cada tipo de permiso entre comillas y, a continuación, separe los tipos con comas. Por ejemplo, este único comando comprueba los permisos de usuario, equipo y contacto:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Para obtener más información, consulte el [tema de ayuda del cmdlet test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si ya se han establecido los permisos necesarios, test-CsOUPermission devolverá una respuesta de una palabra:

True

Si no se establecen los permisos necesarios, test-CsOUPermission devolverá el valor false. Es posible que deba buscar un momento para encontrar este valor. Por lo general, se incrustará en varias advertencias que lo acompañan. Por ejemplo:

ADVERTENCIA: entrada de control de acceso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; permita ReadProperty ContainerInherit; Descendientes bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

ADVERTENCIA: las entradas de control de acceso (ACE) del objeto "OU = Norteamérica, DC = atl-cs-001\DC = litwareinc, DC = com" no están preparadas. 

False 

ADVERTENCIA: el procesamiento de "test-CsOUPermission" se completó con advertencias. se han registrado advertencias de "2" durante esta ejecución. 

ADVERTENCIA: los resultados detallados se pueden encontrar en "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Si test-CsOUPermission produce un error, suele significar que no se ha asignado el permiso especificado al grupo RTCUniversalUserAdmins. Puede resolver este problema y asignar los permisos necesarios mediante el cmdlet Grant-CsOUPermission. Por ejemplo, este comando proporciona permisos de unidad organizativa para usuarios, contactos y inetOrgPersons al grupo RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Para obtener más información, consulte el [tema de ayuda del cmdlet test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).
