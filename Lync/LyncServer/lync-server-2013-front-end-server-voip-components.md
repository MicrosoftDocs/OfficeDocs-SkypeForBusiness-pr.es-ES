---
title: 'Lync Server 2013: componentes de VoIP del servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3558d230b1fb767f0e7844be3894b579149c3f6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Componentes de VoIP de servidor front-end para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Los componentes de VoIP que se encuentran en los servidores front-end son los siguientes:

  - Servicio de conversión

  - Componente de enrutamiento de entrada

  - Componente de enrutamiento de salida

  - Componente de enrutamiento de mensajería unificada (UM) de Exchange

  - Componente de enrutamiento entre clústeres

  - [Componente de servidor de mediación de Lync Server 2013](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a>Servicio de conversión

El servicio de conversión es el componente del servidor que se encarga de convertir un número marcado al formato E.164 u otro formato, de acuerdo con las reglas de normalización definidas por el administrador. El servicio de conversión puede convertir a formatos distintos de E.164 si la organización utiliza un sistema de numeración privado, o una puerta de enlace o PBX que no admite E.164.

</div>

<div>

## <a name="inbound-routing-component"></a>Componente de enrutamiento de entrada

El componente de enrutamiento entrante gestiona las llamadas entrantes en gran medida según las preferencias especificadas por los usuarios en sus clientes de telefonía empresarial. También facilita las llamadas delegadas y las llamadas simultáneas, si el usuario las configura. Por ejemplo, los usuarios especifican si las llamadas sin contestar se reenvían o simplemente se registran para su notificación. Si el desvío de llamadas está habilitado, los usuarios pueden especificar si las llamadas no contestadas deben desviarse a otro número o a un servidor de mensajería unificada de Exchange configurado para proporcionar respuesta a llamadas. El componente de enrutamiento entrante se instala de forma predeterminada en todos los servidores Standard Edition y servidores front-end.

</div>

<div>

## <a name="outbound-routing-component"></a>Componente de enrutamiento de salida

El componente de enrutamiento de salida redirige las llamadas a destinos PBX o RTC. Aplica reglas de autorización de llamadas, que se definen en la directiva de voz del usuario, a los autores de las llamadas y determina la puerta de enlace RTC óptima para redirigir cada llamada. El componente de enrutamiento de salida se instala de forma predeterminada en todos los servidores Standard Edition y servidores front-end.

La lógica de enrutamiento que utiliza el componente de enrutamiento de salida la configuran, en gran medida, los administradores de red o de telefonía de acuerdo con los requisitos de sus organizaciones.

</div>

<div>

## <a name="exchange-um-routing-component"></a>Componente de enrutamiento de mensajería unificada (UM) de Exchange

El componente de enrutamiento de MU de Exchange administra el enrutamiento entre Lync Server y los servidores que ejecutan mensajería unificada (UM) de Exchange para integrar Lync Server con características de mensajería unificada.

El componente de enrutamiento de MU de Exchange también controla el redireccionamiento del correo de voz a través de la RTC si los servidores de mensajería unificada de Exchange no están disponibles. Si tiene usuarios de Enterprise Voice en sitios de sucursales que no tienen un vínculo WAN resistente a un sitio central, el dispositivo de sucursal con la que se realiza el despliegue en el sitio de la sucursal ofrece la supervivencia del correo de voz durante una interrupción de la WAN. Cuando el vínculo WAN no está disponible, el equipo con la aplicación con supervivencia hace lo siguiente:

  - Desvía las llamadas no respondidas a través de la RTC al servidor de mensajería unificada de Exchange del sitio central.

  - Proporciona al usuario la posibilidad de recuperar mensajes de correo de voz a través de la RTC.

  - Pone en cola las notificaciones de las llamadas perdidas y, luego, las carga en el servidor de mensajería unificada (UM) de Exchange cuando el vínculo WAN se restaura.

Para habilitar el redireccionamiento del correo de voz, recomendamos que el administrador de Exchange configure el operador automático de MU de Exchange (AA) para que solo acepte mensajes.

Para obtener más información sobre estas características, consulte [planificación de la integración de mensajería unificada de Exchange en Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y [planeamiento de la resistencia de telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectivamente.

</div>

<div>

## <a name="intercluster-routing-component"></a>Componente de enrutamiento entre clústeres

El componente de enrutamiento entre clústeres es el responsable del enrutamiento de llamadas al grupo principal del registrador de los destinatarios de las llamadas. Si este no está disponible, el componente redirige la llamada al grupo de copia de seguridad del registrador de los destinatarios de las llamadas. Si no se puede tener acceso a los grupos principal y de copia de seguridad del registrador de los destinatarios de las llamadas por la red IP, el componente de enrutamiento entre clústeres desvía la llamada por la RTC al número de teléfono del usuario.

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>Otros componentes de servidor front-end necesarios para VoIP

Otros componentes que residen en el servidor front-end o director que proporcionan compatibilidad esencial para VoIP, pero que no son componentes de VoIP, incluyen lo siguiente:

  - **Servicios de usuario.** Este componente realiza una búsqueda inversa de números en el número de teléfono de destino de cada llamada entrante y asocia ese número al URI de SIP del usuario de destino. Con esta información, el componente de enrutamiento de entrada distribuye la llamada a los extremos de SIP registrados del usuario. Servicios de usuario es un componente fundamental en todos los servidores y directores de front-end.

  - **Replicador de usuarios.** Extrae números de teléfono de los usuarios de servicios de dominio de Active Directory y los escribe en las tablas de la base de datos RTC, donde estarán disponibles para los servicios de usuario y el servidor de la libreta de direcciones. El replicador de usuarios es un componente fundamental en todos los servidores de aplicaciones para el usuario.

  - **Servidor de libreta de direcciones.** Proporciona información de la lista global de direcciones de los servicios de dominio de Active Directory a clientes de Lync Server. También recupera información de usuarios y contactos de la base de datos RTC, escribe la información en los archivos de la libreta de direcciones y, a continuación, almacena los archivos en una carpeta compartida en la que los clientes de Lync los descargan. El servidor de la libreta de direcciones escribe la información en la base de datos RTCAb, que es utilizada por el servicio de consultas Web de la libreta de direcciones para responder a las consultas de búsqueda de usuario de Microsoft Lync 2010 Mobile. Opcionalmente, normaliza los números de teléfono de los usuarios de la empresa que se escriben en la base de datos RTC con el fin de aprovisionar los contactos de los usuarios en Lync. El servicio de libreta de direcciones se instala de forma predeterminada en todos los servidores de aplicaciones para el usuario. El servicio de consultas Web de la libreta de direcciones se instala de forma predeterminada con los servicios web en cada servidor front-end.

</div>

</div>

<span> </span>

</div>

</div>

</div>

