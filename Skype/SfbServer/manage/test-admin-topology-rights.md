---
title: Prueba de derechos administrativos de la topología de Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cómo probar los derechos de topología en Skype para Business Server
ms.openlocfilehash: 239c35eba451166f4e9fb5755535cf15999cdaea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910371"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Prueba de derechos administrativos de la topología de Skype para Business Server

| | |
|--|--|
|Programación de comprobación|Después de Skype inicial para la implementación de Business Server. Según sea necesario si surgen problemas relacionados con el permiso.|
|Herramienta de prueba|Windows PowerShell|
|Permisos necesarios|Cuando se ejecuta localmente mediante la Skype para Shell de administración de servidor empresarial, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.<br/><br/>Cuando se ejecuta con una instancia remota de Windows PowerShell, los usuarios deben asignarse un rol RBAC que tiene permiso para ejecutar el cmdlet Test-CsSetupPermission. Para ver una lista de todas las funciones RBAC que puede usar este cmdlet, ejecute el comando siguiente desde el símbolo del sistema de Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$_. Cmdlets de-match "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Descripción

De forma predeterminada, solo los administradores de dominio pueden habilitar un Skype de topología de servidores de negocio y realizar grandes cambios en el Skype para infraestructura de Business Server. Esto no será un problema siempre y cuando los administradores de dominio y su Skype para los administradores de Business Server son el mismo. En muchas organizaciones, Skype para los administradores de Business Server no mantiene presionado derechos administrativos a todo el dominio. De forma predeterminada, que significa que estos administradores (definidos como miembros del grupo RTCUniversalServerAdmins) no pueden realizar Skype para que los cambios de topología de servidor empresarial. Para proporcionar a los integrantes del grupo RTCUniversalServerAdmins el derecho a realizar cambios en la topología, debe asignar los permisos necesarios de Active Directory mediante el cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) .
 
El cmdlet Test-CsSetupPermission comprueba que están configurados los permisos necesarios que son necesarios para instalar Skype para Business Server o uno de sus componentes en el contenedor de Active Directory especificado. Si no se asignan los permisos, a continuación, puede ejecutar el cmdlet Grant-CsSetupPermission para proporcionar a los integrantes del grupo RTCUniversalServerAdmins el derecho a instalar y habilitar Skype para Business Server.

## <a name="running-the-test"></a>Ejecuta la prueba

Para determinar si se asignan permisos de instalación para un contenedor de Active Directory, llame el cmdlet Test-CsSetupPermission. Especifique el nombre distintivo (DN) del contenedor que se va a comprobar. Por ejemplo, este comando comprueba los permisos del programa de instalación en la unidad organizativa de contenedor = CsServers, dc = litwareinc, dc = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Para obtener más información, vea el tema de ayuda para el cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si Test-CsSetupPermission determina que los permisos necesarios se han establecido en un contenedor de Active Directory, el cmdlet devolverá el valor True:

True 

Si no se establecen permisos, Test-CsSetupPermission devolverá el valor False. Tenga en cuenta que este valor normalmente se incluirá en muchos mensajes de advertencia. Por ejemplo:

Advertencia: Control de acceso (ACE) de entrada atl-cs-001\RTCUniversalServerAdmins; Permitir; ExtendedRight; Ninguno; Ninguno; 1131f6aa-9c07-11D1-f79f-00c04fc2dcd2 

Advertencia: La entradas control de acceso (ACE) en el objeto "CN = Computers, DC = litwareinc, DC = com" no está listo. 

False 

Advertencia: Procesamiento de "Test-CsSetupPermission" ha finalizado con advertencias. las advertencias de "2" se registraron durante esta ejecución. 

Advertencia: Resultados detallados pueden encontrarse en "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>¿Por qué podría haber fallado la prueba de motivos

Aunque existen algunas raras excepciones, si Test-CsSetupPermission se produce un error normalmente significa que los permisos de instalación no está asignado para el contenedor de Active Directory especificado. Estos permisos se pueden asignar mediante el cmdlet Grant-CsSetupPermission. Por ejemplo, este comando concede permisos de instalación para el contenedor de equipos en el dominio litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Para obtener más información, vea el tema de ayuda para el cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .
