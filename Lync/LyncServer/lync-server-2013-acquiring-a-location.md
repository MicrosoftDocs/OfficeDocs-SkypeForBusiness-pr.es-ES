---
title: 'Lync Server 2013: Adquirir una ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb123cf2f38d935bc0cc641c67e6d0ff1d54e4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>Adquirir una ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-06_

En una implementación de Lync Server 2013 E9-1-1, cada cliente de Lync o Lync Phone Edition conectado internamente adquiere su propia ubicación. Después del registro SIP, el cliente brinda toda la información de conectividad de red que él conoce sobre él en una solicitud de ubicación en el servicio de información de ubicación, que es un servicio Web respaldado por una base de datos de SQL Server replicada. Cada grupo de sitios central tiene un servicio de información de ubicación, que usa la información de la red para consultar sus registros en busca de una ubicación coincidente. Si hay una coincidencia, el servicio de información de ubicación devuelve una ubicación al cliente. Si no hay una coincidencia, puede que se pida al usuario que escriba una ubicación manualmente (según la configuración de la directiva de ubicación). Los datos de ubicación se transmiten de vuelta al cliente en un formato XML estandarizado del Grupo de trabajo de ingeniería de Internet (IETF) conocido como Objeto de ubicación para formato de datos de información sobre presencia (PIDF-LO).

El cliente de Lync Server incluye los datos de PIDF como parte de una llamada de emergencia y el proveedor de servicios E9-1-1 usa estos datos para determinar el PSAP adecuado y enrutar la llamada a ese PSAP junto con el ESQK correcto, lo que permite al PSAP distribuidor obtener el Ubicación del autor de la llamada.

En el siguiente diagrama se muestra cómo un cliente de Lync Server adquiere una ubicación (excepto para el método de ubicación basado en direcciones MAC del cliente de terceros):

![Cómo obtiene el cliente un diagrama de ubicación] (images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Cómo obtiene el cliente un diagrama de ubicación")

Para que un cliente adquiera una ubicación, es preciso seguir estos pasos:

1.  El administrador rellena la base de datos del servicio de información de ubicación con el Wiremap de red (tablas que asignan varios tipos de direcciones de red a las ubicaciones de respuesta de emergencia correspondientes (ERLs)).

2.  Si utiliza un proveedor de servicio E9-1-1 para troncos SIP, el administrador validará las partes de dirección postal de las ERL con una base de datos de guía de direcciones principal (MSAG) mantenida por el proveedor del servicio E9-1-1. Si utiliza una puerta de enlace ELIN, el administrador se asegurará de que la portadora RTC cargue las ELIN a la base de datos de identificación automática de ubicaciones (ALI).

3.  Durante el registro o cuando se produce un cambio en la red, un cliente conectado internamente envía una solicitud de ubicación que contiene las direcciones de red detectadas del cliente al servicio de información de ubicación.

4.  El servicio de información de ubicación consulta sus registros publicados en busca de una ubicación y, si se encuentra una coincidencia, devuelve el ERL al cliente con el formato PIDF-es.

</div>

<span> </span>

</div>

</div>

</div>

