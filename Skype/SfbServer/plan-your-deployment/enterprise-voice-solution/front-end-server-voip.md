---
title: Componentes de Front-End Server VoIP para Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Obtenga información sobre los componentes de Enterprise Voice que se encuentran en servidores Front-End en Skype para Business Server, incluido el servicio de traducción automática y diversos componentes de enrutamiento.
ms.openlocfilehash: caeec86f4b4a965570773ee4bc51a4e752e76e46
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892804"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Componentes de Front-End Server VoIP para Skype para Business Server

Obtenga información sobre los componentes de Enterprise Voice que se encuentran en servidores Front-End en Skype para Business Server, incluido el servicio de traducción automática y diversos componentes de enrutamiento.

Los componentes VoIP ubicados en servidores Front-End son los siguientes:

- Servicio de conversión

- Componente de enrutamiento de entrada

- Componente de enrutamiento de salida

- Componente de enrutamiento de mensajería unificada (UM) de Exchange

- Componente de enrutamiento entre clústeres

- [Componente de servidor de mediación en Skype para Business Server](mediation-server.md)

## <a name="translation-service"></a>Servicio de conversión

El servicio de conversión es el componente del servidor que se encarga de convertir un número marcado al formato E.164 u otro formato, de acuerdo con las reglas de normalización definidas por el administrador. El servicio de conversión puede convertir a formatos distintos de E.164 si la organización utiliza un sistema de numeración privado, o una puerta de enlace o PBX que no admite E.164.

## <a name="inbound-routing-component"></a>Componente de enrutamiento de entrada

El componente de enrutamiento de entrada administra las llamadas entrantes en gran medida de acuerdo con las preferencias especificadas por los usuarios en sus clientes de Enterprise Voice. También facilita las llamadas delegadas y las llamadas simultáneas, si el usuario las configura. Por ejemplo, los usuarios especifican si las llamadas sin contestar se reenvían o simplemente se registran para su notificación. Si el desvío de llamadas está habilitado, los usuarios pueden especificar si se deben reenviar las llamadas no respondidas a otro número o a un servidor de mensajería unificada de Exchange que se ha configurado para proporcionar el contestador automático. El componente de enrutamiento de entrada se instala de forma predeterminada en todos los servidores Standard Edition y servidores Front-End.

## <a name="outbound-routing-component"></a>Componente de enrutamiento de salida

El componente de enrutamiento de salida redirige las llamadas a destinos PBX o RTC. Se aplica las reglas de autorización de llamada, como se define mediante una directiva de voz del usuario, a los autores de llamadas y determina la puerta de enlace de RTC óptima para redirigir cada llamada. El componente de enrutamiento de salida se instala de forma predeterminada en todos los servidores Standard Edition y servidores Front-End.

La lógica de enrutamiento que utiliza el componente de enrutamiento de salida la configuran, en gran medida, los administradores de red o de telefonía de acuerdo con los requisitos de sus organizaciones.

## <a name="exchange-um-routing-component"></a>Componente de enrutamiento de mensajería unificada (UM) de Exchange

El componente de enrutamiento mensajería unificada de Exchange administra el enrutamiento entre Skype para Business Server y los servidores que ejecutan Exchange mensajería unificada (UM), para integrar Skype para Business Server con características de mensajería unificada.

El componente de enrutamiento mensajería unificada de Exchange también administra reenrutamiento de correo de voz a través de la RTC si los servidores de mensajería unificada de Exchange no están disponibles. Si tiene usuarios de Enterprise Voice en sitios de sucursal que no tienen una WAN resistente vincular a un sitio central, la aplicación de sucursal con funciones de supervivencia que implemente en el sitio de sucursal proporciona las funciones de supervivencia de correo de voz para usuarios de sucursal durante una interrupción de la WAN. Cuando el vínculo WAN no está disponible, la aplicación de sucursal con funciones de supervivencia hace lo siguiente:

- Desvía las llamadas no respondidas a través de la RTC al servidor de mensajería unificada de Exchange del sitio central.

- Proporciona al usuario la posibilidad de recuperar mensajes de correo de voz a través de la RTC.

- Pone en cola las notificaciones de las llamadas perdidas y, luego, las carga en el servidor de mensajería unificada (UM) de Exchange cuando el vínculo WAN se restaura.

Para habilitar el desvío de correo de voz, se recomienda que el Administrador de Exchange configure Exchange UM operador automático (AA) para que únicamente acepte mensajes.

Para obtener más información sobre estas características, mira [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) y [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectivamente.

## <a name="intercluster-routing-component"></a>Componente de enrutamiento entre clústeres

El componente de enrutamiento entre clústeres es responsable de enrutar las llamadas a grupo de registrador principal el destinatario de la llamada. Si no está disponible, el componente enruta la llamada a grupo de registrador de copia de seguridad del destinatario de la llamada. Si los grupos de registrador principales y de copia de seguridad del destinatario de la llamada no puedo acceder son través de la red IP, el componente de enrutamiento entre clústeres vuelve a enrutar la llamada a través de la RTC a número de teléfono del usuario.

## <a name="other-front-end-server-components-required-for-voip"></a>Otros componentes de servidor front-end necesarios para VoIP

Otros componentes que residen en el servidor Front-End o un Director que proporcionan soporte para VoIP, pero no son ellos mismos componentes VoIP, son los siguientes:

- **Servicios de usuario.** Este componente realiza una búsqueda inversa de números en el número de teléfono de destino de cada llamada entrante y asocia ese número al URI de SIP del usuario de destino. Con esta información, el componente de enrutamiento de entrada distribuye la llamada a los extremos SIP registrados de dicho usuario. Servicios de usuario es un componente básico de todos los servidores Front-End y directores.

- **Replicador de usuarios.** Extrae los números de teléfono del usuario de los servicios de dominio de Active Directory y los escribe en las tablas de la base de datos RTC, donde están disponibles para servicios de usuario y el servidor de la libreta de direcciones. Replicador de usuarios es un componente básico de todos los servidores Front-End.

- **Servidor de libreta de direcciones.** Proporciona información sobre la lista global de direcciones de los servicios de dominio de Active Directory a Skype para los clientes de Business Server. También se recupera información de usuario y contacto de la base de datos RTC, escribe la información en los archivos de libreta de direcciones y, a continuación, almacena los archivos en una carpeta compartida donde se descargan por Skype para clientes empresariales. El servidor de la libreta de direcciones se escribe la información en la base de datos RTCAb, que se usa el servicio de consulta Web de libreta de direcciones para responder a las consultas de búsqueda de usuario de Skype para la empresa móvil. Opcionalmente, normaliza los números de teléfono de usuario de empresa que se escriben en la base de datos RTC con el fin de aprovisionamiento de los contactos del usuario en Skype para la empresa. El servicio de libreta de direcciones se instala de forma predeterminada en todos los servidores Front-End. El servicio de consulta Web de libreta de direcciones se instala de forma predeterminada con los servicios Web en cada servidor front-end.


