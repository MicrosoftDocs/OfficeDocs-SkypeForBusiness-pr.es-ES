---
title: Plan for Enterprise Voice resiliency in Skype for Business Server
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
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Obtenga información sobre cómo admitir la resistencia de voz en Skype para Business Server Enterprise Voice, en sitios centrales y sitios de sucursal. Opciones de sitio de sucursal incluyen implementar aplicaciones de sucursal con funciones de supervivencia o servidores de sucursal con funciones de supervivencia.
ms.openlocfilehash: 8b6b414cc1667c0764ac8878ea0f06da7468e781
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207177"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Plan for Enterprise Voice resiliency in Skype for Business Server

Obtenga información sobre cómo admitir la resistencia de voz en Skype para Business Server Enterprise Voice, en sitios centrales y sitios de sucursal. Opciones de sitio de sucursal incluyen implementar aplicaciones de sucursal con funciones de supervivencia o servidores de sucursal con funciones de supervivencia.

Resistencia de voz hace referencia a la capacidad de los usuarios para continuar realizar y recibir llamadas si un sitio central que hosts Skype para Business Server deja de estar disponible, ya sea a través de un área extensa (WAN) error u otra causa de red. Si se produce un error en un sitio central, servicio de Enterprise Voice debe seguir ininterrumpido a través de la conmutación por error transparente a un sitio de copia de seguridad. En caso de error de WAN, se deben redirigir las llamadas del sitio de sucursal a una puerta de enlace de RTC local. En esta sección se describe la planeación para la resistencia de voz en caso de fallo del sitio central o WAN.

## <a name="central-site-resiliency"></a>Resistencia del sitio central

Cada vez más, las empresas tienen varios sitios dispersos por todo el mundo. Mantenimiento de los servicios de emergencia, acceso al servicio de asistencia y la capacidad de llevar a cabo las tareas críticas del negocio cuando un sitio central está fuera de servicio es esencial para cualquier solución de resistencia de Enterprise Voice. Cuando un sitio central deja de estar disponible, deben cumplirse las siguientes condiciones:

- Se debe proporcionar conmutación por error de voz.

- Los usuarios que normalmente registrar con el grupo de servidores Front-End en el sitio central deben poder registrar con un grupo de servidores Front-End alternativo. Esto puede realizarse mediante la creación de registros, cada uno de los cuales se resuelve en un grupo de directores o grupo de servidores Front-End en cada uno de los sitios centrales de varios SRV de DNS. Puede ajustar la prioridad y el peso de los registros SRV para que los usuarios que presta servicio ese sitio central obtendrán el grupo de servidores Front-End y Director correspondiente por delante de las de otros registros SRV.

- Las llamadas a y desde usuarios ubicados en otros sitios deben enrutarse de nuevo a la RTC.

En este tema se describe la solución recomendada para garantizar la resistencia de voz del sitio central.

### <a name="architecture-and-topology"></a>Arquitectura y topología

Planeación de resistencia de voz en un sitio central requiere un conocimiento básico de la función central reproducido el Skype para Business Server registrador en la habilitación de la conmutación por error de voz. El Skype para el registrador de servidor empresarial es un servicio que permite la autenticación y el registro de cliente y proporciona servicios de enrutamiento. Se ejecuta en todos los servidores Standard Edition, servidor Front-End, Director o aplicación de sucursal con funciones de supervivencia. Un grupo de registrador formado por servicios de registrador que se ejecutan en el grupo de servidores Front-End y que residen en el mismo sitio. Un Skype para clientes empresariales detecta el grupo de servidores Front-End mediante el mecanismo de detección siguiente:

1. Registro SRV de DNS

2. Servicio Web de detección automática

3. Opción DHCP 120

Después de la Skype para clientes empresariales se conecta al grupo de servidores Front-End, se dirige por el equilibrador de carga a uno de los servidores Front-End del grupo de servidores. Ese servidor Front-End, a su vez, redirige al cliente a un registrador preferido en el grupo de servidores.

Cada usuario habilitado para Enterprise Voice se asigna a un determinado grupo de registrador, que se convierte en el grupo de registrador principal de dicho usuario. En un sitio determinado, cientos o miles de usuarios suelen compartan un único grupo de registrador principal. Para tener en cuenta para el consumo de recursos del sitio central por los usuarios de sitio de sucursal que se basan en el sitio central de presencia, conferencias o conmutación por error, se recomienda que tenga en cuenta de cada usuario del sitio de sucursal como si el usuario fuera un usuario registrado con el sitio central. Actualmente no hay ningún límite en el número de usuarios del sitio de sucursal, incluidos los usuarios registrados con una aplicación de sucursal con funciones de supervivencia.

A fin de garantizar la resistencia de voz en el caso de un error en el sitio central, el grupo de registrador principal debe tener un grupo de registrador de reserva designado único que se encuentra en otro sitio. La copia de seguridad se puede configurar con la configuración de resistencia de generador de topología. Suponiendo que un vínculo WAN resistente entre los dos sitios, automáticamente se dirigen a los usuarios cuyo grupo de registrador principal ya no está disponible para el grupo de registrador de copia de seguridad.

Los siguientes pasos describen el proceso de detección y registro de cliente:

1. Un cliente descubre Skype para Business Server a través de los registros DNS SRV. En Skype para Business Server, los registros DNS SRV pueden configurarse para devolver más de un FQDN a la consulta DNS SRV. Por ejemplo, si la empresa Contoso tiene tres sitios centrales (América del Norte, Europa y Asia Pacífico) y un grupo de directores en cada sitio central, pueden apuntar registros SRV de DNS para el FQDN del grupo de directores en cada una de las tres ubicaciones. Siempre y cuando el grupo de directores en una de las ubicaciones está disponible, puede conectar el cliente para el primer salto Skype para Business Server.

    > [!NOTE]
    > Uso de un grupo de servidores de Director es opcional. Un grupo de servidores Front-End se puede usar en su lugar.

2. El grupo de directores informa a la Skype para cliente de negocio sobre grupo de registrador principal del usuario y grupo de registrador de copia de seguridad.

3. El Skype para clientes empresariales intenta conectarse primero al grupo de registrador principal del usuario. Si el grupo de registrador principal está disponible, el registrador acepta el registro. Si el grupo de registrador principal no está disponible, el Skype para clientes empresariales intenta conectarse al grupo de registrador de copia de seguridad. Si el grupo de registrador de copia de seguridad está disponible y ha determinado que grupo de registrador principal del usuario no está disponible (mediante la detección de una falta de latido para un intervalo especificado de conmutación por error) grupo de registrador de copia de seguridad acepta el registro del usuario. Después de que el registrador de copia de seguridad detecta que el registrador principal vuelve a estar disponible, el grupo de registrador de copia de seguridad le llevará a los clientes de conmutación por error a su grupo principal.

### <a name="requirements-and-recommendations"></a>Requisitos y recomendaciones

Los siguientes requisitos y las recomendaciones para implementar la resistencia de voz del sitio central son adecuadas para la mayoría de las organizaciones:

- Los sitios en la que residen los grupos de registrador principales y de reserva deberán estar conectados mediante un vínculo WAN resistente.

- Cada sitio central debe contener un grupo de registrador formado por uno o varios registradores.

- Cada grupo de registrador debe ser con equilibrio de carga mediante el uso de DNS el equilibrio de carga, equilibrio de carga de hardware o ambos. Para obtener información detallada acerca de cómo planear la configuración de equilibrio de carga, vea [requisitos de Skype para la empresa del equilibrio de carga](../../plan-your-deployment/network-requirements/load-balancing.md).

- Cada usuario debe estar asignado a un grupo de registrador principal mediante el uso de puede ser la Skype para el cmdlet **set-CsUser** de Shell de administración de servidor empresarial o el Skype para el Panel de Control de servidor empresarial.

- El grupo de registrador principal debe tener un único grupo de registrador de copia de seguridad que se encuentra en un sitio central diferente.

- El grupo de registrador principal debe configurarse para conmutar por error al grupo de registrador de copia de seguridad. De forma predeterminada, se establece el registrador principal para conmutar por error al grupo de registrador de copia de seguridad después de un intervalo de 300 segundos. Puede cambiar este intervalo mediante la Skype para Business Server Topology Builder.

- Configurar una ruta de conmutación por error. Al configurar la ruta, especifique una puerta de enlace que se encuentra en un sitio diferente de la puerta de enlace especificado en la ruta principal.

- Si el sitio central incluido el servidor de administración principal y el sitio es probable que esté inactivo durante un período prolongado, deberá volver a instalar las herramientas de administración en el sitio de copia de seguridad; de lo contrario, no podrá cambiar cualquier configuración de administración.

### <a name="dependencies"></a>Dependencias

Skype para Business Server depende de los siguientes componentes de software e infraestructura para garantizar la resistencia de voz:

|**Componente** <br/> |**Funcional** <br/> |
|:-----|:-----|
|DNS  <br/> |Resolver registros SRV y A para la conectividad de servidor a servidor y cliente a servidor  <br/> |
|Exchange y los servicios Web Exchange (EWS)  <br/> |Póngase en contacto con el almacenamiento de información; datos del calendario  <br/> |
|Mensajería unificada de Exchange y servicios Web de Exchange  <br/> |Llamar a los registros, lista de correo de voz, correo de voz  <br/> |
|Opciones de DHCP 120  <br/> |Si DNS SRV no está disponible, el cliente intentará usar la opción DHCP 120 para detectar al registrador. Para que funcione, debe configurarse un servidor DHCP o Skype para profesionales servidor DHCP debe estar habilitada.  <br/> |

### <a name="survivable-voice-features"></a>Características de voz con funciones de supervivencia

Si se han implementado los requisitos y recomendaciones anterior, se proporcionará las siguientes características de voz por grupo de registrador de copia de seguridad:

- Llamadas RTC salientes

- Llamadas RTC entrantes, si el proveedor de servicios de telefonía es compatible con la capacidad de conmutación por error a un sitio de copia de seguridad

- Llamadas entre los usuarios en el mismo sitio y entre dos sitios diferentes de empresa

- Administración de llamadas básica, incluidos espera de llamada, recuperación y transferencia

- Dos proveedores de mensajería instantánea y uso compartido de audio y vídeo entre los usuarios en el mismo sitio

- Desvío de llamadas, llamadas simultáneas de extremos, delegación de llamadas y servicios de llamada de equipo, pero sólo si se configuran ambas partes para la delegación de llamada, o todos los miembros del equipo, en el mismo sitio.

- Teléfonos y clientes existentes siguen funcionando.

- Registro detallado de llamadas (CDR)

- Autenticación y autorización

Dependiendo de cómo estén configuradas, las siguientes características de voz pueden o no funcionen cuando un sitio central principal está fuera de servicio:

- Depósito de correo de voz y la recuperación

    Si desea que la mensajería unificada de Exchange que estén disponibles cuando el sitio central principal está fuera de servicio, debe hacer una de las siguientes:

  - Cambiar registros SRV de DNS para que los servidores de mensajería unificada de Exchange en el sitio central elija copia de seguridad servidores de mensajería unificada de Exchange en otro sitio.

  - Configurar el plan de marcado de cada usuario mensajería unificada de Exchange para incluir los servidores de mensajería unificada de Exchange en el sitio central y el sitio de copia de seguridad, pero designar los servidores de mensajería unificada de Exchange backup como deshabilitado. Si el sitio primario deja de estar disponible, el Administrador de Exchange debe marcar los servidores de mensajería unificada de Exchange en el sitio de copia de seguridad como habilitado.

    Si ninguna de las soluciones anteriores es posible, a continuación, mensajería unificada de Exchange no estará disponible en el sitio central deja de estar disponible de eventos.

- Conferencia de todos los tipos

    Un usuario que no ha podido a través de un sitio de copia de seguridad puede unirse a una conferencia que se crea u hospedada por un organizador cuyo grupo está disponible pero no se puede crear u hospedar una conferencia en su propio grupo principal, que ya no está disponible. De forma similar, otros usuarios no pueden unirse a las conferencias que se hospedan en el grupo principal del usuario afectado.

Las siguientes características de voz no funcionan cuando un sitio central principal está fuera de servicio:

- Operador automático de conferencia

- Presencia y enrutamiento basado en DNS

- Actualizar la configuración de transferencia de llamadas

- Servicio de grupo de respuesta y estacionamiento de llamadas

- Aprovisionamiento de nuevos teléfonos y clientes

- Búsqueda de Web de la libreta de direcciones

## <a name="branch-site-resiliency"></a>Resistencia de la sucursal

Si desea proporcionar resistencia de sitios de sucursal, es decir, servicio de Enterprise Voice de alta disponibilidad, tiene tres opciones para hacerlo:

- Aplicación de sucursal con funciones de supervivencia

- Servidor de sucursal con funciones de supervivencia

- Una completa Skype para la implementación de Business Server en el sitio de sucursal

Esta guía le ayudará a evaluar qué solución de resistencia es mejor para su organización y, en función de su solución de resistencia, la solución de conectividad RTC a usar. También le ayudará a preparar la implementación de la solución que elija mediante la descripción de los requisitos previos y otras consideraciones de planeación.

### <a name="branch-site-resiliency-features"></a>Características de resistencia de sitios de sucursal

Si proporcionar resistencia de sitios de sucursal, si se produce un error en la conexión de WAN del sitio de sucursal a un sitio central o si el sitio central es inaccesible, deberían seguir estén disponibles las siguientes características de voz:

- Llamadas entrantes y salientes telefónica conmutada (RTC)

- Llamadas entre los usuarios en el mismo sitio y entre dos sitios diferentes de empresa

- Administración de llamadas básica, incluidos espera de llamada, recuperación y transferencia

- Mensajería instantánea de dos participantes

- Desvío de llamadas, llamadas simultáneas de extremos, delegación de llamadas y servicios de llamada de equipo, pero sólo si el usuario delegado y delegado (por ejemplo, un administrador y administrador del director) o todos los miembros del equipo, se configuran en el mismo sitio

- Registros de detalles de llamadas (CDR)

- Conferencia de acceso telefónico RTC con operador automático de conferencia

- Capacidades de correo de voz, si se configura el redireccionamiento de configuración de correo de voz.

- Autorización y autenticación de usuario

Las siguientes características estarán disponibles solo si su solución de resistencia es una Skype a gran escala para la implementación de Business Server en la sucursal:

- Mensajería instantánea, web y / conferencia A/v

- Presencia y basado en No molestar DNS enrutamiento (donde las llamadas se impide suenen en extensiones con DND activado)

- Actualizar la configuración de transferencia de llamadas

- Aplicación de grupo de respuesta y aplicación estacionamiento de llamadas

- Aprovisionamiento de nuevos teléfonos y clientes, pero sólo si los servicios de dominio de Active Directory está presente en el sitio de sucursal.

- 9-1-1 mejorado (E9-1-1)

    Si se implementa E9-1-1 y el tronco SIP en el sitio central no está disponible debido a que el vínculo WAN está inactivo, a continuación, la aplicación de sucursal con funciones de supervivencia enrutarán las llamadas de E9-1-1 a la puerta de enlace de la sucursal local. Para habilitar esta característica, las directivas de voz de los usuarios de los sitios de sucursal deben enrutar las llamadas a la puerta de enlace local en el caso de error de WAN.

> [!NOTE]
> SBA (sucursal con funciones de supervivencia) no se admite para XMPP. Los usuarios alojados en una SBA configuraciones no podrá enviar mensajes instantáneos o ver el estado de presencia con los contactos XMPP.

### <a name="branch-site-resiliency-solutions"></a>Soluciones de resistencia de sitios de sucursal

Existen ventajas obvias para proporcionar resistencia de sitios de sucursal a su organización. En concreto, si se pierde la conexión con el sitio central, los usuarios del sitio de sucursal seguirán tiene correo de voz y de servicio de Enterprise Voice (si se configura el redireccionamiento de configuración de correo de voz). Sin embargo, para los sitios con menos de 25 usuarios, una solución de resistencia de no puede proporcionar un suficiente retorno de la inversión.

Si decide proporcionar resistencia de sitios de sucursal, tiene tres opciones. En la siguiente tabla puede ayudarle a determinar la mejor opción para su organización.

|**Si se...**|**Se recomienda que use un...**|
|:-----|:-----|
|Hospeda entre 25 y 1000 usuarios en su sitio de sucursal, y si el retorno de la inversión no es compatible con una distribución completa o donde local asistencia administrativa no está disponible  <br/> |Aplicación de sucursal con funciones de supervivencia  <br/> La aplicación de sucursal con funciones de supervivencia es un servidor blade estándar del sector con un Skype para el registrador de servidor empresarial y servidor de mediación que se ejecutan en Windows Server 2008 R2. La aplicación de sucursal con funciones de supervivencia también contiene una puerta de enlace de telefónica conmutada (RTC). Dispositivos compatibles de terceros (desarrollados por los socios de Microsoft en el programa de calificación y certificación de dispositivo de sucursal con funciones de supervivencia (SBA)) proporcionan una conexión RTC continua en caso de error de WAN, pero este enfoque no proporciona resistente presencia y conferencia porque estas características dependen de los servidores Front-End en el sitio central.  <br/> Para obtener información detallada acerca de las aplicaciones de sucursal con funciones de supervivencia, vea "Detalles de dispositivo de sucursal con funciones de supervivencia", más adelante en este tema.  <br/> **Nota:** Si decide usar también un tronco SIP con su aplicación de sucursal con funciones de supervivencia, póngase en contacto con el proveedor de la aplicación de sucursal con funciones de supervivencia para obtener más información sobre qué proveedor de servicios es mejor para su organización. <br/> |
|Hospeda entre 1000 y 2000 usuarios en su sitio de sucursal, carecen de una conexión WAN resistente y han formación Skype empresarial para administradores de servidor disponibles  <br/> |Un servidor de sucursal con funciones de supervivencia o dos aplicaciones de sucursal con funciones de supervivencia.  <br/> El servidor de sucursal con funciones de supervivencia es un servidor de Windows los requisitos de hardware especificado de la reunión que tenga Skype para el registrador de servidor empresarial y servidor de mediación software instalado en él. Se debe conectar a una puerta de enlace RTC o un tronco SIP a un proveedor de servicios telefónicos.  <br/> Para obtener información detallada acerca de los servidores de sucursal con funciones de supervivencia, vea "Detalles de servidor de sucursal con funciones de supervivencia", más adelante en este tema.  <br/> |
|Si necesita las características de presencia y conferencia en además de voz las características de hasta 5000 usuarios y han formación Skype empresarial para administradores de servidor disponibles  <br/> |Implementar como un sitio central con un servidor Standard Edition en lugar de un sitio de sucursal.  <br/> Un Skype a gran escala para la implementación de Business Server proporciona una conexión RTC y resistente presencia y conferencia en caso de error de WAN.  <br/> |

#### <a name="resiliency-topologies"></a>Topologías de resistencia

La figura siguiente muestra las topologías recomendadas para la resistencia de sitios de sucursal.

**Opciones de resistencia de sitios de sucursal**

![Opciones de resistencia de voz para sucursal](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Detalles de la aplicación de sucursal con funciones de supervivencia

El Skype para aplicación de sucursal con funciones de supervivencia de Business Server incluye los siguientes componentes:

- Un registrador para la autenticación de usuario, el registro y el enrutamiento de llamadas

- Un servidor de mediación para controlar la señalización entre el registrador y una puerta de enlace de RTC

- Una puerta de enlace de RTC para enrutar las llamadas a la RTC como un transporte de reserva si se produce una interrupción de la WAN

- SQL Server Express para el almacenamiento de datos de usuario local

La aplicación de sucursal con funciones de supervivencia también incluye troncos RTC, puertos analógicos y un adaptador Ethernet.

Si la conexión de WAN del sitio de sucursal a un sitio central deja de estar disponible, los usuarios de sucursal interno continuarán para registrarse con el registrador de dispositivo de sucursal con funciones de supervivencia y obtener un servicio ininterrumpido voice mediante el uso de la conexión de aplicación de sucursal con funciones de supervivencia a la RTC. Los usuarios que se conectan desde casa u otras ubicaciones remotas podrán registrar con un servidor de registrador en un sitio central si el vínculo WAN a la sucursal en el sitio de sucursal no está disponible. Estos usuarios tendrán la funcionalidad completa de comunicaciones unificadas, con la única excepción que se realizarán las llamadas entrantes para el sitio de sucursal al correo de voz. Cuando la conexión WAN pasa a estar disponible, se debería restaurar toda la funcionalidad a los usuarios del sitio de sucursal. Ni la conmutación por error a la aplicación de sucursal con funciones de supervivencia ni la restauración del servicio requiere la presencia de un administrador de TI.

Skype para Business Server admite hasta dos aplicación de sucursal con funciones de supervivencia en un sitio de sucursal.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Información general sobre la implementación de dispositivo de sucursal con funciones de supervivencia

La aplicación de sucursal con funciones de supervivencia se fabricó por fabricantes de equipos originales en asociación con Microsoft y se implementan en su nombre por los minoristas de valor agregados. Esta implementación debe producirse sólo una vez que Skype para Business Server se ha implementado en el sitio central, una conexión WAN con el sitio de sucursal en su lugar, y los usuarios del sitio de sucursal están habilitados para Enterprise Voice.

Para obtener información detallada acerca de estas fases, vea [implementación de un servidor o una aplicación de sucursal con funciones de supervivencia](https://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) en la documentación de implementación.

|**Fase**|**Pasos**|**Derechos de usuario**|
|:-----|:-----|:-----|
|Configurar los servicios de dominio de Active Directory para la aplicación de sucursal con funciones de supervivencia  <br/> |**En el sitio central:** <br/>  Cree una cuenta de usuario de dominio (o identidad de empresa) para el técnico que vaya a instalar y activar la aplicación de sucursal con funciones de supervivencia en el sitio de sucursal. <br/>  Cree una cuenta de equipo (con el correspondiente nombre de dominio completo (FQDN)) para la aplicación de sucursal con funciones de supervivencia en los servicios de dominio de Active Directory. <br/>  En el generador, crear y publicar la aplicación de sucursal con funciones de supervivencia. <br/> |La cuenta de usuario del técnico debe ser un miembro de RTCUniversalSBATechnicians. La aplicación de sucursal con funciones de supervivencia debe pertenecer al grupo de RTCSBAUniversalServices, lo que sucede automáticamente al usar el generador de topología.  <br/> |
|Instalar y activar la aplicación de sucursal con funciones de supervivencia.  <br/> |**En la sucursal:** <br/>  Conectar la aplicación de sucursal con funciones de supervivencia a un puerto Ethernet y el puerto de RTC. <br/>  Inicie la aplicación de sucursal con funciones de supervivencia. <br/>  Unirse a la aplicación de sucursal con funciones de supervivencia en el dominio, con la cuenta de usuario de dominio creada para la aplicación de sucursal con funciones de supervivencia en el sitio central. Establecer la dirección IP y FQDN para que coincida con el FQDN creado en la cuenta de equipo. <br/>  Configurar la aplicación de sucursal con funciones de supervivencia mediante la interfaz de usuario OEM. <br/>  Probar la conectividad de RTC. <br/> |La cuenta de usuario del técnico debe ser un miembro de RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Detalles del servidor de sucursal con funciones de supervivencia

En el generador de topología crear el sitio de sucursal, agregue el servidor de sucursal con funciones de supervivencia a ese sitio y, a continuación, ejecute el Skype para el Asistente para la implementación de Business Server en el equipo donde desea instalar el rol.

### <a name="branch-site-resiliency-requirements"></a>Requisitos de resistencia de sitios de sucursal

En este tema le ayudará a preparar a los usuarios para la resistencia de sucursales y las funciones de supervivencia de correo de voz y también especifica los requisitos de hardware y software pertinentes.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparación de los usuarios de sucursal para la resistencia de sitios de sucursal

Preparar a los usuarios para la resistencia de sitios de sucursal mediante la configuración de su grupo de registrador como el dispositivo de sucursal con funciones de supervivencia (SBA) o el servidor de sucursal con funciones de supervivencia.

#### <a name="registrar-assignments-for-branch-users"></a>Asignaciones de registrador para usuarios de sucursal

Independientemente de qué solución de resistencia de sitios de sucursal que elija, debe asignar a un registrador principal a cada usuario. Los usuarios del sitio de sucursal siempre deben registrar con el registrador en la sucursal, independientemente de si ese registrador reside en la aplicación de sucursal con funciones de supervivencia, un servidor de sucursal con funciones de supervivencia o Skype independiente para Business Server Standard o Enterprise Edition servidor. Un registro de recursos de servicio (SRV) de dominio nombre del sistema (de dominio DNS) es necesario para que un cliente puede detectar su grupo de registrador. Si la aplicación de sucursal con funciones de supervivencia deja de estar disponible, esto es cómo los clientes de sitios de sucursal descubre automáticamente el registrador de copia de seguridad.

Si un sitio de sucursal no tiene un servidor DNS, existen dos métodos alternativos para configurar la detección de la aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia:

- Configurar la opción de DHCP 120 en el servidor de protocolo de configuración dinámica de Host (DHCP) del sitio de sucursal para que apunte al nombre de dominio completo (FQDN) de la aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia.

- Configurar la aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia para responder a las consultas de DHCP 120.

#### <a name="voice-routing-for-branch-users"></a>Enrutamiento para usuarios de sucursal de voz

Le recomendamos que cree una voz de nivel de usuario independiente a través de la directiva de protocolo de Internet (VoIP) para los usuarios en un sitio de sucursal. Esta directiva debe incluir una ruta principal que utiliza la puerta de enlace de servidor de aplicación de sucursal con funciones de supervivencia o de sucursal y una o varias rutas de copia de seguridad que utilice un tronco con una puerta de enlace de telefónica conmutada (RTC) en el sitio central. Si la ruta principal no está disponible, la ruta de copia de seguridad que utiliza una o más puertas de enlace de sitio central se usa en su lugar. De este modo, independientemente de donde se registró un usuario, en el sitio de sucursal registrador o grupo de registrador de copia de seguridad en el sitio central: la directiva del usuario VoIP siempre es en efecto. Esto es una consideración importante para los escenarios de conmutación por error. Por ejemplo, si necesita cambiar el nombre de la aplicación de sucursal con funciones de supervivencia o volver a configurar la aplicación de sucursal con funciones de supervivencia para conectarse a una copia de seguridad del grupo de registrador en el sitio central, debe mover los usuarios del sitio de sucursal al sitio central para la duración. (Para obtener información detallada sobre el cambio de nombre o volver a configurar una aplicación de sucursal con funciones de supervivencia, vea [Apéndice B: administración de una aplicación de sucursal con funciones de supervivencia](https://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx) en la documentación de implementación). Si los usuarios no tienen las directivas de nivel de usuario VoIP o planes de marcado de nivel de usuario, cuando los usuarios se mueven a otro sitio, las directivas de VoIP de nivel de sitio y el marcado de nivel de sitio planes del sitio central se aplican a los usuarios de forma predeterminada, en lugar de la sucursal nivel de sitio VoIP las directivas y marcado planes. En este escenario, a menos que se utilizó de planes de marcado de las directivas de VoIP de nivel de sitio y de nivel de sitio de grupo de registrador de copia de seguridad también se puede aplicar a los usuarios del sitio de sucursal, sus llamadas se producirá un error. Por ejemplo, si los usuarios de un sitio de sucursal que se encuentra en Japón se mueven a un sitio central en Redmond, un plan de marcado con reglas de normalización que anteponga + 1425 a todas las llamadas de 7 dígitos es poco probable que traducir correctamente las llamadas para esos usuarios.

> [!IMPORTANT]
> Cuando se crea una ruta de copia de seguridad de office de sucursal, se recomienda que agregue dos registros de uso de teléfono RTC a la directiva de usuario de office de sucursal y asignar rutas independientes para cada uno de ellos. La primera, o primario, ruta sería dirigir las llamadas a la puerta de enlace asociada con el dispositivo de sucursal con funciones de supervivencia (SBA) o el servidor de sucursal; el segundo, o una copia de seguridad, ruta sería dirigir las llamadas a la puerta de enlace en el sitio central. En dirigir las llamadas, el servidor de sucursal o SBA intentará todas las rutas asignadas al primer registro de uso de RTC antes de intentar el segundo registro de uso.

Para ayudar a garantizar que las llamadas entrantes a los usuarios del sitio de sucursal alcanzará esos usuarios cuando no está disponible la puerta de enlace de la sucursal o el componente de Windows del sitio de la aplicación de sucursal con funciones de supervivencia (que ocurriría, por ejemplo, si la aplicación de sucursal con funciones de supervivencia o sucursal puerta de enlace eran hacia abajo para el mantenimiento), crear una ruta de conmutación por error en la puerta de enlace (o trabajar con su proveedor de llamada directa (DID)) para redirigir las llamadas entrantes al grupo de registrador de copia de seguridad en el sitio central. Desde allí, las llamadas se enrutarán a través de la WAN vínculo a los usuarios de sucursal. Asegúrese de que la ruta convierte los números para cumplir con la puerta de enlace RTC o formatos de números de teléfono aceptados del otro interlocutor tronco. Para obtener información detallada sobre la creación de una ruta de conmutación por error, vea [Configurar una ruta de conmutación por error](https://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx). También crear planes de marcado de nivel de servicio para el tronco asociado con la puerta de enlace en el sitio de sucursal para normalizar las llamadas entrantes. Si tiene dos aplicaciones de sucursal con funciones de supervivencia en un sitio de sucursal, puede crear un plan de marcado de nivel de sitio para ambos a menos que sea necesario un plan de nivel de servicio independiente para cada uno.

> [!NOTE]
> Para tener en cuenta para el consumo de recursos del sitio central por los usuarios de sitio de sucursal que se basan en el sitio central de presencia, conferencias o conmutación por error, se recomienda que tenga en cuenta de cada usuario del sitio de sucursal como si el usuario se ha registrado en el sitio central. Actualmente no hay ningún límite en el número de usuarios del sitio de sucursal, incluidos los usuarios registrados con una aplicación de sucursal con funciones de supervivencia.

También se recomienda que cree una directiva de voz y el plan de marcado de nivel de usuario y, a continuación, se asigna a los usuarios del sitio de sucursal. Para obtener información detallada, vea [crear o modificar un plan de marcado de Skype para Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) y [crear la directiva de enrutamiento VoIP para usuarios de sucursal](https://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx) en la documentación de implementación.

#### <a name="routing-extension-numbers"></a>Números de extensión de enrutamiento

Al preparar planes de marcado y las directivas de voz para que los usuarios del sitio de sucursal, asegúrese de incluir las reglas de normalización y reglas de conversión que coinciden con las cadenas y el formato de número utilizado en la msRTCSIP-line (o URI de línea) de atributo, para que habilite Skype para llamadas de trabajo entre los usuarios del sitio de sucursal y el sitio central a los usuarios se van a enrutar correctamente, especialmente cuando las llamadas deben enrutarse de nuevo a través de la RTC debido a que el vínculo WAN no está disponible. Además, existen consideraciones especiales para los números marcados que incluyan los números de extensión, simplemente los números de teléfono.

Reglas de normalización y traducciones las reglas que coinciden con los URI de línea que contienen un número de extensión, si exclusivamente o además de un número de teléfono E.164 completo, tienen requisitos adicionales. En esta sección se describe varios escenarios de ejemplo para enrutar las llamadas para los identificadores URI de línea con un número de extensión.

Si su organización no dispone de los números de teléfono directo DID (llamada) configurados para usuarios individuales y el URI de línea de cada usuario se configura con solo un número de extensión, los usuarios internos pueden llamar a otro marcando sólo un número de extensión. Sin embargo, debe configurar reglas de normalización que se pueden aplicar a las llamadas de un usuario del sitio de sucursal a un usuario del sitio central, que coinciden con los números de extensión.

En un escenario donde el vínculo WAN entre una sucursal y un sitio central está disponible, las llamadas de los usuarios del sitio de sucursal a los usuarios del sitio central no requieren la regla de normalización coincidente para convertir el número, porque la llamada no se enrutan a través de la RTC. Por ejemplo:

|**Nombre de la regla**|**Descripción**|**Patrón de números**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |No traduce números de 5 dígitos  <br/> |^(\d{5})$  <br/> |$1  <br/> |no traduce 10001  <br/> |

También debe dar cabida a los números de extensión para escenarios específicos, como cuando el vínculo WAN entre un sitio de sucursal y el sitio central no está disponible y se debe enrutar una llamada desde un sitio de sucursal a través de la RTC. Durante una interrupción de la WAN, si un usuario del sitio de sucursal llama a un usuario del sitio central marcando la extensión del usuario del sitio central, debe tener una regla de conversión de salida que agrega el número de teléfono completo del usuario del sitio central. Si un URI de línea de un usuario contiene el número de teléfono completo de su organización y el número de extensión único del usuario en lugar de un número de teléfono completo que es único para el usuario, debe tener una regla de conversión de salida que agrega el número de teléfono completo de su organización en su lugar . Por ejemplo:

|**Descripción**|**Coincidencia de patrón**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Convierte los números de 5 dígitos al número de teléfono y la extensión de un usuario  <br/> |^(\d{5})$  <br/> |+ 14255550123; ext = $1  <br/> |10001 se traduce a + 14255550123; ext = 10001  <br/> |
|Convierte los números de 5 dígitos al número de teléfono de la organización y la extensión de un usuario  <br/> |^(\d{5})$  <br/> |+ 14255550100; ext = $1  <br/> |10001 se traduce a + 14255550100; ext = 10001  <br/> |

En este escenario, si el par de tronco que administra el desvío a la RTC no es compatible con los números de extensión, a continuación, la regla de conversión de salida también debe quitar el número de extensión. Por ejemplo:

|**Descripción**|**Coincidencia de patrón**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Quita la extensión de los números de teléfono con extensiones  <br/> |^\+(\d\*); ext=(\d\*)$  <br/> |+$1  <br/> |+ 14255550123; ext = 10001 se traduce a + 14255550123  <br/> |

O no está disponible, si la organización no tiene un vínculo WAN ha configurado para los usuarios individuales de los números y el URI de línea para un usuario contiene el número de teléfono de la organización y el número de extensión único del usuario y, a continuación, debe configurar su teléfono número URI de línea la organización con un número que es accesible por el mismo nivel de tronco o puerta de enlace RTC en el sitio de sucursal. También debe configurar URI para incluir su propia extensión exclusiva para las llamadas deben enrutarse a ese número de la línea de número de teléfono de su organización.

#### <a name="preparing-for-voice-mail-survivability"></a>Preparación para la supervivencia de correo de voz

Mensajería unificada de Exchange (UM) normalmente se instala sólo en un sitio central y no en sitios de sucursal. Un autor de la llamada debe ser capaz de dejar un mensaje de correo de voz, incluso si el vínculo WAN entre sitios de sucursal y el sitio central no está disponible. Como resultado, configurar el URI de línea para el número de teléfono del operador de automático en mensajería unificada de Exchange que proporciona correo de voz para los usuarios del sitio de sucursal requiere consideraciones especiales, además de la directiva de voz, de marcado plan y reglas de normalización aplicables a ese correo de voz número.

Aplicaciones de sucursal con funciones de supervivencia (SBA) y servidores de sucursal con funciones de supervivencia proporcionan las funciones de supervivencia de correo de voz para usuarios de sucursal durante una interrupción de la WAN. En concreto, si está utilizando una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia y la WAN deja de estar disponible, la SBA o un servidor de sucursal con funciones de supervivencia redistribuye las llamadas no respondidas a través de la RTC para mensajería unificada de Exchange en el sitio central. Con una SBA o un servidor de sucursal con funciones de supervivencia, los usuarios también pueden recuperar los mensajes de correo de voz a través de la RTC durante una interrupción de la WAN. Por último, durante una interrupción de la WAN la aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia pone en cola las notificaciones de llamadas perdidas y, a continuación, carga en el servidor de mensajería unificada de Exchange cuando se restaura la WAN. Para ayudar a garantizar que el desvío de correo de voz es resistente, asegúrese de que se agregue una entrada para FQDN del grupo de servidores del sitio central y una entrada para el FQDN del servidor perimetral en el archivo hosts en el servidor de sucursal con funciones de supervivencia. De lo contrario, la resolución DNS puede tiempo de espera si no tiene un servidor DNS en la sucursal.

Se recomienda la siguiente configuración para las funciones de supervivencia del correo de voz para los usuarios del sitio de sucursal:

- Un administrador de Microsoft Exchange debe configurar Exchange UM operador automático (AA) para que únicamente acepte mensajes. Esta configuración deshabilita todos los otro funcionalidad genérica, como la transferencia a un usuario o a un operador y limita el AA para que solamente acepten mensajes. Como alternativa, puede usar el Administrador de Exchange una AA genérico o un AA personalizado para enrutar la llamada a un operador.

- El Skype para el administrador del servidor empresarial debe tomar el número de teléfono del AA y usar ese número de teléfono como el número de **exchange um operador automático** en la configuración de la aplicación de sucursal con funciones de supervivencia o un servidor de sucursal de reenrutamiento del correo de voz.

- El Skype para el administrador del servidor empresarial debe obtener número de teléfono de acceso de suscriptor de mensajería unificada de Exchange y usar ese número como el número de **acceso de suscriptor** en la configuración de la aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia de reenrutamiento del correo de voz .

- El Skype para el administrador del servidor empresarial debe configurar la mensajería unificada de Exchange para que sólo un plan de marcado está asociado con todos los usuarios de sucursal que necesiten obtener acceso al correo de voz durante una interrupción de la WAN.

- Cuando el vínculo WAN no está disponible, las llamadas a los usuarios del sitio de sucursal se puedan enrutar a buzón de correo de voz de mensajería unificada de Exchange (UM) del usuario, pero sólo si la directiva de voz se aplica a la llamada especifica un número de teléfono del correo de voz que es único y no incluye una extensión número.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware y Software para la resistencia de sitios de sucursal

Los requisitos de hardware y software pueden variar dependiendo de la solución de resistencia.

#### <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para aplicaciones de sucursal con funciones de supervivencia

Hardware y software necesario está integrado en la aplicación de sucursal con funciones de supervivencia. Sin embargo, también se recomienda que cada sitio de sucursal implementar un servidor DHCP para obtener direcciones IP; de cliente de lo contrario, cuando expira la concesión DHCP, los clientes no tendrán conectividad IP.

Si los servidores DNS de empresa se encuentran únicamente en los sitios centrales, los usuarios del sitio de sucursal no podrán conectarse a ellos durante una interrupción de la WAN y, por lo tanto, se producirá un error de Skype para la detección Business Server que usa DNS SRV (registro de recursos de servicio (SRV)). A fin de garantizar reenrutamiento prompt durante una interrupción de la WAN, se deben almacenar en caché los registros DNS en la sucursal. Si lo admite el enrutador de la sucursal, activar el almacenamiento en caché de DNS. O bien, puede implementar un servidor DNS en la sucursal. Esto puede ser un servidor independiente o una versión de la aplicación de sucursal con funciones de supervivencia que es compatible con las capacidades DNS. Para obtener más información, póngase en contacto con su proveedor de la aplicación de sucursal con funciones de supervivencia.

> [!NOTE]
> No es necesario disponer de un controlador de dominio en un sitio de sucursal. La aplicación de sucursal con funciones de supervivencia autentica a los clientes mediante el uso de un certificado especial que envía al cliente en respuesta a la solicitud de certificado de cliente cuando inicia sesión en.

Skype para los clientes empresariales puede descubrir el Skype para Business Server mediante el uso de la opción de DHCP 120 (opción de registrador SIP). Esto puede configurarse de dos maneras:

- Configurar el servidor DHCP en el sitio de sucursal para responder a las consultas de DHCP 120, que devuelven el FQDN del registrador en la aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia.

- Activar Skype para Business Server DHCP. Cuando esto está activado, el Skype para Business Server registrador responde a las consultas de la opción DHCP 120. Tenga en cuenta que el registrador no responde a las consultas DHCP distinto de las opciones de DHCP 120.

Además, para los sitios de sucursal más grandes que tengan varias subredes, deben habilitarse agentes de retransmisión DHCP para reenviar consultas de la opción DHCP 120 al servidor DHCP (configuración 1) o al registrador (configuración 2).

Por último, los usuarios del sitio de sucursal deben ser configurados para Enterprise Voice y aprovisionados con un extremo de comunicaciones unificadas apropiado.

#### <a name="requirements-for-survivable-branch-servers"></a>Requisitos para los servidores de sucursal con funciones de supervivencia

Los requisitos para servidores de sucursal con funciones de supervivencia son los mismos que los requisitos para un servidor Front-End. Para más información, vea [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisitos de Skype a gran escala para las implementaciones de sitio de sucursal de servidor empresarial

Para obtener información detallada, vea [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) en la documentación de planeación.

### <a name="example-configuring-a-failover-route"></a>Ejemplo: configuración de una ruta de conmutación por error

 En el ejemplo siguiente se muestra cómo un administrador puede definir una ruta de conmutación por error para su uso si la Dallas-GW1 está inactivo para el mantenimiento o no está disponible. En las tablas siguientes ilustran el cambio de configuración necesarias.

**La tabla 1. Directiva de usuario**

|**Directiva de usuario**|**Uso de teléfono**|
|:-----|:-----|
|Directiva de llamada predeterminada  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Directiva Local de Redmond  <br/> |RedmondLocal  <br/> |
|Directiva de llamada de Dallas  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tabla 2. Rutas**


| **Nombre de ruta**             | **Patrón de números** | **Uso de teléfono**         | **baúl**                                 | **Puerta de enlace**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Ruta Local de Redmond  <br/> | ^\+1 (425           | 206                     | 253)(\d{7})$  <br/>                       | Local  <br/> RedmondLocal  <br/>                |
| Ruta Local de Dallas  <br/>  | ^\+1 (972           | 214                     | 469)(\d{7})$  <br/>                       | Local  <br/>                                    |
| Ruta universal  <br/>     | ^\+?(\d\*)$  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Ruta de usuarios de Dallas  <br/>  | ^\+?(\d\*)$  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

En la tabla 1, se agrega un uso telefónico GlobalPSTNHopoff después del uso de la directiva de llamada de Dallas telefónico DallasUsers. Esto permite que las llamadas con la directiva de llamada de Dallas usen las rutas que se configuran para el uso de teléfono GlobalPSTNHopoff si una ruta para el uso telefónico DallasUsers no está disponible.


