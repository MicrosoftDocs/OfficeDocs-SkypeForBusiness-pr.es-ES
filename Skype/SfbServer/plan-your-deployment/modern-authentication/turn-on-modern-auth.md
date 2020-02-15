---
title: Planeación para desactivar los métodos de autenticación heredada interna y externamente en la red
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: En este artículo se describen los cmdlets que proporcionan a los administradores más control sobre los métodos de autenticación que se usan dentro y fuera de una empresa. Los administradores pueden activar o desactivar los métodos de autenticación interna o externamente en su red.
ms.openlocfilehash: a3f26e0bb29a58b53547083a4410da849c054b03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043722"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planear la desactivación interna y externa de los métodos de autenticación heredados en la red.

> [!NOTE]
> Si está a punto de leer este artículo, ya debe conocer las topologías de autenticación moderna admitidas, ADAL y la configuración de autenticación moderna, pero, en caso contrario, estos son los artículos que debe empezar: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
La autenticación moderna no solo permite métodos más seguros de autenticación, como la autenticación en dos fases o la autenticación basada en certificados, puede llevar a cabo la autorización del usuario sin necesidad de tener un nombre de usuario o una contraseña. Es muy útil.

Este artículo le ayudará a conectar los agujeros que se han aprovechado para ataques por denegación de servicio (DOS) en servidores de Skype empresarial, desactivando los métodos más antiguos usados para la autenticación, de forma externa, interna o ambas, en la red. Por ejemplo, un buen método para ayudar a detener ataques DOS sería desactivar la autenticación integrada de Windows (que incluye NTLM y Kerberos). Desactivar NTLM externamente y confiar en la autenticación basada en certificados ayuda a proteger las contraseñas de la exposición. Esto se debe a que NTLM usa las credenciales de contraseña para autenticar a los usuarios, pero la autenticación basada en certificados (habilitada por la autenticación moderna) no. Esto significa que una opción ideal para reducir los ataques DOS es bloquear NTLM externamente y, en su lugar, usar solamente la autenticación basada en certificados.

A la derecha, vamos a empezar.

## <a name="what-would-you-be-changing"></a>¿Qué cambiaría? 

Estos cmdlets funcionan para los puntos de acceso de SIP y de los servicios Web. Aunque estos dos canales usan métodos de acceso diferentes, que ejecutan la gama de NTLM y Kerberos a acceso anónimo, se han tenido en cuenta todos los métodos estándar que usa Skype empresarial.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Cómo obtener los cmdlets get-y set-CsAuthConfig

Estos cmdlets solo se instalarán después de la actualización acumulativa de julio de 2018 (6.0.9319.534) para Microsoft Skype empresarial Server 2015 y, a continuación, dispone de una variedad de topologías que se pueden implementar en Skype empresarial Server.

## <a name="topologies"></a>Topologías

Es importante tener en cuenta que estas son las topologías compatibles que participan en este escenario. Si necesita ir a soporte técnico para obtener ayuda con el bloqueo de un método, por ejemplo, necesitará tener una configuración entre los tipos que se indican a continuación. 

> [!IMPORTANT]
> En la tabla y las descripciones siguientes, la *autenticación moderna* se abrevia como __MA__ y la *autenticación de Windows integrada* se abrevia como __Win__. Como recordatorio, la autenticación integrada de Windows consta de dos métodos: autenticación NTLM y Kerberos. Necesitará saber esto para leer la tabla correctamente.


|       |Externamente  |Internamente  |Parámetro  |
|---------|:---------|:---------|---------|
|__Tipo 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tipo 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Tipo 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Tipo 4__   |  MA       | Adjudica        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Tipo 5__   |  MA + Win       | Adjudica        | BlockModernAuthInternally         |

__Descripción de tipo 1:__ Este es el escenario predeterminado cuando MA está activado __para Skype__ empresarial Server. Es decir, este es el *punto de partida* cuando se configura MA.

__Descripción de tipo 2:__ Esta topología bloquea NTLM *externamente*, pero permite a NTLM o Kerberos (para clientes que no son compatibles con Adal) trabajar *internamente*. Si los clientes admiten ADAL, usarán MA internamente.

__Descripción de tipo 3:__ Esta topología requiere MA para todos los usuarios. Todos los clientes compatibles con ADAL funcionarán en esta topología y las contraseñas no se aprovecharán si, por ejemplo, desactiva el uso de contraseñas con la autenticación basada en certificados.

__Descripción de tipo 4:__ Esta topología bloquea NTLM *externa* y Ma internamente. Permite que *todos los clientes* usen métodos de autenticación heredados *internamente* (incluso clientes compatibles con Adal).

__Tipo 5 Descripción:__ *externamente*, los clientes de Adal modernos usarán MA y los clientes que no admitan Adal usarán los métodos de autenticación heredados. Pero, *internamente* , *todos los clientes* usarán la autenticación heredada (incluidos todos los clientes compatibles con Adal).

Es muy fácil perder el seguimiento del objetivo de proteger las contraseñas en las opciones disponibles. Tenga en cuenta que la situación ideal es usar MA externamente (por ejemplo, al configurar la autenticación basada en certificados) para evitar ataques DOS. Si lo aprovecha internamente para sus clientes modernos, también le resultará más adelante su red con respecto a los ataques DOS de Skype empresarial Server.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Por qué usar Set-CsAuthConfig en el nivel global

La `Set-CsAuthConfig` configuración de efectos de cmdlets en los roles registrar y servicios Web.

Este cmdlet está diseñado para ejecutarse en el nivel global de Skype empresarial Server. Se *puede* ejecutar en el nivel de grupo pero no se *recomienda* , ya que agregará complejidad a la instalación. Al ejecutar estos comandos en el nivel de grupo, si el grupo no tiene todas las funciones incluidas (por ejemplo, no tiene servicios web), la configuración solo se establece para el rol de registrador. En ese caso, los servicios web seguirán con la configuración del nivel global, que puede ser un comportamiento confuso (especialmente cuando esto se realiza de forma involuntaria).

Si un cliente usa la configuración del registrador de un grupo de servidores y la configuración de los servicios Web de otro grupo y la configuración de autenticación está en un estado incoherente, es posible que los clientes de yous no puedan iniciar sesión.

Además, si solo hay un rol presente para un grupo de servidores: 
* Set: solo establecerá la configuración que corresponda a la función existente. No se proporcionará ninguna advertencia especial porque *no* se estableció ninguna configuración. 
* Get-devolverá la configuración que corresponda a la función existente y la configuración global para la función que no existe.
* Si no hay ninguna función presente para un grupo de servidores, set-and Get-devolverá un mensaje de error.
* Si ambos roles están presentes para un grupo de servidores, pero las directivas no se definen en el nivel de grupo, Get-devolverá un mensaje de error.

Puede ser aconsejable obtener acceso a estos valores y realizar una captura de pantalla o registrar el estado inicial antes de realizar cambios. También puede considerar la posibilidad de mantener un registro de cambios en un archivo de OneNote.

> [!NOTE]
> 
> Nota: después de configurar la CsAuthConfig, debe ejecutar enable-CsComputer en cada equipo para que la configuración surta efecto.

> [!IMPORTANT]
> Si está usando Lync Web Access (LWA) y debe usar acceso basado en formularios (FBA) para acceso externo, vuelva a configurar LWA para que los clientes puedan acceder a él con acceso anónimo para admitir estos escenarios. Del mismo modo, si usa PIN de acceso telefónico, FBA se bloqueará solo para los usuarios externos. Si necesitan cambiar su PIN, deberán iniciar sesión en su Corporación para hacerlo internamente.

> [!NOTE]
> 
> Si usa el parámetro BlockWindowsAuthExternally para bloquear externamente NTLM, tenga en cuenta que también bloquea NTLM internamente para el canal SIP. Sin embargo, los clientes de Skype empresarial y Lync posteriores a 2010 seguirán pudiendo iniciar sesión porque usarán NTLM sobre HTTP para el inicio de sesión, y luego recuperarán un certificado para iniciar sesión a través de SIP. Sin embargo, los clientes con una antigüedad superior a 2010 no podrán iniciar sesión internamente en este caso, por lo que es posible que desee considerar la posibilidad de actualizar estas aplicaciones para que los usuarios puedan reanudar la funcionalidad de seguridad.


## <a name="links"></a>Vínculos 
- Para obtener más información sobre PowerShell:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Para más información sobre cómo usar los comandos o el CU necesario para instalarlos:
    - [Informe sobre cmdlets](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Actualizaciones de Skype empresarial Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (general)
    - La actualización de los [componentes principales de 2018 de julio de Skype empresarial Server 2015](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
