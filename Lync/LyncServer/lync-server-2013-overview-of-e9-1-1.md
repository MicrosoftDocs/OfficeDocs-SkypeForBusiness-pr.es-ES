---
title: 'Lync Server 2013: Información general sobre E9-1-1'
TOCTitle: Información general sobre E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48276544
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general sobre E9-1-1 en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-29_

Microsoft Lync Server 2013 es compatible con las llamadas al 9-1-1 mejorado (E9-1-1) desde clientes de Lync y dispositivos de Lync Phone Edition. Cuando un usuario configura Lync Server para E9-1-1, las llamadas SOS que se realizan desde Lync 2013 o Lync Phone Edition incluyen información de ubicación de respuesta de emergencia (ERL) de la base de datos de Servicio de información de ubicaciones. Las ERL se componen de direcciones civiles (es decir, postales) e información adicional que ayuda a identificar con mayor precisión una ubicación en edificios de oficinas y otras instalaciones con varios inquilinos. Cuando un usuario realiza una llamada SOS, Lync Server redirige el audio de la llamada, junto con información de ubicación y devolución de llamada, a través de Servidor de mediación a un proveedor de servicios de E9-1-1, quien usa la dirección civil del autor de la llamada para redirigir la llamada al punto de respuesta de seguridad pública (PSAP) específico. Desde aquí se facilita la ubicación del autor de la llamada junto con una clave de consulta de servicios de emergencia (ESQK) que permite al PSAP buscar la ERL de esta persona.

Lync Server admite dos métodos para redirigir llamadas SOS al proveedor de servicios E9-1-1:

  - Una conexión de enlace troncal SIP (Protocolo de inicio de sesión) a un proveedor de servicios E9-1-1 cualificado.

  - Una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) a un proveedor de servicios E9-1-1 basado en una Red telefónica conmutada (RTC).

Cuando se usa un proveedor de servicios de E9-1-1 de enlace troncal SIP, se agregan las ERL a la base de datos de Servicio de información de ubicaciones y se validan las ubicaciones cotejándolas con la Guía de calles maestra (MSAG) del proveedor de servicios E9-1-1. Si el proveedor recibe una llamada que no cuenta con información de ubicación o cuya ubicación no se ha validado en la MSAG, redirige la llamada a un Centro de respuesta de llamadas SOS (ECRC) nacional o regional, que dispone de personal especialmente preparado para obtener de forma oral la ubicación del autor de la llamada (si es posible) y redirigir manualmente la llamada al PSAP correspondiente. Algunos proveedores de servicios E9-1-1 de enlace troncal SIP también proporcionan a los clientes un número de marcado directo (DID) de RTC para el ECRC, que constituye un medio alternativo de enrutamiento de las llamadas al 9-1-1 si por algún motivo se produce un error en el enlace troncal SIP.

A diferencia de los teléfonos de centrales de conmutación (PBX) basados en IP y multiplexación por división de tiempo (TDM) que cuentan con ubicaciones fijas, un extremo de Lync puede tener una gran movilidad. Cuando se implementa la característica E9-1-1, Lync Server ayuda a garantizar que, con independencia de donde se halle el autor de la llamada, la llamada SOS va a redirigirse al PSAP que facilita la ubicación de esta persona. Por ejemplo, si la oficina principal de un usuario está ubicada en Redmond (Washington), pero el usuario realiza una llamada SOS desde el equipo de una sucursal en Wichita (Kansas), el proveedor de servicios E9-1-1 basado en RTC o de enlace troncal SIP redirigirá la llamada al PSAP de Wichita, y no al de Redmond.

Cuando se usa una puerta de enlace de ELIN, también se agregan ERL a la base de datos de Servicio de información de ubicaciones, pero además se incluye un número ELIN para cada ubicación. El número ELIN pasa a ser el número de llamada SOS durante la llamada. Debe comprobar que el proveedor de RTC carga los ELIN en una base de datos de identificación de ubicación automática (ALI).


> [!NOTE]
> Los dispositivos analógicos conectados a Lync no pueden recibir información de ubicación de Servicio de información de ubicaciones ni transmitir la ubicación al proveedor de servicios E9-1-1. Si usa la opción del proveedor de servicios E9-1-1 de enlace troncal SIP y tiene que admitir llamadas E9-1-1 desde teléfonos analógicos, tiene dos opciones: 
> <UL>
> <LI>
> <P><STRONG>Opción PS-ALI tradicional</STRONG> Si dispone de puertas de enlace de RTC locales en cada sitio donde se implementan teléfonos analógicos y cada teléfono analógico tiene un DID, puede proporcionar la ubicación del dispositivo analógico directamente con un proveedor de servicios de identificación de ubicación automática o conmutador privado (PS-ALI). En este caso, debe configurar directivas de voz específicas de Lync y asignarlas a los objetos contacto del dispositivo analógico para que las llamadas E9-1-1 que se realizan desde esos teléfonos se redirijan directamente a través de la puerta de enlace local al proveedor de RTC del sitio (en lugar de redirigir la llamada a un enlace troncal SIP del proveedor de servicios E9-1-1). Cuando se realiza una llamada SOS, una base de datos de un proveedor de PS-ALI asociado con el enlace troncal de RTC asigna el DID de cada teléfono analógico a una ubicación física, y proporciona esta ubicación al PSAP. Estos registros deben actualizarse con el proveedor de servicios de PS-ALI cada vez que los teléfonos se desplazan a ERL diferentes.</P>
> <LI>
> <P><STRONG>Opción de proveedor de servicios E9-1-1</STRONG> Puede registrar los DID de teléfono analógico y sus ERL correspondientes con el proveedor de servicios E9-1-1 si dicho proveedor lo admite. Si el proveedor recibe una llamada de Lync Server que no incluye datos PIDF-LO, puede ver si hay una coincidencia de la base de datos en el número DID de quien realiza la llamada. Mediante la ERL que se recupera desde su base de datos, el proveedor puede redirigir automáticamente la llamada SOS al PSAP correcto y este recibirá el DID del dispositivo analógico y un registro de ESQK que permite al distribuidor buscar la ubicación del autor de la llamada.</P></LI></UL>Si usa la opción de puerta de enlace de ELIN y necesita compatibilidad con las llamadas E9-1-1 desde teléfonos analógicos, puede dar la ubicación del dispositivo analógico directamente con el proveedor de servicios PS-ALI, como se describe en la primera opción mencionada anteriormente.



Desde el punto de vista de Lync Server, el proceso de E9-1-1 se puede diferenciar en dos fases independientes:

  - Fase 1: adquisición de una ubicación

  - Fase 2: enrutamiento de la llamada SOS al proveedor de servicios E9-1-1

En esta sección se describe cómo funcionan estas fases.

Si va a configurar la infraestructura para detectar automáticamente la ubicación del cliente, primero debe decidir qué elementos de red usará para asignar los autores de las llamadas a las ubicaciones. Para más información sobre las opciones posibles, consulte [Definir los elementos de red que se usan para determinar la ubicación en Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).

## En esta sección

  - [Adquirir una ubicación en Lync Server 2013](lync-server-2013-acquiring-a-location.md)

  - [Enrutamiento de llamadas E9-1-1 mediante un SIP troncal en Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Enrutamiento de llamadas E9-1-1 mediante una puerta de enlace ELIN en Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

