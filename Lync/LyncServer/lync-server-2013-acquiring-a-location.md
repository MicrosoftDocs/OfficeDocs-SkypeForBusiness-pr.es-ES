---
title: 'Lync Server 2013: Adquirir una ubicación'
TOCTitle: Adquirir una ubicación
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48276216
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Adquirir una ubicación en Lync Server 2013

 

_**Última modificación del tema:** 2012-06-06_

En una implementación Lync Server 2013 E9-1-1, cada cliente de Lync o Lync Phone Edition conectado internamente adquiere activamente su propia ubicación. Tras el registro de SIP, el cliente facilita toda la información de conectividad de red que conozca sobre sí mismo en una solicitud de ubicación al Servicio de información de ubicaciones, que es un servicio web respaldado por una base de datos replicada de SQL Server. Cada grupo de servidores de un sitio central tiene un Servicio de información de ubicaciones, que usa la información de red para consultar sus registros y buscar una ubicación que coincida. Si hay una coincidencia, el Servicio de información de ubicaciones devuelve una ubicación al cliente. Si no hay una coincidencia, puede que se pida al usuario que escriba una ubicación manualmente (según la configuración de la directiva de ubicación). Los datos de ubicación se transmiten de vuelta al cliente en un formato XML estandarizado del Grupo de trabajo de ingeniería de Internet (IETF) conocido como Objeto de ubicación para formato de datos de información sobre presencia (PIDF-LO).

El cliente de Lync Server incluye los datos de PIDF-LO como parte de una llamada de emergencia y el proveedor del servicio E9-1-1 utiliza dichos datos para determinar el PSAP apropiado y enrutar la llamada a dicho PSAP siguiendo el ESQK correcto, lo que permite al distribuidor de PSAP obtener la ubicación del autor de la llamada.

El siguiente diagrama muestra cómo adquiere una ubicación un cliente de Lync Server (excepto en el método de ubicación basado en direcciones MAC en clientes de terceros):

![Diagrama sobre cómo adquiere una ubicación el cliente](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Diagrama sobre cómo adquiere una ubicación el cliente")

Para que un cliente adquiera una ubicación, deben seguirse estos pasos:

1.  El administrador rellena la base de datos del Servicio de información de ubicaciones con la asignación de cable de red (tablas que asignan los diversos tipos de direcciones de red a las correspondientes ubicaciones de respuesta de emergencia, ERL).

2.  Si utiliza un proveedor de servicio E9-1-1 para troncos SIP, el administrador validará las partes de dirección postal de las ERL con una base de datos de guía de direcciones principal (MSAG) mantenida por el proveedor del servicio E9-1-1. Si utiliza una puerta de enlace ELIN, el administrador se asegurará de que la portadora RTC cargue las ELIN a la base de datos de identificación automática de ubicaciones (ALI).

3.  Durante el registro o cada vez que se produzca un cambio en la red, un cliente conectado internamente enviará al Servicio de información de ubicaciones una solicitud de ubicación que contendrá las direcciones de red del cliente que se hayan detectado.

4.  El Servicio de información de ubicaciones consulta en sus registros publicados para buscar una ubicación y, si encuentra una coincidencia, devuelve al cliente la ERL en formato PIDF-LO.

