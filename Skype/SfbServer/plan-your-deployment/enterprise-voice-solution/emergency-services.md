---
title: Planear los servicios de emergencia en Skype Empresarial Server
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
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: Obtenga información sobre los servicios mejorados de 9-1-1 (E9-1-1) en Skype Empresarial Server Telefonía IP empresarial, incluida la adquisición de ubicación y el enrutamiento de llamadas.
ms.openlocfilehash: d480a679367da4e8b6070c69127735b7ab59252d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101556"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planear los servicios de emergencia en Skype Empresarial Server

Obtenga información sobre los servicios mejorados de 9-1-1 (E9-1-1) en Skype Empresarial Server Telefonía IP empresarial, incluida la adquisición de ubicación y el enrutamiento de llamadas.

Skype Empresarial Server admite servicios mejorados 9-1-1 (E9-1-1) en los Estados Unidos como parte de una Telefonía IP empresarial implementación. E9-1-1 es una característica de envío de emergencia que asocia un llamada 9-1-1 con una ubicación de respuesta de emergencia (ERL) que consta de direcciones de la ciudad (es decir, calle) y otra información de ubicación más específica, como los números de planta, para las llamadas de edificios de oficinas y otras instalaciones multiempresa. Mediante el uso de la ERL proporcionada, un Punto de respuesta de seguridad pública (PSAP) puede enviar inmediatamente a los primeros usuarios que responden a la persona que realiza la llamada en apuros con un riesgo menor de dirigir inadvertidamente al interlocutor a una ubicación incorrecta o es ambigua.

> [!NOTE]
> Skype Empresarial Server ahora admite la configuración de varios números de emergencia para un cliente. Para obtener más información, vea [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md).

> [!NOTE]
> Skype Empresarial Server tiene tres características Telefonía IP empresarial avanzadas: control de admisión de llamadas, servicios de emergencia (E9-1-1) y desvío de medios. Para obtener información general sobre la planeación que es común a las tres características, vea Configuración de red para las características Telefonía IP empresarial avanzadas en [Skype Empresarial Server](network-settings-for-advanced-features.md).

Skype Empresarial Server admite llamadas mejoradas 9-1-1 (E9-1-1) desde clientes de Skype Empresarial y dispositivos Lync Phone Edition. Al configurar Skype Empresarial Server para E9-1-1, las llamadas de emergencia realizadas desde Skype Empresarial o Lync Phone Edition incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos del servicio de información de ubicación. Las ERL se componen de direcciones civiles (es decir, postales) e información adicional que ayuda a identificar con mayor precisión una ubicación en edificios de oficinas y otras instalaciones con varios inquilinos. Cuando un usuario realiza una llamada de emergencia, Skype Empresarial Server enruta el audio de la llamada, junto con la ubicación y la información de devolución de llamada, a través de un servidor de mediación a un proveedor de servicios E9-1-1. Desde aquí se facilita la ubicación del autor de la llamada junto con una clave de consulta de servicios de emergencia (ESQK) que permite al PSAP buscar la ERL de esta persona.

Skype Empresarial Server admite dos métodos para enrutar llamadas de emergencia a un proveedor de servicios E9-1-1:

- Una conexión de enlace troncal SIP (Protocolo de inicio de sesión) a un proveedor de servicios E9-1-1 cualificado.

- Una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios E9-1-1 basado en una Red telefónica conmutada (RTC).

Cuando se usa un proveedor de servicios E9-1-1 de tronco SIP, se agregan ERLs a la base de datos del servicio de información de ubicación y, a continuación, se validan las ubicaciones con una Guía maestra de direcciones de calle (MSAG) que mantiene el proveedor de servicios E9-1-1. Si un proveedor de servicios E9-1-1 recibe una llamada que no tiene información de ubicación o tiene una ubicación que no se ha validado en MSAG, el proveedor de servicios E9-1-1 enruta la llamada a un Centro de respuesta a llamadas de emergencia (ECRC) nacional o regional, que está formado por personal especialmente formado que obtiene verbalmente la ubicación del autor de la llamada, si es posible, y enruta manualmente la llamada al PSAP adecuado. Algunos proveedores de servicios E9-1-1 de enlace troncal SIP también proporcionan a los clientes un número de marcado directo (DID) de RTC para el ECRC, que constituye un medio alternativo de enrutamiento de las llamadas al 9-1-1 si por algún motivo se produce un error en el enlace troncal SIP.

A diferencia de la multiplexación de división de tiempo (TDM) y los teléfonos de central de conmutación (PBX) basados en IP, que tienen ubicaciones fijas, un extremo de Skype Empresarial puede ser muy móvil. Al implementar la característica E9-1-1, Skype Empresarial Server ayuda a garantizar que, independientemente de dónde se encuentra el autor de la llamada, la llamada de emergencia se puede enrutar al PSAP que sirve la ubicación del autor de la llamada. Por ejemplo, si la oficina principal de un usuario se encuentra en Redmond, Washington, pero el usuario hace una llamada de emergencia desde un equipo de una sucursal en Wichita, Kansas, el tronco SIP o el proveedor de servicios E9-1-1 basado en RTC enrutarán la llamada al PSAP en Wichita, no al PSAP en Redmond.

Cuando se usa una puerta de enlace ELIN, también se agregan LASR a la base de datos del servicio de información de ubicación, pero también se incluye un número ELIN para cada ubicación. El número ELIN pasa a ser el número de llamada SOS durante la llamada. Debe comprobar que el proveedor de RTC carga los ELIN en una base de datos de identificación de ubicación automática (ALI).

> [!NOTE]
> Los dispositivos analógicos conectados a Skype Empresarial no pueden recibir información de ubicación del servicio de información de ubicación ni transmitir la ubicación al proveedor de servicios E9-1-1.

 Si usa la opción del proveedor de servicios E9-1-1 de enlace troncal SIP y tiene que admitir llamadas E9-1-1 desde teléfonos analógicos, tiene dos opciones:

- **Opción PS-ALI tradicional** Si tienes puertas de enlace RTC locales en cada sitio donde se implementan teléfonos analógicos y cada teléfono analógico tiene un DID, puedes aprovisionar la ubicación del dispositivo analógico directamente con un proveedor de servicios de identificación de ubicación automática (PS-ALI). En este caso, se configuran directivas de voz de Skype Empresarial especialmente diseñadas y se asignan a los objetos de contacto de dispositivo analógico para que las llamadas E9-1-1 de esos teléfonos se enruten directamente a través de la puerta de enlace local al proveedor rtc que proporciona servicios al sitio (en lugar de enrutar la llamada a un tronco SIP del proveedor de servicios E9-1-1). Cuando se realiza una llamada SOS, una base de datos de un proveedor de PS-ALI asociado con el enlace troncal de RTC asigna el DID de cada teléfono analógico a una ubicación física, y proporciona esta ubicación al PSAP. Estos registros deben actualizarse con el proveedor de servicios de PS-ALI cada vez que los teléfonos se desplazan a ERL diferentes.

- Opción de proveedor de servicios **E9-1-1** Puede registrar los DID de teléfono analógico y sus ERLs correspondientes con el proveedor de servicios E9-1-1, si es compatible con el proveedor de servicios E9-1-1. Si el proveedor recibe una llamada de Skype Empresarial Server que no incluye datos PIDF-LO, el proveedor puede ver si hay una coincidencia de base de datos en el número DID de la parte que realiza la llamada. Mediante el ERL recuperado de su base de datos, el proveedor puede enrutar automáticamente la llamada de emergencia al PSAP correcto y el PSAP recibirá el DID del dispositivo analógico y un registro ESQK que permite al distribuidor buscar la ubicación del autor de la llamada.

Si usa la opción de puerta de enlace de ELIN y necesita compatibilidad con las llamadas E9-1-1 desde teléfonos analógicos, puede dar la ubicación del dispositivo analógico directamente con el proveedor de servicios PS-ALI, como se describe en la primera opción mencionada anteriormente.

Desde una perspectiva de Skype Empresarial Server, el proceso E9-1-1 se puede separar en dos fases:

- Fase 1: adquisición de una ubicación

- Fase 2: enrutamiento de la llamada SOS al proveedor de servicios E9-1-1

En esta sección se describe cómo funcionan estas fases.

Si va a configurar la infraestructura para detectar automáticamente la ubicación del cliente, primero debe decidir qué elementos de red usará para asignar los autores de las llamadas a las ubicaciones. Para obtener más información sobre las opciones posibles, vea [Definir los elementos de red usados para determinar](network-location.md)la ubicación en Skype Empresarial Server .

## <a name="acquiring-a-location"></a>Adquirir una ubicación

En una implementación de Skype Empresarial Server E9-1-1, cada cliente de Skype Empresarial o Lync Phone Edition conectado internamente adquiere activamente su propia ubicación. Después del registro SIP, el cliente proporciona toda la información de conectividad de red que conoce sobre ella en una solicitud de ubicación al servicio de información de ubicación, que es un servicio web con el respaldo de una base de datos SQL Server replicada. Cada grupo de sitios centrales tiene un servicio de información de ubicación, que usa la información de red para consultar sus registros en busca de una ubicación que coincida. Si hay una coincidencia, el servicio de información de ubicación devuelve una ubicación al cliente. Si no hay ninguna coincidencia, puede que se pida al usuario que escriba una ubicación manualmente (según la configuración de la directiva de ubicación). Los datos de ubicación se devuelven al cliente en un formato XML estándar de grupo de trabajo de ingeniería de Internet (IETF) denominado PIDF-LO (Presence Information Data Format Location Object).

El cliente de Skype Empresarial incluye los datos PIDF-LO como parte de una llamada de emergencia y el proveedor de servicios E9-1-1 usa estos datos para determinar el PSAP adecuado y enrutar la llamada a ese PSAP junto con el ESQK correcto, lo que permite al distribuidor de PSAP obtener la ubicación del autor de la llamada.

En el diagrama siguiente se muestra cómo un cliente de Skype Empresarial adquiere una ubicación (excepto para el método de ubicación basada en direcciones MAC del cliente de terceros):

![Cómo el cliente adquiere un diagrama de ubicación](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Para que el cliente pueda adquirir la ubicación, deben llevarse a cabo los pasos siguientes:

1. El administrador rellena la base de datos del servicio de información de ubicación con el mapa de conexión de red (tablas que asignan varios tipos de direcciones de red a las ubicaciones de respuesta de emergencia (ERLs) correspondientes).

2. Si usa un proveedor de servicios E9-1-1 mediante troncos SIP, el administrador valida la parte de la dirección postal de la ERL con una base de datos de guía de direcciones principal (MSAG) del proveedor de servicios E9-1-1. Si usa una puerta de enlace ELIN, el administrador se asegura de que el operador de RTC cargue los ELIN en la base de datos de identificación de ubicación automática (ALI).

3. Durante el registro o cuando se produce un cambio de red, un cliente conectado internamente envía una solicitud de ubicación que contiene las direcciones de red detectadas del cliente al servicio de información de ubicación.

4. El servicio de información de ubicación consulta sus registros publicados para una ubicación y, si se encuentra una coincidencia, devuelve el ERL al cliente en formato PIDF-LO.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Enrutamiento de llamadas E9-1-1 con un tronco SIP

El uso de troncos SIP para establecer una conexión con un proveedor de servicios E9-1-1 es una de las formas de implementar servicios E9-1-1. Para obtener detalles sobre el uso de una puerta de enlace ELIN para conectar con un proveedor de servicios E9-1-1 mediante la red pública conmutada (RTC), vea [Routing E9-1-1 Calls by Using an ELIN Gateway](/previous-versions/office/lync-server-2013/lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway).

En el siguiente diagrama se muestra cómo se enruta una llamada de emergencia de Skype Empresarial Server al Punto de respuesta de seguridad pública (PSAP) cuando se usa un tronco SIP y un proveedor de servicios E9-1-1 cualificado.

**Enrutamiento de llamadas E9-1-1 mediante troncos SIP**

![Enrutamiento de llamadas de emergencia de Lync Server a PSAP](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Cuando se hace una llamada de emergencia desde un cliente compatible de Skype Empresarial Server:

1. Una INVITACIÓN SIP que contiene la ubicación, el número de devolución de llamada del autor de la llamada y la dirección URL de notificación (opcional) y el número de devolución de llamada de conferencia se enruta a Skype Empresarial Server.

2. Skype Empresarial Server coincide con el número de emergencia  y enruta la llamada (en función del valor de uso rtc que se define en la directiva de ubicación aplicable) a un servidor de mediación y, desde allí, a través de un tronco SIP al proveedor de servicios E9-1-1.

3. El proveedor de servicios E9-1-1 enruta la llamada de emergencia al PSAP adecuado según la ubicación proporcionada con la llamada. Cuando el cliente incluye una ubicación de respuesta de emergencia (ERL) validada en la llamada de emergencia, el proveedor dirige automáticamente la llamada al punto PSAP adecuado. Si el usuario especificó la ubicación manualmente, el centro de respuestas a llamadas de emergencia (ECRC) verifica verbalmente en primer lugar la exactitud de la ubicación con la persona que llama antes de enrutar la llamada de emergencia al PSAP.

4. Si configuró la directiva de ubicación para las notificaciones, uno o varios de los responsables de seguridad de su organización se envían un mensaje instantáneo de notificación de emergencia de Skype Empresarial especial. Este mensaje siempre aparece en la pantalla de los agentes de seguridad y contiene el nombre, el número de teléfono, la hora y la ubicación del autor de la llamada, lo que permite al personal de seguridad responder rápidamente al autor de la llamada de emergencia mediante un mensaje instantáneo o una voz.

5. Si ha configurado la directiva de ubicación para las conferencias y el proveedor de servicios E9-1-1 lo admite, el departamento de seguridad se unirá a la llamada en conferencia con audio unidireccional o bidireccional.

6. Si la llamada se interrumpe de forma prematura, el PSAP usa el número de devolución de llamada para contactar directamente con la persona que llama.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN

Algunos asociados del Programa de interoperabilidad abierto de comunicaciones unificadas proporcionan puertas de enlace de número de identificación de ubicación de emergencia (ELIN), que constituyen una alternativa a las conexiones troncales SIP con un proveedor de servicio E9-1-1 cualificado. Las puertas de enlace ELIN admiten la conectividad ISDN o de contabilización de mensajes automática y centralizada (CAMA) con servicios E9-1-1 basados en la red telefónica conmutada (RTC). Para obtener más información acerca de los partners que proporcionan puertas de enlace de ELIN y vínculos a su documentación, vea [Infrastructure qualified for Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) and [Telephony Infrastructure for Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md).

Al igual que las conexiones troncales SIP con proveedores de servicios E9-1-1, las puertas de enlace ELIN también proporcionan los medios para enrutar una llamada de emergencia al punto de respuesta de seguridad pública (PSAP) más adecuado del autor de la llamada, pero estas puertas de enlace usan un ELIN como identificador de ubicación. Defina ELIN para cada ubicación de respuesta de emergencia (ERL) de su organización (para obtener más información, vea Administrar ubicaciones para puertas de enlace [ELIN](elin-gateways.md)en Skype Empresarial Server ).

Cuando usa una puerta de enlace ELIN para llamadas de emergencia, usa la misma infraestructura de Skype Empresarial Server E9-1-1 que usaría para una conexión troncal SIP. Es decir, la base de datos del servicio de información de ubicación proporciona la ubicación al cliente de Skype Empresarial y la directiva de ubicación habilita la característica y define el enrutamiento. Sin embargo, con una puerta de enlace ELIN, debe agregar los ELIN a la base de datos del servicio de información de ubicación y hacer que el operador RTC los cargue en la base de datos de identificación automática de ubicación (ALI).

Cuando un cliente de Skype Empresarial obtiene su ubicación del servicio de información de ubicación, la ubicación incluye el ELIN. Durante las llamadas de emergencia, el ELIN se incluye con la información de ubicación que se envía a la puerta de enlace ELIN. Esta puerta de enlace identifica la llamada como llamada de emergencia y cambia el número de la persona que llama por el ELIN. A continuación, la puerta de enlace ELIN enruta la llamada al RTC con el ELIN como número llamante. El proveedor de servicios E9-1-1 de RTC busca el ELIN en la base de datos ALI, que actúa como una base de datos adicional a la base de datos de guía de direcciones principal (MSAG). Acto seguido el operador de RTC envía la llamada al PSAP más adecuado en función de la búsqueda realizada en la base de datos ALI y el PSAP envía el personal de emergencia disponible a la ubicación de la persona que realiza según los resultados de la búsqueda ALI. El número de llamada se almacena en la memoria caché de la puerta de enlace ELIN durante un tiempo predeterminado para las devoluciones de llamadas. Durante la devolución de llamada, el PSAP contacta con la puerta de enlace ELIN que, a su vez, cambia el ELIN por el número de llamada directa a la extensión (DID) de la persona que realiza la llamada.

Las puertas de enlace ELIN solo admiten las llamadas de emergencia desde la red de su organización. No admiten las llamadas de emergencia realizadas fuera de su red.

> [!NOTE]
> Para obtener información detallada sobre cómo usar una conexión troncal SIP en las llamadas de emergencia, consulte [Routing E9-1-1 Calls by Using a SIP Trunk](/previous-versions/office/lync-server-2013/lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk).

El diagrama siguiente muestra cómo se enruta una llamada de emergencia desde Skype Empresarial Server al PSAP cuando se usa una puerta de enlace ELIN.

**Enrutamiento de llamadas E9-1-1 con una puerta de enlace ELIN**

![Muestra cómo una llamada a los servicios de emergencia viaja a través del servidor de mediación y, a continuación, al proveedor de servicios de emergencia. Después de esto, opcionalmente puede haber una mensajería instantánea enviada a la seguridad en el sitio o una llamada de vuelta al autor de la llamada original.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Una INVITACIÓN SIP que contiene la ubicación, el número de devolución de llamada del autor de la llamada y la dirección URL de notificación (opcional) y el número de devolución de llamada de conferencia se enruta a Skype Empresarial Server.

2. Skype Empresarial Server coincide con el número de emergencia  y, a continuación, enruta la llamada (en función del valor de uso RTC definido en la directiva de ubicación aplicable) a un servidor de mediación y desde allí a una puerta de enlace ELIN.

3. La puerta de enlace ELIN enruta la llamada a través de un tronco ISDN o CAMA a la RTC.

4. La RTC identifica la llamada como una llamada de emergencia y la enruta a un enrutador selectivo de E9-1-1 de la red, que busca el número del autor de la llamada en la base de datos ALI para obtener la ubicación geográfica. Tras ello, el enrutador selectivo de E9-1-1 envía la llamada al PSAP más adecuado en función de la información de ubicación que haya suministrado la base de datos ALI.

5. Si configuró la directiva de ubicación para las notificaciones, uno o varios de los responsables de seguridad de su organización se envían un mensaje instantáneo de notificación de emergencia de Skype Empresarial especial. Este mensaje siempre aparece en la pantalla de los agentes de seguridad y contiene el nombre, el número de teléfono, la hora y la ubicación del autor de la llamada, lo que permite al personal de seguridad responder rápidamente al autor de la llamada de emergencia mediante un mensaje instantáneo o una voz.

6. En caso de que la llamada se interrumpa antes de tiempo, el PSAP usa el ELIN para ponerse en contacto directamente con el autor de la llamada. La puerta de enlace ELIN intercambia el ELIN por el DID del autor de la llamada.