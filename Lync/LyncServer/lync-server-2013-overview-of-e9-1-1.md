---
title: 'Lync Server 2013: información general sobre E9-1-1'
description: 'Lync Server 2013: información general sobre E9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fa13d8bfd1c273e8cbbb1d70f1fb3d733ac6167
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571906"
---
# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Información general sobre E9-1-1 en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Microsoft Lync Server 2013 admite llamadas mejoradas 9-1-1 (E9-1-1) desde los clientes de Lync y los dispositivos de Lync Phone Edition. Cuando configure Lync Server para E9-1-1, las llamadas de emergencia realizadas desde Lync 2013 o Lync Phone Edition incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos del servicio de información de ubicación. Las ERL se componen de direcciones civiles (es decir, postales) e información adicional que ayuda a identificar con mayor precisión una ubicación en edificios de oficinas y otras instalaciones con varios inquilinos. Cuando un usuario realiza una llamada de emergencia, Lync Server enruta el audio de la llamada, junto con la ubicación y la información de devolución de llamada, a través de un servidor de mediación a un proveedor de servicios E9-1-1. Desde aquí se facilita la ubicación del autor de la llamada junto con una clave de consulta de servicios de emergencia (ESQK) que permite al PSAP buscar la ERL de esta persona.

Lync Server admite dos métodos para el enrutamiento de llamadas de emergencia a un proveedor de servicios E9-1-1:

  - Una conexión de enlace troncal SIP (Protocolo de inicio de sesión) a un proveedor de servicios E9-1-1 cualificado.

  - Una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios E9-1-1 basado en una Red telefónica conmutada (RTC).

Cuando se usa un proveedor de servicios E9-1-1 de tronco SIP, se agrega ERL a la base de datos del servicio de información de ubicación y, a continuación, se validan las ubicaciones con una guía de dirección principal (MSAG) mantenida por el proveedor de servicios E9-1-1. Si el proveedor recibe una llamada que no cuenta con información de ubicación o cuya ubicación no se ha validado en la MSAG, redirige la llamada a un Centro de respuesta de llamadas SOS (ECRC) nacional o regional, que dispone de personal especialmente preparado para obtener de forma oral la ubicación del autor de la llamada (si es posible) y redirigir manualmente la llamada al PSAP correspondiente. Algunos proveedores de servicios E9-1-1 de enlace troncal SIP también proporcionan a los clientes un número de marcado directo (DID) de RTC para el ECRC, que constituye un medio alternativo de enrutamiento de las llamadas al 9-1-1 si por algún motivo se produce un error en el enlace troncal SIP.

A diferencia de la multiplexación por división de tiempo (TDM) y los teléfonos de central de conmutación (PBX) basados en IP, que tienen ubicaciones fijas, un punto de conexión de Lync puede ser muy móvil. Al implementar la característica E9-1-1, Lync Server ayuda a garantizar que no importa dónde se encuentre el autor de la llamada, a que la llamada de emergencia se puede enrutar a la PSAP que atiende la ubicación del autor de la llamada. Por ejemplo, si la oficina principal de un usuario está ubicada en Redmond (Washington), pero el usuario realiza una llamada SOS desde el equipo de una sucursal en Wichita (Kansas), el proveedor de servicios E9-1-1 basado en RTC o de enlace troncal SIP redirigirá la llamada al PSAP de Wichita, y no al de Redmond.

Cuando se usa una puerta de enlace ELIN, también se agrega ERL a la base de datos del servicio de información de ubicación, pero también se incluye un número de ELIN para cada ubicación. El número ELIN pasa a ser el número de llamada SOS durante la llamada. Debe comprobar que el proveedor de RTC carga los ELIN en una base de datos de identificación de ubicación automática (ALI).

<div>


> [!NOTE]  
> Los dispositivos analógicos conectados a Lync no pueden recibir información de ubicación del servicio de información de ubicación o la ubicación de transmisión al proveedor de servicios E9-1-1. Si usa la opción del proveedor de servicios E9-1-1 de enlace troncal SIP y tiene que admitir llamadas E9-1-1 desde teléfonos analógicos, tiene dos opciones: 
> <UL>
> <LI>
> <P>Opción tradicional PS <STRONG>-Ali</STRONG> &nbsp; &nbsp; &nbsp; Si tiene puertas de enlace RTC locales en cada sitio en el que se implementan los teléfonos analógicos y cada teléfono analógico tiene un, puede aprovisionar la ubicación del dispositivo analógico directamente con un proveedor de servicios de conmutadores privados o de identificación de ubicación automática (PS-ALI). En este caso, debe configurar directivas de voz específicas de Lync y asignarlas a los objetos contacto del dispositivo analógico para que las llamadas E9-1-1 que se realizan desde esos teléfonos se redirijan directamente a través de la puerta de enlace local al proveedor de RTC del sitio (en lugar de redirigir la llamada a un enlace troncal SIP del proveedor de servicios E9-1-1). Cuando se realiza una llamada SOS, una base de datos de un proveedor de PS-ALI asociado con el enlace troncal de RTC asigna el DID de cada teléfono analógico a una ubicación física, y proporciona esta ubicación al PSAP. Estos registros deben actualizarse con el proveedor de servicios de PS-ALI cada vez que los teléfonos se desplazan a ERL diferentes.</P>
> <LI>
> <P>Opción del proveedor <STRONG>de servicios E9-1-1</STRONG> &nbsp; &nbsp; &nbsp; Puede registrar el analógico de teléfono analógico y su ERL correspondiente con el proveedor de servicios E9-1-1, si el proveedor de servicios E9-1-1 lo admite. Si el proveedor recibe una llamada de Lync Server que no incluye datos PIDF-lo, el proveedor puede ver si hay una coincidencia de base de datos en el número DID de la persona que llama. Mediante la ERL que se recupera desde su base de datos, el proveedor puede redirigir automáticamente la llamada SOS al PSAP correcto y este recibirá el DID del dispositivo analógico y un registro de ESQK que permite al distribuidor buscar la ubicación del autor de la llamada.</P></LI></UL>Si usa la opción de puerta de enlace de ELIN y necesita compatibilidad con las llamadas E9-1-1 desde teléfonos analógicos, puede dar la ubicación del dispositivo analógico directamente con el proveedor de servicios PS-ALI, como se describe en la primera opción mencionada anteriormente.</div>

Desde el punto de vista de Lync Server, el proceso de E9-1-1 se puede separar en dos fases:

  - Fase 1: adquisición de una ubicación

  - Fase 2: enrutamiento de la llamada SOS al proveedor de servicios E9-1-1

En esta sección se describe cómo funcionan estas fases.

Si va a configurar la infraestructura para detectar automáticamente la ubicación del cliente, primero debe decidir qué elementos de red usará para asignar los autores de las llamadas a las ubicaciones. Para obtener más información sobre las opciones posibles, consulte [definir los elementos de red que se usan para determinar la ubicación en Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).

<div>

## <a name="in-this-section"></a>En esta sección

  - [Adquirir una ubicación en Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Routing E9-1-1 calls by Using a SIP trunk in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN en Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

