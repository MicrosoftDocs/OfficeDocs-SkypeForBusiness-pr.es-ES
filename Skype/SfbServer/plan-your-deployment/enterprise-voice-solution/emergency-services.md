---
title: Plan de servicios de emergencia en Skype para Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: Conozca los servicios Enhanced 9-1-1 (E9-1-1) en Skype para Telefonía IP empresarial de Business Server, incluyendo adquisición de ubicación y enrutamiento de llamadas.
ms.openlocfilehash: b54a431d831c8b2b8a38e4512286ddd1499a9fe8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-emergency-services-in-skype-for-business-server-2015"></a>Plan de servicios de emergencia en Skype para Business Server 2015
 
Conozca los servicios Enhanced 9-1-1 (E9-1-1) en Skype para Telefonía IP empresarial de Business Server, incluyendo adquisición de ubicación y enrutamiento de llamadas.
  
Skype para Business Server admite los servicios Enhanced 9-1-1 (E9-1-1) dentro de Estados Unidos como parte de una implementación de Telefonía IP empresarial. E9-1-1 es una característica de envío de emergencia que asocia una llamada 9-1-1 con una ubicación de respuesta de emergencia (ERL) que consta de direcciones de la ciudad (es decir, postal) y otra información de ubicación más específica, como los números de planta, para las llamadas de edificios de oficinas y otras instalaciones multiempresa. Con el uso de la ERL proporcionada, un Punto de respuesta de seguridad pública (PSAP) puede enviar inmediatamente los servicios de emergencia a la persona que realiza la llamada en apuros con un riesgo menor de dirigir accidentalmente los servicios de emergencias a una ubicación incorrecta o ambigua.
  
> [!NOTE]
> Skype para Business Server ahora admite la configuración de varios números de emergencia para un cliente. Para obtener más información, consulte [Plan para varios números de emergencia en Skype para Business Server 2015](multiple-emergency-numbers.md). 
  
> [!NOTE]
> Skype para Business Server tiene tres características avanzadas de Telefonía IP empresarial: llame a la omisión de medios, servicios de emergencia (E9-1-1) y el control de admisión. Para obtener una introducción de la información que es común a las tres de estas características de diseño, vea [configuración de red para las funciones avanzadas de Telefonía IP empresarial en Skype para Business Server 2015](network-settings-for-advanced-features.md). 
  
Skype para Business Server es compatible con Enhanced 9-1-1 (E9-1-1) llamando desde Skype para clientes empresariales y dispositivos de Lync Phone Edition. Al configurar Skype para Business Server para llamadas E9-1-1, la emergencia de Skype para empresas o Lync Phone Edition incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos del servicio de información de la ubicación. Las ERL se componen de direcciones civiles (es decir, postales) e información adicional que ayuda a identificar con mayor precisión una ubicación en edificios de oficinas y otras instalaciones con varios inquilinos. Cuando un usuario realiza una llamada de emergencia, Skype para Business Server enruta la llamada de audio, junto con la información de ubicación y devolución de llamada, a través de un servidor de mediación para un proveedor de servicios de E9-1-1. Desde aquí se facilita la ubicación del autor de la llamada junto con una clave de consulta de servicios de emergencia (ESQK) que permite al PSAP buscar la ERL de esta persona. 
  
Skype para Business Server admite dos métodos de enrutamiento llamadas de emergencia a un proveedor de servicios de E9-1-1:
  
- Una conexión de enlace troncal SIP (Protocolo de inicio de sesión) a un proveedor de servicios E9-1-1 cualificado.
    
- Una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios E9-1-1 basado en una Red telefónica conmutada (RTC).
    
Cuando se utiliza un proveedor de servicios SIP tronco E9-1-1, agregue ERLs a la base de datos del servicio de información de ubicación y, a continuación, validar las ubicaciones contra una guía de dirección de la calle del maestro (MSAG) que es mantenida por el proveedor de servicio de E9-1-1. Si un proveedor de servicios de E9-1-1 recibe una llamada que no tiene información de ubicación o que tenga una ubicación que no se ha validado contra el MSAG, el proveedor de servicios de E9-1-1 enruta la llamada a una emergencia llamar respuesta centro (ECRC), que es nacional y regional cuenta con personal especializado que obtienen verbalmente la ubicación del llamador, si es posible y manualmente enrutar la llamada a lo PSAP apropiado. Algunos proveedores de servicios E9-1-1 de enlace troncal SIP también proporcionan a los clientes un número de marcado directo (DID) de RTC para el ECRC, que constituye un medio alternativo de enrutamiento de las llamadas al 9-1-1 si por algún motivo se produce un error en el enlace troncal SIP.
  
A diferencia de tiempo division multiplexing (TDM) y teléfonos de basado en IP private branch exchange (PBX), que poseen ubicaciones fijas, un Skype para el extremo del negocio puede ser muy móvil. Cuando se implementa la característica E9-1-1, Skype para Business Server ayuda a garantizar que independientemente de la que una persona que llama, la llamada de emergencia puede enrutarse a lo PSAP que sirve de ubicación del llamador. Por ejemplo, si la oficina principal de un usuario se encuentra en Redmond, Washington, pero el usuario coloca una llamada de emergencia desde un equipo en una sucursal en Wichita, Kansas, el tronco SIP o proveedor de servicios basada en PSTN E9-1-1 enrutará la llamada al PSAP en Wichita , no para el PSAP en Redmond.
  
Cuando se utiliza una puerta de enlace ELIN, también agrega ERLs a la base de datos del servicio de información de ubicación, pero también incluye un número ELIN para cada ubicación. El número ELIN pasa a ser el número de llamada SOS durante la llamada. Es preciso comprobar que el proveedor de RTC carga los ELIN en una base de datos de identificación de ubicación automática (ALI). 
  
> [!NOTE]
> Skype para dispositivos analógicos conectados de negocio no puede recibir información de ubicación del servicio de información de ubicación o transmitir ubicación al proveedor de servicios E9-1-1. 
  
 Si usa la opción del proveedor de servicios E9-1-1 de enlace troncal SIP y tiene que admitir llamadas E9-1-1 desde teléfonos analógicos, tiene dos opciones:
  
- **Opción tradicional PS-ALI** Si dispone de puertas de enlace de RTC locales en cada sitio donde se implementan los teléfonos analógicos y cada teléfono analógico tiene un DID, puede suministrar la ubicación del dispositivo analógico directamente con un proveedor de servicios de identificación de ubicación privada conmutador automáticas (PS-ALI). En este caso, puede configura Skype diseñado especialmente para las políticas del negocio voz y asignarlos al dispositivo analógico objetos de contacto para que las llamadas desde los teléfonos E9-1-1 enruten directamente a través de la puerta de enlace local al proveedor de PSTN (en su lugar el sitio de servicios de enrutar la llamada a un proveedor de servicios de E9-1-1 SIP trunk). Cuando se realiza una llamada SOS, una base de datos de un proveedor de PS-ALI asociado con el enlace troncal de RTC asigna el DID de cada teléfono analógico a una ubicación física, y proporciona esta ubicación al PSAP. Estos registros necesitan actualizarse con el proveedor de servicios de PS-ALI cada vez que los teléfonos se desplazan a ERL diferentes.
    
- **Opción de proveedor de servicio E9-1-1** Puede registrar el DIDs de teléfono analógico y sus correspondientes ERLs con el proveedor de servicio E9-1-1, si es compatible con el proveedor del servicio E9-1-1. Si el proveedor recibe una llamada de Skype para que no incluya datos PIDF-LO Business Server, el proveedor puede ver si hay una coincidencia de la base de datos en un número DID de la persona que llama. Utilizando el ERL recuperado automáticamente desde su base de datos, el proveedor puede enrutar la llamada de emergencia para el PSAP correcto y el PSAP recibirá el DID del dispositivo analógico y un registro ESQK que permite que el distribuidor buscar la ubicación del llamador.
    
Si usa la opción de puerta de enlace de ELIN y necesita compatibilidad con las llamadas E9-1-1 desde teléfonos analógicos, puede dar la ubicación del dispositivo analógico directamente con el proveedor de servicios PS-ALI, como se describe en la primera opción mencionada anteriormente.
  
Desde un Skype para perspectiva Business Server, el proceso de E9-1-1 se puede dividir en dos etapas:
  
- Fase 1: adquisición de una ubicación
    
- Fase 2: enrutamiento de la llamada SOS al proveedor de servicios E9-1-1
    
En esta sección se describe cómo funcionan estas fases.
  
Si va a configurar la infraestructura para detectar automáticamente la ubicación del cliente, primero necesita decidir qué elementos de red usará para asignar los autores de las llamadas a las ubicaciones. Para obtener más información acerca de las opciones posibles, consulte [definición de los elementos de red que se utilizan para determinar la ubicación de Skype para Business Server 2015](network-location.md). 
  
## <a name="acquiring-a-location"></a>Adquirir una ubicación

En un Skype para la implementación de Business Server E9-1-1, cada Skype conectado internamente para clientes empresariales o Lync Phone Edition adquiere activamente su propia ubicación. Después del registro SIP, el cliente proporciona toda la información de conectividad de red que lo sabe acerca de sí mismo en una solicitud de ubicación para el servicio de información de ubicación, que es un servicio web respaldado por una base de datos replicada de SQL Server. Cada grupo de sitio central tiene un servicio de información de ubicación que utiliza la información de red para consultar sus registros para una ubicación coincidente. Si hay una coincidencia, el servicio de información de ubicación devuelve una ubicación para el cliente. Si no hay una coincidencia, puede que se pida al usuario que escriba una ubicación manualmente (según la configuración de la directiva de ubicación). Los datos de ubicación se transmiten de vuelta al cliente en un formato XML estandarizado del Grupo de trabajo de ingeniería de Internet (IETF) conocido como Objeto de ubicación para formato de datos de información sobre presencia (PIDF-LO).
  
El Skype para Business client incluye los datos PIDF-LO como parte de una llamada de emergencia, y estos datos se utilizan por el proveedor de servicio E9-1-1 para determinar el PSAP apropiado y enrutar la llamada a ese PSAP junto con el ESQK correcta, lo que permite que el distribuidor los PSAP obtener la ubicación del llamador.
  
El siguiente diagrama muestra cómo un Skype para cliente empresarial adquiere una ubicación (excepto para el método de ubicación basados en direcciones MAC de cliente de terceros):
  
![Diagrama sobre cómo adquiere una ubicación el cliente](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)
  
Para que un cliente adquiera una ubicación, es preciso seguir estos pasos:
  
1. El administrador rellena la base de datos del servicio de información de ubicación con el diagrama de cableado de red (tablas que varios tipos de direcciones de red se asignan a las ubicaciones correspondientes de respuesta de emergencia (ERLs)).
    
2. Si utiliza un proveedor de servicio E9-1-1 para troncos SIP, el administrador validará las partes de dirección postal de las ERL con una base de datos de guía de direcciones principal (MSAG) mantenida por el proveedor del servicio E9-1-1. Si utiliza una puerta de enlace ELIN, el administrador se asegurará de que la portadora RTC cargue las ELIN a la base de datos de identificación automática de ubicaciones (ALI).
    
3. Durante el registro o cuando se produce un cambio de red, un cliente conectado internamente envía una solicitud de ubicación que contiene el cliente de descubierto direcciones de red con el servicio de información de ubicación.
    
4. El servicio de información de ubicación consulta sus registros para una ubicación publicadas y, si se encuentra una coincidencia, devuelve el ERL para el cliente en formato PIDF-LO.
    
## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Enrutamiento de llamadas E9-1-1 por medio de un tronco SIP

El uso de un tronco SIP para conectarse a un proveedor de servicios E9-1-1 certificado es una manera de implementar E9-1-1. Para obtener más información acerca de cómo utilizar una puerta de enlace ELIN para conectarse a una red telefónica pública conmutada (PSTN)-base E9-1-1 proveedor de servicios, vea [Enrutamiento de llamadas de E9-1-1 mediante el uso de una puerta de enlace de ELIN](http://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).
  
El diagrama siguiente muestra cómo una llamada de emergencia se enruta de Skype para Business Server a la pública seguridad contestando punto (PSAP) cuando utiliza un troncal SIP y el proveedor de servicios calificado de E9-1-1.
  
**Enrutar las llamadas a través de un SIP trunk E9-1-1**

![Enrutar llamada de emergencia de Lync Server a un punto de respuesta de seguridad pública (PSAP)](../../media/Plan_LyncServer_E911_CallRouting.jpg)
  
Cuando se coloca una llamada de emergencia desde un Skype compatible para el cliente de Business Server:
  
1. Un SIP INVITE que contiene la ubicación, el número de devolución de llamada y el número de devolución de llamada de conferencia y URL de notificación (opcional) se enruta a Skype para Business Server.
    
2. Skype para Business Server coincide con el número de emergencia y enruta la llamada (basada en el valor de **Uso de RTC** que se define en la directiva aplicable ubicación) a un servidor de mediación y, desde ahí, sobre un tronco SIP al proveedor de servicios E9-1-1.
    
3. El proveedor de servicios E9-1-1 enruta la llamada de emergencia al PSAP adecuado según la ubicación proporcionada con la llamada. Cuando el cliente incluye una ubicación de respuesta de emergencia (ERL) validada en la llamada de emergencia, el proveedor dirige automáticamente la llamada al punto PSAP adecuado. Si el usuario especificó la ubicación manualmente, el centro de respuestas a llamadas de emergencia (ECRC) verifica verbalmente en primer lugar la exactitud de la ubicación con la persona que llama antes de enrutar la llamada de emergencia al PSAP.
    
4. Si ha configurado la directiva de ubicación para las notificaciones, uno o más de los agentes de seguridad de la organización se envían un Skype para mensajes instantáneos de negocios notificación de emergencia especial. Este mensaje siempre aparece en las pantallas de los agentes de la seguridad y contiene el nombre, número de teléfono, hora y ubicación, habilitación de personal de seguridad responder rápidamente a la llamada de emergencia mediante un mensaje instantáneo o la voz del llamador.
    
5. Si ha configurado la directiva de ubicación para las conferencias y el proveedor de servicios E9-1-1 lo admite, el departamento de seguridad se unirá a la llamada en conferencia con audio unidireccional o bidireccional.
    
6. Si la llamada se interrumpe de forma prematura, el PSAP usa el número de devolución de llamada para contactar directamente con la persona que llama.
    
## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN

Algunos asociados del Programa de interoperabilidad abierto de comunicaciones unificadas proporcionan puertas de enlace de número de identificación de ubicación de emergencia (ELIN), que constituyen una alternativa a las conexiones troncales SIP con un proveedor de servicio E9-1-1 cualificado. Las puertas de enlace ELIN admiten la conectividad ISDN o de contabilización de mensajes automática y centralizada (CAMA) con servicios E9-1-1 basados en la red telefónica conmutada (RTC). Para obtener más información acerca de los socios que proporcionan vínculos a la documentación y las puertas de enlace ELIN, vea [Infraestructura de telefonía de Skype para el negocio](https://technet.microsoft.com/en-us/office/dn947483)y la [infraestructura calificado para Microsoft Lync](https://go.microsoft.com/fwlink/p/?LinkId=248425) . 
  
Al igual que las conexiones troncales SIP con los proveedores de servicios E9-1-1, las puertas de enlace ELIN también ofrecen los medios necesarios para enrutar una llamada de emergencia al punto de respuesta de seguridad pública (PSAP) más adecuado para el autor de la llamada, pero estas puertas de enlace usan un número ELIN para identificar la ubicación. Definir ELINs para cada ubicación de respuesta de emergencia (ERL) de la organización (para obtener más información, consulte [Administrar ubicaciones para puertas de enlace ELIN en Skype para Business Server 2015](elin-gateways.md)). 
  
Cuando se utiliza una puerta de enlace ELIN para llamadas de emergencia, utilice el mismo Skype para la infraestructura de servidor empresarial E9-1-1 que usaría para una conexión de troncal SIP. Es decir, la base de datos del servicio de información de la ubicación proporciona la ubicación para el Skype para cliente de negocios, y habilita la característica de la política de ubicación y define el enrutamiento. Con una puerta de enlace ELIN, sin embargo, debe agregar el ELINs a la base de datos del servicio de información de ubicación y tienen su operador de telefonía PSTN cargarlos en la base de datos de identificación de ubicación automática (ALI).
  
Cuando un Skype para Business client obtiene su ubicación desde el servicio de información de la ubicación, la ubicación incluye el ELIN. Durante una llamada de emergencia, el ELIN se incluye en la ubicación que se envían a la puerta de enlace ELIN. La puerta de enlace ELIN identifica la llamada como una llamada de emergencia e intercambia el número de la persona que llama con el ELIN. La puerta de enlace ELIN enruta la llamada a la RTC con el ELIN como el número de llamada. El proveedor de PSTN E9-1-1 busca el ELIN en la base de datos de ALI, que es una base de datos del Asistente para la base de datos de la Guía de dirección de la calle principal (MSAG). La RTC, a continuación, envía la llamada a lo PSAP más apropiado basándose en la búsqueda de ALI y el PSAP envía equipos de primeras respuesta a la ubicación del llamador basándose en la búsqueda de ALI. El número de llamada se almacena en caché en la puerta de enlace ELIN para un período predefinido de tiempo para las devoluciones de llamada. Durante una devolución de llamada, el PSAP llega a la puerta de enlace ELIN, que intercambia la ELIN para el número de marcado interno directo (DID).
  
Las puertas de enlace ELIN admiten llamadas de emergencia únicamente desde dentro de la red de la organización; no admite llamadas externas.
  
> [!NOTE]
> Para obtener más información acerca del uso de una conexión de troncal SIP para llamadas de emergencia, vea [Enrutamiento de llamadas de E9-1-1 utilizando un troncal SIP](http://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx). 
  
El diagrama siguiente muestra cómo una llamada de emergencia se enruta de Skype para Business Server el PSAP cuando se utiliza una puerta de enlace ELIN.
  
**Enrutar las llamadas E9-1-1 con una puerta de enlace ELIN**

![Muestra cómo una llamada a los servicios de emergencia pasa por el servidor de mediación al proveedor de los servicios de emergencias. Tras esto, puede que se envíe un mensaje instantáneo a la seguridad del sitio, o que se devuelva la llamada al autor de la llamada original.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)
  
1. Un SIP INVITE que contiene la ubicación, el número de devolución de llamada y el número de devolución de llamada de conferencia y URL de notificación (opcional) se enruta a Skype para Business Server.
    
2. Skype para Business Server coincide con el número de emergencia y enruta la llamada (basada en el valor de **Uso de RTC** definido en la directiva aplicable ubicación) a un servidor de mediación y de allí a una puerta de enlace ELIN.
    
3. La puerta de enlace ELIN enruta la llamada a través de un tronco ISDN o CAMA a la RTC.
    
4. La RTC identifica la llamada como una llamada de emergencia y la enruta a un enrutador selectivo de E9-1-1 de la red, que busca el número del autor de la llamada en la base de datos ALI para obtener la ubicación geográfica. Tras ello, el enrutador selectivo de E9-1-1 envía la llamada al PSAP más adecuado en función de la información de ubicación que haya suministrado la base de datos ALI.  
    
5. Si ha configurado la directiva de ubicación para las notificaciones, uno o más de los agentes de seguridad de la organización se envían un Skype para mensajes instantáneos de negocios notificación de emergencia especial. Este mensaje siempre aparece en las pantallas de los agentes de la seguridad y contiene el nombre, número de teléfono, hora y ubicación, habilitación de personal de seguridad responder rápidamente a la llamada de emergencia mediante un mensaje instantáneo o la voz del llamador.
    
6. En caso de que la llamada se interrumpa antes de tiempo, el PSAP usa el ELIN para ponerse en contacto directamente con el autor de la llamada. La puerta de enlace ELIN intercambia el ELIN por el DID del autor de la llamada.
    

