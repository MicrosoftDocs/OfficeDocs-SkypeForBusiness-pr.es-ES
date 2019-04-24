---
title: Planeación de servicios de emergencia en Skype para Business Server
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
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: Obtenga información acerca de los servicios Enhanced 9-1-1 (E9-1-1) en Skype para Business Server Enterprise Voice, incluidas la adquisición de ubicación y enrutamiento de llamadas.
ms.openlocfilehash: 4dba79c1c1b1b1fed0f60ea4f4c4a9a1d1baea92
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207646"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planeación de servicios de emergencia en Skype para Business Server

Obtenga información acerca de los servicios Enhanced 9-1-1 (E9-1-1) en Skype para Business Server Enterprise Voice, incluidas la adquisición de ubicación y enrutamiento de llamadas.

Skype para Business Server es compatible con los servicios Enhanced 9-1-1 (E9-1-1) dentro de Estados Unidos como parte de una implementación de Enterprise Voice. E9-1-1 es una característica de envío de emergencia que asocia una llamada 9-1-1 con una ubicación de respuesta de emergencia (ERL) que consta de direcciones de la ciudad (es decir, postal) y otra información de ubicación más específica, como los números de planta, para las llamadas de edificios de oficinas y otras instalaciones multiempresa. Con el uso de la ERL proporcionada, un Punto de respuesta de seguridad pública (PSAP) puede enviar inmediatamente los servicios de emergencia a la persona que realiza la llamada en apuros con un riesgo menor de dirigir accidentalmente los servicios de emergencias a una ubicación incorrecta o ambigua.

> [!NOTE]
> Skype para Business Server ahora admite la configuración de varios números de emergencias para un cliente. Para obtener más información, consulte [Plan para varios números de emergencias en Skype para Business Server](multiple-emergency-numbers.md).

> [!NOTE]
> Skype para Business Server tiene tres características avanzadas de Enterprise Voice: desvío de medios, servicios de emergencia (E9-1-1) y el control de admisión de llamadas. Para obtener información general de la planeación de información que es común a todos los tres de estas características, vea [configuración de red para las características avanzadas de Enterprise Voice en Skype para Business Server](network-settings-for-advanced-features.md).

Skype para Business Server es compatible con Enhanced 9-1-1 (E9-1-1) de llamada de Skype para clientes empresariales y dispositivos de Lync Phone Edition. Al configurar Skype para Business Server para las llamadas E9-1-1, emergencias realizadas desde Skype para la empresa o Lync Phone Edition incluyen información de ubicación de respuesta de emergencia (ERL) desde la base de datos de servicio de información de ubicación. Las ERL se componen de direcciones civiles (es decir, postales) e información adicional que ayuda a identificar con mayor precisión una ubicación en edificios de oficinas y otras instalaciones con varios inquilinos. Cuando un usuario realiza una llamada de emergencia, Skype para Business Server enruta la llamada audio, junto con la información de ubicación y la devolución de llamada, a través de un servidor de mediación para un proveedor de servicios E9-1-1. Desde aquí se facilita la ubicación del autor de la llamada junto con una clave de consulta de servicios de emergencia (ESQK) que permite al PSAP buscar la ERL de esta persona.

Skype para Business Server admite dos métodos de enrutamiento para llamadas de emergencia al proveedor de servicios E9-1-1:

- Una conexión de enlace troncal SIP (Protocolo de inicio de sesión) a un proveedor de servicios E9-1-1 cualificado.

- Una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios E9-1-1 basado en una Red telefónica conmutada (RTC).

Cuando se usa un proveedor de servicios SIP E9-1-1 de tronco, agregue Erl a la base de datos de servicio de información de ubicación y, a continuación, compruebe las ubicaciones frente a una guía de direcciones de calle del patrón (MSAG) mantenida por el proveedor de servicios E9-1-1. Si un proveedor de servicios E9-1-1 recibe una llamada que no tiene información de ubicación o que tenga una ubicación que no se ha validado contra la MSAG, el proveedor de servicios E9-1-1 enruta la llamada a una emergencia llamar respuesta centro (ECRC), que es nacionales o regionales cuenta con personal especializado que obtener verbalmente ubicación el autor de la llamada, si es posible y de forma manual enrutar la llamada al PSAP adecuado. Algunos proveedores de servicios E9-1-1 de enlace troncal SIP también proporcionan a los clientes un número de marcado directo (DID) de RTC para el ECRC, que constituye un medio alternativo de enrutamiento de las llamadas al 9-1-1 si por algún motivo se produce un error en el enlace troncal SIP.

A diferencia de tiempo (TDM) de multiplexación por división y teléfonos de IP-based central de conmutación (PBX) de exchange, que poseen ubicaciones fijas, un Skype para extremo empresarial puede ser muy móvil. Al implementar la característica de E9-1-1, Skype para Business Server ayuda a garantizar que independientemente de que un autor de la llamada se encuentra, la llamada de emergencia se puedan enrutar al servicio de emergencia que sirve de ubicación del autor de la llamada. Por ejemplo, si la oficina principal de un usuario se encuentra en Redmond, Washington, pero el usuario coloca una llamada de emergencia desde un equipo en una sucursal en Wichita, Kansas, el tronco SIP o proveedor de servicios basados en RTC E9-1-1 usará para enrutar la llamada al PSAP en Wichita , no para el servicio de emergencia en Redmond.

Cuando se utiliza una puerta de enlace ELIN, también agregar Erl para la base de datos de servicio de información de ubicación, pero también incluye un número de ELIN para cada ubicación. El número ELIN pasa a ser el número de llamada SOS durante la llamada. Es preciso comprobar que el proveedor de RTC carga los ELIN en una base de datos de identificación de ubicación automática (ALI).

> [!NOTE]
> Skype para dispositivos analógicos conectados empresarial no se puede recibir información de ubicación de servicio de información de ubicación de o transmitir ubicación para el proveedor de servicios E9-1-1.

 Si usa la opción del proveedor de servicios E9-1-1 de enlace troncal SIP y tiene que admitir llamadas E9-1-1 desde teléfonos analógicos, tiene dos opciones:

- **Opción de PS-ALI tradicional** Si dispone de puertas de enlace de RTC locales en cada sitio donde se implementan teléfonos analógicos y cada teléfono analógico tiene un DID, puede aprovisionar la ubicación del dispositivo analógico directamente con un proveedor de servicios de identificación de ubicación privada modificador/automático (PS-ALI). En este caso, configure Skype especialmente diseñada para las directivas de voz empresarial y asignarlas al dispositivo analógico objetos de contacto para que las llamadas E9-1-1 de esos teléfonos enrutan directamente a través de la puerta de enlace local para el proveedor de RTC que el sitio de servicios (en su lugar de enrutar la llamada a un proveedor de servicios E9-1-1 tronco SIP). Cuando se realiza una llamada SOS, una base de datos de un proveedor de PS-ALI asociado con el enlace troncal de RTC asigna el DID de cada teléfono analógico a una ubicación física, y proporciona esta ubicación al PSAP. Estos registros necesitan actualizarse con el proveedor de servicios de PS-ALI cada vez que los teléfonos se desplazan a ERL diferentes.

- **Opción de proveedor de servicio de E9-1-1** Puede registrar el DIDs de teléfono analógico y sus correspondientes Erl con el proveedor de servicios E9-1-1, si esto es compatible con el proveedor de servicios E9-1-1. Si el proveedor recibe una llamada de Skype para que no se incluyen datos PIDF-Business Server, el proveedor puede ver si hay una coincidencia de la base de datos en un número DID la persona que llama. Mediante el uso de la ERL recuperada automáticamente desde su base de datos, el proveedor puede enrutar la llamada de emergencia para el servicio de emergencia correcta y el servicio de emergencia recibirá el DID del dispositivo analógico y un registro ESQK que permite que el distribuidor buscar la ubicación del autor de la llamada.

Si usa la opción de puerta de enlace de ELIN y necesita compatibilidad con las llamadas E9-1-1 desde teléfonos analógicos, puede dar la ubicación del dispositivo analógico directamente con el proveedor de servicios PS-ALI, como se describe en la primera opción mencionada anteriormente.

Desde una Skype para perspectiva de Business Server, el proceso de E9-1-1 puede dividirse en dos fases:

- Fase 1: adquisición de una ubicación

- Fase 2: enrutamiento de la llamada SOS al proveedor de servicios E9-1-1

En esta sección se describe cómo funcionan estas fases.

Si va a configurar la infraestructura para detectar automáticamente la ubicación del cliente, primero necesita decidir qué elementos de red usará para asignar los autores de las llamadas a las ubicaciones. Para obtener información detallada acerca de las opciones posibles, consulte [definir los elementos de red que se usan para determinar la ubicación de Skype para Business Server](network-location.md).

## <a name="acquiring-a-location"></a>Adquirir una ubicación

En un Skype para la implementación de servidor empresarial E9-1-1, cada Skype conectado internamente para clientes empresariales o de Lync Phone Edition adquiere activamente su propia ubicación. Después del registro de SIP, el cliente proporciona toda la información de conectividad de red que lo sabe acerca de sí mismo en una solicitud de ubicación para el servicio de información de ubicación, que es un servicio web respaldado por una base de datos replicada de SQL Server. Cada grupo de servidores del sitio central tiene un servicio de información de ubicación, que usa la información de red para consultar sus registros para una ubicación coincidente. Si hay una coincidencia, el servicio de información de ubicación devuelve una ubicación para el cliente. Si no hay una coincidencia, puede que se pida al usuario que escriba una ubicación manualmente (según la configuración de la directiva de ubicación). Los datos de ubicación se transmiten de vuelta al cliente en un formato XML estandarizado del Grupo de trabajo de ingeniería de Internet (IETF) conocido como Objeto de ubicación para formato de datos de información sobre presencia (PIDF-LO).

El Skype para cliente empresarial incluye los datos PIDF-como parte de una llamada de emergencia, y estos datos se utilizan por el proveedor de servicios E9-1-1 para determinar el PSAP adecuado y enrutar la llamada a ese PSAP junto con el ESQK correcta, lo que permite que el distribuidor de servicio de emergencia a obtener la ubicación del autor de la llamada.

El siguiente diagrama muestra cómo un Skype para cliente de negocio adquiere una ubicación (excepto para el método de ubicación basados en direcciones MAC de cliente de terceros):

![Diagrama sobre cómo adquiere una ubicación el cliente](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Para que un cliente adquiera una ubicación, es preciso seguir estos pasos:

1. El administrador rellena la base de datos del servicio de información de ubicación con el diagrama de cables de red (tablas que asignan varios tipos de direcciones de red a las ubicaciones correspondientes de respuesta de emergencia (Erl)).

2. Si utiliza un proveedor de servicio E9-1-1 para troncos SIP, el administrador validará las partes de dirección postal de las ERL con una base de datos de guía de direcciones principal (MSAG) mantenida por el proveedor del servicio E9-1-1. Si utiliza una puerta de enlace ELIN, el administrador se asegurará de que la portadora RTC cargue las ELIN a la base de datos de identificación automática de ubicaciones (ALI).

3. Durante el registro o cada vez que se produce un cambio en la red, un cliente conectado internamente envía una solicitud de ubicación que contiene el cliente detectadas del servicio de información de ubicación de direcciones de red.

4. El servicio de información de ubicación consulta sus registros publicados para una ubicación y, si se encuentra una coincidencia, devuelve la ERL al cliente en formato PIDF-LO.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Enrutamiento de llamadas E9-1-1 por medio de un tronco SIP

El uso de un tronco SIP para conectarse a un proveedor de servicios E9-1-1 certificado es una manera de implementar E9-1-1. Para más detalles sobre el uso de una puerta de enlace ELIN para conectarse a un proveedor de servicios E9-1-1 basado en una red telefónica conmutada (RTC), vea [Routing E9-1-1 Calls by Using an ELIN Gateway](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).

En el siguiente diagrama se muestra cómo una llamada de emergencia se enruta desde Skype para Business Server a pública punto de respuesta de seguridad (PSAP) cuando se usa un tronco SIP y el proveedor de servicios E9-1-1 completa.

**Enrutamiento de llamadas E9-1-1 a través de un tronco SIP**

![Enrutar llamada de emergencia de Lync Server a un punto de respuesta de seguridad pública (PSAP)](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Cuando se realiza una llamada de emergencia desde un Skype compatible para el cliente de Business Server:

1. Una solicitud SIP INVITE que contiene la ubicación, el número de devolución de llamada del autor de la llamada y el número de devolución de llamada de conferencia y la dirección URL de notificación (opcional) se enruta a Skype para Business Server.

2. Skype para Business Server coincide con el número de emergencia y enruta la llamada (en función del valor de **Uso de RTC** que se define en la directiva de ubicación vigente) a un servidor de mediación y, desde allí, a través de un tronco SIP para el proveedor de servicios E9-1-1.

3. El proveedor de servicios E9-1-1 enruta la llamada de emergencia al PSAP adecuado según la ubicación proporcionada con la llamada. Cuando el cliente incluye una ubicación de respuesta de emergencia (ERL) validada en la llamada de emergencia, el proveedor dirige automáticamente la llamada al punto PSAP adecuado. Si el usuario especificó la ubicación manualmente, el centro de respuestas a llamadas de emergencia (ECRC) verifica verbalmente en primer lugar la exactitud de la ubicación con la persona que llama antes de enrutar la llamada de emergencia al PSAP.

4. Si ha configurado la directiva de ubicación para las notificaciones, uno o varios de los agentes de seguridad de su organización se envían un Skype especial de mensaje instantáneo de notificación de emergencia de negocio. Este mensaje siempre aparece en la pantalla o pantallas de los agentes de la seguridad y contiene el nombre del autor de la llamada, número de teléfono, hora y la ubicación, habilitar personal de seguridad responder rápidamente a la persona que llama emergencia mediante el uso de un mensaje instantáneo o voz.

5. Si ha configurado la directiva de ubicación para las conferencias y el proveedor de servicios E9-1-1 lo admite, el departamento de seguridad se unirá a la llamada en conferencia con audio unidireccional o bidireccional.

6. Si la llamada se interrumpe de forma prematura, el PSAP usa el número de devolución de llamada para contactar directamente con la persona que llama.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN

Algunos asociados del Programa de interoperabilidad abierto de comunicaciones unificadas proporcionan puertas de enlace de número de identificación de ubicación de emergencia (ELIN), que constituyen una alternativa a las conexiones troncales SIP con un proveedor de servicio E9-1-1 cualificado. Las puertas de enlace ELIN admiten la conectividad ISDN o de contabilización de mensajes automática y centralizada (CAMA) con servicios E9-1-1 basados en la red telefónica conmutada (RTC). Para obtener información detallada acerca de los socios que ofrecen las puertas de enlace ELIN y vínculos a la documentación, vea [infraestructura compatibles con Microsoft Lync](https://go.microsoft.com/fwlink/p/?LinkId=248425) e [Infraestructura de telefonía de Skype para la empresa](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

Al igual que las conexiones troncales SIP con los proveedores de servicios E9-1-1, las puertas de enlace ELIN también ofrecen los medios necesarios para enrutar una llamada de emergencia al punto de respuesta de seguridad pública (PSAP) más adecuado para el autor de la llamada, pero estas puertas de enlace usan un número ELIN para identificar la ubicación. Definir Elin para cada ubicación de respuesta de emergencia (ERL) de la organización (para obtener información detallada, vea [Administrar ubicaciones para puertas de enlace ELIN en Skype para Business Server](elin-gateways.md)).

Cuando se utiliza una puerta de enlace ELIN para las llamadas de emergencia, utilice el mismo Skype para infraestructura de Business Server E9-1-1 que usaría para una conexión troncal SIP. Es decir, la base de datos de servicio de información de ubicación proporciona la ubicación a la Skype para clientes empresariales, y habilita la característica de la directiva de ubicación y define el enrutamiento. Con una puerta de enlace ELIN, sin embargo, es necesario agregar los Elin a la base de datos de servicio de información de ubicación y tener su operador de RTC cargarlos en la base de datos de identificación de ubicación automática (ALI).

Cuando un Skype para cliente empresarial obtiene su ubicación del servicio de información de ubicación, la ubicación incluye el ELIN. Durante una llamada de emergencia, el ELIN se incluye con la ubicación que se envían a la puerta de enlace ELIN. La puerta de enlace ELIN identifica la llamada como una llamada de emergencia e intercambia el número de la persona que llama con la ELIN. La puerta de enlace ELIN, a continuación, enruta la llamada a la RTC con la ELIN como el número de llamada. El proveedor de RTC E9-1-1 busca los ELIN en la base de datos ALI, que es una base de datos complementarios a la base de datos maestra calle dirección guía (MSAG). La RTC, a continuación, envía la llamada al PSAP más adecuado en función de la búsqueda de ALI, y el servicio de emergencia envía equipos de primeros respuesta a la ubicación del autor de la llamada en función de la búsqueda de ALI. El número de llamada se almacena en caché en la puerta de enlace ELIN para un período predefinido de tiempo para realizar devoluciones de llamadas. Durante una devolución de llamada, el servicio de emergencia llega a la puerta de enlace ELIN, que intercambia los ELIN para directa hacia dentro (número el autor de la llamada DID).

Las puertas de enlace ELIN admiten llamadas de emergencia únicamente desde dentro de la red de la organización; no admite llamadas externas.

> [!NOTE]
> Para obtener información detallada sobre cómo usar una conexión troncal SIP en las llamadas de emergencia, consulte [Routing E9-1-1 Calls by Using a SIP Trunk](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx).

En el siguiente diagrama se muestra cómo una llamada de emergencia se enruta desde Skype para Business Server al PSAP cuando se utiliza una puerta de enlace ELIN.

**Enrutamiento de llamadas E9-1-1 con una puerta de enlace ELIN**

![Muestra cómo una llamada a los servicios de emergencia pasa por el servidor de mediación al proveedor de los servicios de emergencias. Tras esto, puede que se envíe un mensaje instantáneo a la seguridad del sitio, o que se devuelva la llamada al autor de la llamada original.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Una solicitud SIP INVITE que contiene la ubicación, el número de devolución de llamada del autor de la llamada y el número de devolución de llamada de conferencia y la dirección URL de notificación (opcional) se enruta a Skype para Business Server.

2. Skype para Business Server coincide con el número de emergencia y, a continuación, enruta la llamada (basada en el valor de **Uso de RTC** definido en la directiva de ubicación vigente) a un servidor de mediación y, desde allí, a una puerta de enlace ELIN.

3. La puerta de enlace ELIN enruta la llamada a través de un tronco ISDN o CAMA a la RTC.

4. La RTC identifica la llamada como una llamada de emergencia y la enruta a un enrutador selectivo de E9-1-1 de la red, que busca el número del autor de la llamada en la base de datos ALI para obtener la ubicación geográfica. Tras ello, el enrutador selectivo de E9-1-1 envía la llamada al PSAP más adecuado en función de la información de ubicación que haya suministrado la base de datos ALI. 

5. Si ha configurado la directiva de ubicación para las notificaciones, uno o varios de los agentes de seguridad de su organización se envían un Skype especial de mensaje instantáneo de notificación de emergencia de negocio. Este mensaje siempre aparece en la pantalla o pantallas de los agentes de la seguridad y contiene el nombre del autor de la llamada, número de teléfono, hora y la ubicación, habilitar personal de seguridad responder rápidamente a la persona que llama emergencia mediante el uso de un mensaje instantáneo o voz.

6. En caso de que la llamada se interrumpa antes de tiempo, el PSAP usa el ELIN para ponerse en contacto directamente con el autor de la llamada. La puerta de enlace ELIN intercambia el ELIN por el DID del autor de la llamada.


