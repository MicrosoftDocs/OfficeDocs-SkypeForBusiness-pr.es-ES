---
title: Planear la Telefonía IP empresarial resistencia en Skype Empresarial Server
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
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Obtenga información sobre cómo admitir la resistencia de voz en Skype Empresarial Server Telefonía IP empresarial, tanto en sitios centrales como en sitios de sucursal. Las opciones de sitio de sucursal incluyen la implementación de aplicaciones de sucursal con funciones de supervivencia o servidores de sucursal con funciones de supervivencia.
ms.openlocfilehash: ed5a410c30d1091a335e3c3ce3e4c7a5523f28399281f3a3f6f4686de08024a4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280045"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Planear la Telefonía IP empresarial resistencia en Skype Empresarial Server

Obtenga información sobre cómo admitir la resistencia de voz en Skype Empresarial Server Telefonía IP empresarial, tanto en sitios centrales como en sitios de sucursal. Las opciones de sitio de sucursal incluyen la implementación de aplicaciones de sucursal con funciones de supervivencia o servidores de sucursal con funciones de supervivencia.

La resistencia de voz hace referencia a la capacidad de los usuarios para seguir realizando y recibiendo llamadas si un sitio central que hospeda Skype Empresarial Server deja de estar disponible, ya sea a través de un error de red de área extensa (WAN) u otra causa. Si se produce un error en un sitio central, el servicio de Telefonía IP empresarial debe continuar sin interrupciones a través de la conmutación por error sin problemas al sitio de copia de seguridad. En caso de error de red WAN, las llamadas de sitios de sucursal deben redirigirse a una puerta de enlace RTC local. En esta sección se analiza la planeación de la resistencia de voz en el caso de error de sitio central o de red WAN.

## <a name="central-site-resiliency"></a>Resistencia del sitio central

Cada día con mayor frecuencia, las empresas tienen varios sitios distribuidos por todo el mundo. Mantener los servicios de emergencia, el acceso al servicio de asistencia y la capacidad de llevar a cabo tareas empresariales críticas cuando un sitio central está fuera de servicio es esencial para cualquier solución Telefonía IP empresarial resistencia. Cuando un sitio central no está disponible, es necesario que se cumplan las siguientes condiciones:

- Debe proporcionar conmutación por error de voz.

- Los usuarios que normalmente se registran con el grupo de servidores front-end en el sitio central deben poder registrarse con un grupo de servidores front-end alternativo. Para ello, cree varios registros SRV de DNS, cada uno de los cuales se resuelve en un grupo de directores o un grupo de servidores front-end en cada uno de los sitios centrales. Puede ajustar la prioridad y los pesos de los registros SRV para que los usuarios que son atendidos por ese sitio central obtengan el director y el grupo de servidores front-end correspondientes por delante de los de otros registros SRV.

- Las llamadas realizadas a usuarios o desde usuarios ubicados en otros sitios se deben enrutar a través de la RTC.

En este tema se describe la solución recomendada para garantizar la resistencia de voz del sitio central.

### <a name="architecture-and-topology"></a>Arquitectura y topología

La planeación de la resistencia de voz en un sitio central requiere una comprensión básica del rol central que desempeña el registrador de Skype Empresarial Server habilitar la conmutación por error de voz. El Skype Empresarial Server registrador es un servicio que habilita el registro y la autenticación del cliente y proporciona servicios de enrutamiento. Se ejecuta en todos los Standard Edition servidor, servidor front-end, director o aplicación de sucursal con funciones de supervivencia. Un grupo de registradores consta de servicios de registrador que se ejecutan en el grupo de servidores front-end y que residen en el mismo sitio. Un Skype Empresarial detecta el grupo de servidores front-end mediante el siguiente mecanismo de detección:

1. Registro DNS SRV

2. Servicio web de detección automática

3. Opción 120 de DHCP

Después de Skype Empresarial cliente se conecta al grupo de servidores front-end, el equilibrador de carga lo dirige a uno de los servidores front-end del grupo. Ese servidor front-end, a su vez, redirige el cliente a un registrador preferido del grupo.

Cada usuario habilitado para Telefonía IP empresarial se asigna a un grupo de registradores determinado, que se convierte en el grupo de registradores principal de ese usuario. En un sitio determinado, cientos o miles de usuarios normalmente comparten un único grupo de registrador principal. Para tener en cuenta el consumo de los recursos del sitio central a través de los usuarios de cualquier sitio de sucursal que confíen en el sitio central para fines de presencia, conferencia o conmutación por error, se aconseja considerar cada usuario de sitio de sucursal teniendo en cuenta que el usuario es un usuario registrado en el sitio central. Actualmente no hay límites en el número de usuarios del sitio de sucursal, incluidos los usuarios registrados con una aplicación de sucursal con funciones de supervivencia.

Para garantizar la resistencia de voz en caso de error en el sitio central, el grupo de registrador principal debe tener un solo grupo de registrador de reserva designado ubicado en otro sitio. La copia de seguridad se puede configurar mediante la configuración de resistencia del Generador de topologías. Dando por supuesto que existe un vínculo WAN resistente entre los dos sitios, los usuarios cuyo grupo de registrador primario ya no está disponible se direccionan automáticamente al grupo de registrador de reserva.

En los pasos siguientes se describe el proceso de detección y registro de clientes:

1. Un cliente detecta Skype Empresarial Server a través de registros SRV dns. En Skype Empresarial Server, los registros SRV dns se pueden configurar para devolver más de un FQDN a la consulta SRV de DNS. Por ejemplo, si la empresa Contoso tiene tres sitios centrales (Norteamérica, Europa y Asia-Pacífico) y un grupo de directores en cada sitio central, los registros del servidor DNS pueden orientarse a los FQDN de los grupos de directores de cada una de las tres ubicaciones. Siempre que el grupo de directores de una de las ubicaciones esté disponible, el cliente puede conectarse al primer salto Skype Empresarial Server.

    > [!NOTE]
    > El uso de un grupo de directores es opcional. En su lugar, se puede usar un grupo de servidores front-end.

2. El grupo de directores informa al Skype Empresarial sobre el grupo de registradores principal del usuario y el grupo de registradores de copia de seguridad.

3. El Skype Empresarial intenta conectarse primero al grupo de registradores principal del usuario. Si el grupo de registrador principal está disponible, el registrador acepta el registro. Si el grupo de registradores principal no está disponible, Skype Empresarial cliente intenta conectarse al grupo de registradores de copia de seguridad. Si el grupo de registradores de copia de seguridad está disponible y ha determinado que el grupo de registradores principal del usuario no está disponible (al detectar una falta de latido para un intervalo de conmutación por error especificado), el grupo de registradores de copia de seguridad acepta el registro del usuario. Después de que el registrador de copia de seguridad detecte que el registrador principal está disponible de nuevo, el grupo de registradores de copia de seguridad redirigirá los clientes de conmutación por error a su grupo de servidores principal.

### <a name="requirements-and-recommendations"></a>Requisitos y recomendaciones

A continuación se muestran los requisitos y las recomendaciones para implementar una resistencia de voz de sitio central adecuados para la mayoría de las organizaciones:

- Los sitios en los que se encuentren los grupos de registrador principal y de reserva deberán estar conectados mediante un vínculo WAN resistente.

- Cada sitio central debe contener un grupo de registrador formado por uno o varios registradores.

- Cada grupo de registradores debe tener equilibrio de carga mediante el equilibrio de carga DNS, el equilibrio de carga de hardware o ambos. Para obtener información detallada acerca de la planeación de la configuración de equilibrio de carga, vea [Requisitos de](../../plan-your-deployment/network-requirements/load-balancing.md)equilibrio de carga para Skype Empresarial .

- Cada usuario debe estar asignado a un grupo de registradores principal mediante el cmdlet **set-CsUser** del Shell de administración de Skype Empresarial Server o el panel de control Skype Empresarial Server administración.

- El grupo de registrador principal debe tener un único grupo de registrador de reserva en otro sitio central.

- El grupo de registrador principal se debe configurar para realizar la conmutación por error para el grupo de registrador de reserva. De forma predeterminada, el registrador principal se configura para realizar la conmutación por error para el grupo de registrador de reserva después de un intervalo de 300 segundos. Puede cambiar este intervalo mediante el generador Skype Empresarial Server topología.

- Configurar una ruta de conmutación por error. Al configurar la ruta, especifique una puerta de enlace que se encuentre en un sitio diferente al de la puerta de enlace especificada en la ruta principal.

- Si el sitio central contenía el servidor de administración principal y es probable que el sitio esté abajo durante un período prolongado, deberá reinstalar las herramientas de administración en el sitio de copia de seguridad; de lo contrario, no podrá cambiar ninguna configuración de administración.

### <a name="dependencies"></a>Dependencias

Skype Empresarial Server depende de los siguientes componentes de infraestructura y software para garantizar la resistencia de voz:

|**Componente** <br/> |**Funcional** <br/> |
|:-----|:-----|
|DNS  <br/> |Resolver registros de servidor y registros A para conectividad de servidor a servidor y de servidor a cliente  <br/> |
|Exchange y servicios Web Exchange (EWS)  <br/> |Almacenamiento de contactos; datos de calendario  <br/> |
|Mensajería unificada de Exchange y servicios Web Exchange  <br/> |Registros de llamadas, lista de correo de voz y correo de voz  <br/> |
|Opciones de DHCP 120  <br/> |Si el servidor DNS no está disponible, el cliente intentará usar Opción de DHCP 120 para descubrir el registrador. Para que esto funcione, debe configurarse un servidor DHCP o Skype Empresarial Server dhcp debe estar habilitado.  <br/> |

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

  - Configure el plan de marcado de mensajería unificada Exchange de cada usuario para incluir servidores de mensajería unificada Exchange tanto en el sitio central como en el sitio de copia de seguridad, pero designe la copia de seguridad Exchange servidores de mensajería unificada como deshabilitados. Si el sitio principal deja de estar disponible, el administrador de Exchange debe marcar el Exchange de mensajería unificada en el sitio de copia de seguridad como habilitado.

    Si ninguna de las soluciones anteriores es posible, Exchange la mensajería unificada no estará disponible en caso de que el sitio central no esté disponible.

- Conferencias de todos los tipos

    Un usuario que ha experimentado una conmutación por error a un sitio de copia de seguridad se puede unir a una conferencia creada u hospedada por un organizador cuyo grupo esté disponible, pero no puede crear ni hospedar una conferencia en su propio grupo principal, que ya no está disponible. Del mismo modo, otros usuarios no pueden unirse a conferencias hospedadas en el grupo de servidores principal del usuario afectado.

Las características de voz que se indican a continuación no funcionan cuando un sitio central principal está fuera de servicio:

- Operador automático de conferencia

- Enrutamiento basado en DNS y presencia

- Actualización de la configuración del desvío de llamadas

- Servicio de grupo de respuesta y estacionamiento de llamadas

- Aprovisionamiento de nuevos teléfonos y clientes

- Búsqueda en la web de la libreta de direcciones

## <a name="branch-site-resiliency"></a>Resistencia del sitio de sucursal

Si desea proporcionar resistencia a sitios de sucursal, es decir, servicio de alta disponibilidad Telefonía IP empresarial, tiene tres opciones para hacerlo:

- Aplicación de sucursal con funciones de supervivencia

- Servidor de sucursal con funciones de supervivencia

- Una implementación Skype Empresarial Server completa en el sitio de sucursal

Esta guía le ayudará a evaluar qué solución de resistencia es la más adecuada para su organización y, en función de la solución de resistencia, qué solución de conexión RTC usar. También le ayudará a preparar la implementación de la solución que elija describiendo requisitos previos y otras consideraciones referentes a la planeación.

### <a name="branch-site-resiliency-features"></a>Características de resistencia de sitios de sucursal

Si proporciona resistencia a sitios de sucursal, si se produce un error en la conexión WAN de un sitio de sucursal a un sitio central o si el sitio central no es accesible, las siguientes características de voz deben seguir estando disponibles:

- Llamadas de red telefónica conmutada (RTC) entrantes y realizadas.

- Llamadas de empresa entre usuarios del mismo sitio y entre dos sitios diferentes

- Administración básica de llamadas, incluida la retención, recuperación y transferencia de llamadas.

- Mensajería instantánea entre dos participantes

- Reenvío de llamadas, llamadas simultáneas de puntos de conexión, delegación de llamadas y servicios de llamadas de equipo, pero solo si el delegado y el delegado (por ejemplo, un administrador y el administrador del administrador) o todos los miembros del equipo están configurados en el mismo sitio

- Registros de detalles de las llamadas (CDR)

- Conferencias de acceso telefónico local RTC con operador automático de conferencia

- Capacidades de correo de voz, si configura la configuración de reobrución de correo de voz.

- Autorización y autenticación de usuarios

Las siguientes características solo estarán disponibles si la solución de resistencia es una implementación de Skype Empresarial Server a escala completa en el sitio de sucursal:

- Conferencia A/V, web y MI

- Enrutamiento basado en presencia y No molestar (DND) (con el que se evita que las llamadas suenen en extensiones con DND activado)

- Actualización de la configuración del desvío de llamadas

- Aplicación de grupo de respuesta y aplicación de estacionamiento de llamadas

- Aprovisionamiento de nuevos teléfonos y clientes, pero solo si los Servicios de dominio de Active Directory están presentes en el sitio de sucursal.

- 9-1-1 mejorado (E9-1-1)

    Si se implementa E9-1-1 y el tronco SIP del sitio central no está disponible porque el vínculo WAN está abajo, la aplicación de sucursal con funciones de supervivencia enruta las llamadas de E9-1-1 a la puerta de enlace de sucursal local. Para habilitar esta característica, las directivas de voz de los usuarios del sitio de sucursal deben enrutar las llamadas a la puerta de enlace local en caso de error de WAN.

> [!NOTE]
> SBA (sucursal con funciones de supervivencia) no es compatible con XMPP. Los usuarios que están en una configuración de SBA no podrán enviar IMs ni ver presencia con contactos XMPP.

### <a name="branch-site-resiliency-solutions"></a>Soluciones de resistencia de sitios de sucursal

Las ventajas que una organización obtiene al disponer de resistencia en las sucursales son más que evidentes. En concreto, si pierde la conexión con el sitio central, los usuarios del sitio de sucursal seguirán teniendo un servicio y un correo de voz Telefonía IP empresarial (si configura la configuración de reotración de correo de voz). Sin embargo, una solución de resistencia probablemente no compense lo suficiente en sitios con menos de 25 usuarios.

Si decide proporcionar resistencia en las sucursales, tiene tres maneras de hacerlo. La siguiente tabla puede ayudarle a saber cuál es la mejor opción para su organización.

|**Si quiere...**|**Se recomienda...**|
|:-----|:-----|
|Hospeda entre 25 y 1000 usuarios en la sucursal y no compensa una implementación completa o no se dispone de asistencia administrativa local  <br/> |Aplicación de sucursal con funciones de supervivencia  <br/> La aplicación de sucursal con funciones de supervivencia es un servidor blade estándar del sector con un servidor de mediación y registrador de Skype Empresarial Server que se ejecuta en Windows Server 2008 R2. La aplicación de sucursal con funciones de supervivencia también contiene una puerta de enlace de red telefónica conmutada (RTC). Los dispositivos de otros fabricantes calificados (desarrollados por socios de Microsoft en el programa de certificación/calificación de aplicación de sucursal con funciones de supervivencia [SBA]) ofrecen una conexión RTC ininterrumpida en caso de que se produzca un error de WAN, aunque este enfoque no proporciona presencia y conferencia resistentes, ya que ambas características dependen de los servidores front-end del sitio central.  <br/> Para obtener más información sobre los dispositivos de sucursal con funciones de supervivencia, consulte "Detalles de la aplicación de sucursal con funciones de supervivencia", más adelante en este tema.  <br/> **Nota:** Si decide usar también un tronco SIP con la aplicación de sucursal con funciones de supervivencia, póngase en contacto con su proveedor de aplicaciones de sucursal con funciones de supervivencia para obtener información sobre qué proveedor de servicios es mejor para su organización. <br/> |
|Hospedar entre 1000 y 2000 usuarios en el sitio de sucursal, carecer de una conexión WAN resistente y tener administradores de Skype Empresarial Server capacitados disponibles  <br/> |Servidor de sucursal con funciones de supervivencia o dos aplicaciones de sucursal con funciones de supervivencia.  <br/> El servidor de sucursal con funciones de supervivencia es un servidor de Windows que cumple los requisitos de hardware especificados que Skype Empresarial Server software de servidor de mediación y registrador instalado en él. Debe conectarse a una puerta de enlace RTC o a un tronco SIP hacia un proveedor de servicios telefónicos.  <br/> Para obtener más información acerca de los servidores de sucursal con funciones de supervivencia, vea "Detalles del servidor de sucursal con funciones de supervivencia", más adelante en este tema.  <br/> |
|Si necesita características de presencia y conferencia, además de características de voz para hasta 5000 usuarios, y tiene administradores de Skype Empresarial Server disponibles  <br/> |Realizar una implementación como un sitio central con un servidor Standard Edition en lugar de como una sucursal.  <br/> Una implementación de Skype Empresarial Server a escala completa proporciona una conexión RTC continua y una presencia resistente y conferencia en caso de error de WAN.  <br/> |

#### <a name="resiliency-topologies"></a>Topologías de resistencia

La siguiente figura refleja las topologías recomendadas de resistencia en las sucursales.

**Opciones de resistencia de las sucursales**

![Opciones de resistencia de la rama de voz](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Detalles de la aplicación de sucursal con funciones de supervivencia

La Skype Empresarial Server de sucursal con funciones de supervivencia incluye los siguientes componentes:

- Un registrador para la autenticación y registro de usuarios y el enrutado de llamadas

- Un servidor de mediación para controlar la señalización entre el registrador y una puerta de enlace RTC

- Una puerta de enlace RTC para enrutar llamadas a la RTC a modo de transporte de reserva en caso de que se produzca una interrupción en la red WAN

- SQL Server Express para el almacenamiento local de los datos de usuario

La aplicación de sucursal con funciones de supervivencia también incluye troncos RTC, puertos analógicos y un adaptador Ethernet.

Si la conexión WAN del sitio de sucursal a un sitio central deja de estar disponible, los usuarios internos de sucursales seguirán registrados en el registrador de la aplicación de sucursal con funciones de supervivencia y obtendrán un servicio de voz ininterrumpido mediante la conexión de la aplicación de sucursal con funciones de supervivencia a la RTC. En caso de que el vínculo WAN a una sucursal no esté disponible, los usuarios de sucursal que se conecten desde casa o desde otras ubicaciones remotas tendrán la posibilidad de registrarse con un servidor registrador ubicado en el sitio central. Estos usuarios disfrutarán de la funcionalidad de comunicaciones unificadas completa, con la única salvedad de que las llamadas entrantes a la sucursal se trasladarán al correo de voz. Cuando la conexión WAN vuelva, deberá restaurarse la funcionalidad completa para los usuarios de las sucursales. Ni la conmutación por error en la aplicación de sucursal con funciones de supervivencia ni la restauración del servicio requieren la presencia de un administrador de TI.

Skype Empresarial Server admite hasta dos aplicación de sucursal con funciones de supervivencia en un sitio de sucursal.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Descripción general de la implementación de la aplicación de sucursal con funciones de supervivencia

La aplicación de sucursal con funciones de supervivencia la fabrican los fabricantes de equipos originales en asociación con Microsoft y las implementan en su nombre los minoristas de valor agregado. Esta implementación solo debe producirse después de Skype Empresarial Server se haya implementado en el sitio central, haya una conexión WAN al sitio de sucursal y los usuarios del sitio de sucursal estén habilitados para Telefonía IP empresarial.

Para obtener información detallada sobre estas fases, consulte [Deploying a Survivable Branch Appliance or Server](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-a-survivable-branch-appliance-or-server) en la documentación de implementación.

|**Fase**|**Pasos**|**Derechos de usuario**|
|:-----|:-----|:-----|
|Configurar los servicios de dominio de Active Directory para la aplicación de sucursal con funciones de supervivencia  <br/> |**En el sitio central:** <br/>  Cree una cuenta de usuario de dominio (o identidad de empresa) para el técnico que instalará y activará la aplicación de sucursal con funciones de supervivencia en el sitio de sucursal. <br/>  Cree una cuenta de equipo (con el nombre de dominio completo (FQDN) aplicable para la aplicación de sucursal con funciones de supervivencia en servicios de dominio de Active Directory. <br/>  En el Generador de topologías, cree y publique la aplicación de sucursal con funciones de supervivencia. <br/> |La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians. La aplicación de sucursal con funciones de supervivencia debe pertenecer al grupo RTCSBAUniversalServices, que se produce automáticamente cuando se usa el Generador de topologías.  <br/> |
|Instale y active la aplicación de sucursal con funciones de supervivencia.  <br/> |**En la sucursal:** <br/>  Conectar la aplicación de sucursal con funciones de supervivencia a un puerto Ethernet y un puerto RTC. <br/>  Inicie la aplicación de sucursal con funciones de supervivencia. <br/>  Une la aplicación de sucursal con funciones de supervivencia al dominio mediante la cuenta de usuario de dominio creada para la aplicación de sucursal con funciones de supervivencia en el sitio central. Establezca el FQDN y la dirección IP de forma que coincidan con el FQDN creado en la cuenta del equipo. <br/>  Configure la aplicación de sucursal con funciones de supervivencia mediante la interfaz de usuario oem. <br/>  Compruebe la conectividad RTC. <br/> |La cuenta de usuario del técnico debe ser miembro de RTCUniversalSBATechnicians.  <br/> |

#### <a name="survivable-branch-server-details"></a>Detalles del servidor de sucursal con funciones de supervivencia

En el Generador de topologías, cree el sitio de sucursal, agregue el servidor de sucursal con funciones de supervivencia a ese sitio y, a continuación, ejecute el Asistente para la implementación de Skype Empresarial Server en el equipo donde desea instalar el rol.

### <a name="branch-site-resiliency-requirements"></a>Requisitos de resistencia de sitios de sucursal

Este tema le ayudará a preparar a los usuarios para la resistencia de sitios de sucursal y la supervivencia del correo de voz, y también especifica los requisitos de hardware y software relevantes.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparación de usuarios de sucursal para Branch-Site resistencia

Prepare a los usuarios para la resistencia de sitios de sucursal estableciendo su grupo de registradores como la aplicación de sucursal con funciones de supervivencia (SBA) o el servidor de sucursal con funciones de supervivencia.

#### <a name="registrar-assignments-for-branch-users"></a>Asignaciones de registradores para usuarios de sucursal

Independientemente de la solución de resistencia de sitios de sucursal que elija, deberá asignar un registrador principal a cada usuario. Los usuarios del sitio de sucursal siempre deben registrarse con el registrador en el sitio de sucursal, independientemente de si ese registrador reside en la aplicación de sucursal con funciones de supervivencia, el servidor de sucursal con funciones de supervivencia o el servidor Skype Empresarial Server estándar o Enterprise Edition independiente. Se requiere un registro de recursos de servicio de sistema de nombres de dominio (SRV) para que un cliente pueda detectar su grupo de registradores. Si la aplicación de sucursal con funciones de supervivencia deja de estar disponible, así es como los clientes del sitio de sucursal descubrirán automáticamente el registrador de copia de seguridad.

Si un sitio de sucursal no tiene un servidor DNS, existen dos formas alternativas de configurar la detección de la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia:

- Configure la opción DHCP 120 en el servidor del Protocolo de configuración dinámica de host (DHCP) del sitio de sucursal para que apunte al nombre de dominio completo (FQDN) de la aplicación de sucursal con funciones de supervivencia o del servidor de sucursal con funciones de supervivencia.

- Configure la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia para responder a las consultas DHCP 120.

#### <a name="voice-routing-for-branch-users"></a>Enrutamiento de voz para usuarios de sucursal

Se recomienda crear una directiva de voz sobre protocolo de Internet (VoIP) independiente para los usuarios de un sitio de sucursal. Esta directiva debe incluir una ruta principal que use la aplicación de sucursal con funciones de supervivencia o la puerta de enlace de servidor de sucursal, y una o más rutas de copia de seguridad que usen un tronco con una puerta de enlace de red telefónica conmutada (RTC) en el sitio central. Si la ruta principal no está disponible, se usa la ruta de copia de seguridad que usa una o más puertas de enlace de sitio central. De este modo, independientemente de dónde esté registrado un usuario (en el registrador del sitio de sucursal o en el grupo de registradores de copia de seguridad del sitio central), la directiva VoIP del usuario siempre está en vigor. Esta es una consideración importante para los escenarios de conmutación por error. Por ejemplo, si necesita cambiar el nombre de la aplicación de sucursal con funciones de supervivencia o volver a configurar la aplicación de sucursal con funciones de supervivencia para conectarse a un grupo de registradores de copia de seguridad en el sitio central, debe mover los usuarios del sitio de sucursal al sitio central durante la duración. (Para obtener más información acerca del cambio de nombre o la reconfiguración de una aplicación de sucursal con funciones de supervivencia, consulte [Apéndice B:](/previous-versions/office/lync-server-2013/lync-server-2013-appendix-b-managing-a-survivable-branch-appliance) Administración de una aplicación de sucursal con funciones de supervivencia en la documentación de implementación). Si esos usuarios no tienen directivas VoIP de nivel de usuario o planes de marcado de nivel de usuario, cuando los usuarios se mueven a otro sitio, las directivas VoIP de nivel de sitio y los planes de marcado de nivel de sitio del sitio central se aplican a los usuarios de forma predeterminada, en lugar de las directivas VoIP de nivel de sitio de sucursal y los planes de marcado,. En este escenario, a menos que las directivas VoIP de nivel de sitio y los planes de marcado de nivel de sitio usados por el grupo de registradores de copia de seguridad también se puedan aplicar a los usuarios del sitio de sucursal, sus llamadas producirán un error. Por ejemplo, si los usuarios de un sitio de sucursal ubicado en Japón se mueven a un sitio central en Redmond, es poco probable que un plan de marcado con reglas de normalización que anteponen +1425 a todas las llamadas de 7 dígitos traduzca correctamente las llamadas para esos usuarios.

> [!IMPORTANT]
> Al crear una ruta de copia de seguridad de sucursal, se recomienda agregar dos registros de uso de teléfono RTC a la directiva de usuario de sucursal y asignar rutas independientes a cada una de ellas. La primera ruta, o principal, dirigiría llamadas a la puerta de enlace asociada con la aplicación de sucursal con funciones de supervivencia (SBA) o el servidor de sucursal; la segunda ruta, o copia de seguridad, dirigiría llamadas a la puerta de enlace en el sitio central. Al dirigir llamadas, el SBA o el servidor de sucursal intentarán todas las rutas asignadas al primer registro de uso de RTC antes de intentar el segundo registro de uso.

Para ayudar a garantizar que las llamadas entrantes a los usuarios del sitio de sucursal lleguen a esos usuarios cuando la puerta de enlace de sucursal o el componente Windows del sitio de aplicación de sucursal con funciones de supervivencia no están disponibles (lo que ocurriría, por ejemplo, si la aplicación de sucursal con funciones de supervivencia o la puerta de enlace de sucursal estuvieran sin mantenimiento), cree una ruta de conmutación por error en la puerta de enlace (o trabaje con su proveedor de marcado directo interno (DID) para redirigir las llamadas entrantes al grupo de registradores de copia de seguridad en el sitio central. A partir de ahí, las llamadas se enrutarán a través del vínculo WAN a los usuarios de sucursal. Asegúrese de que la ruta traduce números para cumplir con la puerta de enlace RTC u otros formatos de número de teléfono aceptados del mismo nivel del tronco. Para obtener más información sobre cómo crear una ruta de conmutación por error, vea [Configuring a Failover Route](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-a-failover-route). También cree planes de marcado de nivel de servicio para el tronco asociado con la puerta de enlace en el sitio de sucursal para normalizar las llamadas entrantes. Si tiene dos aplicaciones de sucursal con funciones de supervivencia en un sitio de sucursal, puede crear un plan de marcado de nivel de sitio para ambos a menos que sea necesario un plan de nivel de servicio independiente para cada uno.

> [!NOTE]
> Para tener en cuenta el consumo de recursos del sitio central por parte de los usuarios del sitio de sucursal que dependen del sitio central para la presencia, conferencia o conmutación por error, se recomienda tener en cuenta cada usuario del sitio de sucursal como si el usuario estuviera registrado en el sitio central. Actualmente no hay límites en el número de usuarios del sitio de sucursal, incluidos los usuarios registrados con una aplicación de sucursal con funciones de supervivencia.

También se recomienda crear un plan de marcado de nivel de usuario y una directiva de voz y, a continuación, asignarlo a los usuarios del sitio de sucursal. Para obtener más información, consulte [Create or modify a dial plan in Skype Empresarial Server](../../deploy/deploy-enterprise-voice/dial-plans.md) y Create the [VoIP Routing Policy for Branch Users](/previous-versions/office/lync-server-2013/lync-server-2013-create-the-voip-routing-policy-for-branch-users) en la documentación sobre implementación.

#### <a name="routing-extension-numbers"></a>Números de extensión de enrutamiento

Al preparar planes de marcado y directivas de voz para los usuarios de sitios de sucursal, asegúrese de incluir reglas de normalización y reglas de traducción que coincidan con las cadenas y el formato de número usados en el atributo msRTCSIP-line (o URI de línea Skype Empresarial), de modo que las llamadas habilitadas entre los usuarios del sitio de sucursal y los usuarios del sitio central se enruten correctamente, especialmente cuando las llamadas deben redirigirse a través de la RTC porque el vínculo WAN no está disponible. Además, hay consideraciones especiales para los números marcados que incluyen números de extensión, en lugar de simplemente números de teléfono.

Las reglas de normalización y las reglas de traducción que coinciden con los URI de línea que contienen un número de extensión, ya sea exclusivamente o además de un número de teléfono E.164 completo, tienen requisitos adicionales. En esta sección se describen varios escenarios de ejemplo para enrutar llamadas para URI de línea con un número de extensión.

Si su organización no tiene configurados números de teléfono de Direct Inward Dial (DID) para usuarios individuales y el URI de línea de cada usuario está configurado con solo un número de extensión, los usuarios internos pueden llamarse entre sí marcando solo un número de extensión. Sin embargo, debe configurar reglas de normalización que se puedan aplicar a las llamadas de un usuario de sitio de sucursal a un usuario del sitio central, que coincidan con los números de extensión.

En un escenario en el que el vínculo WAN entre un sitio de sucursal y un sitio central está disponible, las llamadas de usuarios de sitios de sucursal a usuarios del sitio central no requieren que la regla de normalización correspondiente traduzca el número porque la llamada no se enruta a través de la RTC. Por ejemplo:

|**Nombre de regla**|**Descripción**|**Patrón de número**|**Conversión**|**Ejemplo**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |No traduce números de 5 dígitos  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 no se traduce  <br/> |

También debe incluir números de extensión para escenarios específicos, como cuando el vínculo WAN entre un sitio de sucursal y un sitio central no está disponible y se debe enrutar una llamada desde un sitio de sucursal a través de la RTC. Durante una interrupción de WAN, si un usuario del sitio de sucursal llama a un usuario del sitio central solo marcando la extensión del usuario del sitio central, debe tener una regla de traducción saliente que agrega el número de teléfono completo del usuario del sitio central. Si el URI de línea de un usuario contiene el número de teléfono completo de la organización y el número de extensión único del usuario en lugar de un número de teléfono completo que es único para el usuario, debe tener una regla de traducción saliente que agrega el número de teléfono completo de la organización en su lugar. Por ejemplo:

|**Description**|**Patrón de coincidencia**|**Conversión**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Traduce números de 5 dígitos al número de teléfono y la extensión de un usuario  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 se traduce a +14255550123;ext=10001  <br/> |
|Traduce números de 5 dígitos al número de teléfono de la organización y la extensión de un usuario  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 se traduce a +14255550100;ext=10001  <br/> |

En este escenario, si el tronco del mismo nivel que controla el rerouting a la RTC no admite números de extensión, la regla de traducción saliente también debe quitar el número de extensión. Por ejemplo:

|**Description**|**Patrón de coincidencia**|**Conversión**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Quita extensión de números de teléfono con extensiones  <br/> |^\+(\d \* ); ext=(\d \* )$  <br/> |+$1  <br/> |+14255550123;ext=10001 se traduce a +14255550123  <br/> |

Independientemente de si un vínculo WAN está disponible o no, si su organización no tiene números DID configurados para usuarios individuales y el URI de línea para un usuario contiene el número de teléfono de la organización y el número de extensión único del usuario, debe configurar el URI de línea de número de teléfono de la organización con un número al que se pueda acceder mediante la puerta de enlace RTC o del mismo nivel del tronco en el sitio de sucursal. También debe configurar el URI de línea de número de teléfono de la organización para incluir su propia extensión única para que las llamadas se enrute a ese número.

#### <a name="preparing-for-voice-mail-survivability"></a>Preparación para la supervivencia del correo de voz

Exchange La mensajería unificada (UM) normalmente se instala solo en un sitio central y no en los sitios de sucursal. Un autor de la llamada debe poder dejar un mensaje de correo de voz, incluso si el vínculo WAN entre el sitio de sucursal y el sitio central no está disponible. Como resultado, la configuración del URI de línea para el número de teléfono Operador automático de mensajería unificada de Exchange que proporciona correo de voz para los usuarios del sitio de sucursal requiere consideraciones especiales, además de las reglas de directiva de voz, plan de marcado y normalización aplicables a ese número de correo de voz.

Los dispositivos de sucursal con funciones de supervivencia (SBA) y los servidores de sucursal con funciones de supervivencia proporcionan la supervivencia del correo de voz para los usuarios de sucursales durante una interrupción de WAN. En concreto, si usa una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia y la WAN deja de estar disponible, el SBA o el servidor de sucursal con funciones de supervivencia redirige las llamadas sin respuesta a través de la RTC Exchange la mensajería unificada en el sitio central. Con un SBA o un servidor de sucursal con funciones de supervivencia, los usuarios también pueden recuperar mensajes de correo de voz a través de la RTC durante una interrupción de WAN. Por último, durante una interrupción de WAN, la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia pone en cola las notificaciones de llamadas perdidas y, a continuación, las carga en el servidor de mensajería unificada Exchange cuando se restaura la WAN. Para asegurarse de que el reenvía de correo de voz sea resistente, asegúrese de agregar una entrada para el FQDN del grupo de sitios central y una entrada para el FQDN del servidor perimetral al archivo hosts del servidor de sucursal con funciones de supervivencia. De lo contrario, la resolución dns puede hacer tiempo de espera si no tiene un servidor DNS en el sitio de sucursal.

Se recomiendan las siguientes configuraciones para la supervivencia del correo de voz para los usuarios del sitio de sucursal:

- Un administrador de Exchange microsoft debe configurar Exchange um Operador automático (AA) solo para aceptar mensajes. Esta configuración deshabilita todas las demás funciones genéricas, como la transferencia a un usuario o la transferencia a un operador, y limita la AA a aceptar solo mensajes. Como alternativa, el Exchange puede usar un AA genérico o un AA personalizado para enrutar la llamada a un operador.

- El administrador de Skype Empresarial Server debe tomar el número de teléfono AA y usar ese número de teléfono como el número de operador automático de mensajería unificada de **exchange** en la configuración de rerouting de correo de voz para la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal.

- El administrador de Skype Empresarial Server debe obtener el número de teléfono de acceso  de suscriptor de mensajería unificada de Exchange y usar ese número como número de acceso de suscriptor en la configuración de reobrución de correo de voz para la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.

- El Skype Empresarial Server debe configurar la mensajería unificada Exchange para que solo se asocie un plan de marcado a todos los usuarios de sucursal que necesiten acceso al correo de voz durante una interrupción de wan.

- Cuando el vínculo WAN no está disponible Exchange, las llamadas a usuarios del sitio de sucursal se pueden enrutar al buzón de voz de mensajería unificada (MU) del usuario, pero solo si la directiva de voz aplicada a la llamada especifica un número de teléfono de correo de voz único y no incluye un número de extensión.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware y software para Branch-Site resistencia

Los requisitos de hardware y software varían en función de la solución de resistencia.

#### <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para aplicaciones de sucursal con funciones de supervivencia

El hardware y el software necesarios están integrados en la aplicación de sucursal con funciones de supervivencia. Sin embargo, también se recomienda que cada sitio de sucursal implemente un servidor DHCP para obtener direcciones IP de cliente; de lo contrario, cuando expire la concesión dhcp, los clientes no tendrán conectividad IP.

Si los servidores DNS de empresa solo se encuentran en sitios centrales, los usuarios del sitio de sucursal no podrán conectarse Skype Empresarial Server a ellos durante una interrupción de WAN y, por lo tanto, se producirá un error en la detección que usa el registro de recursos SRV (servicio (SRV) de DNS. Para garantizar que se vuelva a enrir durante una interrupción de WAN, los registros DNS deben almacenarse en caché en el sitio de sucursal. Si el enrutador de sucursal lo admite, active el almacenamiento en caché dns. O bien, puede implementar un servidor DNS en la rama. Puede ser un servidor independiente o una versión de la aplicación de sucursal con funciones de supervivencia que admite funcionalidades DNS. Para obtener más información, póngase en contacto con su proveedor de aplicación de sucursal con funciones de supervivencia.

> [!NOTE]
> No es necesario tener un controlador de dominio en un sitio de sucursal. La aplicación de sucursal con funciones de supervivencia autentica a los clientes mediante un certificado especial que envía al cliente en respuesta a la solicitud de certificado del cliente cuando inicia sesión.

Skype Empresarial los clientes pueden descubrir el Skype Empresarial Server mediante la opción DHCP 120 (opción registrador SIP). Esto se puede configurar de dos maneras:

- Configure el servidor DHCP en el sitio de sucursal para responder a las consultas DHCP 120, que devuelven el FQDN del registrador en la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.

- Active el Skype Empresarial Server DHCP. Cuando está activado, el registrador de Skype Empresarial Server responde a las consultas de la opción DHCP 120. Tenga en cuenta que el registrador no responde a ninguna consulta DHCP que no sea dhcp Options 120.

Además, para los sitios de sucursal más grandes que tienen varias subredes, los agentes de retransmisión DHCP deben habilitarse para reenviar consultas de la opción DHCP 120 al servidor DHCP (configuración 1) o al registrador (configuración 2).

Por último, los usuarios del sitio de sucursal deben configurarse para Telefonía IP empresarial y aprovisionarse con un extremo de comunicaciones unificadas adecuado.

#### <a name="requirements-for-survivable-branch-servers"></a>Requisitos para servidores de sucursal con funciones de supervivencia

Los requisitos para los servidores de sucursal con funciones de supervivencia son los mismos que para un servidor front-end. Para obtener más información, vea [Server requirements for Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisitos para Full-Scale Skype Empresarial Server Branch-Site implementaciones

Para obtener más información, consulte [Server requirements for Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) en la documentación de planeación.

### <a name="example-configuring-a-failover-route"></a>Ejemplo: configurar una ruta de conmutación por error

 En el siguiente ejemplo se muestra cómo puede un administrador definir una ruta de conmutación por error para usarla en caso de que se desconecte Dallas-GW1 por motivos de mantenimiento o no esté disponible. En las tablas siguientes se muestra el cambio de configuración necesario.

**Tabla 1. Directiva de usuario**

|**Directiva de sitio**|**Uso de teléfono**|
|:-----|:-----|
|Directiva de llamada predeterminada  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Directiva local de Redmond  <br/> |RedmondLocal  <br/> |
|Directiva de llamada de Dallas  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tabla 2. Rutas**


| **Nombre de ruta**             | **Patrón de número** | **Uso de teléfono**         | **Tronco**                                 | **Puerta de enlace**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Ruta local de Redmond  <br/> | ^\+1(425           | 206                     | 253)(\d {7} )$  <br/>                       | Local  <br/> RedmondLocal  <br/>                |
| Ruta local de Dallas  <br/>  | ^\+1(972           | 214                     | 469)(\d {7} )$  <br/>                       | Local  <br/>                                    |
| Ruta universal  <br/>     | ^\+? (\d \* ) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Ruta de usuarios de Dallas  <br/>  | ^\+? (\d \* ) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

En la Tabla 1, se agrega el uso de teléfono GlobalPSTNHopoff después del uso de teléfono DallasUsers en la directiva de llamada de Dallas. Esto permite que las llamadas con la directiva de llamada de Dallas usen las rutas configuradas para el uso de teléfono GlobalPSTNHopoff en caso de que una ruta para el uso telefónico DallasUsers no esté disponible.