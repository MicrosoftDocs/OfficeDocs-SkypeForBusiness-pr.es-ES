---
title: 'Lync Server 2013: componentes VoIP del servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62261a4d4651e38941f5068b58636b82d0151965
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500707"
---
# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Componentes VoIP del servidor front-end para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Los componentes de VoIP ubicados en los servidores front-end son los siguientes:

  - Servicio de conversión

  - Componente de enrutamiento de entrada

  - Componente de enrutamiento de salida

  - Componente de enrutamiento de mensajería unificada de Exchange

  - Componente de enrutamiento entre clústeres

  - [Componente de servidor de mediación en Lync Server 2013](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a>Servicio de conversión

El servicio de conversión es el componente de servidor que se encarga de convertir un número marcado al formato E.164 u otro formato, de acuerdo con las reglas de normalización definidas por el administrador. El Servicio de conversión puede convertir a formatos distintos de E.164 si la organización utiliza un sistema de numeración privado o una puerta de enlace o PBX que no admite E.164.

</div>

<div>

## <a name="inbound-routing-component"></a>Componente de enrutamiento de entrada

El componente de enrutamiento de entrada se encarga de las llamadas entrantes, en gran medida de acuerdo con las preferencias especificadas por los usuarios en los clientes de Enterprise Voice. También facilita las llamadas delegadas y las llamadas simultáneas, si el usuario las configura. Por ejemplo, los usuarios especifican si las llamadas sin contestar se transfieren o simplemente se registran para su notificación. Si el desvío de llamadas está habilitado, los usuarios pueden especificar si las llamadas no respondidas deben reenviarse a otro número o a un servidor de mensajería unificada de Exchange que se haya configurado para proporcionar el contestador automático. El componente de enrutamiento de entrada está instalado de forma predeterminada en todos los servidores front-end y de servidor Standard Edition.

</div>

<div>

## <a name="outbound-routing-component"></a>Componente de enrutamiento de salida

El componente de enrutamiento de salida redirige las llamadas a destinos PBX o RTC. Aplica reglas de autorización de llamadas, que se definen en la directiva de voz del usuario, a los autores de las llamadas y determina la puerta de enlace RTC óptima para enrutar cada llamada. El componente de enrutamiento de salida está instalado de forma predeterminada en todos los servidores front-end y de servidor Standard Edition.

La lógica de enrutamiento utilizada por el componente de enrutamiento de salida la configuran en gran medida administradores de red o de telefonía de acuerdo con los requisitos de sus organizaciones.

</div>

<div>

## <a name="exchange-um-routing-component"></a>Componente de enrutamiento de mensajería unificada de Exchange

El componente de enrutamiento de mensajería unificada de Exchange administra el enrutamiento entre Lync Server y los servidores que ejecutan la mensajería unificada (MU) de Exchange para integrar Lync Server con las características de mensajería unificada.

El componente de enrutamiento de mensajería unificada de Exchange también controla el reenrutamiento del correo de voz por la RTC si los servidores de mensajería unificada de Exchange no están disponibles. Si tiene usuarios de Enterprise Voice en sitios de sucursal que no tienen un vínculo WAN resistente a un sitio central, la aplicación de sucursal con funciones de supervivencia que se implementa en el sitio de sucursal proporciona supervivencia de correo de voz para usuarios de sucursal durante una interrupción de la WAN. Cuando el vínculo WAN no está disponible, la aplicación de sucursal con funciones de supervivencia hace lo siguiente:

  - vuelve a enrutar las llamadas por la RTC al servidor de mensajería unificada de Exchange del sitio central

  - proporciona al usuario la posibilidad de recuperar mensajes de correo de voz por la RTC

  - pone en cola las notificaciones de llamada perdida y luego las carga en el servidor de mensajería unificada de Exchange cuando el vínculo WAN se restaura.

Para habilitar el redireccionamiento del correo de voz, se recomienda que el administrador de Exchange configure el operador automático de mensajería unificada (AA) de Exchange para que sólo acepte mensajes.

Para obtener más información sobre estas características, consulte [Planning for Exchange Unified Messaging Integration in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) y [Planning for Enterprise Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectivamente.

</div>

<div>

## <a name="intercluster-routing-component"></a>Componente de enrutamiento entre clústeres

El componente de enrutamiento entre clústeres es el responsable del enrutamiento de llamadas al grupo principal del registrador de los destinatarios de las llamadas. Si este no está disponible, el componente enruta la llamada al grupo de reserva del registrador de los destinatarios de las llamadas. Si no se puede tener acceso a los grupos principal y de reserva del registrador de los destinatarios de las llamadas por la red IP, el componente de enrutamiento entre clústeres desvía la llamada por la RTC al número de teléfono del usuario.

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>Otros componentes de servidor front-end necesarios para VoIP

Entre otros componentes que residen en el servidor front-end o el director que proporciona compatibilidad esencial para VoIP, pero que no son componentes de VoIP, se incluyen los siguientes:

  - **Servicios de usuario.** Realiza una búsqueda inversa de número en el número de teléfono de destino de cada llamada entrante y asocia ese número al URI de SIP del usuario de destino. Con esta información, el componente de enrutamiento de entrada distribuye la llamada a los extremos de SIP registrados del usuario. Servicios de usuario es un componente principal de todos los directores y servidores front-end.

  - **Replicador de usuarios.** Extrae números de teléfono de usuario de servicios de dominio de Active Directory y los escribe en las tablas de la base de datos RTC, donde están disponibles para los servicios de usuario y el servidor de la libreta de direcciones. El replicador de usuarios es un componente principal en todos los servidores front-end.

  - **Servidor de libreta de direcciones.** Proporciona información de la lista global de direcciones de servicios de dominio de Active Directory a clientes de Lync Server. También recupera información de contactos y usuarios de la base de datos RTC, escribe la información en los archivos de la libreta de direcciones y, a continuación, almacena los archivos en una carpeta compartida en la que los clientes de Lync los descargan. El servidor de la libreta de direcciones escribe la información en la base de datos de RTCAb, que usa el servicio de consulta Web de la libreta de direcciones para responder a las consultas de búsqueda de los usuarios desde Microsoft Lync 2010 Mobile. Opcionalmente, normaliza los números de teléfono de los usuarios de la empresa que se escriben en la base de datos RTC con el fin de aprovisionar contactos de usuarios en Lync. El servicio de libreta de direcciones está instalado de forma predeterminada en todos los servidores front-end. El servicio de consulta Web de la libreta de direcciones se instala de forma predeterminada con los servicios web en cada uno de los servidores front-end.

</div>

</div>

<span> </span>

</div>

</div>

</div>

