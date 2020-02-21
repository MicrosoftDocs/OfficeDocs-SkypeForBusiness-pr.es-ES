---
title: 'Lync Server 2013: adquisición de una ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88ed32ed07f709e0a047e8fc07e9124bc129adca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>Adquirir una ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-06-06_

En una implementación de Lync Server 2013 E9-1-1, cada cliente conectado internamente a Lync o Lync Phone Edition adquiere su propia ubicación de forma activa. Después del registro SIP, el cliente facilita toda la información de conectividad de red que se conoce a sí misma en una solicitud de ubicación en el servicio de información de ubicaciones, que es un servicio Web respaldado por una base de datos replicada de SQL Server. Cada grupo de sitio central tiene un servicio de información de ubicación, que usa la información de red para consultar sus registros en busca de una ubicación coincidentes. Si hay una coincidencia, el servicio de información de ubicación devuelve una ubicación al cliente. Si no hay ninguna coincidencia, puede que se pida al usuario que escriba una ubicación manualmente (según la configuración de la directiva de ubicación). Los datos de ubicación se devuelven al cliente en un formato XML estándar de grupo de trabajo de ingeniería de Internet (IETF) denominado PIDF-LO (Presence Information Data Format Location Object).

El cliente de Lync Server incluye los datos de PIDF-lo como parte de una llamada de emergencia y el proveedor de servicios E9-1-1 utiliza estos datos para determinar el PSAP adecuado y enrutar la llamada a dicho PSAP junto con el ESQK correcto, lo que permite que el distribuidor de PSAP obtenga el Ubicación del autor de la llamada.

El siguiente diagrama muestra cómo un cliente de Lync Server adquiere una ubicación (excepto para el método de ubicación basado en direcciones MAC de cliente de terceros):

![Modo en que el cliente adquiere un diagrama de ubicación](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Modo en que el cliente adquiere un diagrama de ubicación")

Para que el cliente pueda adquirir la ubicación, deben llevarse a cabo los pasos siguientes:

1.  El administrador rellena la base de datos del servicio de información de ubicaciones con el cableado de red (tablas que asignan varios tipos de direcciones de red a las correspondientes ubicaciones de respuesta de emergencia (ERL)).

2.  Si usa un proveedor de servicios E9-1-1 mediante troncos SIP, el administrador valida la parte de la dirección postal de la ERL con una base de datos de guía de direcciones principal (MSAG) del proveedor de servicios E9-1-1. Si usa una puerta de enlace ELIN, el administrador se asegura de que el operador de RTC cargue los ELIN en la base de datos de identificación de ubicación automática (ALI).

3.  Durante el registro o cuando se produce un cambio en la red, un cliente conectado internamente envía una solicitud de ubicación que contiene las direcciones de red detectadas del cliente al servicio de información de ubicación.

4.  El servicio de información de ubicación consulta sus registros publicados para buscar una ubicación y, si se encuentra una coincidencia, devuelve el ERL al cliente en formato PIDF-lo.

</div>

<span> </span>

</div>

</div>

</div>

