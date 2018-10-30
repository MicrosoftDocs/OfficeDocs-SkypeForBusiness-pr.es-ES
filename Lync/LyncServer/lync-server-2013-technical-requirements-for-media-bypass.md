---
title: "Lync Server 2013 : Conf. tech. requise pour la déviation du trafic multimédia"
TOCTitle: Requisitos técnicos para la omisión de medios
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48275435
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos técnicos para la omisión de medios en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

En cada llamada a la RTC, el Servidor de mediación determina si los medios del extremo de origen de Lync se pueden enviar directamente a un componente del mismo nivel del Servidor de mediación sin recorrer el Servidor de mediación. El componente del mismo nivel puede ser una puerta de enlace RTC, un sistema IP-PBX o un controlador SBC en un proveedor de servicios de telefonía por Internet (ITSP) asociado con el tronco entre el servidor de mediación hacia el que se ha enrutado la llamada.

Puede emplearse el desvío de medios cuando se reúnen los siguientes requisitos:

  - Un componente del mismo nivel del Servidor de mediación debe admitir las funcionalidades necesarias para el desvío de medios, siendo la más importante la capacidad de controlar varias respuestas bifurcadas (denominadas “diálogos iniciales”). Póngase en contacto con el fabricante de su puerta de enlace, sistema PBX o ITSP para obtener el valor del número máximo de diálogos iniciales que la puerta de enlace, el sistema PBX o el SBC puede aceptar.

  - El componente del mismo nivel del Servidor de mediación debe aceptar el tráfico de medios directamente desde los extremos de Lync. Muchos ITSP permiten que sus SBC reciban tráfico únicamente desde el Servidor de mediación. Póngase en contacto con su ITSP para averiguar si su SBC acepta el tráfico de medios directamente desde los extremos de Lync.

  - Los clientes de Lync y un componente del mismo nivel del Servidor de mediación deben estar bien conectados, lo que significa que deben estar en la misma región de red o en sitios de red que se conecten a la región sobre vínculos WAN sin límites de ancho de banda.

## Vea también

#### Conceptos

[Modos de omisión de medios en Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Omisión de medios y control de admisión de llamadas en Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

