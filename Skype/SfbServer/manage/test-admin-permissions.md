---
title: Comprobación de permisos de administrador en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cómo probar los permisos de administrador en Skype para Business Server
ms.openlocfilehash: f769870991cfd5578fc8bd809d26c0aea912d03a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898293"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Comprobación de permisos de administrador en Skype para Business Server

| | |
|--|--|
|Programación de comprobación|Después de Skype inicial para la implementación de Business Server. Según sea necesario si surgen problemas relacionados con el permiso.|
|Herramienta de prueba|Windows PowerShell|
|Permisos necesarios|Cuando se ejecuta localmente mediante la Skype para Shell de administración de servidor empresarial, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.<br><br/>Cuando se ejecuta con una instancia remota de Windows PowerShell, los usuarios deben asignarse un rol RBAC que tiene permiso para ejecutar el cmdlet Test-CsOUPermission. Para ver una lista de todas las funciones RBAC que puede usar este cmdlet, ejecute el comando siguiente desde el símbolo del sistema de Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$_. Cmdlets de-match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Descripción

Al instalar Skype para Business Server, una de las tareas que se llevó a cabo mediante el programa de instalación concede al grupo RTCUniversalUserAdmins los permisos de Active Directory que son necesarios para administrar los usuarios, equipos, contactos, contactos de la aplicación y InetOrg personas. Si ha deshabilitado la herencia de permisos en Active Directory, el programa de instalación no podrá asignar esos permisos. Como resultado, los miembros del grupo RTCUniversalUserAdmins no puedan administrar Skype para las entidades de Business Server. Los privilegios de administración sólo estarán disponibles para los administradores de dominio. 

El cmdlet Test-CsOUPermission comprueba que se establecen los permisos necesarios para administrar usuarios, equipos y otros objetos en un contenedor de Active Directory. Si no se establecen los permisos de dichos, puede resolver este problema ejecutando el [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission). 

Tenga en cuenta que Grant-CsOUPermission sólo puede asignar permisos a los miembros del grupo RTCUniversalUserAdmins. No puede usar este cmdlet para conceder permisos a un usuario o grupo arbitrario. Si desea que un usuario o grupo diferente para tener permisos de administración de usuario, debe agregar ese usuario (o grupo) al grupo RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Ejecuta la prueba

Para comprobar que se establecen los permisos de administración en un contenedor, ejecute el cmdlet Test-CsOUPermission seguido por el nombre distintivo (DN) del contenedor y por el tipo de permisos que desea comprobar. Por ejemplo, este comando comprueba si los permisos de usuario se establecen en la unidad organizativa OU = Redmond, dc = litwareinc, dc = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Para comprobar varios permisos mediante el uso de un solo comando, escríbalo entre cada tipo de permiso entre comillas, a continuación, separe esos tipos con comas. Por ejemplo, comprueba este comando de un usuario, equipo y contacto permisos:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Para obtener más información, vea el [tema de ayuda para el cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si ya se han establecido los permisos necesarios, Test-CsOUPermission devolverá una respuesta de una palabra:

True

Si no se establecen los permisos necesarios, Test-CsOUPermission devolverá el valor False. Debe buscar un momento buscar este valor. Normalmente se incrustarán dentro de varias advertencias que lo acompaña. Por ejemplo:

Advertencia: control de acceso (ACE) de entrada atl-cs-001\RTCUniversalUserReadOnlyGroup; Permitir; ReadProperty; ContainerInherit; Descendientes; bf967aba-0de6 - 11d 0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

Advertencia: La entradas control de acceso (ACE) en el objeto "OU = Norteamérica, DC = atl-cs-001\DC = litwareinc, DC = com" no está listo. 

False 

Advertencia: Procesamiento de "Test-CsOUPermission" ha finalizado con advertencias. las advertencias de "2" se registraron durante esta ejecución. 

Advertencia: Resultados detallados pueden encontrarse en "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>¿Por qué podría haber fallado la prueba de motivos

Si se produce un error en Test-CsOUPermission, normalmente significa que no se ha asignado el permiso especificado para el grupo de RTCUniversalUserAdmins. Puede resolver este problema y asignar los permisos necesarios, mediante el cmdlet Grant-CsOUPermission. Por ejemplo, este comando proporciona permisos de unidades Organizativas para los usuarios, contactos y objetos InetOrgPerson para el grupo de RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Para obtener más información, vea el [tema de ayuda para el cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).
