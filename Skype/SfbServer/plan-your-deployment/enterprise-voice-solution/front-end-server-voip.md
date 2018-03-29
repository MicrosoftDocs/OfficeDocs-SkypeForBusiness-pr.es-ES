---
title: Componentes VoIP del servidor front-end para Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Obtenga información acerca de los componentes de Telefonía IP empresarial que se encuentran en los servidores frontales de Skype para Business Server, incluido el servicio de traducción y los distintos componentes de enrutamiento.
ms.openlocfilehash: eca9a83943d045c48b2b811e6370e54fc41f1714
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-server-voip-components-for-skype-for-business-server-2015"></a>Componentes VoIP del servidor front-end para Skype Empresarial Server 2015
 
Obtenga información acerca de los componentes de Telefonía IP empresarial que se encuentran en los servidores frontales de Skype para Business Server, incluido el servicio de traducción y los distintos componentes de enrutamiento.
  
Los componentes de VoIP ubicados en servidores frontales son los siguientes:
  
- Servicio de conversión
    
- Componente de enrutamiento de entrada
    
- Componente de enrutamiento de salida
    
- Componente de enrutamiento de mensajería unificada (UM) de Exchange
    
- Componente de enrutamiento entre clústeres
    
- [Componente de servidor de mediación de Skype para Business Server 2015](mediation-server.md)
    
## <a name="translation-service"></a>Servicio de conversión

El servicio de conversión es el componente del servidor que se encarga de convertir un número marcado al formato E.164 u otro formato, de acuerdo con las reglas de normalización definidas por el administrador. El servicio de conversión puede convertir a formatos distintos de E.164 si la organización utiliza un sistema de numeración privado, o una puerta de enlace o PBX que no admite E.164.
  
## <a name="inbound-routing-component"></a>Componente de enrutamiento de entrada

El componente de enrutamiento de entrada controla las llamadas entrantes en gran medida según las preferencias que se especifican los usuarios en sus clientes de Telefonía IP empresarial. También facilita las llamadas delegadas y las llamadas simultáneas, si el usuario las configura. Por ejemplo, los usuarios especifican si las llamadas sin contestar se reenvían o simplemente se registran para su notificación. Si está habilitado el reenvío de llamadas, los usuarios pueden especificar si se deben reenviar llamadas no respondidas a otro número o a un servidor de mensajería unificada de Exchange que se ha configurado para proporcionar contestación de llamadas. El componente de enrutamiento de entrada se instala de forma predeterminada en todos los servidores Standard Edition y servidores frontales. 
  
## <a name="outbound-routing-component"></a>Componente de enrutamiento de salida

El componente de enrutamiento de salida redirige las llamadas a destinos PBX o RTC. Aplica las reglas de autorización de llamada, como se define en la directiva de voz del usuario, a los llamadores y determina la puerta de enlace PSTN óptimo para el enrutamiento de cada llamada. El componente de enrutamiento de salida se instala de forma predeterminada en todos los servidores Standard Edition y servidores frontales.
  
La lógica de enrutamiento que utiliza el componente de enrutamiento de salida la configuran, en gran medida, los administradores de red o de telefonía de acuerdo con los requisitos de sus organizaciones. 
  
## <a name="exchange-um-routing-component"></a>Componente de enrutamiento de mensajería unificada (UM) de Exchange

El componente de mensajería unificada de Exchange enrutamiento controla el enrutamiento entre Skype para Business Server y los servidores que ejecutan Exchange Unified Messaging (UM), integrar Skype para Business Server con características de mensajería unificada. 
  
El componente de mensajería unificada de Exchange enrutamiento también controla reenrutamiento de correo de voz por PSTN, si los servidores mensajería unificada de Exchange no están disponibles. Si tiene usuarios de Telefonía IP empresarial en sucursales que no tienen una WAN resistente vincular a un sitio central, el dispositivo que sobreviven de sucursal que se despliegan en el sitio de la sucursal proporciona la supervivencia de correo de voz para los usuarios de sucursales durante una interrupción de la WAN. Cuando el vínculo WAN no está disponible, el dispositivo de la rama que sobreviven hace lo siguiente:
  
- Desvía las llamadas no respondidas a través de la RTC al servidor de mensajería unificada de Exchange del sitio central.
    
- Proporciona al usuario la posibilidad de recuperar mensajes de correo de voz a través de la RTC.
    
- Pone en cola las notificaciones de las llamadas perdidas y, luego, las carga en el servidor de mensajería unificada (UM) de Exchange cuando el vínculo WAN se restaura.
    
Para habilitar el redireccionamiento de correo de voz, se recomienda que el Administrador de Exchange configura Exchange UM Operador automático (AA) para aceptar sólo los mensajes.
  
Para obtener más información acerca de estas características, consulte [Integración local Exchange Unified Messaging](http://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) y [planeación para Telefonía IP empresarial resiliencia](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectivamente.
  
## <a name="intercluster-routing-component"></a>Componente de enrutamiento entre clústeres

El componente de enrutamiento Intercluster es responsable de enrutar las llamadas al grupo de registrador principal del destinatario de la llamada. Si no está disponible, el componente enruta la llamada a grupo de registrador auxiliar del destinatario de la llamada. Si son inalcanzables pools de registrador principales y de reserva del destinatario de la llamada sobre la red IP, el componente de enrutamiento Intercluster redirige la llamada por PSTN al número de teléfono del usuario.
  
## <a name="other-front-end-server-components-required-for-voip"></a>Otros componentes de servidor front-end necesarios para VoIP

Otros componentes que residen en el servidor Front-End o Director que proporcionan apoyo esencial para VoIP, pero no son ellos mismos componentes de VoIP, son las siguientes:
  
- **Servicios de usuario.** Este componente realiza una búsqueda inversa de números en el número de teléfono de destino de cada llamada entrante y asocia ese número al URI de SIP del usuario de destino. Con esta información, el componente de enrutamiento de entrada distribuye la llamada a los extremos SIP registrados de ese usuario. Servicios de usuario es un componente principal en todos los servidores frontales y directores.
    
- **Replicador de usuarios.** Extrae números de teléfono del usuario de servicios de dominio de Active Directory y los escribe en las tablas de la base de datos RTC, donde estarán disponibles para los servicios de usuario y servidor de libreta de direcciones. Replicador de usuarios es un componente principal en todos los servidores frontales.
    
- **Servidor de libreta de direcciones.** Proporciona información de la lista global de direcciones de los servicios de dominio de Active Directory a Skype para clientes de Business Server. También recupera información de usuario y contacto de la base de datos RTC, escribe la información en los archivos de libreta de direcciones y, a continuación, almacena los archivos en una carpeta compartida donde se descargan por Skype para clientes empresariales. El servidor de libreta de direcciones se escribe la información en la base de datos RTCAb, que es utilizado por el servicio de consulta Web de libreta de direcciones para responder a las consultas de búsqueda de usuarios de Skype para negocios móviles. Opcionalmente, normaliza los números de teléfono de usuario de empresa que se escriben en la base de datos RTC con el fin de aprovisionamiento de contactos de los usuarios de Skype para el negocio. El servicio de libreta de direcciones se instala de forma predeterminada en todos los servidores frontales. El servicio de consulta Web de libreta de direcciones se instala de forma predeterminada con los servicios Web en cada servidores frontales.
    

