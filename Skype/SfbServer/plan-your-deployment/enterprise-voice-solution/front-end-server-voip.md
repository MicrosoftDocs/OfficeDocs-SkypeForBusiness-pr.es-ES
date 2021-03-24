---
title: Componentes voIP del servidor front-end para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Obtenga información sobre los Telefonía IP empresarial que se encuentran en los servidores front-end de Skype Empresarial Server, incluidos el servicio de traducción y varios componentes de enrutamiento.
ms.openlocfilehash: 830f54e59e0d2135e3748fd03474b19e22741136
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101496"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Componentes voIP del servidor front-end para Skype Empresarial Server

Obtenga información sobre los Telefonía IP empresarial que se encuentran en los servidores front-end de Skype Empresarial Server, incluidos el servicio de traducción y varios componentes de enrutamiento.

Los componentes voIP ubicados en servidores front-end son los siguientes:

- Servicio de conversión

- Componente de enrutamiento de entrada

- Componente de enrutamiento de salida

- Componente de enrutamiento de mensajería unificada de Exchange

- Componente de enrutamiento entre clústeres

- [Componente de servidor de mediación en Skype Empresarial Server](mediation-server.md)

## <a name="translation-service"></a>Servicio de conversión

El servicio de conversión es el componente de servidor que se encarga de convertir un número marcado al formato E.164 u otro formato, de acuerdo con las reglas de normalización definidas por el administrador. El Servicio de conversión puede convertir a formatos distintos de E.164 si la organización utiliza un sistema de numeración privado o una puerta de enlace o PBX que no admite E.164.

## <a name="inbound-routing-component"></a>Componente de enrutamiento de entrada

El componente de enrutamiento de entrada se encarga de las llamadas entrantes, en gran medida de acuerdo con las preferencias especificadas por los usuarios en los clientes de Enterprise Voice. También facilita las llamadas delegadas y las llamadas simultáneas, si el usuario las configura. Por ejemplo, los usuarios especifican si las llamadas sin contestar se transfieren o simplemente se registran para su notificación. Si el reenvío de llamadas está habilitado, los usuarios pueden especificar si las llamadas sin responder deben reenviarse a otro número o a un servidor de mensajería unificada de Exchange configurado para proporcionar respuesta a llamadas. El componente de enrutamiento de entrada se instala de forma predeterminada en todos los servidores Standard Edition y servidores front-end.

## <a name="outbound-routing-component"></a>Componente de enrutamiento de salida

El componente de enrutamiento de salida redirige las llamadas a destinos PBX o RTC. Aplica reglas de autorización de llamadas, como se define en la directiva de voz del usuario, a los autores de llamadas y determina la puerta de enlace RTC óptima para enrutar cada llamada. El componente de enrutamiento saliente se instala de forma predeterminada en todos los servidores Standard Edition y servidores front-end.

La lógica de enrutamiento utilizada por el componente de enrutamiento de salida la configuran en gran medida administradores de red o de telefonía de acuerdo con los requisitos de sus organizaciones.

## <a name="exchange-um-routing-component"></a>Componente de enrutamiento de mensajería unificada de Exchange

El componente de enrutamiento de mensajería unificada de Exchange controla el enrutamiento entre Skype Empresarial Server y los servidores que ejecutan mensajería unificada (MU) de Exchange, para integrar Skype Empresarial Server con características de mensajería unificada.

El componente de enrutamiento de mensajería unificada de Exchange también controla el reenrutado del correo de voz a través de la RTC si los servidores de mensajería unificada de Exchange no están disponibles. Si tiene usuarios Telefonía IP empresarial en sitios de sucursal que no tienen un vínculo WAN resistente a un sitio central, la aplicación de sucursal con funciones de supervivencia que implementa en el sitio de sucursal proporciona la supervivencia del correo de voz para los usuarios de sucursal durante una interrupción de wan. Cuando el vínculo WAN no está disponible, la aplicación de sucursal con funciones de supervivencia hace lo siguiente:

- vuelve a enrutar las llamadas por la RTC al servidor de mensajería unificada de Exchange del sitio central

- proporciona al usuario la posibilidad de recuperar mensajes de correo de voz por la RTC

- pone en cola las notificaciones de llamada perdida y luego las carga en el servidor de mensajería unificada de Exchange cuando el vínculo WAN se restaura.

Para habilitar el rerouting de correo de voz, se recomienda que el administrador de Exchange configure exchange um Operador automático (AA) solo para aceptar mensajes.

Para obtener más información sobre estas características, consulte [On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) y [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency), respectivamente.

## <a name="intercluster-routing-component"></a>Componente de enrutamiento entre clústeres

El componente de enrutamiento entre clústeres es responsable de enrutar llamadas al grupo de registradores principal del destinatario. Si no está disponible, el componente enruta la llamada al grupo de registradores de copia de seguridad del destinatario. Si los grupos de registradores principales y de copia de seguridad del destinatario son inaccesibles a través de la red IP, el componente de enrutamiento entre clústeres redirige la llamada a través de la RTC al número de teléfono del usuario.

## <a name="other-front-end-server-components-required-for-voip"></a>Otros componentes de servidor front-end necesarios para VoIP

Otros componentes que residen en el servidor front-end o director que proporcionan soporte esencial para VoIP, pero no son ellos mismos componentes VoIP, incluyen lo siguiente:

- **Servicios de usuario.** Realiza una búsqueda inversa de número en el número de teléfono de destino de cada llamada entrante y asocia ese número al URI de SIP del usuario de destino. Con esta información, el componente de enrutamiento de entrada distribuye la llamada a los extremos SIP registrados de ese usuario. Servicios de usuario es un componente principal en todos los servidores front-end y directores.

- **Replicador de usuarios.** Extrae números de teléfono de usuario de Servicios de dominio de Active Directory y los escribe en tablas de la base de datos RTC, donde están disponibles para servicios de usuario y servidor de libreta de direcciones. El replicador de usuarios es un componente principal en todos los servidores front-end.

- **Servidor de libreta de direcciones.** Proporciona información global de lista de direcciones de Servicios de dominio de Active Directory a clientes de Skype Empresarial Server. También recupera información de usuario y contacto de la base de datos RTC, escribe la información en los archivos de la libreta de direcciones y, a continuación, almacena los archivos en una carpeta compartida en la que los clientes de Skype Empresarial los descargan. El servidor de libreta de direcciones escribe la información en la base de datos RTCAb, que usa el servicio de consulta web de libreta de direcciones para responder a las consultas de búsqueda del usuario desde skype empresarial móvil. Opcionalmente, normaliza los números de teléfono de usuario de empresa que se escriben en la base de datos RTC con el fin de aprovisionar contactos de usuario en Skype Empresarial. El servicio de libreta de direcciones está instalado de forma predeterminada en todos los servidores front-end. El servicio de consulta web de libreta de direcciones se instala de forma predeterminada con los servicios web en cada servidor front-end.