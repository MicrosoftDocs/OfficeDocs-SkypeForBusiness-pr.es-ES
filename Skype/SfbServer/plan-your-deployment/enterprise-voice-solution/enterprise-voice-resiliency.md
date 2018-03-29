---
title: Planificar la resistencia de la Telefonía IP en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Aprenda a admitir resistencia de voz de Skype para Business Server Telefonía IP empresarial, en los sitios centrales y sitios de sucursales. Opciones de sitio de sucursal incluyen implementar que sobreviven de rama de dispositivos o servidores de sucursal que sobreviven.
ms.openlocfilehash: a4ce7e01ef93ef7bfca2357b65b315b4be5c6781
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server-2015"></a>Planificar la resistencia de la Telefonía IP en Skype Empresarial Server 2015
 
Aprenda a admitir resistencia de voz de Skype para Business Server Telefonía IP empresarial, en los sitios centrales y sitios de sucursales. Opciones de sitio de sucursal incluyen implementar que sobreviven de rama de dispositivos o servidores de sucursal que sobreviven.
  
Resistencia de voz se refiere a la capacidad de los usuarios para seguir realizar y recibir llamadas si un sitio central que hosts Skype para Business Server no está disponible, ya sea a través de un área extensa red falla (WAN) o a otra causa. Si se produce un error en un sitio central, el servicio de Telefonía IP empresarial debe continuar sin interrupciones mediante un failover transparente a un sitio de backup. En caso de error de la WAN, llamadas de sitio de sucursal deben redirigirse a una puerta de enlace PSTN local. Esta sección analiza los planes de resistencia de voz en caso de fallo del sitio central o WAN.
  
## <a name="central-site-resiliency"></a>Resiliencia del sitio central

Cada vez más, las empresas tienen varios sitios repartidos por todo el mundo. Mantenimiento de los servicios de emergencia, acceso al servicio de asistencia y la capacidad para realizar tareas empresariales críticas cuando un sitio central está fuera de servicio es esencial para cualquier solución de resistencia de la Telefonía IP empresarial. Cuando un sitio central no está disponible, se deben cumplir las siguientes condiciones:
  
- Se debe proporcionar failover de voz.
    
- Los usuarios que normalmente se registran con el grupo de Front-End en el sitio central deben ser capaces de registrar con un grupo de servidores frontales alternativo. Esto puede hacerse mediante la creación de SRV de DNS varios registros, cada uno de los cuales se resuelve en un grupo de directores o grupo de servidores Front-End en cada uno de los sitios centrales. Puede ajustar la prioridad y el peso de los registros SRV para que los usuarios que son atendidos por ese sitio central obtendrán el grupo correspondiente de Director y Front-End por delante de las de otros registros SRV.
    
- Llamadas a y desde los usuarios ubicados en otros sitios deben enrutarse de nuevo a la RTC.
    
Este tema describe la solución recomendada para proteger la resistencia de voz del sitio central.
  
### <a name="architecture-and-topology"></a>Arquitectura y topología

Planear la resistencia de voz en un sitio central, requiere un conocimiento básico de la función central desempeñada por el Skype para Business Server Registrar para habilitar la conmutación por error de voz. El Skype para Registrar servidor de negocios es un servicio que permite la autenticación y el registro de cliente y proporciona servicios de enrutamiento. Se ejecuta en todos los servidor Standard Edition, servidor Front-End, Director o dispositivo que sobreviven de rama. Un grupo de registrador consiste en Registrar servicios ejecutándose en el grupo de servidores Front-End y que residen en el mismo sitio. Un Skype para Business client descubre el grupo de servidores Front-End mediante el mecanismo de descubrimiento siguientes: 
  
1. Registro SRV de DNS
    
2. Servicio Web de detección automática 
    
3. Opción DHCP 120
    
Una vez el Skype para Business client se conecta al grupo de Front-End, está dirigida por el equilibrador de carga a uno de los servidores frontales en el grupo. Ese servidor Front-End, a su vez, redirige al cliente a un registrador preferido del grupo.
  
Cada usuario habilitado para Telefonía IP empresarial se asigna a un grupo de Registrar determinado, que se convierte en conjunto de registrador principal del usuario. En un sitio determinado, cientos o miles de usuarios normalmente comparten un único repositorio principal del registrador. Para tener en cuenta el consumo de recursos de sitio central por cualquier usuario del sitio de sucursal que se basan en el sitio central de presencia, conferencias o conmutación por error, le recomendamos que considere cada usuario del sitio de sucursal como si el usuario fuera un usuario registrado en el sitio central. Actualmente no hay ningún límite en el número de usuarios del sitio de sucursal, incluidos los usuarios registrados con un dispositivo de la rama que sobreviven.
  
Para garantizar la resistencia de voz en caso de una falla en el sitio central, el grupo principal del registrador debe tener un único grupo designado de backup registrador ubicado en otro sitio. La copia de seguridad puede configurarse mediante configuración resistencia de generador de topología. Suponiendo que un vínculo WAN resistente entre los dos sitios, automáticamente se dirigen a los usuarios cuyo grupo de registrador principal ya no está disponible al grupo copia de seguridad de registrador.
  
Los pasos siguientes describen el proceso de descubrimiento y registro de cliente:
  
1. Un cliente descubre Skype para Business Server a través de los registros SRV de DNS. En Skype para Business Server, los registros SRV de DNS pueden configurarse para devolver más de un FQDN a la consulta DNS SRV. Por ejemplo, si la empresa Contoso tiene tres sitios centrales (Norteamérica, Europa y Asia Pacífico) y un grupo de directores en cada sitio central, pueden señalar los registros SRV de DNS para el FQDN del grupo de Director en cada una de las tres ubicaciones. Como el grupo de Director en una de las ubicaciones está disponible, puede conectar el cliente para el primer salto Skype para Business Server.
    
    > [!NOTE]
    > Uso de un grupo de directores es opcional. Un grupo de servidores Front-End puede utilizarse en su lugar. 
  
2. El grupo de directores informa el Skype para Business client pool de registrador principal del usuario y backup registrador.
    
3. El Skype para Business client intenta conectarse primero al grupo de registrador principal del usuario. Si el grupo principal del registrador está disponible, el registrador acepta el registro. Si el grupo principal del registrador no está disponible, el Skype para empresa cliente intenta conectarse al grupo copia de seguridad de registrador. Si el grupo de registrador auxiliar está disponible y ha determinado que el conjunto de registrador principal del usuario está disponible (al detectar una falta de latido para un intervalo especificado de conmutación por error) el grupo copia de seguridad del registrador acepta el registro del usuario. Una vez que el registrador de copia de seguridad detecta que el registrador principal nuevo está disponible, el grupo copia de seguridad del registrador redirigirá a clientes de conmutación por error a su grupo principal.
    
### <a name="requirements-and-recommendations"></a>Requisitos y recomendaciones

Los siguientes requisitos y recomendaciones para implementar la resistencia de voz del sitio central son adecuadas para la mayoría de las organizaciones:
  
- Los sitios en los que residen los grupos de registro principales y de reserva deben estar conectados mediante un vínculo WAN resistente.
    
- Cada sitio central debe contener un grupo de registrador que consta de uno o varios registradores.
    
- Cada pool de registrador debe ser compensados utilizando DNS equilibrio de carga, equilibrio de carga de hardware o ambos. Para obtener información detallada acerca de cómo planear la configuración de equilibrio de carga, vea [requisitos de equilibrio de Skype para el negocio de carga](../../plan-your-deployment/network-requirements/load-balancing.md).
    
- Cada usuario debe asignarse a un grupo de registrador principal utilizando ambos el Skype para el Shell de administración de servidor de negocio **Conjunto CsUser** cmdlet o el Skype para Business Server Control Panel.
    
- El grupo principal del registrador debe tener un único repositorio de registrador backup ubicado en un sitio central diferente. 
    
- El grupo principal del registrador debe configurarse para que conmutar por error al grupo copia de seguridad de Registrar. De forma predeterminada, el registro principal se establece en conmutar al grupo Registrar backup después de un intervalo de 300 segundos. Puede cambiar este intervalo utilizando el Skype para el generador de topología de servidor empresarial.
    
- Configurar una ruta de migración tras error. Al configurar la ruta, especificar una puerta de enlace que se encuentra en un sitio diferente de la especificada en la ruta principal de la puerta de enlace.
    
- Si el sitio central contiene el servidor de administración principal y el sitio es probable que esté inactivo durante un período prolongado, deberá volver a instalar las herramientas de administración en el sitio de copia de seguridad; de lo contrario, no podrá cambiar ninguna configuración de administración.
    
### <a name="dependencies"></a>Dependencias

Skype para Business Server depende de los siguientes componentes de software y la infraestructura para garantizar la resistencia de voz:
  
|||
|:-----|:-----|
|**Componente** <br/> |**Funcional** <br/> |
|DNS  <br/> |Resolver los registros SRV y A para la conectividad de servidor y cliente a servidor  <br/> |
|Exchange y los servicios Web Exchange (EWS)  <br/> |Póngase en contacto con almacenamiento de información; datos de calendario  <br/> |
|Mensajería unificada de Exchange y los servicios Web de Exchange  <br/> |Llamar a registros, lista de correo de voz, correo de voz  <br/> |
|Opciones DHCP 120  <br/> |Si SRV de DNS no está disponible, el cliente intentará utilizar DHCP opción 120 para descubrir al registrador. Para que esto funcione, debe configurarse un servidor DHCP o Skype para negocios servidor DHCP debe estar habilitado.  <br/> |
   
### <a name="survivable-voice-features"></a>Características de voz que sobreviven

Si se han implementado los requisitos y las recomendaciones anteriores, el grupo de registrador auxiliar proporcionará las siguientes características de voz:
  
- Llamadas salientes de RTC
    
- Llamadas entrantes de PSTN, si el proveedor de servicios de telefonía es compatible con la capacidad de conmutación por error a un sitio de backup
    
- Llamadas entre los usuarios en el mismo sitio y entre dos sitios diferentes de Enterprise
    
- Tratamiento de llamada básico, incluidos espera de llamada, la recuperación y transferencia
    
- Dos proveedores de mensajería instantánea y compartir audio y vídeo entre los usuarios en el mismo sitio
    
- Transferencia, de llamadas simultáneas de timbres de extremos, la delegación de llamada y los servicios de llamada de equipo, pero sólo si se configuran ambas partes para llamar a la delegación, o todos los miembros del equipo, en el mismo sitio.
    
- Los clientes y los teléfonos existentes seguirán funcionando.
    
- Registro detallado de llamadas (CDR)
    
- Autenticación y autorización
    
Dependiendo de cómo están configurados, las siguientes características de voz pueden o no funcionen cuando un sitio principal central está fuera de servicio:
  
- Depósito de correo de voz y la recuperación 
    
    Si desea disponer de mensajería unificada de Exchange al sitio principal central está fuera de servicio, debe hacer uno de estos procedimientos:
    
  - Cambiar registros SRV de DNS para que señalen los servidores mensajería unificada de Exchange en el sitio central para backup servidores mensajería unificada de Exchange en otro sitio.
    
  - Configurar el plan de marcado de cada usuario mensajería unificada de Exchange para incluir servidores de mensajería unificada de Exchange en el sitio central y el sitio de copia de seguridad, sin designar los servidores de mensajería unificada de Exchange backup como deshabilitado. Si el sitio primario está disponible, el Administrador de Exchange debe marcar los servidores mensajería unificada de Exchange en el sitio de copia de seguridad como habilitado.
    
    Si ninguna de las soluciones anteriores es posible, a continuación, mensajería unificada de Exchange no estarán disponible en caso de que el sitio central deja de estar disponible.
    
- Conferencia de todos los tipos
    
    Un usuario que ha fallado a un sitio de backup puede unirse a una conferencia que se crea o alojada en un organizador cuyo grupo está disponible pero no se puede crear o anfitrión de una conferencia en su propio grupo primario, que ya no está disponible. De igual forma, otros usuarios no pueden unirse a conferencias alojadas en el grupo principal del usuario afectado.
    
Las siguientes características de voz no funcionan cuando un sitio principal central está fuera de servicio:
  
- Operador automático de conferencia
    
- Presencia y enrutamiento basado en DND
    
- Actualizar la configuración del reenvío de llamada
    
- Servicio de grupo de respuesta y el parque de llamada
    
- Aprovisionamiento de teléfonos nuevos y clientes
    
- Búsqueda de Web de libreta de direcciones
    
## <a name="branch-site-resiliency"></a>Resistencia de sitios de sucursal

Si desea proporcionar resiliencia del sitio de la sucursal, es decir, servicio de Telefonía IP empresarial de alta disponibilidad, tiene tres opciones para hacerlo:
  
- Aplicación de sucursal con funciones de supervivencia
    
- Servidor de sucursal con funciones de supervivencia
    
- Un completo Skype para la implementación de Business Server en el sitio de la sucursal 
    
Esta guía le ayudará a evaluar qué solución de resiliencia es mejor para su organización y, en función de la solución de resistencia, qué solución de conectividad PSTN a utilizar. También le ayudará a preparar la implementación de la solución que elija mediante la descripción de los requisitos previos y otras consideraciones de planeación.
  
### <a name="branch-site-resiliency-features"></a>Características de resistencia de sitios de sucursal

Si proporciona resistencia del sitio de la sucursal, si se produce un error en la conexión de WAN del sitio de una sucursal a un sitio central o si el sitio central es inaccesible, deben seguir siendo disponibles las siguientes características de voz:
  
- Entrante y saliente telefónica pública conmutada (PSTN) de red llamadas
    
- Llamadas entre los usuarios en el mismo sitio y entre dos sitios diferentes de Enterprise
    
- Tratamiento de llamada básico, incluidos espera de llamada, la recuperación y transferencia
    
- Dos proveedores de mensajería instantánea
    
- Transferencia, de llamadas simultáneas de timbres de extremos, la delegación de llamada y los servicios de llamada de equipo, pero sólo si el usuario delegado y delegado (por ejemplo, un administrador y administrador del administrador) o todos los miembros del equipo, se configuran en el mismo sitio
    
- Registros de detalles de llamadas (CDR)
    
- Conferencia telefónica de PSTN con conferencias AutoAttendant
    
- Funciones de correo de voz, si configura opciones de redireccionamiento de correo de voz.
    
- Autorización y autenticación de usuario
    
Las siguientes características estarán disponibles sólo si su solución de resistencia es un Skype a gran escala para la implementación de Business Server en el sitio de la sucursal:
  
- Mensajería instantánea, web y A / conferencias audiovisuales
    
- Presencia y enrutamiento basado en No molestar DND (donde las llamadas se impide timbre en las extensiones que tienen activado el DND)
    
- Actualizar la configuración del reenvío de llamada
    
- Aplicación de grupo de respuesta y la aplicación de llamada Park
    
- Aprovisionamiento de teléfonos nuevos y los clientes, pero sólo si los servicios de dominio de Active Directory está presente en el sitio de la sucursal.
    
- 9-1-1 mejorado (E9-1-1)
    
    Si se implementa E9-1-1 y la troncal SIP en el sitio central no está disponible porque el vínculo WAN está inactivo, el dispositivo de la rama que sobreviven enrutará llamadas E9-1-1 a la puerta de enlace de la sucursal local. Para habilitar esta característica, las directivas de voz de los usuarios del sitio de la sucursal deben enrutar las llamadas a la puerta de enlace local en caso de error de la WAN.
    
> [!NOTE]
> SBA (sucursal que sobreviven) no se admite para XMPP. Los usuarios alojados en una SBA configuraciones no podrá enviar IMs o ver presencia con contactos XMPP. 
  
### <a name="branch-site-resiliency-solutions"></a>Soluciones de resistencia de sitios de sucursal

Existen ventajas evidentes para proporcionar resistencia del sitio de la sucursal para su organización. En concreto, si pierde la conexión con el sitio central, los usuarios del sitio de sucursal seguirá dispone de correo de voz y servicio de Telefonía IP empresarial (si configurar redireccionamiento de configuración de correo de voz). Sin embargo, en los sitios con menos de 25 usuarios, una solución de resistencia puede no proporcionar suficiente un retorno de la inversión. 
  
Si decide proporcionar resistencia del sitio de la sucursal, tiene tres opciones. En la tabla siguiente puede ayudarle a determinar la mejor opción para su organización.
  
|**Si usted...**|**Le recomendamos que utilice un...**|
|:-----|:-----|
|Alojar entre 25 y 1000 usuarios en el sitio de sucursal y el retorno de la inversión no admite una implementación completa o cuando local está disponible soporte administrativo  <br/> |Aplicación de sucursal con funciones de supervivencia  <br/> El dispositivo de la rama que sobreviven es un servidor en placa estándar de la industria con un Skype para el registrador de servidor empresarial y servidor de mediación que se ejecuta en Windows Server 2008 R2. El dispositivo de la rama que sobreviven también contiene una puerta de enlace de telefonía pública conmutada (PSTN) de la red. Dispositivos calificados de terceros (desarrollados por los socios de Microsoft en el sistema de calificación y certificación de dispositivo de rama funciones de supervivencia (SBA)) proporcionan una conexión continua de PSTN en caso de error de la WAN, pero este enfoque no proporciona resistente presencia y conferencias porque estas características dependen de servidores frontales en el sitio central.  <br/> Para obtener más información acerca de dispositivos de sucursales que sobreviven, consulte "Detalles de dispositivo de sucursal que sobreviven", más adelante en este tema.  <br/> **Nota:** Si decide usar también un tronco SIP con el dispositivo de la rama que sobreviven, póngase en contacto con su proveedor del dispositivo de sucursal que sobreviven para obtener información acerca de qué proveedor de servicios es mejor para su organización. <br/> |
|Alojar entre 1000 y 2000 los usuarios del sitio de la sucursal, carecen de una conexión WAN resistente y ha entrenado Skype para los administradores de servidores de negocios disponibles  <br/> |Servidor de sucursal que sobreviven o dos dispositivos de sucursal que sobreviven.  <br/> El servidor de sucursal que sobreviven es cumplir los requisitos de hardware especificado un servidor de Windows que tenga Skype software registrador de servidor empresarial y servidor de mediación instalado en él. Debe conectarse a una puerta de enlace PSTN o un tronco SIP a un proveedor de servicio telefónico.  <br/> Para obtener más información acerca de servidores de sucursal que sobreviven, consulte "Detalles de servidor de sucursal que sobreviven", más adelante en este tema.  <br/> |
|Si necesita características de presencia y conferencias en además de voz características de hasta 5000 usuarios y ha entrenado Skype para los administradores de servidores de negocios disponibles  <br/> |Implementar un sitio central con un servidor Standard Edition en lugar de un sitio de sucursal.  <br/> Un Skype a gran escala para la implementación de Business Server proporciona una conexión continua de RTC y resistente presencia y conferencias en caso de error de la WAN.  <br/> |
   
#### <a name="resiliency-topologies"></a>Topologías de resiliencia

La figura siguiente muestra las topologías recomendadas para resistencia del sitio de la sucursal.
  
**Opciones de resistencia del sitio de sucursal**

![Opciones de resistencia de voz para sucursal](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)
  
#### <a name="survivable-branch-appliance-details"></a>Detalles del dispositivo de la rama que sobreviven

El Skype para Business Server Appliance que sobreviven de rama incluye los siguientes componentes:
  
- Registrador de autenticación de usuario, registro y enrutamiento de llamadas
    
- Un servidor de mediación para el tratamiento de señales entre el registrador y una puerta de enlace PSTN
    
- Una puerta de enlace PSTN para enrutar las llamadas a la PSTN como un transporte de reserva en caso de una interrupción de la WAN
    
- SQL Server Express para almacenar datos de usuario local
    
El dispositivo de la rama que sobreviven también incluye los troncos PSTN, puertos analógicos y un adaptador de Ethernet. 
  
Si está disponible la conexión de WAN del sitio de la sucursal en un sitio central, los usuarios de rama interna continuar registrar con el registrador de dispositivo rama que sobreviven y obtener servicio ininterrumpido de voz mediante la conexión del dispositivo de sucursal que sobreviven a la RTC. Sitio de sucursal, los usuarios que se conectan desde casa u otras ubicaciones remotas podrán registrar con un servidor de registros en un sitio central, si el vínculo WAN al sitio de sucursal no está disponible. Estos usuarios tendrán funcionalidad completa de comunicaciones unificadas, con la única excepción que las llamadas entrantes al sitio de sucursal irá al correo de voz. Cuando esté disponible la conexión WAN, los usuarios del sitio de sucursal debe restaurar toda la funcionalidad. La conmutación por error para el dispositivo de la rama que sobreviven ni la restauración del servicio requiere la presencia de un administrador de TI.
  
Skype para Business Server admite hasta dos dispositivo de sucursal que sobreviven en un sitio de sucursal. 
  
#### <a name="survivable-branch-appliance-deployment-overview"></a>Información general sobre la implementación de dispositivo que puede perdurar rama

El dispositivo de la rama que sobreviven es fabricado por fabricantes de equipos originales en asociación con Microsoft y desplegado en su nombre por distribuidores de valor añadidos. Esta implementación debe producirse después de Skype para Business Server se ha implementado en el sitio central, una conexión WAN con el sitio de sucursal está en su sitio y los usuarios del sitio de sucursal están habilitados para Telefonía IP empresarial.
  
Para obtener más información acerca de estas fases, vea [implementar un servidor o dispositivo de sucursal que sobreviven](http://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) en la documentación de implementación.
  
|**Fase**|**Pasos**|**Derechos de usuario**|
|:-----|:-----|:-----|
|Configurar servicios de dominio de Active Directory para el dispositivo de la rama que sobreviven  <br/> |**En el sitio central:** <br/>  Crear una cuenta de usuario de dominio (o la identidad de la empresa) para el técnico que va a instalar y activar el dispositivo de sucursal que sobreviven en el sitio de sucursal. <br/>  Crear una cuenta de equipo (con el correspondiente nombre de dominio completo (FQDN)) para el dispositivo de sucursal que sobreviven en servicios de dominio de Active Directory. <br/>  Generador de topología, crear y publicar el dispositivo de la rama que sobreviven. <br/> |La cuenta de usuario del técnico debe ser un miembro de RTCUniversalSBATechnicians. El dispositivo de la rama que puede perdurar debe pertenecer al grupo de RTCSBAUniversalServices, lo que sucede automáticamente cuando se utiliza el generador de topología.  <br/> |
|Instalar y activar el dispositivo de la rama que sobreviven.  <br/> |**En el sitio de la sucursal:** <br/>  Conecte el dispositivo de la rama que sobreviven a un puerto Ethernet y puerto PSTN. <br/>  Inicie el dispositivo de la rama que sobreviven. <br/>  Unir el dispositivo de la rama que sobreviven al dominio, usando la cuenta de usuario de dominio creada para el dispositivo que sobreviven de sucursal en el sitio central. Establezca el FQDN y la dirección IP para que coincida con el FQDN en la cuenta de equipo. <br/>  Configurar el dispositivo de sucursal que sobreviven mediante la interfaz de usuario OEM. <br/>  Probar la conectividad PSTN. <br/> |La cuenta de usuario del técnico debe ser un miembro de RTCUniversalSBATechnicians.  <br/> |
   
#### <a name="survivable-branch-server-details"></a>Detalles del servidor de sucursal que sobreviven

En el generador de topología crear el sitio de la sucursal, agregue el servidor de sucursal que sobreviven a ese sitio y ejecutar el Skype para el Asistente para implementación de Business Server en el equipo donde desea instalar la función.
  
### <a name="branch-site-resiliency-requirements"></a>Requisitos de resistencia del sitio de sucursal

Este tema le ayudará a preparar los usuarios para la supervivencia de correo de voz y resiliencia de sitio de la sucursal y también especifica los requisitos de hardware y software pertinentes.
  
#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparar a los usuarios de la sucursal para el sitio de la sucursal resistencia

Preparar los usuarios para la resiliencia del sitio de sucursal estableciendo su grupo Registrar como el dispositivo de sucursal funciones de supervivencia (SBA) o el servidor de sucursal que sobreviven.
  
#### <a name="registrar-assignments-for-branch-users"></a>Registrar asignaciones para los usuarios de la sucursal

Independientemente de qué solución de resistencia de sitio de la sucursal que elija, debe asignar a un registrador principal a cada usuario. Los usuarios del sitio de sucursal siempre deben registrar con el registrador en el sitio de la sucursal, independientemente de si dicho registrador reside en el dispositivo de sucursal que sobreviven, servidor de sucursal que sobreviven o Skype independiente para Business Server Standard o Enterprise Edition servidor de. Un registro de recursos de servicio (SRV) de dominio nombre (de dominio DNS) del sistema es necesario para que un cliente puede descubrir su grupo de registrador. Si el dispositivo de la rama que sobreviven está disponible, se trata cómo los clientes del sitio de sucursal detectará automáticamente el registrador de copia de seguridad.
  
Si un sitio de la sucursal no tiene un servidor DNS, hay dos formas de configurar la detección del dispositivo de sucursal que sobreviven o del servidor de sucursal que sobreviven:
  
- Configurar 120 de opción de DHCP en el servidor de protocolo de configuración dinámica de Host (DHCP) del sitio de la sucursal para que señale el nombre de dominio completo (FQDN) del equipo de sucursal que sobreviven o servidor de la sucursal que sobreviven.
    
- Configurar el dispositivo de sucursal que sobreviven o el servidor de sucursal que sobreviven para responder a las consultas de 120 de DHCP.
    
#### <a name="voice-routing-for-branch-users"></a>Voz de enrutamiento para los usuarios de la sucursal

Recomendamos que cree una voz de nivel de usuario independiente sobre la directiva del protocolo de Internet (VoIP) para los usuarios de un sitio de sucursal. Esta directiva debe incluir una ruta principal que utiliza la puerta de enlace de servidor de dispositivo de sucursal que sobreviven o sucursal y una o varias rutas de copia de seguridad que utilice un tronco con una puerta de enlace de telefonía pública conmutada (PSTN) de red en el sitio central. Si la ruta principal no está disponible, se utilizará la ruta de copia de seguridad que utiliza una o varias puertas de enlace de sitio central. De este modo, independientemente de donde está registrado un usuario — en el sitio de sucursal registrador o el grupo copia de seguridad de Registrar en el sitio central, la directiva del usuario VoIP siempre está en efecto. Ésta es una consideración importante para los escenarios de conmutación por error. Por ejemplo, si necesita cambiar el nombre del dispositivo de la rama que sobreviven o volver a configurar el dispositivo de sucursal que sobreviven para conectarse a un grupo de registrador en el sitio central de copia de seguridad, debe mover los usuarios del sitio de sucursal al sitio central para la duración. (Para obtener más información acerca de cómo cambiar el nombre o volver a configurar un dispositivo de la rama que sobreviven, vea [Apéndice B: administrar un dispositivo de la rama que sobreviven](http://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx) en la documentación de implementación). Si los usuarios no tienen políticas a nivel de usuario VoIP o planes de marcado de nivel de usuario, cuando los usuarios se mueven a otro sitio, el sitio VoIP y políticas del marcado de nivel de sitio planes del sitio central aplican a los usuarios de forma predeterminada, en lugar del sitio de sucursal nivel de sitio VoIP políticas y marcado planes. En este escenario, a menos que se utiliza de planes de marcado de las directivas de VoIP de nivel de sitio y de nivel de sitio también puede aplicar el grupo copia de seguridad de Registrar a los usuarios del sitio de sucursal, se producirá un error en las llamadas. Por ejemplo, si los usuarios de un sitio de sucursal en Japón se mueven a un sitio central en Redmond, un plan de marcado con reglas de normalización que anteponer +1425 para todas las llamadas de 7 dígitos es improbable adecuadamente traducir llamadas para esos usuarios.
  
> [!IMPORTANT]
> Cuando se crea una ruta de copia de seguridad de office de sucursales, se recomienda que agregue dos registros de uso de teléfono PSTN a la directiva de usuario de oficina sucursal y asignar rutas diferentes a cada uno de ellos. El primero, o primario, ruta podría dirigir llamadas a la puerta de enlace asociada al dispositivo de sucursal funciones de supervivencia (SBA) o servidor de la sucursal; el segundo, o copia de seguridad, ruta podría dirigir llamadas a la puerta de enlace en el sitio central. En la dirección de las llamadas, el servidor de SBA o sucursales intentará todas las rutas que se asigna al primer registro de uso PSTN antes de intentar el segundo registro de uso. 
  
Para ayudar a garantizar que las llamadas entrantes a los usuarios del sitio de sucursal llegará a los usuarios cuando la puerta de enlace de la sucursal o el componente de Windows del sitio que sobreviven dispositivo de sucursales está disponible (que ocurriría, por ejemplo, si el dispositivo de sucursal que sobreviven o sucursal puerta de enlace funcionaran por mantenimiento), crear una ruta de conmutación por error en la puerta de enlace (o trabajar con su proveedor de marcado interno directo (DID)) para redirigir las llamadas entrantes al grupo copia de seguridad de Registrar en el sitio central. Desde allí, las llamadas se enrutarán a través de la WAN vínculo a los usuarios de la sucursal. Asegúrese de que la ruta traduce números para cumplir con la puerta de enlace PSTN o formatos de número de teléfono aceptados del otro interlocutor de tronco. Para obtener más información acerca de la creación de una ruta de conmutación por error, consulte [configuración de una ruta de migración tras error](http://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx). También crear planes de marcado de nivel de servicio para el tronco asociado a la puerta de enlace en el sitio de la sucursal para normalizar las llamadas entrantes. Si dispone de dos dispositivos de sucursal que sobreviven en un sitio de sucursal, puede crear un plan de marcado de nivel de sitio para ambos a menos que sea necesario un plan de nivel de servicio independiente para cada uno.
  
> [!NOTE]
> Para tener en cuenta el consumo de recursos de sitio central por cualquier usuario del sitio de sucursal que se basan en el sitio central de presencia, conferencias o conmutación por error, le recomendamos que considere cada usuario del sitio de sucursal como si el usuario se ha registrado en el sitio central. Actualmente no hay ningún límite en el número de usuarios del sitio de sucursal, incluidos los usuarios registrados con un dispositivo de la rama que sobreviven. 
  
También se recomienda que cree una directiva de voz y el plan de marcado de nivel de usuario y asignarlo a los usuarios del sitio de sucursal. Para obtener más información, consulte [crear o modificar un plan de marcado de Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md) y [crear la directiva de enrutamiento VoIP para los usuarios de la sucursal](http://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx) en la documentación de implementación.
  
#### <a name="routing-extension-numbers"></a>Números de extensión de enrutamiento

Al preparar los planes de marcado y las directivas de voz para los usuarios del sitio de sucursal, no olvide incluir las reglas de normalización y las reglas de conversión que coinciden con las cadenas y el formato de número utilizado en la msRTCSIP-línea (o línea URI) de atributos, para que habilite Skype para llamadas de negocios entre los usuarios del sitio de sucursal y el sitio central de los usuarios se enrutarán correctamente, especialmente cuando las llamadas deben enrutarse de nuevo por PSTN porque el vínculo WAN no está disponible. Además, existen consideraciones especiales para los números marcados que incluyen números de extensión, simplemente los números de teléfono.
  
Reglas de normalización y reglas de traducciones que coincidan con los URI de línea que contienen un número de extensión, ya sea exclusivamente o además de un número de teléfono E.164 completo tienen requisitos adicionales. Esta sección describe varios escenarios de ejemplo para dirigir las llamadas de identificadores URI de línea con un número de extensión.
  
Si su organización no tiene números de teléfono de marcado interno directo (DID) configurados para usuarios individuales y el URI de la línea de cada usuario se configura con sólo un número de extensión, los usuarios internos pueden llamar a uno de otro sólo un número de extensión de marcado. Sin embargo, debe configurar reglas de normalización que se pueden aplicar a las llamadas de un usuario del sitio de sucursal a un usuario del sitio central, que coinciden con los números de extensión.
  
En un escenario donde el vínculo WAN entre un sitio de sucursal y un sitio central está disponible, llamadas de los usuarios del sitio de sucursal a los usuarios del sitio central no requieren la regla de normalización coincidente para traducir el número, porque la llamada no se enruta a través la RTC. Por ejemplo:
  
|**Nombre de la regla**|**Descripción**|**Patrón de números**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |No traducir números de 5 dígitos  <br/> |^ (\d{5})$  <br/> |$1  <br/> |no se ha traducido 10001  <br/> |
   
También debe dar cabida a números de extensión para escenarios específicos, como cuando el vínculo WAN entre un sitio de sucursal y el sitio central no está disponible y se debe enrutar una llamada desde un sitio de sucursal por PSTN. Durante una interrupción de la WAN, si un usuario del sitio de sucursal llama a un usuario del sitio central marcando su sitio central de extensión, debe tener una regla de salida de traducción que agrega el número de teléfono completo del usuario del sitio central. Si el URI de línea de un usuario contiene el número de teléfono completo de la organización y el único número de extensión en lugar de un número de teléfono completo que es único para el usuario, debe tener una regla de salida de traducción que se agrega el número de teléfono completo de su organización en su lugar . Por ejemplo:
  
|**Descripción**|**Patrón de coincidencia**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Convierte números de 5 dígitos para el número de teléfono y extensión de un usuario  <br/> |^ (\d{5})$  <br/> |+14255550123; ext = $1  <br/> |10001 se traduce a +14255550123; ext = 10001  <br/> |
|Convierte números de 5 dígitos para el número de teléfono de la organización y la extensión de un usuario  <br/> |^ (\d{5})$  <br/> |+14255550100; ext = $1  <br/> |10001 se traduce a +14255550100; ext = 10001  <br/> |
   
En este escenario, si el interlocutor de tronco que controla el redireccionamiento a la RTC no admite números de extensión, a continuación, la regla de conversión de salida también debe quitar el número de extensión. Por ejemplo:
  
|**Descripción**|**Patrón de coincidencia**|**Traducción**|**Ejemplo**|
|:-----|:-----|:-----|:-----|
|Quita la extensión de los números de teléfono con extensiones  <br/> |^\+(\d\*); $ ext=(\d\*)  <br/> |+$1  <br/> |+14255550123; ext = 10001 se traduce a +14255550123  <br/> |
   
Si es o no un vínculo WAN disponible si su organización no tiene HICIERON configurado para los usuarios individuales de números y el URI de la línea de un usuario contiene el número de teléfono de la organización y el número de extensión exclusiva del usuario, debe configurar su número línea telefónica de la organización URI con un número que es accesible por el interlocutor de tronco o puerta de enlace PSTN en el sitio de la sucursal. También debe configurar la línea de número de teléfono de su organización URI para incluir su propia extensión exclusiva para las llamadas a enrutarse a ese número.
  
#### <a name="preparing-for-voice-mail-survivability"></a>Preparación para la supervivencia de correo de voz

Generalmente, Exchange Unified Messaging (UM) está instalado sólo en un sitio central y no en los sitios de sucursal. Un llamador podrá dejar un mensaje de correo de voz, incluso si el vínculo WAN entre los sitios de sucursal y central no está disponible. Como resultado, la configuración de los URI de línea para el número de teléfono de Operador automático en mensajería unificada de Exchange proporciona correo de voz para los usuarios del sitio de sucursal requiere consideraciones especiales, además de la directiva de voz dial plan y reglas de normalización aplicables a ese correo de voz número.
  
Que sobreviven de rama de supervivencia (SBA) y servidores de sucursal que sobreviven proporcionan la supervivencia de correo de voz para los usuarios de sucursales durante una interrupción de la WAN. En concreto, si está utilizando un dispositivo de la rama que sobreviven o servidor de sucursal que sobreviven y la WAN no está disponible, la SBA o el servidor de sucursal que sobreviven redistribuye llamadas no respondidas por PSTN para mensajería unificada de Exchange en el sitio central. Con un servidor de sucursal que sobreviven o de SBA, los usuarios también pueden recuperar mensajes de correo de voz a través de la red PSTN durante una interrupción de la WAN. Finalmente, durante una interrupción de la WAN del dispositivo de sucursal que sobreviven o servidor de sucursal que sobreviven pone en cola las notificaciones de llamada perdida y, a continuación, las cargas en el servidor de mensajería unificada de Exchange cuando se restaura la WAN. Para asegurar que el redireccionamiento de correo de voz es resistente, asegúrese de que se agregue una entrada para el FQDN del grupo de servidores del sitio central y una entrada para el FQDN del servidor de borde al archivo hosts en el servidor de sucursal que sobreviven. De lo contrario, la resolución DNS puede tiempo de espera si no tiene un servidor DNS en el sitio de la sucursal.
  
Se recomienda la siguiente configuración para la supervivencia de correo de voz para los usuarios del sitio de sucursal: 
  
- Un administrador de Microsoft Exchange debe configurar Exchange UM Operador automático (AA) para aceptar sólo los mensajes. Esta configuración deshabilita todas las otras funciones genéricas, como transferencia a un usuario o a un operador y limita el AA para que solamente acepten mensajes. Como alternativa, puede utilizar el Administrador de Exchange una AA genérico o un AA personalizado para enrutar la llamada a un operador.
    
- El Skype para el Administrador de servidor de Business debe tomar el número de teléfono de AA y utilizar ese número de teléfono como el número de **exchange um auto attendant** en el correo de voz redireccionamiento de configuración para el dispositivo de sucursal que sobreviven o servidor de sucursal.
    
- El Skype para el administrador del servidor de la empresa debe obtener número de teléfono de acceso de suscriptor de mensajería unificada de Exchange y utilizará ese número como el número de **acceso de suscriptor** en el correo de voz redireccionamiento de configuración para el dispositivo de sucursal que sobreviven o servidor de la sucursal que sobreviven .
    
- El Skype para el administrador del servidor de la empresa debe configurar mensajería unificada de Exchange, por lo que sólo un plan de marcado está asociado a todos los usuarios de sucursales que necesitan tener acceso a correo de voz durante una interrupción de la WAN.
    
- Cuando el vínculo WAN no está disponible, las llamadas a los usuarios del sitio de sucursal se pueden enrutar al buzón de voz de Exchange Unified Messaging (UM) del usuario, pero sólo si se aplica la directiva de voz a la llamada especifica un número de teléfono del correo de voz que es único y no incluye una extensión número.
    
#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware y Software para el sitio de la sucursal resistencia

Los requisitos de hardware y software varían dependiendo de la solución de resistencia.
  
#### <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para los dispositivos de la rama que sobreviven

Software y hardware necesario está integrado en el dispositivo de la rama que sobreviven. Sin embargo, también se recomienda que cada sitio de sucursal implementar un servidor DHCP para obtener direcciones IP; de cliente de lo contrario, cuando la concesión DHCP caduca, los clientes no tendrán conectividad IP.
  
Si los servidores DNS de empresa se encuentran únicamente en los sitios centrales, los usuarios del sitio de sucursal no podrán conectarse a ellos durante una interrupción de la WAN y, por tanto, se producirá un error de Skype para el descubrimiento de Business Server que utiliza DNS SRV (registro de recursos de servicio (SRV)). Para asegurar el redireccionamiento de petición de datos durante una interrupción de la WAN, deben almacenarse en caché registros DNS en el sitio de la sucursal. Si lo admite el enrutador de la sucursal, activar el almacenamiento en caché de DNS. O bien, puede implementar un servidor DNS en la sucursal. Esto puede ser un servidor independiente o una versión del dispositivo que sobreviven rama que admite capacidades de DNS. Para obtener más información, póngase en contacto con el proveedor del dispositivo de sucursal que sobreviven.
  
> [!NOTE]
> No es necesario disponer de un controlador de dominio en un sitio de sucursal. El dispositivo de la rama que sobreviven autentica a los clientes mediante un certificado especial que envía al cliente como respuesta a la solicitud de certificado de cliente cuando inicia una sesión. 
  
Skype para clientes de empresa puede descubrir el Skype para Business Server utilizando DHCP opción 120 (opción de registrador SIP). Esto puede configurarse de dos maneras:
  
- Configurar el servidor DHCP en el sitio de la sucursal para responder a las consultas de 120 de DHCP, que devuelven el nombre completo del registrador en el dispositivo de sucursal que sobreviven o un servidor de sucursal que sobreviven.
    
- Activar Skype para Business Server DHCP. Cuando esto está activado, el Skype para Registrar servidor de negocio responde a las consultas de 120 de opción de DHCP. Tenga en cuenta que el registrador no responde a las consultas DHCP que no sean de 120 de opciones DHCP.
    
Además, para los sitios de sucursales más grandes que tienen varias subredes, los agentes de retransmisión DHCP deben estar habilitados para reenviar consultas de 120 de opción de DHCP al servidor DHCP (configuración 1) o al registrador (configuración 2).
  
Por último, los usuarios del sitio de sucursal deben ser configurados para Telefonía IP empresarial y provisionados de un extremo de comunicaciones unificadas apropiado.
  
#### <a name="requirements-for-survivable-branch-servers"></a>Requisitos de servidores de sucursal que sobreviven

Los requisitos para los servidores de sucursal que sobreviven son lo mismo que los requisitos para un servidor Front-End. Para obtener más información, consulte [requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Requisitos de Skype a gran escala para implementaciones de Business Server sitio de sucursal

Para obtener más información, vea [requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) en la documentación de planeamiento.
  
### <a name="example-configuring-a-failover-route"></a>Ejemplo: configuración de una ruta de conmutación por error

 En el ejemplo siguiente se muestra cómo un administrador puede definir una ruta de conmutación por error para su uso si el GW1 de Dallas se encuentra inactiva para mantenimiento o no está disponible. Las tablas siguientes ilustran el cambio de configuración necesario.
  
**La tabla 1. Directiva de usuario**

|**Directiva de usuario**|**Uso del teléfono**|
|:-----|:-----|
|Directiva predeterminada de llamada  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Directiva Local de Redmond  <br/> |RedmondLocal  <br/> |
|Directiva de llamada de Dallas  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |
   
**La tabla 2. Rutas**

|**Nombre de ruta**|**Patrón de números**|**Uso del teléfono**|**Tronco**|**Puerta de enlace**|
|:-----|:-----|:-----|:-----|:-----|
|Ruta Local de Redmond  <br/> |^\+1 (425|206|$ 253)(\d{7})  <br/> |Local  <br/> RedmondLocal  <br/> |Trunk1  <br/> Trunk2  <br/> |Rojo-GW1  <br/> Rojo-GW2  <br/> |
|Ruta Local de Dallas  <br/> |^\+1 (972|214|$ 469)(\d{7})  <br/> |Local  <br/> |Trunk3  <br/> |GW1 de Dallas  <br/> |
|Ruta universal  <br/> |^\+?(\d\*)$  <br/> |GlobalPSTNHopoff  <br/> |Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> |Rojo-GW1  <br/> Rojo-GW2  <br/> GW1 de Dallas  <br/> |
|Ruta de los usuarios de Dallas  <br/> |^\+?(\d\*)$  <br/> |DallasUsers  <br/> |Trunk3  <br/> |GW1 de Dallas  <br/> |
   
En la tabla 1, se agrega un uso de teléfono de GlobalPSTNHopoff después de la DallasUsers uso en la directiva de Dallas llamada de teléfono. Esto habilita las llamadas con la directiva de Dallas llamando a utilizar rutas que se configuran para el uso de teléfono GlobalPSTNHopoff, si está disponible una ruta para el uso de teléfono DallasUsers.
  

