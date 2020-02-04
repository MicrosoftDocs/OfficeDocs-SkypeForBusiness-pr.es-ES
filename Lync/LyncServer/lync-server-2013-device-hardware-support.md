---
title: 'Lync Server 2013: Compatibilidad con hardware de dispositivos'
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
ms.openlocfilehash: ea720eda982ab20333e56de268085a706ab2cdc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a>Compatibilidad con hardware de dispositivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-12-14_

Las configuraciones de hardware específicas deben estar vigentes antes de implementar los teléfonos IP y los dispositivos analógicos.

Teléfonos IP que ejecutan Lync Phone Edition compatibilidad con el protocolo de descubrimiento de nivel de vínculo: detección de puntos de conexión de medios (LLDP-MED) y alimentación a través de Ethernet (PoE).Para aprovechar LLDP-MED, el switch debe ser compatible con IEEE 802.1 AB y ANSI/and-1057. Para aprovechar las ventajas de PoE, el conmutador debe ser compatible con PoE 802.3 AF o 802.3 en.

Para habilitar LLDP-MED, el administrador debe habilitar LLDP mediante la ventana cambiar consola y configurar la Directiva de red LLDP-MED con la identificación de voz VLAN correcta.

Además, si su implementación incluye dispositivos analógicos, debe configurar la puerta de enlace analógica para usar Lync Server, y la puerta de enlace debe ser una de las siguientes:

  - Un adaptador de teléfono analógico (ATA)

  - Una puerta de enlace analógica RTC

  - Un dispositivo de sucursal con la que se incluye una puerta de enlace analógica RTC

  - Un dispositivo de sucursal con la que se incluye una puerta de enlace RTC que se comunica con un ATA

Para obtener información sobre cómo configurar una puerta de enlace analógica, consulte "planear la implementación de [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) dispositivos analógicos" en la biblioteca de TechNet de 2010 de Lync Server. (Los dispositivos analógicos funcionan de la misma manera en Lync Server 2013 que en Lync Server 2010).

<div>


> [!IMPORTANT]  
> Puede configurar el modificador para una 9-1-1 mejorada (E9-1-1), si el modificador lo admite.



</div>

</div>

<span> </span>

</div>

</div>

</div>

