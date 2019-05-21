---
title: Planear los servicios de emergencia en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ed843ed7-371f-46cc-969a-f8062c06fc55
description: Obtenga más información sobre los servicios mejorados de 9-1-1 (E9-1-1) en la telefonía IP empresarial de Skype empresarial, incluida la adquisición de la ubicación y el enrutamiento de llamadas.
ms.openlocfilehash: 20d1a258b022b8369f59aaa74a2b95de45f931e2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276897"
---
# <a name="plan-for-emergency-services-in-skype-for-business-server"></a>Planear los servicios de emergencia en Skype empresarial Server

Obtenga más información sobre los servicios mejorados de 9-1-1 (E9-1-1) en la telefonía IP empresarial de Skype empresarial, incluida la adquisición de la ubicación y el enrutamiento de llamadas.

Skype empresarial Server es compatible con los servicios mejorados de 9-1-1 (E9-1-1) dentro de los Estados Unidos como parte de una implementación de telefonía IP empresarial. E9-1-1 es una característica de envío de emergencia que asocia una llamada 9-1-1 con una ubicación de respuesta de emergencia (ERL) que consta de direcciones de la ciudad (es decir, postal) y otra información de ubicación más específica, como los números de planta, para las llamadas de edificios de oficinas y otras instalaciones multiempresa. Con el uso de la ERL proporcionada, un Punto de respuesta de seguridad pública (PSAP) puede enviar inmediatamente los servicios de emergencia a la persona que realiza la llamada en apuros con un riesgo menor de dirigir accidentalmente los servicios de emergencias a una ubicación incorrecta o ambigua.

> [!NOTE]
> Skype empresarial Server ahora es compatible con la configuración de varios números de emergencia para un cliente. Para obtener más información, consulte [planear varios números de emergencia en Skype empresarial Server](multiple-emergency-numbers.md).

> [!NOTE]
> Skype empresarial Server tiene tres características avanzadas de voz empresarial: control de admisión de llamadas, servicios de emergencia (E9-1-1) y omisión de medios. Para obtener una descripción general de la información de planeación común para estas tres características, consulte [configuración de red para las características de telefonía avanzada empresarial en Skype empresarial Server](network-settings-for-advanced-features.md).

Skype empresarial Server es compatible con las llamadas mejoradas de 9-1-1 (E9-1-1) desde los clientes de Skype empresarial y los dispositivos de Lync Phone Edition. Al configurar Skype empresarial Server para E9-1-1, las llamadas de emergencia realizadas desde Skype empresarial o Lync Phone Edition incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos del servicio de información de ubicación. Las ERL se componen de direcciones civiles (es decir, postales) e información adicional que ayuda a identificar con mayor precisión una ubicación en edificios de oficinas y otras instalaciones con varios inquilinos. Cuando un usuario realiza una llamada de emergencia, Skype empresarial Server enruta el audio de la llamada, junto con la información de la ubicación y la devolución de llamada, a través de un servidor de mediación a un proveedor de servicios E9-1-1. Desde aquí se facilita la ubicación del autor de la llamada junto con una clave de consulta de servicios de emergencia (ESQK) que permite al PSAP buscar la ERL de esta persona.

Skype empresarial Server admite dos métodos para enrutar llamadas de emergencia a un proveedor de servicios E9-1-1:

- Una conexión de enlace troncal SIP (Protocolo de inicio de sesión) a un proveedor de servicios E9-1-1 cualificado.

- Una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios E9-1-1 basado en una Red telefónica conmutada (RTC).

Cuando usa un proveedor de servicios E9-1-1 de SIP, agrega ERLs a la base de datos de servicios de información de ubicación y, a continuación, valida las ubicaciones con una guía de dirección maestra (MSAG) que mantiene el proveedor de servicios E9-1-1. Si un proveedor de servicios E9-1 recibe una llamada que no tiene información de ubicación o tiene una ubicación que no se ha validado contra el MSAG, el E9-1-1 dirige la llamada a un centro de respuesta de llamada de emergencia nacional o regional (ECRC), que es personal con personal de formación especial que obtiene verbalmente la ubicación de la persona que llama, siempre que sea posible, y enrute manualmente la llamada a la PSAP adecuada. Algunos proveedores de servicios E9-1-1 de enlace troncal SIP también proporcionan a los clientes un número de marcado directo (DID) de RTC para el ECRC, que constituye un medio alternativo de enrutamiento de las llamadas al 9-1-1 si por algún motivo se produce un error en el enlace troncal SIP.

A diferencia de la multiplexación de división de tiempo (TDM) y los teléfonos de central de conmutación (PBX) basados en IP, que tienen ubicaciones fijas, un punto de conexión de Skype empresarial puede ser muy móvil. Al implementar la característica E9-1-1, Skype empresarial Server le ayuda a garantizar que no importa dónde se encuentre la persona que llama, la llamada de emergencia puede enrutarse al PSAP que sirve la ubicación de la persona que llama. Por ejemplo, si la oficina principal de un usuario se encuentra en Redmond, Washington, pero el usuario realiza una llamada de emergencia desde un equipo de una sucursal en Wichita, Kansas, el enlace SIP o el proveedor de servicios E9-1-based de RTC enrutará la llamada al PSAP en Wichita , no al PSAP en Redmond.

Al usar una puerta de enlace de ELIN, también puede Agregar ERLs a la base de datos de servicios de información de ubicación, pero también puede incluir un número de ELIN para cada ubicación. El número ELIN pasa a ser el número de llamada SOS durante la llamada. Es preciso comprobar que el proveedor de RTC carga los ELIN en una base de datos de identificación de ubicación automática (ALI).

> [!NOTE]
> Los dispositivos analógicos conectados a Skype empresarial no pueden recibir información de la ubicación del servicio de información de ubicación o la ubicación de transmisión al proveedor de servicios E9-1-1.

 Si usa la opción del proveedor de servicios E9-1-1 de enlace troncal SIP y tiene que admitir llamadas E9-1-1 desde teléfonos analógicos, tiene dos opciones:

- **Opción PS: Ali tradicional** Si tiene puertas de enlace RTC locales en cada sitio en el que se implementan teléfonos analógicos y cada teléfono analógico tiene un, puede aprovisionar la ubicación del dispositivo analógico directamente con un proveedor de servicios de identificación de ubicación automática/conmutador privado (PS-ALI). En este caso, configurará directivas de voz de Skype empresarial especialmente diseñadas y las asignaremos a los objetos de contacto de dispositivos analógicos para que las llamadas de E9 desde esos teléfonos enruten directamente a través de la puerta de enlace local al proveedor de RTC que presta servicio al sitio (en su lugar de enrutar la llamada a un proveedor de servicios de E9-1-1, troncal SIP). Cuando se realiza una llamada SOS, una base de datos de un proveedor de PS-ALI asociado con el enlace troncal de RTC asigna el DID de cada teléfono analógico a una ubicación física, y proporciona esta ubicación al PSAP. Estos registros necesitan actualizarse con el proveedor de servicios de PS-ALI cada vez que los teléfonos se desplazan a ERL diferentes.

- **Opción de proveedor de servicios E9-1-1** Puede registrar el DIDs de teléfono analógico y su ERLs correspondiente con el proveedor de servicios E9-1-1, si es compatible con el proveedor de servicios E9-1-1. Si el proveedor recibe una llamada de Skype empresarial Server que no incluye datos de PIDF-lo, el proveedor puede ver si hay una coincidencia de base de datos en el número de personas que llama. Al usar el ERL recuperado de su base de datos, el proveedor puede enrutar automáticamente la llamada de emergencia al PSAP correcto y el PSAP recibirá el hecho del dispositivo analógico y un registro de ESQK que permita al distribuidor buscar la ubicación del autor de la llamada.

Si usa la opción de puerta de enlace de ELIN y necesita compatibilidad con las llamadas E9-1-1 desde teléfonos analógicos, puede dar la ubicación del dispositivo analógico directamente con el proveedor de servicios PS-ALI, como se describe en la primera opción mencionada anteriormente.

Desde una perspectiva de Skype empresarial Server, el E9-1-1 se puede dividir en dos fases:

- Fase 1: adquisición de una ubicación

- Fase 2: enrutamiento de la llamada SOS al proveedor de servicios E9-1-1

En esta sección se describe cómo funcionan estas fases.

Si va a configurar la infraestructura para detectar automáticamente la ubicación del cliente, primero necesita decidir qué elementos de red usará para asignar los autores de las llamadas a las ubicaciones. Para obtener más información sobre las posibles opciones, consulte [definir los elementos de red que se usan para determinar la ubicación en Skype empresarial Server](network-location.md).

## <a name="acquiring-a-location"></a>Adquirir una ubicación

En una implementación de Skype empresarial Server E9-1-1, cada cliente con conexión interna de Skype para empresas o Lync Phone Edition adquiere su propia ubicación. Después del registro SIP, el cliente brinda toda la información de conectividad de red que él conoce sobre él en una solicitud de ubicación en el servicio de información de ubicación, que es un servicio Web respaldado por una base de datos de SQL Server replicada. Cada grupo de sitios central tiene un servicio de información de ubicación, que usa la información de la red para consultar sus registros en busca de una ubicación coincidente. Si hay una coincidencia, el servicio de información de ubicación devuelve una ubicación al cliente. Si no hay una coincidencia, puede que se pida al usuario que escriba una ubicación manualmente (según la configuración de la directiva de ubicación). Los datos de ubicación se transmiten de vuelta al cliente en un formato XML estandarizado del Grupo de trabajo de ingeniería de Internet (IETF) conocido como Objeto de ubicación para formato de datos de información sobre presencia (PIDF-LO).

El cliente de Skype empresarial incluye los datos de PIDF como parte de una llamada de emergencia, y el proveedor de servicios E9-1-1 utiliza estos datos para determinar el PSAP adecuado y enrutar la llamada a ese PSAP junto con el ESQK correcto, que permite al PSAP distribuidor Obtén la ubicación de la persona que llama.

En el siguiente diagrama se muestra cómo un cliente de Skype empresarial adquiere una ubicación (excepto para el método de ubicación basado en direcciones MAC del cliente de terceros):

![Diagrama sobre cómo adquiere una ubicación el cliente](../../media/Plan_LyncServer_E911_LocationAcquisition.jpg)

Para que un cliente adquiera una ubicación, es preciso seguir estos pasos:

1. El administrador rellena la base de datos del servicio de información de ubicación con el Wiremap de red (tablas que asignan varios tipos de direcciones de red a las ubicaciones de respuesta de emergencia correspondientes (ERLs)).

2. Si utiliza un proveedor de servicio E9-1-1 para troncos SIP, el administrador validará las partes de dirección postal de las ERL con una base de datos de guía de direcciones principal (MSAG) mantenida por el proveedor del servicio E9-1-1. Si utiliza una puerta de enlace ELIN, el administrador se asegurará de que la portadora RTC cargue las ELIN a la base de datos de identificación automática de ubicaciones (ALI).

3. Durante el registro o cuando se produce un cambio en la red, un cliente conectado internamente envía una solicitud de ubicación que contiene las direcciones de red detectadas del cliente al servicio de información de ubicación.

4. El servicio de información de ubicación consulta sus registros publicados en busca de una ubicación y, si se encuentra una coincidencia, devuelve el ERL al cliente con el formato PIDF-es.

## <a name="routing-e9-1-1-calls-using-a-sip-trunk"></a>Enrutamiento de llamadas E9-1-1 por medio de un tronco SIP

El uso de un tronco SIP para conectarse a un proveedor de servicios E9-1-1 certificado es una manera de implementar E9-1-1. Para más detalles sobre el uso de una puerta de enlace ELIN para conectarse a un proveedor de servicios E9-1-1 basado en una red telefónica conmutada (RTC), vea [Routing E9-1-1 Calls by Using an ELIN Gateway](https://technet.microsoft.com/library/5a3997e3-898d-49cb-922a-4184c3373350.aspx).

En el siguiente diagrama se muestra cómo se dirige una llamada de emergencia desde Skype empresarial Server al punto de respuesta de seguridad pública (PSAP) cuando usa un tronco de SIP y un proveedor de servicios de E9-1-1 calificado.

**Enrutamiento de llamadas E9-1-1 a través de un tronco SIP**

![Enrutar llamada de emergencia de Lync Server a un punto de respuesta de seguridad pública (PSAP)](../../media/Plan_LyncServer_E911_CallRouting.jpg)

Cuando se realiza una llamada de emergencia desde un cliente de servidor de Skype empresarial compatible:

1. Una invitación SIP que contiene la ubicación, el número de devolución de llamada de la persona que llama y la dirección URL de notificación (opcional) y el número de devolución de llamada de la Conferencia se dirigen a Skype empresarial Server.

2. Skype empresarial Server hace coincidir el número de emergencia y enruta la llamada (según el valor de **uso de RTC** que se define en la política de ubicación aplicable) a un servidor de mediación, y desde allí, a través de un tronco SIP al proveedor de servicios E9-1-1.

3. El proveedor de servicios E9-1-1 enruta la llamada de emergencia al PSAP adecuado según la ubicación proporcionada con la llamada. Cuando el cliente incluye una ubicación de respuesta de emergencia (ERL) validada en la llamada de emergencia, el proveedor dirige automáticamente la llamada al punto PSAP adecuado. Si el usuario especificó la ubicación manualmente, el centro de respuestas a llamadas de emergencia (ECRC) verifica verbalmente en primer lugar la exactitud de la ubicación con la persona que llama antes de enrutar la llamada de emergencia al PSAP.

4. Si ha configurado la Directiva de ubicación para las notificaciones, uno o más de los responsables de seguridad de la organización reciben un mensaje instantáneo especial de notificación de emergencia de Skype empresarial. Este mensaje aparece siempre en la (s) pantalla (s) de los directores de seguridad y contiene el nombre de la persona que llama, el número de teléfono, la hora y la ubicación, lo que permite al personal de seguridad responder rápidamente a la persona que llama con un mensaje instantáneo o una voz.

5. Si ha configurado la directiva de ubicación para las conferencias y el proveedor de servicios E9-1-1 lo admite, el departamento de seguridad se unirá a la llamada en conferencia con audio unidireccional o bidireccional.

6. Si la llamada se interrumpe de forma prematura, el PSAP usa el número de devolución de llamada para contactar directamente con la persona que llama.

## <a name="routing-e9-1-1-calls-by-using-an-elin-gateway"></a>Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN

Algunos asociados del Programa de interoperabilidad abierto de comunicaciones unificadas proporcionan puertas de enlace de número de identificación de ubicación de emergencia (ELIN), que constituyen una alternativa a las conexiones troncales SIP con un proveedor de servicio E9-1-1 cualificado. Las puertas de enlace ELIN admiten la conectividad ISDN o de contabilización de mensajes automática y centralizada (CAMA) con servicios E9-1-1 basados en la red telefónica conmutada (RTC). Para obtener más información sobre los socios que proporcionan puertas de enlace de ELIN y vínculos a la documentación, consulte [infraestructura cualificada para Microsoft Lync](https://go.microsoft.com/fwlink/p/?LinkId=248425) y la [infraestructura de telefonía de Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

Al igual que las conexiones troncales SIP con los proveedores de servicios E9-1-1, las puertas de enlace ELIN también ofrecen los medios necesarios para enrutar una llamada de emergencia al punto de respuesta de seguridad pública (PSAP) más adecuado para el autor de la llamada, pero estas puertas de enlace usan un número ELIN para identificar la ubicación. Defina ELINs para cada ubicación de respuesta de emergencia (ERL) de su organización (para obtener más información, vea [administrar ubicaciones de puertas de enlace de Elin en Skype empresarial Server](elin-gateways.md)).

Cuando usas una puerta de enlace de ELIN para llamadas de emergencia, usas la misma infraestructura de Skype empresarial Server E9-1-1 que usarías para una conexión SIP de enlace. Es decir, la base de datos del servicio de información de ubicación proporciona la ubicación al cliente de Skype empresarial y la Directiva de ubicación habilita la característica y define el enrutamiento. Sin embargo, con una puerta de enlace de ELIN necesita agregar la ELINs a la base de datos de servicios de información de ubicación y hacer que el operador PSTN la cargue en la base de datos de identificación de ubicación automática (ALI).

Cuando un cliente de Skype empresarial obtiene su ubicación desde el servicio de información de ubicación, la ubicación incluye la ELIN. Durante una llamada de emergencia, ELIN se incluye con la ubicación que se envía a la puerta de enlace de ELIN. La puerta de enlace de ELIN identifica la llamada como llamada de emergencia e intercambia el número de la persona que llama con el ELIN. A continuación, la puerta de enlace de ELIN enruta la llamada a la RTC con el ELIN como el número de llamada. El proveedor E9-1-1 de RTC busca la ELIN en la base de datos de ALI, que es una base de datos complementaria para la base de datos de la guía de dirección maestra (MSAG). La RTC envía entonces la llamada a la PSAP más adecuada en función de la búsqueda de ALI, y el PSAP envía los primeros respondedores a la ubicación de la persona que llama basándose en la búsqueda de ALI. El número de llamada se almacena en caché en la puerta de enlace de ELIN durante un período de tiempo predefinido para las devoluciones de llamada. Durante una devolución de llamada, el PSAP llega a la puerta de enlace de ELIN, que intercambia el ELIN para el número de marcado interno directo de la persona que llama.

Las puertas de enlace ELIN admiten llamadas de emergencia únicamente desde dentro de la red de la organización; no admite llamadas externas.

> [!NOTE]
> Para obtener información detallada sobre cómo usar una conexión troncal SIP en las llamadas de emergencia, consulte [Routing E9-1-1 Calls by Using a SIP Trunk](https://technet.microsoft.com/library/157753c3-fe74-4e2c-81da-ee06911d4cc2.aspx).

En el siguiente diagrama se muestra cómo se dirige una llamada de emergencia desde Skype empresarial Server al PSAP cuando usa una puerta de enlace de ELIN.

**Enrutamiento de llamadas E9-1-1 con una puerta de enlace ELIN**

![Muestra cómo una llamada a los servicios de emergencia pasa por el servidor de mediación al proveedor de los servicios de emergencias. Tras esto, puede que se envíe un mensaje instantáneo a la seguridad del sitio, o que se devuelva la llamada al autor de la llamada original.](../../media/Plan_LyncServer_E911_ELINCallRouting.jpg)

1. Una invitación SIP que contiene la ubicación, el número de devolución de llamada de la persona que llama y la dirección URL de notificación (opcional) y el número de devolución de llamada de la Conferencia se dirigen a Skype empresarial Server.

2. Skype empresarial Server coincide con el número de emergencia y, después, enruta la llamada (según el valor de **uso de RTC** definido en la política de ubicación correspondiente) a un servidor de mediación y desde allí a una puerta de enlace de Elin.

3. La puerta de enlace ELIN enruta la llamada a través de un tronco ISDN o CAMA a la RTC.

4. La RTC identifica la llamada como una llamada de emergencia y la enruta a un enrutador selectivo de E9-1-1 de la red, que busca el número del autor de la llamada en la base de datos ALI para obtener la ubicación geográfica. Tras ello, el enrutador selectivo de E9-1-1 envía la llamada al PSAP más adecuado en función de la información de ubicación que haya suministrado la base de datos ALI. 

5. Si ha configurado la Directiva de ubicación para las notificaciones, uno o más de los responsables de seguridad de la organización reciben un mensaje instantáneo especial de notificación de emergencia de Skype empresarial. Este mensaje aparece siempre en la (s) pantalla (s) de los directores de seguridad y contiene el nombre de la persona que llama, el número de teléfono, la hora y la ubicación, lo que permite al personal de seguridad responder rápidamente a la persona que llama con un mensaje instantáneo o una voz.

6. En caso de que la llamada se interrumpa antes de tiempo, el PSAP usa el ELIN para ponerse en contacto directamente con el autor de la llamada. La puerta de enlace ELIN intercambia el ELIN por el DID del autor de la llamada.


