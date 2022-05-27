---
title: Planear la resistencia Telefonía IP empresarial en Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Obtenga información sobre cómo admitir la resistencia de voz en Skype Empresarial Server Telefonía IP empresarial, tanto en sitios centrales como en sitios de sucursal. Las opciones del sitio de rama incluyen la implementación de aplicaciones de rama con funciones de supervivencia o servidores de sucursal con funciones de supervivencia.
ms.openlocfilehash: 493f599f7fbec2a67efaaf59851fd7c2f3b2d144
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675482"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Planear la resistencia Telefonía IP empresarial en Skype Empresarial Server

Obtenga información sobre cómo admitir la resistencia de voz en Skype Empresarial Server Telefonía IP empresarial, tanto en sitios centrales como en sitios de sucursal. Las opciones del sitio de rama incluyen la implementación de aplicaciones de rama con funciones de supervivencia o servidores de sucursal con funciones de supervivencia.

La resistencia de voz hace referencia a la capacidad de los usuarios de seguir realizando y recibiendo llamadas si un sitio central que hospeda Skype Empresarial Server deja de estar disponible, ya sea a través de un error de red de área extensa (WAN) u otra causa. Si se produce un error en un sitio central, el servicio de Telefonía IP empresarial debe continuar sin interrupciones a través de la conmutación por error sin problemas al sitio de copia de seguridad. En caso de error de red WAN, las llamadas de sitios de sucursal deben redirigirse a una puerta de enlace RTC local. En esta sección se analiza la planeación de la resistencia de voz en el caso de error de sitio central o de red WAN.

## <a name="central-site-resiliency"></a>Resistencia del sitio central

Cada día con mayor frecuencia, las empresas tienen varios sitios distribuidos por todo el mundo. Mantener los servicios de emergencia, el acceso al departamento de soporte técnico y la capacidad de realizar tareas empresariales críticas cuando un sitio central está fuera de servicio es esencial para cualquier solución de resistencia Telefonía IP empresarial. Cuando un sitio central no está disponible, es necesario que se cumplan las siguientes condiciones:

- Debe proporcionar conmutación por error de voz.

- Los usuarios que normalmente se registran en el grupo de servidores front-end del sitio central deben poder registrarse con un grupo de servidores front-end alternativo. Esto se puede hacer mediante la creación de varios registros SRV de DNS, cada uno de los cuales se resuelve en un grupo de directores o un grupo de servidores front-end en cada uno de los sitios centrales. Puede ajustar la prioridad y los pesos de los registros SRV para que los usuarios a los que atiende ese sitio central obtengan el director y el grupo de servidores front-end correspondientes por delante de los de otros registros SRV.

- Las llamadas realizadas a usuarios o desde usuarios ubicados en otros sitios se deben enrutar a través de la RTC.

En este tema se describe la solución recomendada para garantizar la resistencia de voz del sitio central.

### <a name="architecture-and-topology"></a>Arquitectura y topología

La planeación de la resistencia de voz en un sitio central requiere una comprensión básica del rol central que desempeña el registrador de Skype Empresarial Server al habilitar la conmutación por error de voz. El registrador de Skype Empresarial Server es un servicio que permite el registro y la autenticación del cliente y proporciona servicios de enrutamiento. Se ejecuta en todos Standard Edition servidor, servidor front-end, director o dispositivo de sucursal con funciones de supervivencia. Un grupo de registradores consta de servicios de registrador que se ejecutan en el grupo front-end y residen en el mismo sitio. Un cliente de Skype Empresarial detecta el grupo de servidores front-end mediante el siguiente mecanismo de detección:

1. Registro DNS SRV

2. Servicio web de detección automática

3. Opción 120 de DHCP

Una vez que el cliente Skype Empresarial se conecta al grupo de servidores front-end, el equilibrador de carga lo dirige a uno de los servidores front-end del grupo. Ese servidor front-end, a su vez, redirige el cliente a un registrador preferido en el grupo.

Cada usuario habilitado para Telefonía IP empresarial se asigna a un grupo de registradores determinado, que se convierte en el grupo de registradores principal de ese usuario. En un sitio determinado, cientos o miles de usuarios normalmente comparten un único grupo de registrador principal. Para tener en cuenta el consumo de los recursos del sitio central a través de los usuarios de cualquier sitio de sucursal que confíen en el sitio central para fines de presencia, conferencia o conmutación por error, se aconseja considerar cada usuario de sitio de sucursal teniendo en cuenta que el usuario es un usuario registrado en el sitio central. Actualmente no hay límites en el número de usuarios del sitio de sucursal, incluidos los usuarios registrados con un dispositivo de sucursal con funciones de supervivencia.

Para garantizar la resistencia de voz en caso de error en el sitio central, el grupo de registrador principal debe tener un solo grupo de registrador de reserva designado ubicado en otro sitio. La copia de seguridad se puede configurar mediante la configuración de resistencia del Generador de topologías. Dando por supuesto que existe un vínculo WAN resistente entre los dos sitios, los usuarios cuyo grupo de registrador primario ya no está disponible se direccionan automáticamente al grupo de registrador de reserva.

En los pasos siguientes se describe el proceso de detección y registro de clientes:

1. Un cliente detecta Skype Empresarial Server a través de registros SRV de DNS. En Skype Empresarial Server, los registros SRV de DNS se pueden configurar para devolver más de un FQDN a la consulta SRV de DNS. Por ejemplo, si la empresa Contoso tiene tres sitios centrales (Norteamérica, Europa y Asia-Pacífico) y un grupo de directores en cada sitio central, los registros del servidor DNS pueden orientarse a los FQDN de los grupos de directores de cada una de las tres ubicaciones. Siempre que el grupo de directores de una de las ubicaciones esté disponible, el cliente puede conectarse al primer salto Skype Empresarial Server.

    > [!NOTE]
    > El uso de un grupo de directores es opcional. En su lugar, se puede usar un grupo de servidores front-end.

2. El grupo director informa al cliente de Skype Empresarial sobre el grupo de registradores principal del usuario y el grupo de registradores de copia de seguridad.

3. El cliente Skype Empresarial intenta conectarse primero al grupo de registradores principal del usuario. Si el grupo de registrador principal está disponible, el registrador acepta el registro. Si el grupo de registradores principal no está disponible, el cliente de Skype Empresarial intenta conectarse al grupo de registradores de copia de seguridad. Si el grupo de registradores de copia de seguridad está disponible y ha determinado que el grupo de registradores principal del usuario no está disponible (al detectar una falta de latido para un intervalo de conmutación por error especificado), el grupo de registradores de copia de seguridad acepta el registro del usuario. Una vez que el registrador de copia de seguridad detecta que el registrador principal está disponible de nuevo, el grupo de registradores de copia de seguridad redirigirá los clientes de conmutación por error a su grupo principal.

### <a name="requirements-and-recommendations"></a>Requisitos y recomendaciones

A continuación se muestran los requisitos y las recomendaciones para implementar una resistencia de voz de sitio central adecuados para la mayoría de las organizaciones:

- Los sitios en los que se encuentren los grupos de registrador principal y de reserva deberán estar conectados mediante un vínculo WAN resistente.

- Cada sitio central debe contener un grupo de registrador formado por uno o varios registradores.

- Cada grupo de registradores debe tener equilibrio de carga mediante el equilibrio de carga dns, el equilibrio de carga de hardware o ambos. Para obtener información detallada sobre cómo planear la configuración del equilibrio de carga, consulte Requisitos de equilibrio de carga [para Skype Empresarial](../../plan-your-deployment/network-requirements/load-balancing.md).

- Cada usuario debe asignarse a un grupo de registradores principal mediante el cmdlet **set-CsUser** del Shell de administración de Skype Empresarial Server o el Skype Empresarial Server Panel de control.

- El grupo de registrador principal debe tener un único grupo de registrador de reserva en otro sitio central.

- El grupo de registrador principal se debe configurar para realizar la conmutación por error para el grupo de registrador de reserva. De forma predeterminada, el registrador principal se configura para realizar la conmutación por error para el grupo de registrador de reserva después de un intervalo de 300 segundos. Puede cambiar este intervalo mediante el Generador de topologías de Skype Empresarial Server.

- Configurar una ruta de conmutación por error. Al configurar la ruta, especifique una puerta de enlace que se encuentre en un sitio diferente al de la puerta de enlace especificada en la ruta principal.

- Si el sitio central contenía el servidor de administración principal y es probable que el sitio esté inactivo durante un período prolongado, deberá reinstalar las herramientas de administración en el sitio de copia de seguridad; De lo contrario, no podrá cambiar ninguna configuración de administración.

### <a name="dependencies"></a>Dependencias

Skype Empresarial Server depende de los siguientes componentes de infraestructura y software para garantizar la resistencia de voz:

|**Componente** <br/> |**Funcional** <br/> |
|:-----|:-----|
|DNS  <br/> |Resolver registros de servidor y registros A para conectividad de servidor a servidor y de servidor a cliente  <br/> |
|Exchange y servicios Web Exchange (EWS)  <br/> |Almacenamiento de contactos; datos de calendario  <br/> |
|Mensajería unificada de Exchange y servicios Web Exchange  <br/> |Registros de llamadas, lista de correo de voz y correo de voz  <br/> |
|Opciones de DHCP 120  <br/> |Si el servidor DNS no está disponible, el cliente intentará usar Opción de DHCP 120 para descubrir el registrador. Para que esto funcione, se debe configurar un servidor DHCP o Skype Empresarial Server dhcp debe estar habilitado.  <br/> |

### <a name="survivable-voice-features"></a>Características de voz con funciones de supervivencia

Si ha implementado los requisitos y recomendaciones anteriores, el grupo de registrador de reserva ofrecerá las siguientes características de voz:

- Llamadas RTC realizadas

- Llamadas RTC entrantes, si el proveedor de servicios de telefonía ofrece la posibilidad de conmutar por error a un sitio secundario.

- Llamadas de empresa entre usuarios del mismo sitio y entre dos sitios diferentes

- Administración básica de llamadas, incluida la retención, recuperación y transferencia de llamadas.

- Mensajería instantánea entre dos participantes y uso compartido de audio y vídeo entre usuarios del mismo sitio

- Servicios de desvío de llamadas, llamadas simultáneas de extremos, delegación de llamadas y llamada de equipo, pero solo si están configuradas en el mismo sitio ambas partes para la delegación de llamadas, o todos los miembros del equipo.

- Los teléfonos y clientes existentes siguen funcionando.

- Registro de detalles de llamadas (CDR)

- Autenticación y autorización

En función de cómo estén configuradas, las características de voz que se indican a continuación pueden funcionar o no cuando un sitio central principal está fuera de servicio:

- Depósito y recuperación de correos de voz

    Si desea hacer que la mensajería unificada de Exchange esté disponible cuando el sitio central principal esté fuera de servicio, deberá realizar una de las acciones siguientes:

  - Cambiar los registros de servidor DNS para que los servidores de mensajería unificada de Exchange del sitio central apunten hacia los servidores de mensajería unificada de Exchange de reserva de otro sitio.

  - Configure el plan de marcado de mensajería unificada Exchange de cada usuario para incluir Exchange servidores de mensajería unificada en el sitio central y en el sitio de copia de seguridad, pero designe los servidores de mensajería unificada Exchange copia de seguridad como deshabilitados. Si el sitio principal deja de estar disponible, el administrador de Exchange debe marcar los servidores de mensajería unificada de Exchange en el sitio de copia de seguridad como habilitados.

    Si no es posible ninguna de las soluciones anteriores, Exchange mensajería unificada no estará disponible en caso de que el sitio central deje de estar disponible.

- Conferencias de todos los tipos

    Un usuario que ha experimentado una conmutación por error a un sitio de copia de seguridad se puede unir a una conferencia creada u hospedada por un organizador cuyo grupo esté disponible, pero no puede crear ni hospedar una conferencia en su propio grupo principal, que ya no está disponible. Del mismo modo, otros usuarios no pueden unirse a conferencias hospedadas en el grupo principal del usuario afectado.

Las características de voz que se indican a continuación no funcionan cuando un sitio central principal está fuera de servicio:

- Operador automático de conferencia

- Enrutamiento basado en DNS y presencia

- Actualización de la configuración del desvío de llamadas

- Servicio de grupo de respuesta y estacionamiento de llamadas

- Aprovisionamiento de nuevos teléfonos y clientes

- Búsqueda en la web de la libreta de direcciones

## <a name="branch-site-resiliency"></a>Resistencia del sitio de rama

Si desea proporcionar resistencia de sitio de rama, es decir, alta disponibilidad Telefonía IP empresarial servicio, tiene tres opciones para hacerlo:

- Aplicación de sucursal con funciones de supervivencia

- Servidor de sucursal con funciones de supervivencia

- Una implementación Skype Empresarial Server completa en el sitio de rama

Esta guía le ayudará a evaluar qué solución de resistencia es la más adecuada para su organización y, en función de la solución de resistencia, qué solución de conexión RTC usar. También le ayudará a preparar la implementación de la solución que elija describiendo requisitos previos y otras consideraciones referentes a la planeación.

### <a name="branch-site-resiliency-features"></a>Características de resistencia del sitio de sucursal

Si proporciona resistencia de sitio de rama, si se produce un error en la conexión WAN de un sitio de sucursal a un sitio central o si el sitio central no es accesible, las siguientes características de voz deben seguir estando disponibles:

- Llamadas de red telefónica conmutada (RTC) entrantes y realizadas.

- Llamadas de empresa entre usuarios del mismo sitio y entre dos sitios diferentes

- Administración básica de llamadas, incluida la retención, recuperación y transferencia de llamadas.

- Mensajería instantánea entre dos participantes

- Reenvío de llamadas, llamadas simultáneas de puntos de conexión, delegación de llamadas y servicios de llamada de equipo, pero solo si el delegado y el delegado (por ejemplo, un administrador y el administrador del administrador) o todos los miembros del equipo están configurados en el mismo sitio

- Registros de detalles de las llamadas (CDR)

- Conferencias de acceso telefónico local RTC con operador automático de conferencia

- Funcionalidades de correo de voz, si configura los valores de reenlazador de correo de voz.

- Autorización y autenticación de usuarios

Las siguientes características solo estarán disponibles si la solución de resistencia es una implementación de Skype Empresarial Server a escala completa en el sitio de rama:

- Conferencia A/V, web y MI

- Enrutamiento basado en presencia y No molestar (DND) (con el que se evita que las llamadas suenen en extensiones con DND activado)

- Actualización de la configuración del desvío de llamadas

- Aplicación de grupo de respuesta y aplicación de estacionamiento de llamadas

- Aprovisionamiento de nuevos teléfonos y clientes, pero solo si Servicios de dominio de Active Directory está presente en el sitio de sucursal.

- 9-1-1 mejorado (E9-1-1)

    Si se implementa E9-1-1 y el tronco SIP en el sitio central no está disponible porque el vínculo WAN está inactivo, el dispositivo de sucursal con funciones de supervivencia enrutará las llamadas E9-1-1 a la puerta de enlace de rama local. Para habilitar esta característica, las directivas de voz de los usuarios del sitio de sucursal deben enrutar las llamadas a la puerta de enlace local en caso de error de WAN.

> [!NOTE]
> SBA (sucursal con funciones de supervivencia) no es compatible con XMPP. Los usuarios hospedados en configuraciones de SBA no podrán enviar máquinas virtuales ni ver la presencia con contactos XMPP.

### <a name="branch-site-resiliency-solutions"></a>Soluciones de resistencia del sitio de sucursal

Las ventajas que una organización obtiene al disponer de resistencia en las sucursales son más que evidentes. En concreto, si pierde la conexión con el sitio central, los usuarios del sitio de sucursal seguirán teniendo Telefonía IP empresarial servicio y correo de voz (si configura las opciones de redireccionamiento del correo de voz). Sin embargo, una solución de resistencia probablemente no compense lo suficiente en sitios con menos de 25 usuarios.

Si decide proporcionar resistencia en las sucursales, tiene tres maneras de hacerlo. La siguiente tabla puede ayudarle a saber cuál es la mejor opción para su organización.

|**Si usted...**|**Se recomienda usar un...**|
|:-----|:-----|
|Hospeda entre 25 y 1000 usuarios en la sucursal y no compensa una implementación completa o no se dispone de asistencia administrativa local  <br/> |Aplicación de sucursal con funciones de supervivencia  <br/> El dispositivo de sucursal con funciones de supervivencia es un servidor de hoja estándar del sector con un registrador de Skype Empresarial Server y un servidor de mediación que se ejecuta en Windows Server 2008 R2. El dispositivo de sucursal con funciones de supervivencia también contiene una puerta de enlace de red telefónica conmutada (RTC). Los dispositivos de otros fabricantes calificados (desarrollados por socios de Microsoft en el programa de certificación/calificación de aplicación de sucursal con funciones de supervivencia [SBA]) ofrecen una conexión RTC ininterrumpida en caso de que se produzca un error de WAN, aunque este enfoque no proporciona presencia y conferencia resistentes, ya que ambas características dependen de los servidores front-end del sitio central.  <br/> Para obtener más información sobre los dispositivos de sucursal con funciones de supervivencia, consulte "Detalles del dispositivo de sucursal con funciones de supervivencia", más adelante en este tema.  <br/> **Nota:** Si decide usar también un tronco SIP con el dispositivo de sucursal con funciones de supervivencia, póngase en contacto con el proveedor del dispositivo de sucursal con funciones de supervivencia para obtener información sobre qué proveedor de servicios es el mejor para su organización. <br/> |
|Hospedar entre 1000 y 2000 usuarios en el sitio de la rama, carecer de una conexión WAN resistente y haber entrenado Skype Empresarial Server administradores disponibles  <br/> |Servidor de sucursal con funciones de supervivencia o dos aplicaciones de rama con funciones de supervivencia.  <br/> El servidor de sucursal con funciones de supervivencia es un servidor de Windows que cumple los requisitos de hardware especificados que tiene instalado Skype Empresarial Server software de registrador y servidor de mediación. Debe conectarse a una puerta de enlace RTC o a un tronco SIP hacia un proveedor de servicios telefónicos.  <br/> Para obtener más información sobre los servidores de sucursal con funciones de supervivencia, vea "Detalles del servidor de sucursal con funciones de supervivencia", más adelante en este tema.  <br/> |
|Si necesita características de presencia y conferencia, además de las características de voz para hasta 5000 usuarios, y ha entrenado Skype Empresarial Server administradores disponibles  <br/> |Realizar una implementación como un sitio central con un servidor Standard Edition en lugar de como una sucursal.  <br/> Una implementación de Skype Empresarial Server a escala completa proporciona una conexión RTC continua y presencia resistente y conferencias en caso de error de WAN.  <br/> |

#### <a name="resiliency-topologies"></a>Topologías de resistencia

La siguiente figura refleja las topologías recomendadas de resistencia en las sucursales.

**Opciones de resistencia de las sucursales**

![Opciones de resistencia de rama de voz.](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Detalles de la aplicación de sucursal con funciones de supervivencia

El Skype Empresarial Server aplicación de sucursal con funciones de supervivencia incluye los siguientes componentes:

- Un registrador para la autenticación y registro de usuarios y el enrutado de llamadas

- Un servidor de mediación para controlar la señalización entre el registrador y una puerta de enlace RTC

- Una puerta de enlace RTC para enrutar llamadas a la RTC a modo de transporte de reserva en caso de que se produzca una interrupción en la red WAN

- SQL Server Express para el almacenamiento local de los datos de usuario

El dispositivo de sucursal con funciones de supervivencia también incluye troncos RTC, puertos analógicos y un adaptador Ethernet.

Si la conexión WAN del sitio de sucursal a un sitio central deja de estar disponible, los usuarios de la rama interna seguirán registrándose en el registrador del dispositivo de sucursal con funciones de supervivencia y obtendrán un servicio de voz ininterrumpido mediante la conexión del dispositivo de sucursal con funciones de supervivencia a la RTC. En caso de que el vínculo WAN a una sucursal no esté disponible, los usuarios de sucursal que se conecten desde casa o desde otras ubicaciones remotas tendrán la posibilidad de registrarse con un servidor registrador ubicado en el sitio central. Estos usuarios disfrutarán de la funcionalidad de comunicaciones unificadas completa, con la única salvedad de que las llamadas entrantes a la sucursal se trasladarán al correo de voz. Cuando la conexión WAN vuelva, deberá restaurarse la funcionalidad completa para los usuarios de las sucursales. Ni la conmutación por error al dispositivo de sucursal con funciones de supervivencia ni la restauración del servicio requieren la presencia de un administrador de TI.

Skype Empresarial Server admite hasta dos aplicaciones de sucursal con funciones de supervivencia en un sitio de sucursal.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Descripción general de la implementación de la aplicación de sucursal con funciones de supervivencia

El dispositivo de sucursal con funciones de supervivencia está fabricado por fabricantes de equipos originales en asociación con Microsoft e implementado en su nombre por minoristas de valor añadido. Esta implementación debe producirse solo después de que se haya implementado Skype Empresarial Server en el sitio central, haya una conexión WAN al sitio de sucursal y los usuarios del sitio de sucursal estén habilitados para Telefonía IP empresarial.

Para obtener información detallada sobre estas fases, consulte [Deploying a Survivable Branch Appliance or Server](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-a-survivable-branch-appliance-or-server) en la documentación de implementación.

|**Fase**|**Pasos**|**Derechos de usuario**|
|:-----|:-----|:-----|
|Configuración de Servicios de dominio de Active Directory para el dispositivo de sucursal con funciones de supervivencia  <br/> |**En el sitio central:** <br/>  Cree una cuenta de usuario de dominio (o identidad empresarial) para el técnico que instalará y activará el dispositivo de sucursal con funciones de supervivencia en el sitio de la rama. <br/>  Cree una cuenta de equipo (con el nombre de dominio completo (FQDN) aplicable para el dispositivo de sucursal con funciones de supervivencia en Servicios de dominio de Active Directory. <br/>  En el Generador de topologías, cree y publique el dispositivo de sucursal con funciones de supervivencia. <br/> |La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians. El dispositivo de sucursal con funciones de supervivencia debe pertenecer al grupo RTCSBAUniversalServices, que se produce automáticamente cuando se usa el Generador de topologías.  <br/> |
|Instale y active el dispositivo de sucursal con funciones de supervivencia.  <br/> |**En la sucursal:** <br/>  Conectar el dispositivo de sucursal con funciones de supervivencia a un puerto Ethernet y un puerto RTC. <br/>  Inicie el dispositivo de sucursal con funciones de supervivencia. <br/>  Una el dispositivo de sucursal con funciones de supervivencia al dominio mediante la cuenta de usuario de dominio creada para el dispositivo de sucursal con funciones de supervivencia en el sitio central. Establezca el FQDN y la dirección IP de forma que coincidan con el FQDN creado en la cuenta del equipo. <br/>  Configure el dispositivo de sucursal con funciones de supervivencia mediante la interfaz de usuario oem. <br/>  Compruebe la conectividad RTC. <br/> |La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Detalles del servidor de sucursal con funciones de supervivencia

En el Generador de topologías, cree el sitio de rama, agregue el servidor de sucursal con funciones de supervivencia a ese sitio y, a continuación, ejecute el Asistente para la implementación de Skype Empresarial Server en el equipo donde desea instalar el rol.

### <a name="branch-site-resiliency-requirements"></a>Requisitos de resistencia del sitio de sucursal

Este tema le ayudará a preparar a los usuarios para la resistencia del sitio de sucursal y la supervivencia del correo de voz, y también especifica los requisitos de hardware y software pertinentes.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparación de usuarios de rama para la resistencia Branch-Site

Prepare a los usuarios para la resistencia del sitio de sucursal estableciendo su grupo de registradores como aplicación de sucursal con funciones de supervivencia (SBA) o servidor de sucursal con funciones de supervivencia.

#### <a name="registrar-assignments-for-branch-users"></a>Asignaciones de registrador para usuarios de rama

Independientemente de la solución de resistencia del sitio de sucursal que elija, deberá asignar un registrador principal a cada usuario. Los usuarios del sitio de sucursal siempre deben registrarse con el registrador en el sitio de sucursal, independientemente de si ese registrador reside en el dispositivo de sucursal con funciones de supervivencia, servidor de sucursal con funciones de supervivencia o Skype Empresarial Server estándar o Enterprise Edition servidor independiente. Se requiere un registro de recursos del servicio de sistema de nombres de dominio (DNS) (SRV) para que un cliente pueda detectar su grupo de registradores. Si el dispositivo de sucursal con funciones de supervivencia deja de estar disponible, así es como los clientes del sitio de sucursal detectarán automáticamente el registrador de copia de seguridad.

Si un sitio de sucursal no tiene un servidor DNS, hay dos maneras alternativas de configurar la detección del dispositivo de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia:

- Configure la opción DHCP 120 en el servidor del protocolo de configuración dinámica de host (DHCP) del sitio de sucursal para que apunte al nombre de dominio completo (FQDN) del dispositivo de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia.

- Configure el dispositivo de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia para responder a las consultas DHCP 120.

#### <a name="voice-routing-for-branch-users"></a>Enrutamiento de voz para usuarios de rama

Se recomienda crear una directiva independiente de protocolo de voz a través de Internet (VoIP) de nivel de usuario para los usuarios de un sitio de sucursal. Esta directiva debe incluir una ruta principal que use el dispositivo de sucursal con funciones de supervivencia o la puerta de enlace del servidor de sucursal, y una o varias rutas de copia de seguridad que usen un tronco con una puerta de enlace de red telefónica conmutada (RTC) pública en el sitio central. Si la ruta principal no está disponible, en su lugar se usa la ruta de copia de seguridad que usa una o varias puertas de enlace de sitio central. De este modo, independientemente de dónde esté registrado un usuario (en el registrador del sitio de sucursal o en el grupo de registradores de copia de seguridad del sitio central), la directiva VoIP del usuario siempre está en vigor. Se trata de una consideración importante para escenarios de conmutación por error. Por ejemplo, si necesita cambiar el nombre del dispositivo de sucursal con funciones de supervivencia o volver a configurar el dispositivo de sucursal con funciones de supervivencia para conectarse a un grupo de registradores de copia de seguridad en el sitio central, debe mover los usuarios del sitio de sucursal al sitio central mientras dure. (Para obtener más información sobre el cambio de nombre o la reconfiguración de un dispositivo de rama con funciones de supervivencia, consulte [Apéndice B: Administración de un dispositivo de sucursal con funciones de supervivencia](/previous-versions/office/lync-server-2013/lync-server-2013-appendix-b-managing-a-survivable-branch-appliance) en la documentación de implementación). Si esos usuarios no tienen directivas VoIP de nivel de usuario ni planes de marcado de nivel de usuario, cuando los usuarios se mueven a otro sitio, las directivas voIP de nivel de sitio y los planes de marcado de nivel de sitio del sitio central se aplican a los usuarios de forma predeterminada, en lugar de las directivas de VoIP de nivel de sitio de sucursal y los planes de marcado, . En este escenario, a menos que las directivas voIP de nivel de sitio y los planes de marcado de nivel de sitio usados por el grupo de registradores de copia de seguridad también se puedan aplicar a los usuarios del sitio de sucursal, se producirá un error en sus llamadas. Por ejemplo, si los usuarios de un sitio de sucursal ubicado en Japón se mueven a un sitio central en Redmond, es poco probable que un plan de marcado con reglas de normalización que anteponga +1425 a todas las llamadas de 7 dígitos convierta correctamente las llamadas para esos usuarios.

> [!IMPORTANT]
> Al crear una ruta de copia de seguridad de sucursal, se recomienda agregar dos registros de uso de teléfono RTC a la directiva de usuario de sucursal y asignar rutas independientes a cada una. La primera ruta, o principal, dirigiría las llamadas a la puerta de enlace asociada con el dispositivo de sucursal con funciones de supervivencia (SBA) o el servidor de sucursal; la segunda ruta, o copia de seguridad, dirigiría las llamadas a la puerta de enlace en el sitio central. Al dirigir llamadas, el SBA o el servidor de sucursal intentarán todas las rutas asignadas al primer registro de uso de RTC antes de intentar el segundo registro de uso.

Para ayudar a garantizar que las llamadas entrantes a los usuarios del sitio de sucursal llegarán a esos usuarios cuando la puerta de enlace de sucursal o el componente de Windows del sitio del dispositivo de sucursal con funciones de supervivencia no estén disponibles (lo que sucedería, por ejemplo, si el dispositivo de sucursal con funciones de supervivencia o la puerta de enlace de rama no estuvieran disponibles para el mantenimiento), cree una ruta de conmutación por error en la puerta de enlace (o trabaje con el proveedor de marcado de entrada directa (DID) para redirigir las llamadas entrantes al grupo de registradores de copia de seguridad en el sitio central. Desde allí, las llamadas se enrutarán a través del vínculo WAN a los usuarios de la rama. Asegúrese de que la ruta traduce los números para cumplir con la puerta de enlace RTC u otros formatos de número de teléfono aceptados del mismo nivel del tronco. Para obtener más información sobre cómo crear una ruta de conmutación por error, consulte [Configuración de una ruta de conmutación por error](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-a-failover-route). Cree también planes de marcado de nivel de servicio para el tronco asociado a la puerta de enlace en el sitio de sucursal para normalizar las llamadas entrantes. Si tiene dos aplicaciones de rama con funciones de supervivencia en un sitio de sucursal, puede crear un plan de marcado de nivel de sitio para ambos, a menos que sea necesario un plan de nivel de servicio independiente para cada uno.

> [!NOTE]
> Para tener en cuenta el consumo de recursos de sitio central por parte de los usuarios del sitio de sucursal que dependen del sitio central para la presencia, conferencia o conmutación por error, se recomienda considerar cada usuario del sitio de sucursal como si el usuario estuviera registrado en el sitio central. Actualmente no hay límites en el número de usuarios del sitio de sucursal, incluidos los usuarios registrados con un dispositivo de sucursal con funciones de supervivencia.

También se recomienda crear un plan de marcado de nivel de usuario y una directiva de voz y, a continuación, asignarlo a los usuarios del sitio de sucursal. Para obtener más información, consulte [Creación o modificación de un plan de marcado en Skype Empresarial Server](../../deploy/deploy-enterprise-voice/dial-plans.md) y [Creación de la directiva de enrutamiento de VoIP para usuarios de rama](/previous-versions/office/lync-server-2013/lync-server-2013-create-the-voip-routing-policy-for-branch-users) en la documentación de implementación.

#### <a name="routing-extension-numbers"></a>Números de extensión de enrutamiento

Al preparar planes de marcado y directivas de voz para los usuarios del sitio de sucursal, asegúrese de incluir reglas de normalización y reglas de traducción que coincidan con las cadenas y el formato de número que se usan en el atributo msRTCSIP-line (o URI de línea), de modo que Skype Empresarial llamadas habilitadas entre los usuarios del sitio de sucursal y los usuarios del sitio central se enrutarán correctamente, especialmente cuando las llamadas se deben redirigir a través de la RTC porque el vínculo WAN no está disponible. Además, hay consideraciones especiales para los números marcados que incluyen números de extensión, en lugar de solo números de teléfono.

Las reglas de normalización y las reglas de traducción que coinciden con los URI de línea que contienen un número de extensión, ya sea exclusivamente o además de un número de teléfono E.164 completo, tienen requisitos adicionales. En esta sección se describen varios escenarios de ejemplo para enrutar llamadas a uri de línea con un número de extensión.

Si su organización no tiene números de teléfono de Direct Inward Dial (DID) configurados para usuarios individuales y el URI de línea de cada usuario está configurado con solo un número de extensión, los usuarios internos pueden llamarse entre sí marcando solo un número de extensión. Sin embargo, debe configurar reglas de normalización que se pueden aplicar a las llamadas de un usuario de sitio de sucursal a un usuario de sitio central, que coincidan con los números de extensión.

En un escenario en el que el vínculo WAN entre un sitio de sucursal y un sitio central está disponible, las llamadas de los usuarios del sitio de sucursal a los usuarios del sitio central no requieren que la regla de normalización coincidente traduzca el número porque la llamada no se enruta a través de la RTC. Por ejemplo:

|**Nombre de regla**|**Descripción**|**Patrón de número**|**Conversión**|**Ejemplo**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |No traduce números de 5 dígitos  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 no está traducido  <br/> |

También debe dar cabida a números de extensión para escenarios específicos, como cuando el vínculo WAN entre un sitio de sucursal y un sitio central no está disponible y una llamada desde un sitio de rama debe enrutarse a través de la RTC. Durante una interrupción de WAN, si un usuario de sitio de sucursal llama a un usuario del sitio central solo marcando la extensión del usuario del sitio central, debe tener una regla de traducción saliente que agregue el número de teléfono completo del usuario del sitio central. Si el URI de línea de un usuario contiene el número de teléfono completo de la organización y el número de extensión único del usuario en lugar de un número de teléfono completo que sea único para el usuario, debe tener una regla de traducción de salida que agregue el número de teléfono completo de su organización en su lugar. Por ejemplo:

|**Descripción**|**Patrón coincidente**|**Conversión**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Traduce números de 5 dígitos al número de teléfono y la extensión de un usuario  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 se traduce a +14255550123;ext=10001  <br/> |
|Traduce números de 5 dígitos al número de teléfono de la organización y a la extensión de un usuario  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 se traduce a +14255550100;ext=10001  <br/> |

En este escenario, si el mismo nivel de tronco que controla la redireccionamiento a la RTC no admite números de extensión, la regla de traducción de salida también debe quitar el número de extensión. Por ejemplo:

|**Descripción**|**Patrón coincidente**|**Conversión**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Quita la extensión de los números de teléfono con extensiones  <br/> |^\+(\d\*); ext=(\d\*)$  <br/> |+$1  <br/> |+14255550123;ext=10001 se traduce en +14255550123  <br/> |

Independientemente de si hay un vínculo WAN disponible, si su organización no tiene números DID configurados para usuarios individuales y el URI de línea de un usuario contiene el número de teléfono de la organización y el número de extensión único del usuario, debe configurar el URI de línea de número de teléfono de la organización con un número accesible para el mismo nivel de tronco o la puerta de enlace RTC en el sitio de sucursal. También debe configurar el URI de línea de número de teléfono de su organización para incluir su propia extensión única para que las llamadas se enruten a ese número.

#### <a name="preparing-for-voice-mail-survivability"></a>Preparación para la supervivencia del correo de voz

Exchange mensajería unificada (UM) normalmente solo se instala en un sitio central y no en sitios de sucursal. Un autor de la llamada debe poder dejar un mensaje de correo de voz, incluso si el vínculo WAN entre el sitio de sucursal y el sitio central no está disponible. Como resultado, la configuración del URI de línea para el número de teléfono de operador automático de mensajería unificada Exchange que proporciona correo de voz para los usuarios del sitio de sucursal requiere consideraciones especiales, además de la directiva de voz, el plan de marcado y las reglas de normalización aplicables a ese número de correo de voz.

Los dispositivos de rama con funciones de supervivencia (SBA) y los servidores de sucursal con funciones de supervivencia proporcionan supervivencia de correo de voz a los usuarios de la rama durante una interrupción de WAN. En concreto, si usa un dispositivo de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia y la WAN deja de estar disponible, el SBA o el servidor de sucursal con funciones de supervivencia redirige las llamadas sin respuesta a través de la RTC para Exchange mensajería unificada en el sitio central. Con un SBA o un servidor de sucursal con funciones de supervivencia, los usuarios también pueden recuperar mensajes de correo de voz a través de la RTC durante una interrupción de WAN. Por último, durante una interrupción de WAN, el dispositivo de sucursal con funciones de supervivencia o servidor de sucursal con funciones de supervivencia pone en cola las notificaciones de llamada perdidas y, a continuación, las carga en el servidor de mensajería unificada Exchange cuando se restaura la WAN. Para ayudar a garantizar que la reenrute del correo de voz sea resistente, asegúrese de agregar una entrada para el FQDN del grupo de sitios centrales y una entrada para el FQDN del servidor perimetral al archivo hosts en el servidor de sucursal con funciones de supervivencia. De lo contrario, la resolución DNS puede agotar el tiempo de espera si no tiene un servidor DNS en el sitio de sucursal.

Se recomiendan las siguientes configuraciones para la supervivencia del correo de voz para los usuarios del sitio de sucursal:

- Un administrador de Microsoft Exchange debe configurar Exchange operador automático de mensajería unificada (AA) para aceptar solo mensajes. Esta configuración deshabilita todas las demás funciones genéricas, como la transferencia a un usuario o la transferencia a un operador, y limita el AA a aceptar solo mensajes. Como alternativa, el administrador de Exchange puede usar un AA genérico o un AA personalizado para enrutar la llamada a un operador.

- El administrador de Skype Empresarial Server debe tomar el número de teléfono de AA y usar ese número de teléfono como número de **operador automático de mensajería unificada de intercambio** en la configuración de redireccionamiento del correo de voz para el servidor de sucursal o el dispositivo de sucursal con funciones de supervivencia.

- El administrador de Skype Empresarial Server debe obtener el número de teléfono de acceso de suscriptor de mensajería unificada Exchange y usar ese número como número de **acceso de suscriptor** en la configuración de redireccionamiento del correo de voz para el dispositivo de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.

- El administrador de Skype Empresarial Server debe configurar Exchange mensajería unificada para que solo un plan de marcado esté asociado a todos los usuarios de sucursal que necesiten acceso al correo de voz durante una interrupción de WAN.

- Cuando el vínculo WAN no está disponible, las llamadas a los usuarios del sitio de sucursal se pueden enrutar al buzón de voz Exchange mensajería unificada (UM) del usuario, pero solo si la directiva de voz aplicada a la llamada especifica un número de teléfono de correo de voz que es único y no incluye un número de extensión.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware y software para la resistencia Branch-Site

Los requisitos de hardware y software varían en función de la solución de resistencia.

#### <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para aplicaciones de rama con funciones de supervivencia

El hardware y el software necesarios están integrados en el dispositivo de sucursal con funciones de supervivencia. Sin embargo, también se recomienda que cada sitio de rama implemente un servidor DHCP para obtener direcciones IP de cliente; De lo contrario, cuando expire la concesión DHCP, los clientes no tendrán conectividad IP.

Si los servidores DNS empresariales solo se encuentran en sitios centrales, los usuarios del sitio de sucursal no podrán conectarse a ellos durante una interrupción de WAN y, por lo tanto, se producirá un error en la detección de Skype Empresarial Server que usa el registro de recursos SRV de DNS (servicio (SRV). Para garantizar la reactivación de mensajes durante una interrupción de WAN, los registros DNS deben almacenarse en caché en el sitio de la rama. Si el enrutador de rama lo admite, active el almacenamiento en caché de DNS. O bien, puede implementar un servidor DNS en la rama. Puede ser un servidor independiente o una versión del dispositivo de sucursal con funciones de supervivencia que admita funcionalidades DNS. Para obtener más información, póngase en contacto con el proveedor de aplicación de sucursal con funciones de supervivencia.

> [!NOTE]
> No es necesario tener un controlador de dominio en un sitio de sucursal. El dispositivo de sucursal con funciones de supervivencia autentica a los clientes mediante un certificado especial que envía al cliente en respuesta a la solicitud de certificado del cliente cuando inicia sesión.

Skype Empresarial clientes pueden detectar el Skype Empresarial Server mediante la opción DHCP 120 (opción de registrador SIP). Esto se puede configurar de dos maneras:

- Configure el servidor DHCP en el sitio de rama para responder a las consultas DHCP 120, que devuelven el FQDN del registrador en el dispositivo de sucursal con funciones de supervivencia o en el servidor de sucursal con funciones de supervivencia.

- Active Skype Empresarial Server DHCP. Cuando se activa, el registrador de Skype Empresarial Server responde a las consultas de la opción DHCP 120. Tenga en cuenta que el registrador no responde a ninguna consulta DHCP distinta de las opciones DHCP 120.

Además, para los sitios de rama más grandes que tienen varias subredes, los agentes de retransmisión DHCP deben estar habilitados para reenviar consultas de la opción 120 DHCP al servidor DHCP (configuración 1) o al registrador (configuración 2).

Por último, los usuarios del sitio de sucursal deben configurarse para Telefonía IP empresarial y aprovisionarse con un punto de conexión de comunicaciones unificado adecuado.

#### <a name="requirements-for-survivable-branch-servers"></a>Requisitos para servidores de sucursal con funciones de supervivencia

Los requisitos de servidores de sucursal con funciones de supervivencia son los mismos que los de un servidor front-end. Para obtener más información, consulte [Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisitos para implementaciones de Full-Scale Skype Empresarial Server Branch-Site

Para obtener más información, consulte [Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) en la documentación de planeamiento.

### <a name="example-configuring-a-failover-route"></a>Ejemplo: configuración de una ruta de conmutación por error

 En el siguiente ejemplo se muestra cómo puede un administrador definir una ruta de conmutación por error para usarla en caso de que se desconecte Dallas-GW1 por motivos de mantenimiento o no esté disponible. En las tablas siguientes se muestra el cambio de configuración necesario.

**Tabla 1. Directiva de usuario**

|**Directiva de sitio**|**Uso de teléfono**|
|:-----|:-----|
|Directiva de llamada predeterminada  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Directiva local de Redmond  <br/> |RedmondLocal  <br/> |
|Directiva de llamada de Dallas  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tabla 2. Rutas**


| **Nombre de ruta**             | **Patrón de número** | **Uso de teléfono**         | **Baúl**                                 | **Puerta de enlace**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Ruta local de Redmond  <br/> | ^\+1(425           | 206                     | 253)(\d{7})$  <br/>                       | Local  <br/> RedmondLocal  <br/>                |
| Ruta local de Dallas  <br/>  | ^\+1(972           | 214                     | 469)(\d{7})$  <br/>                       | Local  <br/>                                    |
| Ruta universal  <br/>     | ^\+? (\d\*) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Ruta de usuarios de Dallas  <br/>  | ^\+? (\d\*) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

En la Tabla 1, se agrega el uso de teléfono GlobalPSTNHopoff después del uso de teléfono DallasUsers en la directiva de llamada de Dallas. Esto permite que las llamadas con la directiva de llamada de Dallas usen las rutas configuradas para el uso de teléfono GlobalPSTNHopoff en caso de que una ruta para el uso telefónico DallasUsers no esté disponible.