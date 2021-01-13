---
title: Requisitos de DNS para direcciones URL sencillas en Skype Empresarial Server
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
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Resumen: revise las consideraciones de dirección URL sencilla de este tema antes de implementar registros DNS para Skype Empresarial Server.'
ms.openlocfilehash: d1c4213e1fe28c6f42cd4fa14f48bc8ce9b7bdf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834590"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Requisitos de DNS para direcciones URL sencillas en Skype Empresarial Server

**Resumen:** Revise las consideraciones de dirección URL sencilla de este tema antes de implementar registros DNS para Skype Empresarial Server.

Las direcciones URL sencillas facilitan la unión a reuniones para los usuarios y facilitan a los administradores el acceso a las herramientas administrativas de Skype Empresarial Server. Las direcciones URL sencillas usan su propio dominio, que no debe coincidir con ninguno de los dominios SIP que defina. 

Skype Empresarial Server admite las tres direcciones URL sencillas siguientes: Reunión, Acceso telefónico local y Administrador. Debe configurar direcciones URL sencillas para reunión y acceso telefónico, y la dirección URL sencilla de administración es opcional. Los registros del sistema de nombres de dominio (DNS) necesarios para admitir direcciones URL sencillas varían en función de la forma en que se hayan definido dichas direcciones URL sencillas y de si desea admitir la recuperación ante desastres para las direcciones URL sencillas. 

## <a name="simple-url-scope"></a>Ámbito de dirección URL simple

Las direcciones URL sencillas se pueden configurar para que tengan un ámbito global, o bien se puede especificar una distinta por cada sitio central de la organización. En caso de que se haya especificado una dirección URL sencilla y otra de sitio, esta última tendrá prioridad. 

En la mayoría de los casos, se recomienda establecer direcciones URL sencillas solo en el nivel global, de modo que la dirección URL sencilla de reunión de un usuario no cambie si se mueve de un sitio a otro. Una excepción a esto serían aquellas organizaciones que necesitan usar números de teléfono distintos para los usuarios de acceso telefónicos localizados en sitios distintos. Tenga en cuenta que, si una dirección URL sencilla (como, por ejemplo, de acceso telefónico) se establece en un sitio como dirección URL sencilla de nivel de sitio, también deberá definir el resto de direcciones URL sencillas como de nivel de sitio.

Puede establecer direcciones URL sencillas globales en el Generador de topologías. Para establecer una dirección URL sencilla en el nivel de sitio, use el cmdlet Set-CsSimpleURLConfiguration web.

Definir una dirección URL sencilla también requerirá establecer un registro A y/o AAAA en la configuración DNS.

## <a name="simple-url-naming-and-validation-rules"></a>Reglas de validación y nomenclatura de direcciones URL sencillas
<a name="BK_Valid"> </a>

Topology Builder y los cmdlets del Shell de administración de Skype Empresarial Server aplican varias reglas de validación para las direcciones URL sencillas. Las direcciones URL sencillas para reunión y acceso telefónico deben definirse obligatoriamente, si bien esto es opcional en el caso de las direcciones URL de administración. Cada dominio SIP debe tener una dirección URL sencilla de reunión particular, mientras que solo es preciso tener una dirección URL sencilla de acceso telefónico y de administración para toda la organización.

Cada dirección URL sencilla de la organización debe tener un nombre único y no puede ser un prefijo de otra dirección URL sencilla (por ejemplo, no se pudo establecer SfB2015.contoso.com/Meet como dirección URL sencilla de reunión y SfB2015.contoso.com/Meet/Dialin como dirección URL sencilla de acceso telefónico). Los nombres de dirección URL sencillas no pueden contener el FQDN de ninguno de los grupos de servidores ni ninguna información de puerto (por ejemplo, https://FQDN:88/meet no está permitida). Todas las direcciones URL sencillas deben empezar por el prefijo https://. 

Las direcciones URL sencillas solo pueden contener caracteres alfanuméricos, esto es, a-z, A-Z, 0-9 y el signo de punto (.); si usa otros caracteres, podrían no funcionar del modo previsto.

## <a name="changing-simple-urls-after-deployment"></a>Cambio de direcciones URL sencillas después de la implementación
<a name="BK_Valid"> </a>

Si modifica una dirección URL sencilla tras la implementación inicial, deberá tener presentes los cambios que podrían afectar a los registros DNS y certificados de dichas direcciones. Si el cambio afecta a la base de una dirección URL sencilla, deberá modificar también los certificados y registros DNS. Por ejemplo, al cambiar de a cambia la dirección URL base de SfB2015.contoso.com a meet.contoso.com, por lo que tendría que cambiar los certificados y registros DNS para hacer referencia a https://SfB2015.contoso.com/Meet https://meet.contoso.com meet.contoso.com. Si cambió la dirección URL sencilla de a , la dirección URL base de SfB2015.contoso.com sigue igual, por lo que no se necesitan cambios de https://SfB2015.contoso.com/Meet https://SfB2015.contoso.com/Meetings DNS ni de certificado.

Sin embargo, siempre que cambie un nombre de dirección URL simple, debe ejecutar **Enable-CsComputer** en cada director y servidor front-end para registrar el cambio.

## <a name="naming-examples-for-simple-urls"></a>Ejemplos de nomenclatura para direcciones URL sencillas
<a name="BK_Valid"> </a>

Son tres las opciones recomendadas de nomenclatura de las direcciones URL sencillas. Aquella que elija conllevará una serie de implicaciones a la hora de configurar los registros A de DNS y certificados que admiten direcciones URL sencillas. Con cada opción deberá configurar una dirección URL sencilla de reunión por cada dominio SIP existente en la organización. Tener una dirección URL sencilla para acceso telefónico y otra para administración en toda la organización siempre será suficiente, independientemente del número de dominios SIP que haya. 

Tener una dirección URL sencilla para acceso telefónico y otra para administración en toda la organización siempre será suficiente, independientemente del número de dominios SIP que haya.

Con la opción 1, se crea un nombre de dominio SIP nuevo por cada dirección URL sencilla.

Si se decanta por esta opción, necesitará un registro A de DNS por cada dirección URL sencilla y en los certificados deberá aparecer el nombre de todas las direcciones URL sencillas de reunión.

**Opción 1 de nomenclatura de dirección URL sencilla**


| **Direcciones URL sencillas** <br/> | **Ejemplo** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | https://meet.contoso.com, https://meet.fabrikam.com y así sucesivamente (uno para cada dominio SIP de la organización)  <br/> |
| Acceso telefónico  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Administrador  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

Con la opción 2, las direcciones URL sencillas se basan en el nombre de dominio SfB2015.contoso.com. Por lo tanto, solo necesita un registro A de DNS que permita los tres tipos de direcciones URL sencillas. Este registro A de DNS hace referencia SfB2015.contoso.com. Además, aún necesita registros DNS A independientes para otros dominios SIP de su organización. 

**Opción 2 de nomenclatura de dirección URL sencilla**


| **Direcciones URL sencillas** <br/> | **Ejemplo** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet y así sucesivamente (uno para cada dominio SIP de la organización)  <br/> |
| Acceso telefónico  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Administrador  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

La opción 3 es la más práctica si existen muchos dominios SIP y quiere que cada uno de ellos tenga una dirección URL sencilla de reunión pero, al mismo tiempo, desea reducir al mínimo los requisitos de registros DNS y certificados para dichas direcciones. 

**Opción 3 de nomenclatura de dirección URL sencilla**


| **Direcciones URL sencillas** <br/> | **Ejemplo** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| Acceso telefónico  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Administrador  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Opción de recuperación ante desastres para direcciones URL sencillas
<a name="BK_Valid"> </a>

Si tiene varios sitios que contienen grupos de servidores front-end y su proveedor dns admite GeoDNS, puede configurar los registros DNS de direcciones URL sencillas para admitir la recuperación ante desastres, de modo que la funcionalidad de dirección URL sencilla continúe incluso si un grupo de servidores front-end completo deja de estar disponible. Esta función de recuperación ante desastres admite las direcciones URL sencillas de Acceso telefónico y Reunión.

Para configurar esto, cree dos direcciones de GeoDNS. Cada dirección tiene dos registros DNS A o CNAME que resultan en dos grupos de servidores que funcionan juntos con fines de recuperación ante desastres. Una dirección de GeoDNS se utiliza para el acceso interno y se resuelve en el FQDN web interno o la dirección IP del equilibrador de carga para dos grupos de servidores. La otra dirección de GeoDNS se utiliza para el acceso externo y se resuelve en el FQDN web externo o la dirección IP del equilibrador de carga para dos grupos de servidores. Lo siguiente es un ejemplo de dirección URL sencilla de Reunión, que utiliza los FQDN para los grupos de servidores. 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

Luego cree registros CNAME que se resuelven su dirección URL sencilla de Reunión (como meet.contoso.com) en las dos direcciones de GeoDNS.

> [!NOTE]
> Si su red utiliza vinculaciones (enrutamiento de todo su tráfico de direcciones URL sencillas a través del enlace externo, incluido el tráfico que proviene desde su organización), entonces puede simplemente configurar la dirección de GeoDNS externa y resolver su dirección URL sencilla de Reunión en solo esa dirección externa.

Al utilizar este método, puede configurar cada dirección de GeoDNS para que utilice un método de operación por turnos para distribuir solicitudes en los dos grupos de servidores, o bien para que se conecte a un grupo de servidores (como el grupo de servidores más cercano) y utilizar el otro grupo solo en caso de que no se pueda establecer la conexión. 

Puede configurar los mismos parámetros para la dirección URL sencilla de Acceso telefónico. Para ello, cree registros adicionales como los del ejemplo anterior, sustituyéndolo  `dialin` en `meet` los registros DNS. Para la dirección URL sencilla de Administrador, utilice una de las tres opciones que se mencionaron antes en esta sección.

Una vez que esta configuración esté definida, debe utilizar una aplicación de supervisión para configurar la supervisión HTTP para que esté alerta de los fallos. Para el acceso externo, supervise para asegurarse de que HTTPS GET lyncdiscover.<sipdomain> las solicitudes al FQDN web externo o a la dirección IP del equilibrador de carga para los dos grupos de servidores son correctas. Por ejemplo, las siguientes solicitudes no deben contener ningún encabezado **ACCEPT** y deben devolver **200 OK**.

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Para el acceso interno, debe supervisar el puerto 5061 en el FQDN web interno o la dirección IP del equilibrador de carga para los dos grupos de servidores. Si se detectan errores de conectividad, la DIRECCIÓN VIP de estos grupos de servidores debe cerrar los puertos 80, 443 y 4443.


