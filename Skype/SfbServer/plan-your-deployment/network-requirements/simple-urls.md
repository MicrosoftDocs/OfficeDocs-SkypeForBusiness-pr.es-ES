---
title: Requisitos de DNS para las direcciones URL simples en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Resumen: Revise las consideraciones de la dirección URL simple en este tema antes de implementar los registros DNS para Skype empresarial Server.'
ms.openlocfilehash: 6f5003542f797c6dd275eb8de7c0b00b1ea209ac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297151"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Requisitos de DNS para las direcciones URL simples en Skype empresarial Server

**Resumen:** Revise las consideraciones de la dirección URL simple en este tema antes de implementar los registros DNS para Skype empresarial Server.

Las direcciones URL simples facilitan la Unión a las reuniones para los usuarios y hacen que las herramientas administrativas de Skype empresarial Server sean más sencillas para los administradores. Las direcciones URL simples usan su propio dominio, que no debe coincidir con ninguno de los dominios SIP que defina. 

Skype empresarial Server admite las siguientes tres direcciones URL sencillas: reunirse, acceso telefónico y administrador. Es necesario configurar direcciones URL simples para la reunión y el acceso telefónico, y la dirección URL simple de administración es opcional. Los registros del sistema de nombres de dominio (DNS) necesarios para admitir direcciones URL sencillas varían en función de la forma en que se hayan definido dichas direcciones URL sencillas y de si desea admitir la recuperación ante desastres para las direcciones URL sencillas. 

## <a name="simple-url-scope"></a>Ámbito de dirección URL simple

Puede configurar las direcciones URL simples para que tengan ámbito global o puede especificar direcciones URL simples diferentes para cada sitio central de su organización. Si se especifican tanto una dirección URL simple global como una simple URL de sitio, la dirección URL simple del sitio tiene prioridad. 

En la mayoría de los casos, se recomienda establecer direcciones URL simples solo en el nivel global, de modo que la dirección URL simple de un usuario no cambie si se mueve de un sitio a otro. La excepción serían organizaciones que necesitan usar números de teléfono diferentes para los usuarios de acceso telefónico local en diferentes sitios. Tenga en cuenta que si establece una dirección URL simple (como la dirección URL de acceso telefónico simple) en un sitio para que sea una dirección URL simple de nivel de sitio, también debe establecer las otras direcciones URL simples en ese sitio para que también sean del nivel del sitio.

Puede establecer direcciones URL globales simples en el generador de topología. Para establecer una dirección URL simple en el nivel del sitio, use el cmdlet Set-CsSimpleURLConfiguration.

Definir una dirección URL simple también requerirá configurar un registro A y/o AAAA en su configuración DNS.

## <a name="simple-url-naming-and-validation-rules"></a>Nomenclatura de URL simple y reglas de validación
<a name="BK_Valid"> </a>

El generador de topología y los cmdlets del shell de administración de Skype empresarial Server exigen varias reglas de validación para las direcciones URL simples. Debe establecer direcciones URL simples para reunirse y llamar, pero establecer una para administrador es opcional. Cada dominio SIP debe tener una dirección URL simple de reunirse, pero solo se necesita una dirección URL simple de marcación y una dirección URL simple de administración para toda la organización.

Cada dirección URL simple de su organización debe tener un nombre único y no puede ser un prefijo de otra dirección URL simple (por ejemplo, no puede establecer SfB2015.contoso.com/Meet como su dirección URL simple y SfB2015.contoso.com/Meet/Dialin como la dirección URL simple de marcado). Los nombres de direcciones URL simples no pueden contener el FQDN de ninguna de sus agrupaciones ni ninguna información de https://FQDN:88/meet puerto (por ejemplo, no está permitido). Todas las direcciones URL simples deben comenzar con el prefijo https://. 

Las direcciones URL simples solo pueden contener caracteres alfanuméricos (es decir, a-z, A-Z, 0-9 y el punto (.). Si usa otros caracteres, es posible que las direcciones URL simples no funcionen de la manera esperada.

## <a name="changing-simple-urls-after-deployment"></a>Cambiar direcciones URL simples después de la implementación
<a name="BK_Valid"> </a>

Si cambia una dirección URL simple después de la implementación inicial, debe tener en cuenta cómo afecta el cambio a los registros DNS y los certificados para las direcciones URL simples. Si cambia la base de una dirección URL simple, debe cambiar también los certificados y los registros DNS. Por ejemplo, si cambia https://SfB2015.contoso.com/Meet de https://meet.contoso.com para cambia la dirección URL base de SfB2015.contoso.com a meet.contoso.com, tendrá que cambiar los registros DNS y los certificados para hacer referencia a meet.contoso.com. Si cambió la dirección URL simple de https://SfB2015.contoso.com/Meet a https://SfB2015.contoso.com/Meetings, la dirección URL base de SfB2015.contoso.com permanece igual, por lo que no es necesario realizar cambios en el certificado o DNS.

Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar **enable-CsComputer** en cada director y en el servidor front-end para registrar el cambio.

## <a name="naming-examples-for-simple-urls"></a>Ejemplos de nombres de direcciones URL simples
<a name="BK_Valid"> </a>

Hay tres opciones recomendadas para asignar nombres a las direcciones URL simples. La opción que elija tiene implicaciones en cuanto a la configuración de los registros A de DNS y los certificados que admiten direcciones URL simples. En cada opción, debe configurar una dirección URL simple para cada dominio SIP de su organización. 

Siempre necesita una única dirección URL en toda la organización para el acceso telefónico y otra para el administrador, independientemente del número de dominios SIP que tenga.

En la opción 1, puede crear un nuevo nombre de dominio SIP para cada dirección URL simple.

Si usa esta opción, necesita un registro DNS (A) independiente para cada dirección URL simple, y cada reunión dirección URL simple debe tener un nombre en los certificados.

**Opción de nomenclatura de URL simple 1**


| **Dirección URL sencilla** <br/> | **Ejemplo** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Reunión  <br/>          | https://meet.contoso.com, https://meet.fabrikam.com, y así sucesivamente (uno para cada dominio SIP de su organización)  <br/> |
| Acceso telefónico local  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Administrador  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

Con la opción 2, las direcciones URL simples se basan en el nombre de dominio SfB2015.contoso.com. Por lo tanto, solo necesita un registro DNS para habilitar los tres tipos de direcciones URL simples. Este registro A DNS hace referencia a SfB2015.contoso.com. Además, aún necesitará un registro DNS A para otros dominios SIP de su organización. 

**Opción de nomenclatura de URL simple 2**


| **Dirección URL sencilla** <br/> | **Ejemplo** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Reunión  <br/>          | https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, y así sucesivamente (uno para cada dominio SIP de su organización)  <br/> |
| Acceso telefónico local  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Administrador  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

La opción 3 es más útil si tiene muchos dominios SIP y desea que tengan diferentes direcciones URL simples, pero quiere minimizar los requisitos de certificados y registros DNS para estas direcciones URL simples. 

**Opción de nomenclatura de URL simple 3**


| **Dirección URL sencilla** <br/> | **Ejemplo** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Reunión  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| Acceso telefónico local  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Administrador  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Opción de recuperación ante desastres para direcciones URL simples
<a name="BK_Valid"> </a>

Si tiene varios sitios que contienen grupos front-end y su proveedor DNS admite GeoDNS, puede configurar los registros DNS para que las direcciones URL simples admitan la recuperación ante desastres, de modo que la funcionalidad de dirección URL simple continuará incluso si se produce un grupo de servidores front-end completo. Esta característica de recuperación ante desastres admite las direcciones URL sencillas de acceso telefónico y de reunión.

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

Puede configurar las mismas opciones para la dirección URL sencilla de acceso telefónico. Para ello, cree registros adicionales, como los que se han en el ejemplo anterior `dialin` , `meet` que se sustituirán por los registros DNS. Para la dirección URL sencilla de administrador, utilice una de las tres opciones que se mencionaron antes en esta sección.

Una vez que esta configuración esté definida, necesita utilizar una aplicación de supervisión para configurar la supervisión HTTP para que busque errores. Para obtener acceso externo, supervise para asegurarse de que HTTPS obtenga lyncdiscover.<sipdomain> las solicitudes al FQDN de la web externa o la dirección IP del equilibrador de carga de los dos grupos se han realizado correctamente. Por ejemplo, las siguientes solicitudes no tienen que contener ningún encabezado **ACCEPT** y necesitan devolver **200 OK**.

```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Para el acceso interno, necesita supervisar el puerto 5061 en el FQDN web interno o la dirección IP del equilibrador de carga para los dos grupos de servidores. Si se detecta cualquier problema de conectividad, la dirección VIP de estos grupos de servidores necesita cerrar los puertos 80, 443 y 4443.


