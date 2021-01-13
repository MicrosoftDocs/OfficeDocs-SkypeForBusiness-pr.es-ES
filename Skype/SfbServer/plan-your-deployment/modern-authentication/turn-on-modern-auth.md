---
title: Planeación de desactivar los métodos de autenticación heredados interna y externamente en la red
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: En este artículo se describen los cmdlets que dan a los administradores un mayor control de los métodos de autenticación usados dentro y fuera de una empresa. Los administradores pueden activar o desactivar los métodos de autenticación interna o externamente en su red.
ms.openlocfilehash: dca7dca332564442110c626a222f7ed5d138efaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810034"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planee desactivar los métodos de autenticación heredados interna y externamente en la red.

> [!NOTE]
> Si está a punto de leer este artículo, ya debe conocer las topologías de autenticación moderna admitidas, ADAL y sobre la configuración de autenticación moderna, pero, en caso de que no lo haga, estos son los artículos que necesita para empezar: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
La autenticación moderna no solo habilita métodos de autenticación más seguros, como la autenticación de Two-Factor o la autenticación basada en certificados, también puede llevar a cabo la autorización del usuario sin necesidad de un nombre de usuario o una contraseña. Es muy útil.

Este artículo le ayudará a conectar agujeros que se han aprovechado para ataques por denegación de servicio (DOS) en servidores de Skype Empresarial, desactivando los métodos antiguos usados para la autenticación, externa, interna o ambas, a su red. Por ejemplo, un buen método para ayudar a detener los ataques de DOS sería desactivar la autenticación integrada de Windows (que incluye NTLM y Kerberos). Desactivar NTLM externamente y confiar en la autenticación basada en certificados ayuda a proteger las contraseñas de la exposición. Esto se debe a que NTLM usa credenciales de contraseña para autenticar usuarios, pero la autenticación basada en certificados (habilitada por la autenticación moderna) no lo hace. Esto significa que una opción ideal para reducir los ataques de DOS es bloquear NTLM externamente y, en su lugar, usar solo la autenticación basada en certificados.

Vamos a empezar.

## <a name="what-would-you-be-changing"></a>¿Qué cambiaría? 

Estos cmdlets funcionan tanto para puntos de acceso sip como para servicios web. Aunque estos dos canales usan métodos de acceso diferentes, ejecutando la gama de NTLM y Kerberos al acceso anónimo, se han tenido en cuenta todos los métodos estándar usados por Skype Empresarial.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Cómo obtener los cmdlets Get y Set-CsAuthConfig

Estos cmdlets solo se instalarán después de la actualización acumulativa de julio de 2018 (6.0.9319.534) para Microsoft Skype Empresarial Server 2015 y, a continuación, tiene una variedad de topologías que se pueden implantar para su servidor de Skype Empresarial.

## <a name="topologies"></a>Topologías

Es importante tener en cuenta que estas son las topologías compatibles implicadas en este escenario. Si necesita ir al soporte técnico para obtener ayuda con el bloqueo de un método, por ejemplo, tendrá que tener una configuración entre los siguientes tipos. 

> [!IMPORTANT]
> En la tabla y las descripciones *siguientes,* la autenticación moderna se abrevia como __MA__ y la autenticación integrada de *Windows* se abrevia como __Win__. Como recordatorio, la autenticación integrada de Windows se integra en dos métodos: autenticación NTLM y Kerberos. Tendrás que saber esto para leer la tabla correctamente.


|       |Externamente  |Internamente  |Parameter  |
|---------|:---------|:---------|---------|
|__Tipo 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tipo 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Tipo 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Tipo 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Tipo 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Tipo 1 Descripción:__ Este es el escenario predeterminado cuando MA está __activado__ para Skype Empresarial Server. En otras palabras, este es el *punto de partida* cuando ma está configurado.

__Tipo 2 Descripción:__ Esta topología bloquea *NTLM* externamente, pero permite que NTLM o Kerberos (para clientes que no admiten ADAL) funcionen *internamente.* Si los clientes admiten ADAL, usarán MA internamente.

__Tipo 3 Descripción:__ Esta topología requiere MA para todos los usuarios. Todos los clientes compatibles con ADAL funcionarán en esta topología y las contraseñas no se aprovecharán si, por ejemplo, desactiva el uso de contraseñas con autenticación basada en certificados.

__Tipo 4 Descripción:__ Esta topología bloquea NTLM *externamente y* MA internamente. Permite a *todos los clientes* usar métodos de autenticación heredados *internamente* (incluso clientes compatibles con ADAL).

__Tipo 5 Descripción:__ *Externamente,* los clientes modernos de ADAL usarán MA y los clientes que no admitan ADAL usarán métodos de autenticación heredados. Sin embargo, *internamente* *todos los* clientes usarán la autenticación heredada (incluidos todos los clientes compatibles con ADAL).

Es bastante fácil perder el seguimiento del objetivo de proteger las contraseñas en las opciones disponibles. Tenga en cuenta que la situación ideal es usar MA externamente (por ejemplo, mediante la configuración de la autenticación basada en certificados) para evitar ataques DOS. If you leverage it internally for your modern clients, you'll also future-proof your network regarding Skype for Business Server DOS attacks.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Por qué usar Set-CsAuthConfig a nivel global

El `Set-CsAuthConfig` cmdlet afecta a la configuración tanto en los roles de registrador como de servicios web.

Este cmdlet está diseñado para ejecutarse en el nivel global de su servidor de Skype Empresarial. Se *puede* ejecutar en el nivel  de grupo, pero no se recomienda porque agregará complejidad a la instalación. Al ejecutar estos comandos en el nivel de grupo de servidores, si el grupo de servidores no tiene todos los roles incluidos (por ejemplo, no tiene servicios web), la configuración solo se establecerá para el rol registrador. En ese caso, los servicios web seguirán con la configuración del nivel global, lo que puede resultar confuso (especialmente cuando esto se hace de forma involuntarla).

Si un cliente usa la configuración de registrador de un grupo de servidores y la configuración de servicios web de otro grupo de servidores y la configuración de autenticación están en un estado incoherente, es posible que los clientes no puedan iniciar sesión.

Además, si solo hay un rol presente para un grupo de servidores: 
* Set: solo establecerá la configuración que corresponda al rol que existe. No se mostrará ninguna advertencia especial porque no se han establecido *algunas opciones de* configuración. 
* Get devolverá la configuración que corresponde al rol que existe y la configuración global del rol que no existe.
* Si ninguno de los roles está presente para un grupo de servidores, Set- y Get- devolverán un mensaje de error.
* Si ambos roles están presentes para un grupo de servidores pero las directivas no están definidas en el nivel de grupo, Get devolverá un mensaje de error.

Puede ser más aconsejable hacer un Get para estos valores, y realizar una captura de pantalla o registrar su estado inicial antes de realizar cualquier cambio. También puede considerar la posibilidad de mantener un registro de cambios en oneNote.

> [!NOTE]
> 
> Nota: Después de configurar CsAuthConfig, debe ejecutar Enable-CsComputer en cada equipo para que la configuración suba efecto.

> [!IMPORTANT]
> Si usa Lync Web Access (LWA) y debe usar El acceso basado en formularios (FBA) para el acceso externo, vuelva a configurar LWA para que los clientes puedan acceder a él con acceso anónimo para admitir estos escenarios. Del mismo modo, si usa el Pin de acceso telefónico, la FBA solo se bloqueará para usuarios externos. Si necesitan cambiar su patilla, tendrán que iniciar sesión en su empresa para hacerlo internamente.

> [!NOTE]
> 
> Si usa el parámetro BlockWindowsAuthExternally para bloquear NTLM externamente, tenga en cuenta que también bloquea NTLM internamente para el canal SIP. Sin embargo, los clientes de Skype Empresarial y Lync más recientes que 2010 podrán iniciar sesión porque usarán NTLM sobre HTTP para el inicio de sesión, internamente y, a continuación, recuperarán un certificado para iniciar sesión a través de SIP. Sin embargo, los clientes anteriores a 2010 no podrán iniciar sesión internamente en esta circunstancia y es posible que desee considerar la posibilidad de actualizar estas aplicaciones para que los usuarios puedan reanudar la funcionalidad segura.

> [!IMPORTANT] 
> Algunas de las aplicaciones web de Skype Empresarial no admiten MA. Por lo tanto, al usar el escenario BlockWindowsAuthExternallyAndInternally, no podrá obtener acceso a estas aplicaciones. Las aplicaciones sin compatibilidad con MA son programador web, página de acceso telefónico local, panel de control de Skype Empresarial (CSCP) y página de configuración de grupo de respuesta. 

## <a name="links"></a>Vínculos 
- Para obtener más información sobre PowerShell:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Para obtener más información sobre cómo usar los comandos o en la CU necesaria para instalarlos:
    - [Informe de cmdlets](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Actualizaciones de Skype Empresarial Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (general)
    - The [July 2018 Skype for Business Server 2015, Core Components CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
