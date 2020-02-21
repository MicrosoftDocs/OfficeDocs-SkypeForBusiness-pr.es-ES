---
title: Soporte de hardware para dispositivos de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6786d22d81f6b78d1e551d05f3d908876ca3068
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a>Compatibilidad de hardware de dispositivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-14_

Las configuraciones de hardware específicas deben estar en su ubicación antes de implementar los teléfonos IP y los dispositivos analógicos.

Los teléfonos IP que ejecutan Lync Phone Edition admiten el protocolo de detección de niveles de vínculos: detección de extremos de medios (LLDP-MED) y Power over Ethernet (PoE).Para usar el protocolo LLDP-MED, el conmutador debe admitir IEEE802.1AB y ANSI/TIA-1057. Para usar PoE, el conmutador debe admitir PoE802.3AF o 802.3at.

Para habilitar LLDP-MED, el administrador debe habilitar LLDP mediante la ventana de la consola del conmutador y establecer la directiva de red LLDP-MED con el Id. de VLAN de voz correcto.

Además, si la implementación incluye dispositivos analógicos, debe configurar la puerta de enlace analógica para que use Lync Server, y la puerta de enlace debe ser una de las siguientes:

  - Un adaptador de teléfono analógico (ATA)

  - Una puerta de enlace analógica de RTC

  - Una aplicación de sucursal con funciones de supervivencia que incluya una puerta de enlace analógica de RTC

  - Una aplicación de sucursal con funciones de supervivencia que incluya una puerta de enlace RTC que se comunique con un ATA

Para obtener información sobre cómo configurar una puerta [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) de enlace analógica, vea "planeación para implementar dispositivos analógicos" en la biblioteca de TechNet de 2010 de Lync Server. (Los dispositivos analógicos funcionan del mismo modo en Lync Server 2013 que en Lync Server 2010).

<div>


> [!IMPORTANT]  
> Puede configurar el conmutador para Enhanced 9-1-1 (E9-1-1), si el conmutador lo admite.



</div>

</div>

<span> </span>

</div>

</div>

</div>

