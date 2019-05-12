---
title: Planeación desactivar los métodos de autenticación Legacy interna y externamente a la red
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: En este artículo los cmdlets de esquemas que ofrecen a los administradores más control de métodos de autenticación usado interior y exterior, de una empresa. Los administradores pueden activar los métodos de autenticación o desactivada interna o externamente a su red.
ms.openlocfilehash: ab50913b2a8a784193f30b124f9a212da29fa5bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929206"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planeación desactivar los métodos de autenticación Legacy interna y externamente a su red.

> [!NOTE]
> Si va a leer este artículo, ya debe conocer acerca de las topologías admitidas autenticación moderno, ADAL, y acerca de la configuración de autenticación moderno, pero, en caso de que no lo hace, aquí están los artículos que necesita para empezar: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
Autenticación moderna no habilita solamente más seguros métodos de autenticación, al igual que la autenticación de dos factores o autenticación basada en certificados, puede llevar a cabo la autorización del usuario sin necesidad de un nombre de usuario o contraseña demasiado. Es muy útil.

En este artículo le ayudará a plug huecos que han sido aprovechados para los ataques de denegación de servicio (DOS) en Skype para servidores empresariales, desactivando métodos más antiguos que se usa para la autenticación, externamente, internamente, o ambos, en su red. Por ejemplo, sería un buen método para ayudar a detener los ataques de denegación de servicio desactivar la opción autenticación integrada de Windows (que incluye NTLM y Kerberos). Desactivación de NTLM externamente y confían en la autenticación basada en certificados ayuda a proteger las contraseñas de la exposición. Esto es debido a que NTLM usa credenciales de contraseña para autenticar a los usuarios, pero no la autenticación basada en certificados--habilitada por Auth moderno--. Que significa una opción ideal para reducir los ataques de denegación de servicio es bloque NTLM externamente y utilizar sólo autenticación de certificado-based allí, en su lugar.

Todos los derechos, vamos a empezar.

## <a name="what-would-you-be-changing"></a>¿Qué tendría que ser cambiando? 

Estos cmdlets funcionan para SIP y servicios Web de puntos de acceso. Aunque estos dos canales de usan diferentes métodos de acceso, que se ejecuta la gama de NTLM y Kerberos para el acceso anónimo, todos los métodos estándares que se usan por Skype para la empresa se han tenido en cuenta.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Cómo obtener los cmdlets Get y Set CsAuthConfig

Sólo se va a instalar estos cmdlets registrar julio de 2018 actualización acumulativa (6.0.9319.534) de Microsoft Skype para Business Server 2015 y, a continuación, tienen una gran variedad de topologías que puede ser implantado para su Skype para Business server.

## <a name="topologies"></a>Topologías

Es importante tener en cuenta que éstos son las topologías compatibles implicados en este escenario! Si necesita vaya a soporte para obtener ayuda con un método de bloqueo, por ejemplo, debe tener una configuración entre los siguientes tipos. 

> [!IMPORTANT]
> En la tabla y las descripciones de más abajo, *Autenticación moderno* es una abreviatura __MA__ y *Autenticación integrada de Windows* es una abreviatura __Win__. Como recordatorio, autenticación integrada de Windows se compone de dos métodos: la autenticación NTLM y Kerberos. ¡Necesita saber para leer la tabla correctamente!


|       |Externamente  |Internamente  |Parámetro  |
|---------|:---------|:---------|---------|
|__Tipo 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tipo 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Tipo 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Tipo 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Tipo 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Escriba 1 Descripción:__ Es el valor predeterminado de __escenario cuando MA está activado para Skype para Business Server__ . En otras palabras, este es el *punto de partida* cuando se configura el agente de administración.

__Descripción del tipo 2:__ Esta topología bloquea NTLM *externamente*, pero permite NTLM o Kerberos (para los clientes que no son compatibles con ADAL) para trabajar *internamente*. Si los clientes admiten ADAL usarán MA internamente.

__Descripción del tipo 3:__ Esta topología requiere MA para todos los usuarios. Todos los clientes de ADAL capaz funcionarán en esta topología, y las contraseñas no se aprovechará si, por ejemplo, desactivar el uso de contraseñas con Certificate-based auth.

__Descripción del tipo 4:__ Esta topología bloquea NTLM *externamente* y MA internamente. Permite que *todos los clientes* usar autenticación heredado métodos *internamente* (incluso clientes compatibles con ADAL).

__Descripción del tipo 5:__ *Externamente*, los clientes ADAL modernos usará MA y los clientes que no son compatibles con ADAL, usarán los métodos de autenticación heredados. Pero, *internamente* *todos los clientes* usan la autenticación heredada (incluidos a todos los clientes compatibles con ADAL).

Es bastante fácil perder el control del objetivo de la protección de las contraseñas en las opciones disponibles. Tenga en cuenta la situación ideal es usar MA externamente (por ejemplo, mediante configuración basada en certificados auth), para evitar los ataques de denegación de servicio. Si se lo aprovecha internamente para los clientes modernos, aquí también futuro su red con respecto a Skype para los ataques de denegación de servicio de servidor empresarial.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Por qué usar Set-CsAuthConfig en el nivel Global

El `Set-CsAuthConfig` configuración de efectos de cmdlet en el registrador y las funciones de servicios Web.

Este cmdlet está diseñado para ejecutarse en el nivel Global de su Skype para Business server. Se *puede* ejecutar en el nivel de grupo de servidores, pero es decir *no se recomienda* porque va a agregar complejidad a la instalación. Mediante la ejecución de estos comandos en el nivel de grupo de servidores, si el grupo de servidores no tiene todas las funciones incluidas (por ejemplo, no tiene servicios Web), sólo se establecerá la configuración para el rol de registrador. En ese caso, los servicios Web llevará con la configuración desde el nivel Global, que puede ser confusa comportamiento (sobre todo cuando esto se realiza por equivocación).

Si un cliente usa la configuración de registrador de un grupo de servidores y la configuración de servicios Web desde otro grupo de servidores y la configuración de autenticación que se encuentran en un estado incoherente, los clientes de yous posible que pueda iniciar sesión.

Además, si hay sólo una función presente para un grupo de servidores: 
* Set-sólo establece los valores que corresponden a la función que existe. Ninguna advertencia especial se le dará como algunas opciones de configuración eran *no* conjunto. 
* Get-realizarán devolver el valor que corresponde a la función que existe y la configuración Global para el rol que no existe.
* Si ninguno de los dos roles está presente para un grupo de servidores, ambos Set y Get-podrá devolver un mensaje de error.
* Si ambas funciones están presentes para un grupo de servidores, pero no se definen las directivas en el nivel de grupo de servidores, Get-realizarán devolver un mensaje de error.

Es posible que wisest a hacer un Get-para estos valores y para captura de pantalla o para registrar su estado inicial antes de realizar cambios. También es posible que considere la posibilidad de mantener un registro de cambios en un OneNote.

> [!NOTE]
> 
> Nota: Después de configurar el CsAuthConfig, debe ejecutar Enable-CsComputer en cada equipo para que la configuración surta efecto.

> [!IMPORTANT]
> Si está utilizando Lync Web Access (LWA) y debe usar Access basada en formularios (FBA) para el acceso externo, reconfigurar LWA de modo que los clientes pueden tener acceso a él con el acceso anónimo para admitir estos escenarios. Del mismo modo, si usa el Pin de acceso telefónico, se bloqueará FBA para sólo a los usuarios externos. Si tiene que cambiar su NIP, deben iniciar sesión en su corporation para hacerlo, internamente.

## <a name="links"></a>Vínculos 
- Para obtener más información de PowerShell:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/en-us/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Para obtener más dirección sobre cómo utilizar los comandos o en la CU necesarios para instalar ellos:
    - [Cmdlets briefing](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Actualizaciones de Skype para Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015) (General)
    - El [julio 2018 Skype para Business Server 2015, de componentes CU principales](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
