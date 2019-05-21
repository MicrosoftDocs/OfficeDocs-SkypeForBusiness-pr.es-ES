---
title: Planear la desactivación de los métodos de autenticación heredados de forma interna y externa a la red
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: En este artículo, se describen los cmdlets que ofrecen a los administradores más control sobre los métodos de autenticación que se usan dentro y fuera de una empresa. Los administradores pueden activar o desactivar internamente los métodos de autenticación, o de forma externa, a su red.
ms.openlocfilehash: aaee46b04832cc114f895f905c180fe089d7349d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297270"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planear la desactivación de los métodos de autenticación heredados de forma interna y externa a la red.

> [!NOTE]
> Si está a punto de leer este artículo, ya debe conocer las topologías de autenticación moderna compatibles, ADAL y la configuración de autenticación moderna, pero, en caso de que no lo haga, estos artículos le interesan: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
La autenticación moderna no solo permite métodos más seguros de autenticación, como la autenticación de dos factores o la autenticación basada en certificados, puede llevar a cabo la autorización de su usuario sin necesidad de tener un nombre de usuario o una contraseña. Es muy útil.

Este artículo le ayudará a conectar los agujeros que se han aprovechado para los ataques de denegación de servicio (DOS) en servidores de Skype empresarial, desactivando los métodos más antiguos utilizados para la autenticación, externamente, internamente o ambos, a su red. Por ejemplo, un buen método para ayudar a detener los ataques DOS sería desactivar la autenticación integrada de Windows (que incluye NTLM y Kerberos). Desactivar NTLM externamente y depender de la autenticación basada en certificados ayuda a proteger las contraseñas de la exposición. Esto se debe a que NTLM usa las credenciales de contraseña para autenticar a los usuarios, pero la autenticación basada en certificados, habilitada por la autenticación moderna, no. Eso significa que una opción ideal para reducir los ataques DOS es bloquear NTLM externamente y, en su lugar, usar únicamente la autenticación basada en certificados.

Vamos a empezar.

## <a name="what-would-you-be-changing"></a>¿Qué cambiaría? 

Estos cmdlets funcionan para los puntos de acceso de los servicios SIP y Web. Aunque estos dos canales usan métodos de acceso diferentes, que ejecutan la gama de NTLM y Kerberos a acceso anónimo, se han tenido en cuenta todos los métodos estándar usados por Skype empresarial.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Cómo obtener los cmdlets get-y set-CsAuthConfig

Estos cmdlets solo se instalarán después de la actualización acumulativa de julio de 2018 (6.0.9319.534) para Microsoft Skype empresarial Server 2015 y, a continuación, tendrá una variedad de topologías que se pueden implantar para su servidor de Skype empresarial.

## <a name="topologies"></a>Topologías

Es importante tener en cuenta que estas son las topologías admitidas en este escenario. Si necesita ir a soporte técnico para obtener ayuda para bloquear un método, por ejemplo, necesitará tener una configuración entre los tipos que figuran a continuación. 

> [!IMPORTANT]
> En la tabla y las descripciones siguientes, la *autenticación moderna* se abrevia como __MA__ y la *autenticación integrada de Windows* se abrevia como __Win__. Como recordatorio, la autenticación integrada de Windows consta de dos métodos: autenticación NTLM y Kerberos. Tendrá que saber esto para leer la tabla correctamente.


|       |Externamente  |Internamente  |Parámetro  |
|---------|:---------|:---------|---------|
|__Escriba 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tipo 2__   |  PROMEDIO       | MA + Win         | BlockWindowsAuthExternally        |
|__Escriba 3__   |  PROMEDIO       | PROMEDIO        | BlockWindowsAuthExternallyAndInternally        |
|__Escriba 4__   |  PROMEDIO       | Logros        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Escriba 5__   |  MA + Win       | Logros        | BlockModernAuthInternally         |

__Escriba una descripción:__ Este es el escenario predeterminado cuando el MA está ____ activado para Skype empresarial Server. En otras palabras, este es el *punto de partida* cuando está configurado el mA.

__Descripción del tipo 2:__ Esta topología bloquea NTLM *externamente*, pero permite que NTLM o Kerberos (para los clientes que no son compatibles con Adal) funcionen *internamente*. Si sus clientes admiten ADAL, usarán el MA internamente.

__Descripción del tipo 3:__ Esta topología requiere MA para todos los usuarios. Todos los clientes con capacidad para ADAL funcionarán en esta topología y las contraseñas no se aprovecharán si, por ejemplo, desactiva el uso de contraseñas con autenticación basada en certificados.

__Escriba 4 Descripción:__ Esta topología bloquea NTLM *externamente* y Ma internamente. Permite que *todos los clientes* usen internamente métodos ** de autenticación heredados (incluso clientes compatibles con Adal).

__Descripción del tipo 5:__ *Externamente*, tus clientes modernos de Adal usarán MA y cualquier cliente que no admita Adal usará métodos de autenticación heredados. Pero, de forma *interna* , *todos los clientes* usarán la autenticación heredada (incluidos todos los clientes compatibles con Adal).

Es muy fácil perder el control del objetivo de proteger las contraseñas en las opciones disponibles. Tenga en cuenta que la situación ideal es usar MA externamente (por ejemplo, mediante la configuración de la autenticación basada en certificados) para evitar ataques de DOS. Si lo aprovecha de forma interna para sus clientes modernos, también tendrá que probar más adelante su red con respecto a los ataques DOS de Skype empresarial Server.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Por qué usar Set-CsAuthConfig en el nivel global

La `Set-CsAuthConfig` configuración de efectos de cmdlet en los roles registrar y servicios Web.

Este cmdlet está diseñado para ejecutarse a nivel global de Skype empresarial Server. Se *puede* ejecutar en el nivel de grupo, pero *no se recomienda* porque agregará complejidad a la instalación. Al ejecutar estos comandos en el nivel de grupo, si el grupo no tiene todas las funciones incluidas (por ejemplo, no tiene servicios web), la configuración solo se establece para el rol de registrador. En ese caso, los servicios web seguirán con la configuración del nivel global, lo cual puede conllevar un comportamiento confuso (especialmente cuando esto se realiza de forma involuntaria).

Si un cliente usa la configuración de registrar de un grupo y la configuración de los servicios Web de otro grupo y la configuración de autenticación se encuentran en un estado incoherente, es posible que los clientes de yous no puedan iniciar sesión.

Además, si hay un único rol para un grupo de servidores: 
* Establecer: solo establecerá la configuración que corresponda al rol que existe. No se proporcionará ninguna advertencia especial porque *no* se establecieron algunos ajustes. 
* Get: devolverá la configuración que corresponde al rol que existe y la configuración global para el rol que no existe.
* Si no hay ninguna función para un grupo, ambos conjuntos devolverán un mensaje de error.
* Si ambos roles están presentes para un grupo pero las directivas no se definen en el nivel del grupo, Get-devolverá un mensaje de error.

Es posible que sea más aconsejable usar estos valores, así como realizar capturas de pantalla o registrar su estado de inicio antes de realizar cambios. También puede mantener un registro de cambios en un OneNote.

> [!NOTE]
> 
> Nota: después de configurar la CsAuthConfig, debe ejecutar enable-CsComputer en cada equipo para que la configuración surta efecto.

> [!IMPORTANT]
> Si está usando Lync Web Access (LWA) y debe usar acceso basado en formularios (FBA) para acceso externo, vuelva a configurar el LWA para que los clientes puedan acceder a él con acceso anónimo para admitir estos escenarios. Del mismo modo, si usa el PIN de acceso telefónico, FBA se bloqueará solo para los usuarios externos. Si necesitan cambiar su PIN, deberán iniciar sesión en su Corporación para hacerlo internamente.

## <a name="links"></a>Vínculos 
- Para obtener más información sobre PowerShell:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/en-us/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Para obtener más información sobre cómo usar los comandos o sobre el CU necesario para instalarlos, haga lo siguiente:
    - [Informe sobre cmdlets](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Actualizaciones para Skype empresarial Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015) General
    - Los [componentes principales de la 2018 de julio de Skype 2015 empresarial:](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server)


 
