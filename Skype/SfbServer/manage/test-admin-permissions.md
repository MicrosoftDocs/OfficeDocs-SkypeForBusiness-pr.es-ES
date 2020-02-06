---
title: Probar permisos de administrador en Skype empresarial Server
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
ms.openlocfilehash: 97db574803b575d484240e7339d56603ae5432da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817191"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Probar permisos de administrador en Skype empresarial Server

| | |
|--|--|
|Programación de verificación|Después de la implementación inicial de Skype empresarial Server. Según sea necesario, si surgen problemas relacionados con los permisos.|
|Herramienta de prueba|Windows PowerShell|
|Permisos necesarios|Al ejecutarse de forma local con el shell de administración de Skype empresarial Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.<br><br/>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsOUPermission. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:<br/><br/>Get-CsAdminRole \| -Object {$ _. Cmdlets: Match "test-CsOUPermission"}|
|||

## <a name="description"></a>Descripción

Al instalar Skype empresarial Server, una de las tareas que realizó el programa de instalación proporciona al grupo RTCUniversalUserAdmins los permisos de Active Directory necesarios para administrar usuarios, equipos, contactos, contactos de la aplicación y InetOrg pasajeros. Si ha deshabilitado la herencia de permisos en Active Directory, el programa de instalación no podrá asignar esos permisos. Como resultado, los miembros del grupo RTCUniversalUserAdmins no podrán administrar entidades de Skype empresarial Server. Esos privilegios de administración solo estarán disponibles para los administradores de dominio. 

El cmdlet test-CsOUPermission comprueba que los permisos necesarios para administrar usuarios, equipos y otros objetos se establecen en un contenedor de Active Directory. Si no se han establecido esos permisos, puede resolver este problema ejecutando el [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission). 

Tenga en cuenta que Grant-CsOUPermission solo puede asignar permisos a miembros del grupo RTCUniversalUserAdmins. No puede usar este cmdlet para conceder permisos a un usuario o grupo arbitrario. Si desea que un usuario o grupo diferente tenga permisos de administración de usuarios, debe agregar ese usuario (o grupo) al grupo RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Ejecutar la prueba

Para comprobar que los permisos de administración se establecen en un contenedor, ejecute el cmdlet test-CsOUPermission seguido del nombre distintivo del contenedor y del tipo de permisos que está comprobando. Por ejemplo, este comando comprueba si los permisos de usuario están establecidos en la ou ou = Redmond, DC = litwareinc, DC = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Para comprobar varios permisos con un solo comando, encierra cada tipo de permiso entre comillas y luego separa esos tipos con comas. Por ejemplo, este comando comprueba los permisos de usuario, equipo y contacto:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Para obtener más información, vea el [tema de ayuda para el cmdlet test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si los permisos necesarios ya se han establecido, test-CsOUPermission devolverá una respuesta de una palabra:

Verdadero

Si no se establecen los permisos necesarios, test-CsOUPermission devolverá el valor false. Es posible que tenga que buscar un momento para encontrar este valor. Normalmente, se incluirá en varias advertencias de acompañamiento. Por ejemplo:

ADVERTENCIA: entrada de control de acceso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; permitir ReadProperty; ContainerInherit; Descendientes; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

ADVERTENCIA: las entradas de control de acceso (ACE) del objeto "OU = Norteamérica, DC = atl-cs-001\DC = litwareinc, DC = com" no están listas. 

Falso 

ADVERTENCIA: el procesamiento de "prueba-CsOUPermission" se completó con advertencias. durante esta ejecución, se grabaron "2" advertencias. 

ADVERTENCIA: puede encontrar resultados detallados en "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Si prueba-CsOUPermission falla, normalmente significa que el permiso especificado no se ha asignado al grupo RTCUniversalUserAdmins. Puede resolver este problema y asignar los permisos necesarios mediante el cmdlet Grant-CsOUPermission. Por ejemplo, este comando proporciona a los usuarios, los contactos y el inetOrgPersons permisos para el grupo RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Para obtener más información, vea el [tema de ayuda para el cmdlet test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).
