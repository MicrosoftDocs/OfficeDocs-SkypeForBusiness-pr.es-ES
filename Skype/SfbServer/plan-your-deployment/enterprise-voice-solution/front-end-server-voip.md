---
title: Componentes de VoIP del servidor front-end para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Obtenga más información sobre los componentes de voz de empresa que se encuentran en los servidores front-end de Skype empresarial Server, incluido el servicio de traducción y diversos componentes de enrutamiento.
ms.openlocfilehash: eae2f389720a6c359f442a7a163d5b4b5aef6e26
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802970"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Componentes de VoIP del servidor front-end para Skype empresarial Server

Obtenga más información sobre los componentes de voz de empresa que se encuentran en los servidores front-end de Skype empresarial Server, incluido el servicio de traducción y diversos componentes de enrutamiento.

Los componentes de VoIP que se encuentran en los servidores front-end son los siguientes:

- Servicio de conversión

- Componente de enrutamiento de entrada

- Componente de enrutamiento de salida

- Componente de enrutamiento de mensajería unificada (UM) de Exchange

- Componente de enrutamiento entre clústeres

- [Componente de servidor de mediación en Skype empresarial Server](mediation-server.md)

## <a name="translation-service"></a>Servicio de conversión

El servicio de conversión es el componente del servidor que se encarga de convertir un número marcado al formato E.164 u otro formato, de acuerdo con las reglas de normalización definidas por el administrador. El servicio de conversión puede convertir a formatos distintos de E.164 si la organización utiliza un sistema de numeración privado, o una puerta de enlace o PBX que no admite E.164.

## <a name="inbound-routing-component"></a>Componente de enrutamiento de entrada

El componente de enrutamiento entrante gestiona las llamadas entrantes en gran medida según las preferencias especificadas por los usuarios en sus clientes de telefonía empresarial. También facilita las llamadas delegadas y las llamadas simultáneas, si el usuario las configura. Por ejemplo, los usuarios especifican si las llamadas sin contestar se reenvían o simplemente se registran para su notificación. Si el desvío de llamadas está habilitado, los usuarios pueden especificar si las llamadas no contestadas deben desviarse a otro número o a un servidor de mensajería unificada de Exchange configurado para proporcionar respuesta a llamadas. El componente de enrutamiento entrante se instala de forma predeterminada en todos los servidores Standard Edition y servidores front-end.

## <a name="outbound-routing-component"></a>Componente de enrutamiento de salida

El componente de enrutamiento de salida redirige las llamadas a destinos PBX o RTC. Aplica reglas de autorización de llamadas, definidas por la Directiva de voz del usuario, a las personas que llaman y determina la puerta de enlace RTC óptima para enrutar cada llamada. El componente de enrutamiento de salida se instala de forma predeterminada en todos los servidores Standard Edition y servidores front-end.

La lógica de enrutamiento que utiliza el componente de enrutamiento de salida la configuran, en gran medida, los administradores de red o de telefonía de acuerdo con los requisitos de sus organizaciones.

## <a name="exchange-um-routing-component"></a>Componente de enrutamiento de mensajería unificada (UM) de Exchange

El componente enrutamiento de mensajería unificada de Exchange controla el enrutamiento entre Skype empresarial Server y los servidores que ejecutan mensajería unificada (UM) de Exchange para integrar Skype empresarial Server con características de mensajería unificada.

El componente de enrutamiento de MU de Exchange también controla el redireccionamiento del correo de voz a través de la RTC si los servidores de mensajería unificada de Exchange no están disponibles. Si tiene usuarios de Enterprise Voice en sitios de sucursales que no tienen un vínculo WAN resistente a un sitio central, el dispositivo de sucursal con la que se realiza el despliegue en el sitio de la sucursal ofrece la supervivencia del correo de voz durante una interrupción de la WAN. Cuando el vínculo WAN no está disponible, el equipo con la aplicación con supervivencia hace lo siguiente:

- Desvía las llamadas no respondidas a través de la RTC al servidor de mensajería unificada de Exchange del sitio central.

- Proporciona al usuario la posibilidad de recuperar mensajes de correo de voz a través de la RTC.

- Pone en cola las notificaciones de las llamadas perdidas y, luego, las carga en el servidor de mensajería unificada (UM) de Exchange cuando el vínculo WAN se restaura.

Para habilitar el redireccionamiento del correo de voz, recomendamos que el administrador de Exchange configure el operador automático de MU de Exchange (AA) para que solo acepte mensajes.

Para obtener más información sobre estas características, mira [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) y [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectivamente.

## <a name="intercluster-routing-component"></a>Componente de enrutamiento entre clústeres

El componente de enrutamiento entre clústeres es responsable de dirigir las llamadas al grupo de registrador principal de la persona que llama. Si no está disponible, el componente enruta la llamada al grupo de registro de la copia de seguridad de la persona que llama. Si los grupos principal y de registro de la copia de seguridad de la llamada son inaccesibles a través de la red IP, el componente de enrutamiento entre clústeres redirige la llamada a través de la RTC al número de teléfono del usuario.

## <a name="other-front-end-server-components-required-for-voip"></a>Otros componentes de servidor front-end necesarios para VoIP

Otros componentes que residen en el servidor front-end o director que proporcionan compatibilidad esencial para VoIP, pero que no son componentes de VoIP, incluyen lo siguiente:

- **Servicios de usuario.** Este componente realiza una búsqueda inversa de números en el número de teléfono de destino de cada llamada entrante y asocia ese número al URI de SIP del usuario de destino. Con esta información, el componente de enrutamiento entrante distribuye la llamada a los puntos de conexión SIP registrados de ese usuario. Servicios de usuario es un componente fundamental en todos los servidores y directores de front-end.

- **Replicador de usuarios.** Extrae números de teléfono de los usuarios de servicios de dominio de Active Directory y los escribe en las tablas de la base de datos RTC, donde estarán disponibles para los servicios de usuario y el servidor de la libreta de direcciones. El replicador de usuarios es un componente fundamental en todos los servidores de aplicaciones para el usuario.

- **Servidor de libreta de direcciones.** Proporciona información de la lista global de direcciones de los servicios de dominio de Active Directory a clientes de Skype empresarial Server. También recupera información de usuarios y contactos de la base de datos RTC, escribe la información en los archivos de la libreta de direcciones y, a continuación, almacena los archivos en una carpeta compartida en la que los clientes de Skype empresarial los descargan. El servidor de la libreta de direcciones escribe la información en la base de datos RTCAb, que es utilizada por el servicio de consultas Web de la libreta de direcciones para responder a las consultas de búsqueda de usuario de Skype empresarial Mobile. Opcionalmente, normaliza los números de teléfono de los usuarios de la empresa que se escriben en la base de datos RTC con el fin de aprovisionar los contactos de los usuarios en Skype empresarial. El servicio de libreta de direcciones se instala de forma predeterminada en todos los servidores de aplicaciones para el usuario. El servicio de consultas Web de la libreta de direcciones se instala de forma predeterminada con los servicios web en cada servidor front-end.


