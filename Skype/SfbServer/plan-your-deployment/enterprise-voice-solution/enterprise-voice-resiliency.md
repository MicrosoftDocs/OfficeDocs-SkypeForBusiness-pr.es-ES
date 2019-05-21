---
title: Plan for Enterprise Voice resiliency in Skype for Business Server
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
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Obtenga información sobre cómo admitir la resistencia de voz en Skype empresarial Server Enterprise Voice, en los dos sitios centrales y en los sitios de sucursales. Entre las opciones de sitio de sucursal se incluyen la implementación de equipos con sucursales o servidores de sucursales revivientes.
ms.openlocfilehash: 2ede1677e59753e5f8f39b3e9a35221041b56263
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276890"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Plan for Enterprise Voice resiliency in Skype for Business Server

Obtenga información sobre cómo admitir la resistencia de voz en Skype empresarial Server Enterprise Voice, en los dos sitios centrales y en los sitios de sucursales. Entre las opciones de sitio de sucursal se incluyen la implementación de equipos con sucursales o servidores de sucursales revivientes.

La resistencia de voz hace referencia a la capacidad de los usuarios para continuar realizando y recibir llamadas si un sitio central que hospeda Skype empresarial Server no está disponible, ya sea a través de una falla de red de área extensa (WAN) o de otra causa. Si se produce un error en un sitio central, el servicio de telefonía IP empresarial debe continuar sin interrupciones por failover transparente a un sitio de backup. En el caso de que se produzca un error de WAN, las llamadas a sitios de sucursales deben ser redirigidas a una puerta de enlace RTC local. En esta sección se explica cómo planear la resistencia de voz en el caso de que se produzca un error de sitio central o de WAN.

## <a name="central-site-resiliency"></a>Resistencia de sitios central

Cada vez más, las empresas tienen varios sitios diseminados por todo el mundo. El mantenimiento de los servicios de emergencia, el acceso al Departamento de soporte técnico y la capacidad de realizar tareas críticas empresariales cuando un sitio central está fuera de servicio es esencial para cualquier solución de resiliencia de telefonía empresarial. Cuando un sitio central deja de estar disponible, se deben cumplir las condiciones siguientes:

- Debe proporcionarse la conmutación por error.

- Los usuarios que normalmente se registran con el grupo de servidores front-end en el sitio central deben poder registrarse con un grupo de servidores front-end alternativo. Esto puede hacerse creando varios registros SRV de DNS, cada uno de los cuales se resuelve en un grupo de directores o grupo de servidores front-end en cada uno de sus sitios centrales. Puede ajustar la prioridad y los pesos de los registros SRV para que los usuarios atendidos por ese sitio central obtengan el director y el grupo de servidores front-end correspondiente antes que los de otros registros SRV.

- Las llamadas entre usuarios que se encuentren en otros sitios deben ser redirigidas a la RTC.

En este tema se describe la solución recomendada para proteger la resistencia de voz del sitio central.

### <a name="architecture-and-topology"></a>Arquitectura y topología

La planificación de resistencia de voz en un sitio central requiere un conocimiento básico del rol central que desempeña el registrador de Skype empresarial Server en habilitar la conmutación por error de voz. El registrador de Skype empresarial Server es un servicio que permite el registro y la autenticación de clientes y proporciona servicios de enrutamiento. Se ejecuta en todos los servidores Standard Edition, servidor front-end, director o sucursal con supervivencia. Un grupo de registradores consta de registrar servicios que se ejecutan en el grupo de servidores front-end y que residen en el mismo sitio. Un cliente de Skype empresarial Descubre el grupo de servidores front-end a través del siguiente mecanismo de detección:

1. Registro SRV de DNS

2. Servicio Web de descubrimiento automático

3. Opción de DHCP 120

Después de que el cliente de Skype empresarial se conecte al grupo de servidores front-end, lo dirigirá el equilibrador de carga a uno de los servidores front-end en el grupo. Ese servidor front-end, a su vez, redirige al cliente a un registrador preferido en el grupo.

Cada usuario habilitado para telefonía IP se asigna a un grupo de registrador concreto, que se convierte en el grupo de registrador principal de ese usuario. En un sitio determinado, cientos o miles de usuarios suelen compartir un único grupo de servidores principal. Para tener en cuenta el consumo de recursos del sitio central por parte de los usuarios de un sitio de sucursal que dependen del sitio central para la presencia, la Conferencia o la conmutación por error, le recomendamos que considere a cada usuario del sitio de sucursal como si el usuario fuera un usuario registrado con el sitio central. Por el momento, no hay límites en el número de usuarios de la sucursal, incluidos los registrados en un equipo de sucursales con la supervivencia.

Para garantizar la resistencia de voz en el caso de que se produzca un error en un sitio central, el grupo de registrador principal debe tener un único grupo de registrador de copia de seguridad ubicado en otro sitio. La copia de seguridad se puede configurar con la configuración de resistencia del generador de topología. Suponiendo un vínculo WAN resistente entre los dos sitios, los usuarios cuyo grupo principal ya no esté disponible se dirigen automáticamente al grupo de registro de la copia de seguridad.

Los pasos siguientes describen el proceso de detección y registro de clientes:

1. Un cliente Descubre Skype empresarial Server a través de registros SRV de DNS. En Skype empresarial Server, los registros SRV de DNS se pueden configurar para que devuelvan más de un FQDN a la consulta SRV de DNS. Por ejemplo, si Enterprise Contoso tiene tres sitios centrales (Norteamérica, Europa y Asia Pacífico) y un grupo de directores en cada sitio central, los registros SRV de DNS pueden apuntar a los FQDN del grupo de directores en cada una de las tres ubicaciones. Siempre que el grupo de directores esté disponible en una de las ubicaciones, el cliente puede conectarse al primer salto de Skype empresarial Server.

    > [!NOTE]
    > El uso de un grupo de directores es opcional. En su lugar, se puede usar un grupo de servidores front-end.

2. El grupo de directores informa al cliente de Skype empresarial sobre el grupo de registradores principal del usuario y el grupo de registro de la copia de seguridad.

3. El cliente de Skype empresarial intenta conectarse primero al grupo de registradores principal del usuario. Si el registrador principal está disponible, el registrador acepta el registro. Si el registrador principal del registrador no está disponible, el cliente de Skype empresarial intenta conectarse al grupo de registro de la copia de seguridad. Si el grupo de registro de la copia de seguridad está disponible y ha determinado que el registrador principal del usuario no está disponible (al detectar la falta de latido para un intervalo de conmutación por error especificado) el grupo de registro de la copia de seguridad acepta el registro del usuario. Después de que el registrador de la copia de seguridad detecta que el registrador principal está de nuevo disponible, el grupo de registro de la copia de seguridad redirigirá los clientes de conmutación por error a su grupo principal.

### <a name="requirements-and-recommendations"></a>Requisitos y recomendaciones

Los siguientes requisitos y recomendaciones para implementar la resistencia de voz de sitio central son adecuados para la mayoría de las organizaciones:

- Los sitios en los que residen los grupos principal y de registro de la entidad de seguridad deben conectarse con un vínculo WAN resistente.

- Cada sitio central debe contener un grupo de registradores formado por uno o varios registradores.

- Cada grupo de registrador debe tener equilibrio de carga mediante el equilibrio de carga de DNS, el equilibrio de carga de hardware o ambos. Para obtener información detallada sobre cómo planear la configuración del equilibrio de carga, consulte [requisitos de equilibrio de carga para Skype empresarial](../../plan-your-deployment/network-requirements/load-balancing.md).

- Cada usuario debe estar asignado a un grupo de registrador principal mediante el cmdlet **set-CsUser** del shell de administración de Skype empresarial o el panel de control de Skype empresarial Server.

- El grupo de registrador principal debe tener un único grupo de registradores de copia de seguridad ubicado en un sitio central diferente.

- El grupo de registrador principal debe configurarse para conmutar por error al grupo de registro de la copia de seguridad. De forma predeterminada, el registrador principal se establece para migrar tras un intervalo de 300 segundos. Puede cambiar este intervalo mediante el generador de topologías de Skype empresarial Server.

- Configure una ruta de conmutación por error. Al configurar la ruta, especifique una puerta de enlace que se encuentre en un sitio diferente de la puerta de enlace especificada en la ruta principal.

- Si el sitio central contenía su servidor de administración principal y es probable que el sitio esté inactiva durante un período prolongado, tendrá que volver a instalar las herramientas de administración en el sitio de copia de seguridad. de lo contrario, no podrá cambiar ninguna configuración de administración.

### <a name="dependencies"></a>Dependencias

Skype empresarial Server depende de los siguientes componentes de infraestructura y software para garantizar la resistencia de la voz:

|**Componente** <br/> |**Funcionan** <br/> |
|:-----|:-----|
|DNS  <br/> |Resolver registros SRV y A para la conectividad de servidor-servidor y servidor-cliente  <br/> |
|Exchange y Exchange Web Services (EWS)  <br/> |Almacenamiento de contactos; datos de calendario  <br/> |
|Mensajería unificada de Exchange y servicios Web de Exchange  <br/> |Registros de llamadas, lista de correo de voz, correo de voz  <br/> |
|Opciones de DHCP 120  <br/> |Si SRV de DNS no está disponible, el cliente intentará usar la opción 120 de DHCP para descubrir el registrador. Para que esto funcione, debe estar configurado un servidor DHCP o debe estar habilitado el DHCP de Skype empresarial Server.  <br/> |

### <a name="survivable-voice-features"></a>Características de voz revivientes

Si se han implementado los requisitos y las recomendaciones anteriores, el grupo de registro de la copia de seguridad proporcionará las siguientes características de voz:

- Llamadas RTC salientes

- Llamadas RTC entrantes, si el proveedor de servicios de telefonía admite la posibilidad de migrar por error a un sitio de copia de seguridad

- Llamadas empresariales entre usuarios en el mismo sitio y entre dos sitios diferentes

- Manejo básico de llamadas, que incluye la llamada en espera, la recuperación y la transferencia

- Mensajería instantánea de dos participantes y uso compartido de audio y vídeo entre usuarios del mismo sitio

- Desvío de llamadas, llamadas simultáneas a puntos de conexión, Delegación de llamadas y servicios de llamada de equipo, pero solo si las dos partes para llamar a la delegación o todos los miembros del equipo, se configuran en el mismo sitio.

- Los teléfonos y clientes existentes siguen funcionando.

- Registro detallado de llamadas (CDR)

- Autenticación y autorización

Según el modo en que estén configuradas, las siguientes características de voz pueden funcionar o no cuando un sitio central principal está fuera de servicio:

- Depósito y recuperación de correo de voz

    Si desea que la mensajería unificada de Exchange esté disponible cuando el sitio central principal está fuera de servicio, debe realizar una de las siguientes acciones:

  - Cambie los registros SRV de DNS para que los servidores de mensajería unificada de Exchange en el sitio central apunten a la copia de seguridad de los servidores MU de otro sitio.

  - Configure el plan de marcado de MU de Exchange de cada usuario para incluir servidores MU de Exchange en el sitio central y en el sitio de copia de seguridad, pero designe los servidores de Exchange UM como deshabilitados. Si el sitio primario no está disponible, el administrador de Exchange tiene que marcar los servidores de mensajería unificada de Exchange en el sitio de copia de seguridad como habilitado.

    Si ninguna de las soluciones anteriores es posible, la mensajería unificada de Exchange no estará disponible en caso de que el sitio central deje de estar disponible.

- Conferencias de todos los tipos

    Un usuario que conmuta por error a un sitio de copia de seguridad puede unirse a una conferencia creada o hospedada por un organizador cuyo grupo está disponible, pero no puede crear ni hospedar una conferencia en su propio grupo principal, que ya no está disponible. De forma similar, otros usuarios no pueden unirse a conferencias hospedadas en el grupo primario del usuario afectado.

Las siguientes características de voz no funcionan cuando un sitio central principal está fuera de servicio:

- Operador automático de conferencia

- Presencia y enrutamiento basado en DND

- Actualización de la configuración del desvío de llamadas

- Servicio de grupo de respuesta y Parque de llamadas

- Aprovisionamiento de nuevos teléfonos y clientes

- Búsqueda en Internet de la libreta de direcciones

## <a name="branch-site-resiliency"></a>Resistencia de sitios de sucursal

Si desea proporcionar resistencia al sitio de la sucursal, es decir, servicio de voz empresarial de alta disponibilidad, tiene tres opciones para ello:

- Aplicación de sucursal con funciones de supervivencia

- Servidor de sucursal con funciones de supervivencia

- Implementación completa de Skype empresarial Server en el sitio de la sucursal

Esta guía le ayudará a evaluar qué solución de resistencia es la mejor para su organización y, en función de su solución de resistencia, qué solución de conectividad RTC va a usar. También le ayudará a prepararse para implementar la solución que elija al describir los requisitos previos y otras consideraciones de planeación.

### <a name="branch-site-resiliency-features"></a>Características de resistencia de los sitios de sucursal

Si proporciona resistencia al sitio de la sucursal, si se produce un error en la conexión WAN de un sitio de sucursal con un sitio central o si el sitio central no está accesible, las siguientes características de voz deben seguir estando disponibles:

- Llamadas de red telefónica conmutada (RTC) entrantes y salientes

- Llamadas empresariales entre usuarios en el mismo sitio y entre dos sitios diferentes

- Manejo básico de llamadas, que incluye la llamada en espera, la recuperación y la transferencia

- Mensajería instantánea de dos participantes

- Desvío de llamadas, llamadas simultáneas a puntos de conexión, Delegación de llamadas y servicios de llamada de equipo, pero solo si el delegado y el delegado (por ejemplo, un administrador y el administrador del administrador) o todos los miembros del equipo están configurados en el mismo sitio

- Registros de detalles de llamadas (CDRs)

- Conferencias de acceso telefónico local RTC con operador automático de conferencia

- Capacidades de correo de voz, si configura la configuración de redireccionamiento del correo de voz.

- Autenticación y autorización de usuarios

Las siguientes características solo estarán disponibles si la solución de resistencia es una implementación de Skype empresarial Server completa en el sitio de la sucursal:

- Mensajería instantánea, Web y conferencias A/V

- Enrutamiento basado en presencia y no molestar (DND) (donde se impide que las llamadas suenen en extensiones que tienen la activada DND)

- Actualización de la configuración del desvío de llamadas

- Aplicación de grupo de respuesta y aplicación de estacionamiento de llamadas

- Aprovisionamiento de nuevos teléfonos y clientes, pero solo si los servicios de dominio de Active Directory están presentes en el sitio de la sucursal.

- Enhanced 9-1-1 (E9-1-1)

    Si se implementa E9-1-1 y el tronco del SIP del sitio central no está disponible debido a que el vínculo WAN está desactivado, el equipo de la sucursal con la que es posible que se enruten las llamadas de E9-1 a la puerta de enlace local. Para habilitar esta característica, las directivas de voz de los usuarios de los sitios de sucursales deberían enrutar las llamadas a la puerta de enlace local en el caso de producirse un error de WAN.

> [!NOTE]
> SBA (sucursal superviviente) no es compatible con XMPP. Los usuarios alojados en una configuración de SBA no podrán enviar mensajes instantáneos ni ver su presencia con contactos XMPP.

### <a name="branch-site-resiliency-solutions"></a>Soluciones de resistencia de sitios de sucursal

Existen ventajas obvias para proporcionar resistencia a sitios de sucursales a su organización. En concreto, si pierde la conexión con el sitio central, los usuarios del sitio de la sucursal seguirán teniendo el servicio de voz empresarial y el correo de voz (si configura la configuración de redireccionamiento del correo de voz). Sin embargo, en el caso de sitios con menos de 25 usuarios, una solución de resistencia puede no proporcionar un retorno de la inversión suficiente.

Si decide proporcionar resistencia a sitios de sucursales, tiene tres opciones. La siguiente tabla puede ayudarle a determinar la mejor opción para su organización.

|**Si...**|**Le recomendamos que use un...**|
|:-----|:-----|
|Hospedar entre 25 y 1000 usuarios de su sitio de sucursal y si el retorno de la inversión no admite una implementación completa o si no está disponible el soporte administrativo local  <br/> |Aplicación de sucursal con funciones de supervivencia  <br/> El equipo de la sucursal es un servidor blade estándar del sector con un servidor de mediación y registrador de Skype empresarial Server que se ejecuta en Windows Server 2008 R2. El dispositivo de sucursal con la supervivencia también contiene una puerta de enlace de red telefónica conmutada (RTC). Los dispositivos de terceros cualificados (desarrollados por los socios de Microsoft en el programa de certificación/titulación de la aplicación de rama superviviente (SBA) proporcionan una conexión RTC continua en el caso de una falla de WAN, pero este enfoque no proporciona resistencia presencia y Conferencia porque estas características dependen de servidores front-end en el sitio central.  <br/> Para obtener más información sobre los equipos de las sucursales que son supervivientes, consulte "detalles del equipo de las sucursales supervivientes", más adelante en este tema.  <br/> **Nota:** Si decide usar también un tronco de SIP con su equipo de sucursal con la supervivencia, póngase en contacto con el proveedor de su equipo de sucursales con la supervivencia para obtener información sobre el proveedor de servicios más adecuado para su organización. <br/> |
|El hospedaje entre usuarios de 1000 y 2000 de su sitio de sucursal carece de una conexión WAN resistente y tiene disponibles los administradores de servidores de Skype para empresas.  <br/> |Servidor de sucursal superviviente o dos dispositivos de sucursal con la supervivencia.  <br/> El servidor de sucursal con la supervivencia es un servidor de Windows que cumple los requisitos de hardware especificados que tiene instalado el software de servidor de mediación y el registrador de Skype empresarial Server. Debe conectarse a una puerta de enlace PSTN o a un tronco SIP a un proveedor de servicios telefónicos.  <br/> Para obtener detalles acerca de los servidores de sucursal con la supervivencia, consulte "detalles de servidores de sucursal supervivientes", más adelante en este tema.  <br/> |
|Si necesita características de presencia y de conferencia, además de características de voz para un máximo de 5000 usuarios, y tiene disponibles los administradores de servidores de Skype para empresas capacitados  <br/> |Implementar como un sitio central con un servidor Standard Edition en lugar de como un sitio de sucursal.  <br/> Una implementación de Skype empresarial Server a escala completa proporciona una conexión RTC continua y una presencia resistente y conferencias en caso de producirse un error de WAN.  <br/> |

#### <a name="resiliency-topologies"></a>Topologías de resiliencia

En la siguiente ilustración se muestran las topologías recomendadas para la resistencia a sitios de sucursales.

**Opciones de resistencia de sitio de sucursal**

![Opciones de resistencia de voz para sucursal](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Detalles de los dispositivos de rama supervivientes

El equipo de la sucursal de Skype empresarial Server reviviente incluye los siguientes componentes:

- Un registrador para la autenticación de usuarios, registro y enrutamiento de llamadas

- Un servidor de mediación para controlar la señalización entre el registrador y una puerta de enlace RTC

- Una puerta de enlace RTC para el enrutamiento de llamadas a la RTC como transporte de reserva en el caso de una interrupción de la WAN

- SQL Server Express para almacenamiento de datos de usuario local

El dispositivo de sucursal con la supervivencia también incluye troncos de la RTC, puertos análogos y un adaptador Ethernet.

Si la conexión WAN del sitio de la sucursal a un sitio central no está disponible, los usuarios de la sucursal interna siguen registrándose con el registrador de la aplicación de rama superviviente y obtienen un servicio de voz ininterrumpido usando la conexión de la aplicación de la aplicación de supervivencia a la RTC. Los usuarios de un sitio de sucursal que se conecten desde casa u otras ubicaciones remotas podrán registrarse con un servidor de registro en un sitio central si el vínculo WAN al sitio de la sucursal no está disponible. Estos usuarios tendrán una funcionalidad de comunicaciones unificadas completa, con la única excepción de que las llamadas entrantes al sitio de la sucursal Irán a correo de voz. Cuando la conexión WAN esté disponible, la funcionalidad completa debe restaurarse a los usuarios del sitio de la sucursal. Ni la conmutación por error a la aplicación de rama superviviente ni la restauración de servicio requiere la presencia de un administrador de ti.

Skype empresarial Server admite hasta dos dispositivos de sucursal con la supervivencia en un sitio de sucursal.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Descripción general de la implementación de dispositivos de sucursales

El equipo de sucursales que es superviviente es fabricado por los fabricantes de equipos originales en colaboración con Microsoft y distribuido en su nombre por tiendas minoristas de valor añadido. Esta implementación solo debe realizarse después de que Skype para empresas Server se haya implementado en el sitio central, una conexión WAN al sitio de la sucursal esté en vigor y los usuarios del sitio de la sucursal estén habilitados para telefonía IP empresarial.

Para obtener más información sobre estas fases, consulte [implementación de un dispositivo o servidor de sucursal](https://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) con la que sea reviviente en la documentación de implementación.

|**Fase**|**Pasos**|**Derechos de usuario**|
|:-----|:-----|:-----|
|Configurar los servicios de dominio de Active Directory para la aplicación de rama superviviente  <br/> |**En el sitio central:** <br/>  Cree una cuenta de usuario de dominio (o identidad empresarial) para el técnico que instalará y activará la aplicación de la rama que tiene el mismo nivel en el sitio de la sucursal. <br/>  Cree una cuenta de equipo (con el nombre de dominio completo aplicable (FQDN)) para el equipo de sucursales supervivientes en los servicios de dominio de Active Directory. <br/>  En el generador de topologías, cree y publique la aplicación de rama que sea superviviente. <br/> |La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians. La aplicación de la rama superviviente debe pertenecer al grupo RTCSBAUniversalServices, que se produce automáticamente al utilizar Topology Builder.  <br/> |
|Instale y active la aplicación de rama que sea superviviente.  <br/> |**En el sitio de la sucursal:** <br/>  Conecte el equipo con la sucursal que sea superviviente a un puerto Ethernet y Puerto RTC. <br/>  Inicia la aplicación de la sucursal que sea superviviente. <br/>  Únase al dominio de la sucursal con la que se pueda hacer uso de la cuenta de usuario de dominio que se creó para la aplicación de la rama superviviente en el sitio central. Establezca el FQDN y la dirección IP para que coincidan con el FQDN creado en la cuenta del equipo. <br/>  Configure el equipo con la interfaz de usuario OEM. <br/>  Pruebe la conectividad RTC. <br/> |La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Detalles del servidor de sucursal superviviente

En el generador de topología, cree el sitio de sucursal, agregue el servidor de sucursal con la supervivencia y, a continuación, ejecute el Asistente para la implementación de Skype empresarial Server en el equipo en el que desea instalar el rol.

### <a name="branch-site-resiliency-requirements"></a>Requisitos de resistencia de sitios de sucursales

Este tema le ayudará a preparar a los usuarios para la resiliencia de sitios de sucursales y la supervivencia del correo de voz, y también especifica los requisitos de hardware y software correspondientes.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparar usuarios de la sucursal para la resistencia a sitios de sucursales

Preparar a los usuarios para que tengan una resistencia al sitio de sucursal: Configure su grupo de registradores como el equipo de sucursales con capacidad de supervivencia (SBA) o servidor de sucursal con capacidad de supervivencia.

#### <a name="registrar-assignments-for-branch-users"></a>Registrar tareas para usuarios de la sucursal

Independientemente de la solución de resistencia que elija, tendrá que asignar un registrador principal a cada usuario. Los usuarios de un sitio de sucursal siempre deben registrarse en el sitio de la sucursal, independientemente de si el registrador reside en el dispositivo de sucursal con la supervivencia, en el servidor de sucursal con la supervivencia o con la versión independiente de Skype empresarial Server Standard o Enterprise. servidores. Se necesita un registro de recursos de servicio (SRV) de sistema de nombres de dominio (DNS) para que un cliente pueda descubrir su grupo de registradores. Si la aplicación de rama superviviente no está disponible, esta es la manera en que los clientes de sitios de sucursal detectarán automáticamente el registrador de copias de seguridad.

Si un sitio de sucursal no tiene un servidor DNS, hay dos formas alternativas de configurar el descubrimiento de la aplicación de sucursal que funciona con la supervivencia o el servidor de sucursal con la supervivencia:

- Configure la opción de DHCP 120 en el servidor de protocolo de configuración dinámica de host (DHCP) del sitio de sucursal para que señale el nombre de dominio completo (FQDN) del equipo de sucursal o el servidor de sucursal que sea superviviente.

- Configure la aplicación de rama superviviente o servidor de sucursal superviviente para responder a las consultas de 120 de DHCP.

#### <a name="voice-routing-for-branch-users"></a>Enrutamiento de voz para usuarios de la sucursal

Le recomendamos que cree una directiva de protocolo de voz a través de Internet (VoIP) de nivel de usuario independiente para los usuarios de un sitio de sucursal. Esta Directiva debe incluir una ruta principal que use la aplicación de rama superviviente o la puerta de enlace de servidor de sucursal, y una o más rutas de copia de seguridad que usen un tronco con una puerta de enlace de red telefónica conmutada (RTC) en el sitio central. Si la ruta principal no está disponible, se usa en su lugar la ruta de la copia de seguridad que usa una o más puertas de enlace de sitio central. De esta manera, independientemente de dónde esté registrado un usuario, en el registrador de sitios de la sucursal o en el grupo de registro de la copia de seguridad del sitio central, la Directiva de VoIP del usuario siempre está activa. Esta es una consideración importante para escenarios de conmutación por error. Por ejemplo, si necesita cambiar el nombre de la aplicación de la rama que tiene la configuración o volver a configurar el dispositivo de rama que tiene la mayoría para conectarse a un grupo de registro de la copia de seguridad en el sitio central, debe mover los usuarios del sitio de la sucursal al sitio central durante el tiempo. (Para obtener detalles sobre cómo cambiar el nombre o la configuración de un dispositivo de sucursal que sea reviviente, consulte el [Apéndice B: administrar un dispositivo de sucursal](https://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx) con la mayoría de la documentación de implementación). Si esos usuarios no tienen directivas de VoIP de nivel de usuario o planes de marcado de nivel de usuario, cuando se mueven los usuarios a otro sitio, las directivas de VoIP de nivel de sitio y los planes de marcado de nivel de sitio del sitio central se aplican a los usuarios de forma predeterminada, en lugar de la VoIP de nivel de sitio de sucursal directivas y planes de marcado,. En este caso, a menos que las directivas VoIP de nivel de sitio y los planes de marcado de nivel de sitio que usa el grupo de registro de la copia de seguridad también se apliquen a los usuarios de la sucursal, se producirá un error en sus llamadas. Por ejemplo, si los usuarios de un sitio de sucursal ubicado en Japón se mueven a un sitio central de Redmond, es improbable que un plan de marcado con reglas de normalización que antepongan + 1425 a todas las llamadas de 7 dígitos no sea la adecuada para traducir las llamadas de esos usuarios.

> [!IMPORTANT]
> Al crear una ruta de copia de seguridad de una sucursal, le recomendamos que agregue dos registros de uso de teléfono RTC a la Directiva de usuario de la sucursal y asigne rutas distintas a cada uno de ellos. La primera ruta, o la principal, dirigirían llamadas a la puerta de enlace asociada con el dispositivo de rama con la supervivencia (SBA) o el servidor de sucursal; la ruta del segundo, o de la copia de seguridad, dirigirá las llamadas a la puerta de enlace en el sitio central. En las llamadas directas, el servidor de SBA o de sucursal intentará todas las rutas asignadas al primer registro de uso de RTC antes de intentar el segundo registro de uso.

Para asegurarse de que las llamadas entrantes a los usuarios de un sitio de sucursal llegarán a esos usuarios cuando la puerta de enlace o el componente de Windows del sitio de la aplicación de sucursal superviviente no esté disponible (esto sucede, por ejemplo, si la sucursal o rama superviviente la puerta de enlace estuvo fuera de servicio por el mantenimiento), cree una ruta de conmutación por error en la puerta de enlace (o en el proveedor de marcado interno directo) para redirigir las llamadas entrantes al grupo de registro de la copia de seguridad en el sitio central. Desde allí, las llamadas se redirigirán a través del vínculo WAN a los usuarios de la sucursal. Asegúrese de que la ruta traduce los números para que cumplan con la puerta de enlace PSTN u otros formatos de número de teléfono aceptados del interlocutor del mismo nivel. Para más información sobre cómo crear una ruta de conmutación por error, vea [configurar una ruta de conmutación por error](https://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx). Además, cree planes de marcado de nivel de servicio para el tronco asociado a la puerta de enlace del sitio de la sucursal para normalizar las llamadas entrantes. Si tiene dos dispositivos de sucursal con la supervivencia en un sitio de sucursal, puede crear un plan de marcado de nivel de sitio para ambos, a menos que sea necesario un plan de nivel de servicio diferente para cada uno.

> [!NOTE]
> Para tener en cuenta el consumo de recursos del sitio central por parte de los usuarios de un sitio de sucursal que dependen del sitio central para la presencia, la Conferencia o la conmutación por error, le recomendamos que considere a cada usuario del sitio de sucursal como si el usuario se hubiera registrado con el sitio central. Por el momento, no hay límites en el número de usuarios de la sucursal, incluidos los registrados en un equipo de sucursales con la supervivencia.

También le recomendamos crear un plan de marcado y una directiva de voz de nivel de usuario y, a continuación, asignarla a los usuarios de un sitio de sucursal. Para obtener más información, consulte [crear o modificar un plan de marcado en Skype empresarial Server](../../deploy/deploy-enterprise-voice/dial-plans.md) y [crear la Directiva de enrutamiento de VoIP para usuarios](https://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx) de la implementación.

#### <a name="routing-extension-numbers"></a>Números de extensión de enrutamiento

Al preparar planes de marcado y directivas de voz para usuarios de sitios de sucursal, asegúrese de incluir reglas de normalización y reglas de traducción que coincidan con las cadenas y el formato de número que se usan en el atributo msRTCSIP-line (o URI de línea), para que las llamadas de Skype empresarial estén habilitadas. entre los usuarios de las sucursales y los usuarios del sitio central se enrutarán correctamente, especialmente cuando las llamadas se deben desviar a través de la RTC porque el vínculo WAN no está disponible. Además, existen consideraciones especiales para los números marcados que incluyen números de extensión, en lugar de números de teléfono.

Reglas de normalización y traducciones que coinciden con los identificadores URI que contienen un número de extensión, ya sea de forma exclusiva o adicional a un número de teléfono E. 164 completo, tienen requisitos adicionales. En esta sección se describen varios escenarios de ejemplo para enrutar llamadas de identificadores URI con un número de extensión.

Si su organización no tiene números de teléfono de marcado directo (sí) configurados para usuarios individuales y el URI de línea de cada usuario se configura con un número de extensión, los usuarios internos pueden llamarse solo por un número de extensión. Sin embargo, debe configurar las reglas de normalización que se pueden aplicar a las llamadas de un usuario del sitio de la sucursal a un usuario del sitio central, que coincidan con los números de extensión.

En un escenario en el que está disponible el vínculo WAN entre un sitio de sucursal y un sitio central, las llamadas de usuarios de sitios de sucursales a usuarios de sitios centrales no requieren la regla de normalización correspondiente para traducir el número, porque la llamada no se enruta a través de la RTC. Por ejemplo:

|**Nombre de la regla**|**Descripción**|**Patrón de números**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |No traduce números de 5 dígitos  <br/> |^ (\d{5}) $  <br/> |$1  <br/> |10001 no se traduce  <br/> |

También debe acomodar los números de extensión para escenarios específicos, como cuando el vínculo WAN entre un sitio de sucursal y el sitio central no está disponible y una llamada de un sitio de sucursal debe enrutarse a través de la RTC. Durante una interrupción de la WAN, si un usuario de un sitio de sucursal solo llama a un usuario del sitio central marcando la extensión del usuario del sitio central, debe tener una regla de traducción de salida que agregue el número de teléfono completo del usuario del sitio central. Si el identificador URI de línea de un usuario contiene el número de teléfono completo de su organización y el número de extensión único del usuario, en lugar de un número de teléfono completo que es exclusivo para el usuario, debe tener una regla de traducción de salida que agregue el número de teléfono completo de su organización en su lugar. . Por ejemplo:

|**Descripción**|**Patrón de coincidencia**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Traduce números de 5 dígitos al número de teléfono y a la extensión de un usuario.  <br/> |^ (\d{5}) $  <br/> |+ 14255550123; EXT = $1  <br/> |10001 se traduce a + 14255550123; ext = 10001  <br/> |
|Traduce números de 5 dígitos al número de teléfono de la organización y a la extensión de un usuario  <br/> |^ (\d{5}) $  <br/> |+ 14255550100; EXT = $1  <br/> |10001 se traduce a + 14255550100; ext = 10001  <br/> |

En este caso, si el punto de conexión del mismo nivel que controla el redireccionamiento a la RTC no admite números de extensión, la regla de traducción saliente también debe quitar el número de extensión. Por ejemplo:

|**Descripción**|**Patrón de coincidencia**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Quita la extensión de los números de teléfono con extensiones  <br/> |^\+(\d\*); EXT = (\d\*) $  <br/> |+$1  <br/> |+ 14255550123; ext = 10001 se traduce a + 14255550123  <br/> |

Si un vínculo WAN está disponible o no, si su organización no tiene números realizados para usuarios individuales y el URI de línea para un usuario contiene el número de teléfono de la organización y el número de extensión exclusivo del usuario, debe configurar el URI de la línea del número de teléfono de la organización con un número al que se puede alcanzar la puerta de enlace troncal o la puerta de enlace RTC en el sitio de la sucursal. También debe configurar el URI de la línea de número de teléfono de su organización para que incluya su propia extensión exclusiva para que las llamadas se enruten a ese número.

#### <a name="preparing-for-voice-mail-survivability"></a>Prepararse para la supervivencia del correo de voz

La mensajería unificada de Exchange (UM) suele instalarse únicamente en un sitio central y no en sitios de sucursales. La persona que llama debe poder dejar un mensaje de correo de voz, incluso si el vínculo WAN entre el sitio de la sucursal y el sitio central no está disponible. Como resultado, la configuración del URI de línea para el operador automático de mensajería unificada de Exchange que proporciona el correo de voz para los usuarios del sitio de sucursal requiere consideraciones especiales, además de la Directiva de voz, el plan de marcado y las reglas de normalización que se aplican a ese correo de voz. mero.

Los dispositivos de sucursal (SBAs) y los servidores de sucursales supervivientes proporcionan la supervivencia del correo de voz para los usuarios de la sucursal durante una interrupción de la WAN. En concreto, si está usando un dispositivo de sucursal o un servidor de sucursal supervivientes y la WAN deja de estar disponible, el servidor de sucursal de SBA o de supervivencia redirige las llamadas no contestadas a través de la RTC a la mensajería unificada de Exchange en el sitio central. Con un servidor de sucursal SBA o que sea reviviente, los usuarios también pueden recuperar los mensajes de correo de voz a través de la RTC durante una interrupción de WAN. Por último, durante una interrupción de la WAN, el equipo de sucursales que puede ser superviviente o el servidor de sucursal con la supervivencia, notifica y luego los carga en el servidor de mensajería unificada de Exchange cuando se restaura la WAN. Para ayudar a garantizar que el redireccionamiento del correo de voz sea resistente, asegúrese de agregar una entrada para el FQDN del grupo de sitios central y una entrada para el FQDN del servidor perimetral al archivo hosts en el servidor de sucursal con la supervivencia. En caso contrario, la resolución DNS puede agotar el tiempo si no tiene un servidor DNS en el sitio de la sucursal.

Recomendamos las siguientes configuraciones para los usuarios de sitios de sucursal de la supervivencia del correo de voz:

- Un administrador de Microsoft Exchange debe configurar el operador automático de mensajería unificada de Exchange (AA) para que solo acepte mensajes. Esta configuración deshabilita todas las demás funcionalidades genéricas, como la transferencia a un usuario o la transferencia a un operador, y limita el AA para aceptar solo los mensajes. Como alternativa, el administrador de Exchange puede usar un AA genérico o un AA personalizado para enrutar la llamada a un operador.

- El administrador de Skype empresarial Server debe tomar el número de teléfono AA y usar ese número de teléfono como el número de **operador automático de mensajería unificada de Exchange** en la configuración de redireccionamiento del correo de voz para el dispositivo de sucursal o el servidor de sucursal.

- El administrador de Skype empresarial Server debe obtener el número de teléfono de acceso a la mensajería unificada de Exchange y usar ese número como número de **acceso** del suscriptor en la configuración de redireccionamiento del correo de voz para el equipo de sucursal o servidor de sucursal con la supervivencia .

- El administrador de Skype empresarial Server debe configurar la mensajería unificada de Exchange para que solo se asocie un plan de marcado a todos los usuarios de la sucursal que necesiten acceso al correo de voz durante una interrupción de la WAN.

- Cuando el vínculo WAN no está disponible, las llamadas a usuarios de un sitio de sucursal se pueden enrutar al buzón de voz de mensajería unificada (UM) del usuario, pero solo si la Directiva de voz aplicada a la llamada especifica un número de teléfono de correo de voz que es único y no incluye una extensión mero.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware y software para la resistencia a sitios de sucursal

Los requisitos de hardware y software varían según la solución de resistencia.

#### <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para las sucursales con disvivientes

El hardware y el software necesarios están incorporados en el equipo con la sucursal de supervivencia. Sin embargo, también recomendamos que cada sitio de la sucursal implemente un servidor DHCP para obtener las direcciones IP de los clientes; de lo contrario, cuando la concesión DHCP expira, los clientes no tendrán conectividad IP.

Si los servidores DNS empresariales solo se encuentran en sitios centrales, los usuarios del sitio de la sucursal no podrán conectarse a ellos durante una interrupción de WAN y, por lo tanto, no se podrá realizar la detección de servidores de Skype empresarial que use el registro de recursos SRV (SRV) de DNS (SRV). Para asegurar el redireccionamiento de la solicitud durante una interrupción de WAN, los registros DNS deben almacenarse en caché en el sitio de la sucursal. Si el enrutador de bifurcación lo admite, active el almacenamiento en caché de DNS. O bien, puede implementar un servidor DNS en la sucursal. Puede ser un servidor independiente o una versión de la aplicación de la rama superviviente que admita capacidades DNS. Para obtener más información, póngase en contacto con el proveedor de su equipo de sucursales.

> [!NOTE]
> No es necesario tener un controlador de dominio en un sitio de sucursal. El dispositivo de sucursal con supervivencia autentica los clientes mediante un certificado especial que envía al cliente en respuesta a la solicitud de certificado del cliente cuando inicia sesión.

Los clientes de Skype empresarial pueden descubrir el servidor de Skype empresarial mediante la opción de DHCP 120 (opción de registrador de SIP). Puede configurarse de dos maneras:

- Configure el servidor DHCP en el sitio de la sucursal para responder a las consultas de DHCP 120, que devolverán el FQDN del registrador en la sucursal superviviente o en el servidor de sucursal superviviente.

- Active la opción DHCP de Skype empresarial Server. Cuando esta opción está activada, el registrador de Skype empresarial Server responde a la opción DHCP 120 consultas. Tenga en cuenta que el registrador no responde a ninguna consulta DHCP distinta de las opciones de DHCP 120.

Además, en el caso de sitios de sucursales más grandes que tienen varias subredes, los agentes de retransmisión DHCP deben estar habilitados para reenviar las consultas de la opción DHCP 120 al servidor DHCP (configuración 1) o al registrador (configuración 2).

Por último, los usuarios de sitios de sucursal deben estar configurados para telefonía IP empresarial y aprovisionar un extremo de comunicaciones unificado adecuado.

#### <a name="requirements-for-survivable-branch-servers"></a>Requisitos para servidores de sucursal revivientes

Los requisitos para servidores de sucursal revivientes son los mismos que los de un servidor front-end. Para más información, vea [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisitos para las implementaciones de sitios de sucursales de Skype empresarial de escala completa

Para obtener más información, consulte [requisitos del servidor de Skype empresarial server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) en la documentación de planificación.

### <a name="example-configuring-a-failover-route"></a>Ejemplo: configurar una ruta de conmutación por error

 En el ejemplo siguiente se muestra cómo un administrador puede definir una ruta de conmutación por error para su uso si la GW1 de Dallas está desactivada para su mantenimiento o no está disponible. En las siguientes tablas se muestra el cambio de configuración requerido.

**Tabla 1. Directiva de usuario**

|**Directiva de usuario**|**Uso del teléfono**|
|:-----|:-----|
|Directiva de llamadas predeterminada  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Directiva local de Redmond  <br/> |RedmondLocal  <br/> |
|Política de llamadas de Dallas  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tabla 2. Redirige**


| **Nombre de la ruta**             | **Patrón de números** | **Uso del teléfono**         | **Tronco**                                 | **Puerta**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Camino local de Redmond  <br/> | ^\+1 (425           | 206                     | 253) (\d{7}) $  <br/>                       | Local  <br/> RedmondLocal  <br/>                |
| Ruta local de Dallas  <br/>  | ^\+1 (972           | 214                     | 469) (\d{7}) $  <br/>                       | Local  <br/>                                    |
| Ruta universal  <br/>     | ^\+? (\d\*) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Rojo: GW1  <br/> Rojo: GW2  <br/> Dallas-GW1  <br/> |
| Ruta de usuarios de Dallas  <br/>  | ^\+? (\d\*) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

En la tabla 1, se agrega un uso de teléfono de GlobalPSTNHopoff después del uso del teléfono DallasUsers en la política de llamadas de Dallas. Esto permite que las llamadas con la Directiva de llamadas de Dallas usen rutas configuradas para el uso del teléfono GlobalPSTNHopoff si una ruta para el uso del teléfono DallasUsers no está disponible.


