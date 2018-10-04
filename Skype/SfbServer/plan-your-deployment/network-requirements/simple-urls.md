---
title: Requisitos de DNS para direcciones URL simples en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Resumen: Revise las consideraciones de dirección URL sencilla en este tema antes de implementar los registros DNS para Skype para Business Server.'
ms.openlocfilehash: 89100dc91b9b4a69a295bcbf5992b205fafb15ca
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373432"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Requisitos de DNS para direcciones URL simples en Skype para Business Server

**Resumen:** Revise las consideraciones de dirección URL sencilla en este tema antes de implementar los registros DNS para Skype para Business Server.

Las direcciones URL sencillas que unirse reuniones sea más fácil para los usuarios y asegúrese de dificultades para Skype para herramientas administrativas de servidor empresarial para los administradores. Las direcciones URL sencillas usan su propio dominio, que no coincide con cualquiera de los dominios SIP que defina. 

Skype para Business Server admite los siguientes tres direcciones URL sencillas: cumple, Dial-In y Admin. Es necesario para configurar direcciones URL sencillas para reunirse y Dial-In y la dirección URL de administración simple es opcional. Los registros del sistema de nombres de dominio (DNS) necesarios para admitir direcciones URL sencillas varían en función de la forma en que se hayan definido dichas direcciones URL sencillas y de si desea admitir la recuperación ante desastres para las direcciones URL sencillas. 

## <a name="simple-url-scope"></a>Ámbito de dirección URL simple

Puede configurar las direcciones URL sencillas para tener ámbito global, o puede especificar direcciones URL sencillas diferentes para cada sitio central en la organización. Si se especifican una dirección URL simple global y una dirección URL simple del sitio, la dirección URL del sitio simple tiene prioridad. 

En la mayoría de los casos, se recomienda que establezca las direcciones URL sencillas sólo en el nivel global, para que no cambie URL simples de reunión de un usuario si se trasladan de un sitio a otro. La excepción sería las organizaciones que necesitan usar números de teléfono diferentes para los usuarios de acceso telefónico en sitios diferentes. Tenga en cuenta que si establece una dirección URL sencilla (por ejemplo, el marcado en dirección URL sencilla) en un sitio para ser una dirección URL simple de nivel de sitio, debe establecer también otra direcciones URL sencillas en ese sitio para ser así como de nivel de sitio.

Puede establecer direcciones URL sencillas globales en el generador de topología. Para establecer una dirección URL sencilla en el nivel de sitio, use el cmdlet Set-CsSimpleURLConfiguration.

Definición de una dirección URL simple también se requiere el establecimiento de un registro A o AAAA en la configuración de DNS.

## <a name="simple-url-naming-and-validation-rules"></a>Reglas de nomenclatura y validación de dirección URL simples
<a name="BK_Valid"> </a>

Generador de topología y la Skype para los cmdlets del Shell de administración de servidor empresarial aplican varias reglas de validación para las direcciones URL sencillas. Es necesario para establecer las direcciones URL sencillas para reunirse y acceso telefónico, pero es opcional establecer uno para la administración. Cada dominio SIP debe tener una URL simples de reunión independiente, pero necesita sólo una dirección URL sencilla de acceso telefónico y una dirección URL sencilla de administración para toda la organización.

Cada dirección URL sencilla en su organización debe tener un nombre único y no puede ser un prefijo de dirección URL sencilla de otra (por ejemplo, se podrían no establecer SfB2015.contoso.com/Meet como su URL simples de reunión y SfB2015.contoso.com/Meet/Dialin como la dirección URL sencilla de acceso telefónico). Nombres de dirección URL simples no pueden contener el FQDN de cualquiera de los grupos, o cualquier información de puerto (por ejemplo, https://FQDN:88/meet no se permite). Todas las direcciones URL sencillas deben comenzar con el prefijo https://. 

Las direcciones URL sencillas pueden contener solo caracteres alfanuméricos (es decir, a z, a Z, 0-9 y el punto (.). Si utiliza otros caracteres, la simple las direcciones URL pueden no funcionar según lo esperado.

## <a name="changing-simple-urls-after-deployment"></a>Cambiar las direcciones URL sencillas después de la implementación
<a name="BK_Valid"> </a>

Si cambia una dirección URL sencilla después de la implementación inicial, debe tener en cuenta cómo afecta el cambio a sus registros DNS y los certificados para las direcciones URL sencillas. Si cambia la base de una dirección URL sencilla, debe cambiar los registros DNS y certificados también. Por ejemplo, si cambia de https://SfB2015.contoso.com/Meet a https://meet.contoso.com cambia la dirección URL base de SfB2015.contoso.com a meet.contoso.com, por lo que necesita cambiar los registros DNS y certificados para hacer referencia a meet.contoso.com. Si cambia la dirección URL sencilla de https://SfB2015.contoso.com/Meet a https://SfB2015.contoso.com/Meetings, la dirección URL base de SfB2015.contoso.com sigue siendo el mismo, por lo que no DNS o es necesario realizar cambios de certificado.

Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar **Enable-CsComputer** en cada Director y el servidor Front-End para registrar el cambio.

## <a name="naming-examples-for-simple-urls"></a>Ejemplos de nomenclatura para las direcciones URL sencillas
<a name="BK_Valid"> </a>

Hay tres opciones recomendadas para asignar nombres a las direcciones URL sencillas. Opción que usted elija tiene implicaciones para la configuración de los registros A DNS y los certificados que admiten las direcciones URL sencillas. En cada opción, debe configurar una URL simples de reunión para cada dominio SIP en su organización. 

Siempre necesitará una sola dirección URL sencilla en toda la organización para el acceso telefónico y otra para administración, independientemente de cuántos dominios SIP que haya.

En la opción 1, se crea un nuevo nombre de dominio SIP para cada dirección URL sencilla.

Si utiliza esta opción, necesita un registro DNS A independiente para cada dirección URL sencilla y cada URL simples de reunión deben tener un nombre en los certificados.

**Opción de nomenclatura de dirección URL sencilla 1**


| **Dirección URL sencilla** <br/> | **Ejemplo** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Reunión  <br/>          | https://meet.contoso.com, https://meet.fabrikam.com, y así sucesivamente (uno para cada dominio SIP de la organización)  <br/> |
| Acceso telefónico local  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Administrador  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

Con la opción 2, las direcciones URL sencillas se basan en el nombre de dominio SfB2015.contoso.com. Por lo tanto, es necesario solo un registro DNS A lo que permite a los tres tipos de direcciones URL sencillas. Este registro A DNS hace referencia a SfB2015.contoso.com. Además, seguirá necesitando registros A DNS independiente para otros dominios SIP de la organización. 

**Opción de nomenclatura de dirección URL sencilla 2**


| **Dirección URL sencilla** <br/> | **Ejemplo** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Reunión  <br/>          | https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, y así sucesivamente (uno para cada dominio SIP de la organización)  <br/> |
| Acceso telefónico local  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Administrador  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

Opción 3 es más útil si tiene varios dominios SIP, y desea tener URL simples de reunión independientes pero desea minimizar los requisitos de certificado y de registro DNS para estas direcciones URL sencillas. 

**Opción de nomenclatura de dirección URL sencilla 3**


| **Dirección URL sencilla** <br/> | **Ejemplo** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Reunión  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| Acceso telefónico local  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Administrador  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Opción de recuperación ante desastres para direcciones URL sencillas
<a name="BK_Valid"> </a>

Si tiene varios sitios que contienen los grupos de servidores Front-End y el proveedor de DNS es compatible con GeoDNS, puede establecer sus registros DNS para direcciones URL sencillas admitir la recuperación ante desastres, para que la funcionalidad de dirección URL sencilla continúa incluso si un grupo completo de servidores Front-End deja de funcionar. Esta característica de recuperación ante desastres admite las direcciones URL sencillas de acceso telefónico y de reunión.

Para configurar esto, cree dos direcciones de GeoDNS. Cada dirección tiene dos registros A de DNS o CNAME que se resuelven en dos grupos de servidores que funcionan juntos con fines de recuperación ante desastres. Una dirección de GeoDNS se utiliza para el acceso interno y se resuelve en el FQDN web interno o la dirección IP del equilibrador de carga para dos grupos de servidores. La otra dirección de GeoDNS se utiliza para el acceso externo y se resuelve en el FQDN web externo o la dirección IP del equilibrador de carga para dos grupos de servidores. Lo siguiente es un ejemplo de dirección URL sencilla de reunión, que utiliza los FQDN para los grupos de servidores. 

```
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

Luego, cree registros CNAME que se resuelven en la dirección URL sencilla de reunión (como meet.contoso.com) en las dos direcciones de GeoDNS.

> [!NOTE]
> Si su red utiliza vinculaciones (enrutamiento de todo el tráfico de direcciones URL sencillas a través del vínculo externo, incluido el tráfico que proviene desde su organización), puede sencillamente configurar la dirección de GeoDNS externa y resolver la dirección URL sencilla de reunión en solo esa dirección externa.

Al utilizar este método, puede configurar cada dirección de GeoDNS para que utilice un método round robin para distribuir solicitudes en los dos grupos de servidores, o bien para que se conecte principalmente a un grupo de servidores (como el grupo de servidores más cercano) y utilizar el otro grupo solo en caso de que no se pueda establecer la conexión. 

Puede configurar las mismas opciones para la dirección URL sencilla de acceso telefónico. Para ello, cree registros adicionales como los que en el ejemplo anterior, sustituyendo `dialin` para `meet` en los registros DNS. Para la dirección URL sencilla de administrador, utilice una de las tres opciones que se mencionaron antes en esta sección.

Una vez que esta configuración esté definida, necesita utilizar una aplicación de supervisión para configurar la supervisión HTTP para que busque errores. Para el acceso externo, monitor para asegurarse de que ese lyncdiscover HTTPS GET.<sipdomain> las solicitudes al sitio web externo FQDN o carga la dirección de IP del equilibrador para los dos grupos de servidores son correctas. Por ejemplo, las solicitudes siguientes no debe contener cualquier encabezado **ACCEPT** y debe devolver **200 Aceptar**.

```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Para el acceso interno, necesita supervisar el puerto 5061 en el FQDN web interno o la dirección IP del equilibrador de carga para los dos grupos de servidores. Si se detecta cualquier problema de conectividad, la dirección VIP de estos grupos de servidores necesita cerrar los puertos 80, 443 y 4443.


