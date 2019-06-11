---
title: 'Lync Server 2013: Información general sobre E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 144f189c119653ddb02316193e78b9156fad2278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Información general sobre E9-1-1 en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Microsoft Lync Server 2013 es compatible con las llamadas de 9-1-1 (E9-1-1) mejoradas desde los clientes de Lync y los dispositivos de Lync Phone Edition. Al configurar Lync Server para E9-1-1, las llamadas de emergencia realizadas desde Lync 2013 o Lync Phone Edition incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos del servicio de información de ubicación. Las ERL se componen de direcciones civiles (es decir, postales) e información adicional que ayuda a identificar con mayor precisión una ubicación en edificios de oficinas y otras instalaciones con varios inquilinos. Cuando un usuario realiza una llamada de emergencia, Lync Server enruta el audio de la llamada, junto con la información de la ubicación y la devolución de llamada, a través de un servidor de mediación a un proveedor de servicios E9-1-1. Desde aquí se facilita la ubicación del autor de la llamada junto con una clave de consulta de servicios de emergencia (ESQK) que permite al PSAP buscar la ERL de esta persona.

Lync Server admite dos métodos para el enrutamiento de llamadas de emergencia a un proveedor de servicios E9-1-1:

  - Una conexión de enlace troncal SIP (Protocolo de inicio de sesión) a un proveedor de servicios E9-1-1 cualificado.

  - Una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios E9-1-1 basado en una Red telefónica conmutada (RTC).

Cuando usa un proveedor de servicios E9-1-1 de SIP, agrega ERLs a la base de datos de servicios de información de ubicación y, a continuación, valida las ubicaciones con una guía de dirección maestra (MSAG) que mantiene el proveedor de servicios E9-1-1. Si el proveedor recibe una llamada que no cuenta con información de ubicación o cuya ubicación no se ha validado en la MSAG, redirige la llamada a un Centro de respuesta de llamadas SOS (ECRC) nacional o regional, que dispone de personal especialmente preparado para obtener de forma oral la ubicación del autor de la llamada (si es posible) y redirigir manualmente la llamada al PSAP correspondiente. Algunos proveedores de servicios E9-1-1 de enlace troncal SIP también proporcionan a los clientes un número de marcado directo (DID) de RTC para el ECRC, que constituye un medio alternativo de enrutamiento de las llamadas al 9-1-1 si por algún motivo se produce un error en el enlace troncal SIP.

A diferencia de la multiplexación de división de tiempo (TDM) y los teléfonos de central de conmutación (PBX) basados en IP, que tienen ubicaciones fijas, un punto de conexión de Lync puede ser muy móvil. Al implementar la característica E9-1-1, Lync Server le ayuda a garantizar que no importa dónde se encuentre la persona que llama, la llamada de emergencia se puede enrutar al PSAP que sirve la ubicación de la persona que llama. Por ejemplo, si la oficina principal de un usuario está ubicada en Redmond (Washington), pero el usuario realiza una llamada SOS desde el equipo de una sucursal en Wichita (Kansas), el proveedor de servicios E9-1-1 basado en RTC o de enlace troncal SIP redirigirá la llamada al PSAP de Wichita, y no al de Redmond.

Al usar una puerta de enlace de ELIN, también puede Agregar ERLs a la base de datos de servicios de información de ubicación, pero también puede incluir un número de ELIN para cada ubicación. El número ELIN pasa a ser el número de llamada SOS durante la llamada. Es preciso comprobar que el proveedor de RTC carga los ELIN en una base de datos de identificación de ubicación automática (ALI).

<div>


> [!NOTE]  
> Los dispositivos analógicos conectados a Lync no pueden recibir información de la ubicación del servicio de información de ubicación o la ubicación de transmisión al proveedor de servicios E9-1-1. Si usa la opción del proveedor de servicios E9-1-1 de enlace troncal SIP y tiene que admitir llamadas E9-1-1 desde teléfonos analógicos, tiene dos opciones: 
> <UL>
> <LI>
> <P><STRONG></STRONG>&nbsp;Opción&nbsp;PS&nbsp;-Ali tradicional si tiene puertas de enlace RTC locales en cada sitio en el que se implementan teléfonos analógicos y cada teléfono analógico tiene un sistema, puede aprovisionar la ubicación del dispositivo analógico directamente con un conmutador privado o automático Proveedor de servicios de identificación de ubicación (PS-ALI). En este caso, debe configurar directivas de Skype Lync especialmente diseñadas y asignarlas a los objetos de contacto de dispositivos analógicos para que las llamadas de E9 desde esos teléfonos enruten directamente a través de la puerta de enlace local al proveedor de RTC que presta servicio al sitio (en lugar de enrutar el llamada a un proveedor de servicios de E9-1-1 de SIP). Cuando se realiza una llamada SOS, una base de datos de un proveedor de PS-ALI asociado con el enlace troncal de RTC asigna el DID de cada teléfono analógico a una ubicación física, y proporciona esta ubicación al PSAP. Estos registros necesitan actualizarse con el proveedor de servicios de PS-ALI cada vez que los teléfonos se desplazan a ERL diferentes.</P>
> <LI>
> <P><STRONG></STRONG>&nbsp;Opción&nbsp;de&nbsp;proveedor de servicios E9-1-1 puede registrar el DIDs de teléfono analógico y su ERLs correspondiente con el proveedor de servicios E9-1-1, si es compatible con el proveedor de servicios E9-1-1. Si el proveedor recibe una llamada de Lync Server que no incluye datos de PIDF-lo, el proveedor puede ver si hay una coincidencia de base de datos en el número de "la parte de la llamada". Por medio de la ERL que se recupera desde su base de datos, el proveedor puede redirigir automáticamente la llamada SOS al PSAP correcto y este recibirá el DID del dispositivo analógico y un registro de ESQK que permite al distribuidor buscar la ubicación del autor de la llamada.</P></LI></UL>Si usa la opción de puerta de enlace de ELIN y necesita compatibilidad con las llamadas E9-1-1 desde teléfonos analógicos, puede dar la ubicación del dispositivo analógico directamente con el proveedor de servicios PS-ALI, como se describe en la primera opción mencionada anteriormente.</div>

Desde una perspectiva de Lync Server, el E9-1-1 se puede dividir en dos fases:

  - Fase 1: adquisición de una ubicación

  - Fase 2: enrutamiento de la llamada SOS al proveedor de servicios E9-1-1

En esta sección se describe cómo funcionan estas fases.

Si va a configurar la infraestructura para detectar automáticamente la ubicación del cliente, primero necesita decidir qué elementos de red usará para asignar los autores de las llamadas a las ubicaciones. Para obtener más información sobre las posibles opciones, vea [definir los elementos de red usados para determinar la ubicación en Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).

<div>

## <a name="in-this-section"></a>En esta sección

  - [Adquirir una ubicación en Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Enrutamiento de llamadas E9-1-1 mediante un SIP troncal en Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN en Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

