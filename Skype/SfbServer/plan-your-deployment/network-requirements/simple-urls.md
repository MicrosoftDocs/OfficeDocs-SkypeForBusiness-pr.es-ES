---
title: Requisitos de DNS para direcciones URL simples en Skype para Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Resumen: Revisar las consideraciones de dirección URL sencilla en este tema antes de implementar los registros DNS de Skype para Business Server 2015.'
ms.openlocfilehash: 87346a7c4c03837e5ebfdf0143cdb7c786f0e43b
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server-2015"></a>Requisitos de DNS para direcciones URL simples en Skype para Business Server 2015
 
**Resumen:** Revisar las consideraciones de dirección URL sencilla en este tema antes de implementar los registros DNS de Skype para Business Server 2015.
  
Direcciones URL simples facilitan la unión de las reuniones para los usuarios y asegúrese de obtener a Skype para negocios herramientas administrativas más fácil para los administradores. Direcciones URL simples utilizan su propio dominio, que no puede coincidir con cualquiera de los dominios SIP que se defina. 
  
Skype para Business Server admite las siguientes tres URL simples: satisfacer, acceso telefónico y administrador. Es necesario configurar direcciones URL simples para satisfacer y con acceso telefónico y la dirección URL de administración simple es opcional. Los registros del sistema de nombres de dominio (DNS) necesarios para admitir direcciones URL sencillas varían en función de la forma en que se hayan definido dichas direcciones URL sencillas y de si desea admitir la recuperación ante desastres para las direcciones URL sencillas. 
  
## <a name="simple-url-scope"></a>Ámbito de dirección URL simple

Puede configurar las URL simples para tienen ámbito global o puede especificar diferentes direcciones URL simples para cada sitio central de la organización. Si se especifican una dirección URL simple global y una dirección URL simple, la dirección URL del sitio simple tiene prioridad. 
  
En la mayoría de los casos, recomendamos que establezca simples direcciones URL sólo en el nivel global, para que la dirección URL sencilla satisfacer de un usuario no cambia si se mueven de un sitio a otro. La excepción sería organizaciones que necesitan utilizar números de teléfono diferentes para usuarios de acceso telefónico en lugares diferentes. Tenga en cuenta que si establece una dirección URL simple (como la URL simple Dial in) en un sitio sea una dirección URL simple de nivel de sitio, debe establecer las otras direcciones URL simples también en ese sitio sea también de nivel de sitio.
  
Puede establecer URL simples globales en el generador de topología. Para establecer una dirección URL simple a nivel de sitio, utilice el cmdlet Set-CsSimpleURLConfiguration.
  
Definir una dirección URL simple también requerirá establecer un registro A o AAAA en la configuración de DNS.
  
## <a name="simple-url-naming-and-validation-rules"></a>Reglas de nomenclatura y de validación de dirección URL simples
<a name="BK_Valid"> </a>

Generador de topología y el Skype para los cmdlets del Shell de administración de servidor de Business aplican varias reglas de validación para las URL simples. Es necesario establecer direcciones URL simples para satisfacer y marcado, pero es opcional establecer uno para Admin. Cada dominio SIP debe tener una URL simple satisfacer independiente, pero necesita sólo un marcado simple dirección URL y una administración simple de toda su organización.
  
Cada dirección URL sencilla en su organización debe tener un nombre único y no puede ser un prefijo de otra dirección URL simple (por ejemplo, podría no establece SfB2015.contoso.com/Meet como dirección URL simple satisfacer y SfB2015.contoso.com/Meet/Dialin como dirección URL simple de marcado). Nombres simples de dirección URL no pueden contener el FQDN de cualquiera de los grupos, o cualquier información de puerto (por ejemplo, https://FQDN:88/meet no se permite). Todas las direcciones URL simples deben comenzar con el prefijo https://. 
  
Direcciones URL simples pueden contener sólo caracteres alfanuméricos (es decir,-a-z, A-z, 0-9 y el punto (.). Si utiliza otros caracteres, la simple URL podrían no funcionar como se esperaba.
  
## <a name="changing-simple-urls-after-deployment"></a>Cambiar direcciones URL Simple tras su distribución
<a name="BK_Valid"> </a>

Si cambia una dirección URL simple después de la implementación inicial, debe ser consciente de cómo el cambio afecta a los registros DNS y los certificados para direcciones URL simples. Si cambia la base de una dirección URL simple, debe cambiar los registros DNS y también los certificados. Por ejemplo, al cambiar de https://SfB2015.contoso.com/Meet a https://meet.contoso.com cambia la dirección URL base de SfB2015.contoso.com a meet.contoso.com, por lo que necesitará cambiar los registros DNS y los certificados para hacer referencia a meet.contoso.com. Si cambia la dirección URL simple de https://SfB2015.contoso.com/Meet a https://SfB2015.contoso.com/Meetings, la dirección URL base de SfB2015.contoso.com sigue siendo el mismo, así que no hay DNS o es necesario realizar cambios de certificado.
  
Sin embargo, cada vez que cambia un nombre de dirección URL simple, debe ejecutar **Enable-CsComputer** en cada Director y el servidor Front-End para registrar el cambio.
  
## <a name="naming-examples-for-simple-urls"></a>Ejemplos de nombres para direcciones URL Simple
<a name="BK_Valid"> </a>

Hay tres opciones recomendadas para nombrar las URL simples. Opción que usted elija tiene implicaciones en cómo configurar tus registros DNS A y certificados que admiten direcciones URL simples. En cada opción, debe configurar una dirección URL simple satisfacer para cada dominio SIP de su organización. 
  
Debe siempre una sola dirección URL sencilla en toda la organización para el acceso telefónico y otra para Admin, no importa cuántos dominios SIP tiene.
  
En la opción 1, crear un nuevo nombre de dominio SIP para cada URL simple.
  
Si utiliza esta opción, necesita un registro DNS A independiente para cada dirección URL simple y cada URL simple satisfacer deben denominarse en sus certificados.
  
**Opción de nomenclatura URL simple 1**

|**Dirección URL sencilla** <br/> |**Ejemplo** <br/> |
|:-----|:-----|
|Reunión  <br/> |https://meet.contoso.com, https://meet.fabrikam.com, y así sucesivamente (una para cada dominio SIP de su organización)  <br/> |
|Acceso telefónico local  <br/> |https://dialin.contoso.com  <br/> |
|Administrador  <br/> |https://admin.contoso.com  <br/> |
   
Con la opción 2, simples direcciones URL se basan en el nombre de dominio SfB2015.contoso.com. Por lo tanto, es necesario un único registro A DNS que permite a los tres tipos de direcciones URL simples. Hace referencia a este registro DNS A SfB2015.contoso.com. Además, seguirá necesitando registros DNS A independientes para otros dominios SIP de su organización. 
  
**Opción de nomenclatura URL simple 2**

|**Dirección URL sencilla** <br/> |**Ejemplo** <br/> |
|:-----|:-----|
|Reunión  <br/> |https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, y así sucesivamente (una para cada dominio SIP de su organización)  <br/> |
|Acceso telefónico local  <br/> |https://SfB2015.contoso.com/Dialin  <br/> |
|Administrador  <br/> |https://SfB2015.contoso.com/Admin  <br/> |
   
La opción 3 es más útil si tiene varios dominios SIP, y desea tener direcciones URL simples satisfacer independientes pero desea minimizar los requisitos de registro y certificado DNS para estas direcciones URL simples. 
  
**Opción de nomenclatura URL simple 3**

|**Dirección URL sencilla** <br/> |**Ejemplo** <br/> |
|:-----|:-----|
|Reunión  <br/> |https://SfB2015.contoso.com/contosoSIPdomain/Meet  <br/> https://SfB2015.contoso.com/fabrikamSIPdomain/Meet  <br/> |
|Acceso telefónico local  <br/> |https://SfB2015.contoso.com/Dialin  <br/> |
|Administrador  <br/> |https://SfB2015.contoso.com/Admin  <br/> |
   
## <a name="disaster-recovery-option-for-simple-urls"></a>Opción de recuperación ante desastres para direcciones URL simples
<a name="BK_Valid"> </a>

Si tiene varios sitios que contienen grupos de Front-End y tu proveedor de DNS admite GeoDNS, puede configurar los registros DNS para direcciones URL Simple permitir la recuperación ante desastres, para que la funcionalidad de URL Simple continúa incluso si falla un grupo completo de Front-End. Esta característica de recuperación ante desastres admite las direcciones URL sencillas de acceso telefónico y de reunión.
  
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
> Si su red utiliza hairpinning (todo el tráfico de la dirección URL sencilla a través del vínculo externo, incluido el tráfico que proviene de dentro de la organización de enrutamiento), entonces puede configurar la dirección externa de GeoDNS y resolver su URL simple satisfacer a sólo dirección externa.
  
Al utilizar este método, puede configurar cada dirección de GeoDNS para que utilice un método round robin para distribuir solicitudes en los dos grupos de servidores, o bien para que se conecte principalmente a un grupo de servidores (como el grupo de servidores más cercano) y utilizar el otro grupo solo en caso de que no se pueda establecer la conexión. 
  
Puede configurar las mismas opciones para la dirección URL sencilla de acceso telefónico. Para ello, crear registros adicionales como las del ejemplo anterior, sustituyendo `dialin` de `meet` en los registros DNS. Para la dirección URL sencilla de administrador, utilice una de las tres opciones que se mencionaron antes en esta sección.
  
Una vez que esta configuración esté definida, necesita utilizar una aplicación de supervisión para configurar la supervisión HTTP para que busque errores. Para obtener acceso externo, monitor para asegurarse de que lyncdiscover HTTPS GET.<sipdomain> las solicitudes web dirección IP de equilibrador FQDN o carga para los dos grupos externo están correctamente. Por ejemplo, las siguientes solicitudes no debe contener ningún encabezado **ACCEPT** y debe devolver **200 OK**.
  
```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Para el acceso interno, necesita supervisar el puerto 5061 en el FQDN web interno o la dirección IP del equilibrador de carga para los dos grupos de servidores. Si se detecta cualquier problema de conectividad, la dirección VIP de estos grupos de servidores necesita cerrar los puertos 80, 443 y 4443.
  

