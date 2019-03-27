---
title: Requisitos de hardware y software para conferencias en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Resumen: Lea este tema para obtener más información acerca de los requisitos de hardware y software para conferencias en Skype para Business Server.'
ms.openlocfilehash: 3385395eb34e69fadcdce4ba4bf529a347a2979c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883931"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Requisitos de hardware y software para conferencias en Skype para Business Server

**Resumen:** Lea este tema para obtener más información acerca de los requisitos de hardware y software para conferencias en Skype para Business Server.

En esta sección se describe los requisitos de hardware y software para las conferencias web, audio y vídeo (A / V) conferencias, conferencia de acceso telefónico y conferencias de mensajería instantánea (IM). Todas las funciones de conferencia que se ejecutan en servidores Front-End; Existen requisitos adicionales para diferentes tipos de conferencia, como se muestra en el siguiente diagrama.

Por ejemplo, si desea permitir la conferencia de acceso telefónico, debe implementar un servidor de mediación y una puerta de enlace para conectar a la red telefónica conmutada (RTC). Si desea permitir la conferencia web, debe asegurarse de que Skype para Business Server puede conectarse a un servidor de Office Web Apps. Si desea permitir que los usuarios externos participen en las conferencias, necesitará implementar un servidor perimetral.

**Características y requisitos de conferencia**

![Componentes de conferencia](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Para obtener más información acerca de las consideraciones de topología, consulte [planeación de la topología de conferencia de Skype para Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Requisitos de hardware y software de los servidores front-end

Debido a que conferencia web, / conferencia A/v, conferencia de acceso telefónico y conferencias de mensajería instantánea se combinan con el servidor Front-End, los requisitos de hardware y software de servidor son los mismos que los servidores Front-End. Para obtener información detallada acerca de estos requisitos, vea [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) y [requisitos de entorno para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Requisitos para las conferencias web

Si ha elegido habilitar la conferencia web, tiene que planear lo siguiente:

- Obtenga acceso al almacén de archivos, que se usa para almacenar contenido de conferencia web.

- Integración con Office Web Apps Server, que es necesaria para compartir archivos de PowerPoint durante una conferencia.

### <a name="file-store"></a>Almacén de archivos

El Skype para el servicio de conferencias web de Business Server almacena contenido compartido durante las reuniones en el almacén de archivos. Como parte de la implementación, debe especificar un recurso compartido de archivos que se usará como el almacén de archivos para el servidor Standard Edition o grupo de servidores Front-End de Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especificar uno nuevo indicando el nombre de dominio completo del servidor de archivos donde necesita ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso. Para obtener más información, vea [crear un recurso compartido de archivos en Skype para Business Server](../../deploy/install/create-a-file-share.md). El servicio de conferencia web cifra el contenido antes de almacenarlo en el almacén de archivos.

Skype para Business Server admite el uso de recursos compartidos de archivos en almacenamiento de conexión directa (DAS) o una red de área de almacenamiento (SAN), incluido el sistema de archivos distribuido (DFS) y en una matriz redundante de discos independientes (RAID) para los almacenes de archivos. Después de la Skype para el Asistente para la implementación de Business Server ha definido la ubicación del recurso compartido de archivos, Skype para Business Server crea similar a una estructura de carpetas en el recurso compartido de archivos:

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

El servicio de conferencia web almacena entonces el contenido como diapositivas de PowerPoint, pizarras, sondeos y datos adjuntos en las carpetas CollabContent y CollabMetadata, que se encuentran en la carpeta WebServices.

### <a name="office-web-apps-server"></a>Servidor Office Web Apps

Para poder usar las capacidades de conferencia web, debe instalar a Office Web Apps Server y configurar Skype para Business Server para comunicarse con Office Web Apps Server.

Office Web Apps Server debe instalarse en un equipo independiente que no se está ejecutando Skype para Business Server, SQL Server o cualquier otra aplicación de servidor. (No debe tener cualquier versión de Office instalada en el equipo.) Cualquier equipo que se usa para ejecutar Office Web Apps Server también debe tener un conjunto específico de software instalado (incluidos .NET Framework 4.5 y Windows PowerShell 3.0). Estos requisitos, junto con información sobre la configuración de certificados y servicios de Internet Information Server (IIS), se analizan detalladamente el [sitio Web de implementación de Microsoft Office Web Apps](https://go.microsoft.com/fwlink/p/?linkid=257525).

Para obtener información acerca de cómo configurar Skype para Business Server para que funcione con Office Web Apps Server, vea [Configurar la integración con Office Web Apps Server en Skype para Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Requisitos para conferencias de audio y vídeo

Para planear una conferencia A/V, necesita conocer el ancho de banda necesario para el tipo de medio de conferencia que requiere su organización. Esto podría incluir audio, vídeo y vídeo panorámico. Si el ancho de banda de red no es suficiente, la experiencia del usuario puede verse afectada en gran medida.

Para más información sobre la planificación de capacidad de audio y vídeo para conferencias, vea [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md).

Puede usar el servicio de control de admisión de llamadas (CAC) para administrar el ancho de banda de red que se usa en las conferencias A/V. Esto es importante para redes restringidas, como vínculos de ancho de banda limitados entre los sitios centrales y de sucursal. Para obtener información detallada, consulte [Plan para el control de admisión de llamadas en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Si implementa las audioconferencias en su red, los usuarios necesitarán dispositivos de audio, como pueden ser auriculares, para participar en las audioconferencias. Si implementa las videoconferencias, necesita implementar dispositivos de vídeo, como cámaras web para los usuarios. Tanto para los dispositivos de audio como para los de vídeo, la implementación de los dispositivos y el aprendizaje de los usuarios son pasos importantes que hay que tener en cuenta. Para obtener más información, consulte [Plan para clientes y dispositivos](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft recomienda que use los dispositivos de comunicaciones unificadas (UC) certificados por Microsoft para todos los tipos de dispositivos, con el fin de garantizar una experiencia óptima para el usuario. Para obtener información detallada acerca de dispositivos certificados de comunicaciones unificadas, vea [teléfonos y dispositivos para Skype para la empresa](https://go.microsoft.com/fwlink/?LinkId=619916).

## <a name="requirements-for-dial-in-conferencing"></a>Requisitos para conferencias de acceso telefónico local

Conferencia de acceso telefónico es una característica opcional de la Skype para la carga de trabajo de conferencias de Business Server que incluye una variedad de componentes. Algunos de los componentes que son específicas a la conferencia de acceso telefónico y algunos son componentes de Enterprise Voice. En esta sección se describe los requisitos para los componentes que se necesitan para conferencias de acceso telefónico. Para obtener información detallada sobre el servidor de mediación y requisitos de puerta de enlace de telefónica conmutada (RTC) de red, vea el [componente de servidor de mediación en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) e [implementar un servidor de mediación en el generador de Skype para Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Componentes requeridos

Debe instalar el siguiente Skype para los componentes de Business Server antes de poder configurar conferencia de acceso telefónico:

- Servicio de aplicaciones de comunicaciones unificadas (UCAS) (denominado el servicio de aplicación)

- Aplicación Operador de conferencia

- Aplicación de anuncio de conferencia

- Página web de configuración de la conferencia de acceso telefónico local

- Al menos un servidor de mediación y al menos una puerta de enlace RTC

Para conferencias de acceso telefónico, servicio de la aplicación, la aplicación operador de conferencia y la aplicación de anuncio de conferencia tienen los mismos requisitos de sistema operativo como servidores Front-End. Para más información, vea [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

Aplicación operador de conferencia y aplicación de anuncio de conferencia requieren que esté instalado el tiempo de ejecución de Windows Media Format en servidores Front-End. El tiempo de ejecución de Windows Media Format es necesario para reproducir archivos de Windows Media Audio (WMA) que se usan para la música en espera, nombres registrados y avisos. Si va a instalar en Windows Server 2012 o Windows Server 2012 R2 (que se recomienda), debe instalar Microsoft Media Foundation para obtener el tiempo de ejecución de Windows Media Format. Si va a instalar en cualquier versión de Windows Server anterior a Windows 2012, necesitará asegurarse de que la experiencia de escritorio de Windows esté instalada para obtener el tiempo de ejecución de Windows Media Format.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisitos de archivo de audio para conferencias de acceso telefónico local

Skype para Business Server no admite la personalización de los mensajes de voz y música para conferencias de acceso telefónico. Sin embargo, si tiene una necesidad empresarial seguro que requiere que se cambie los archivos de audio de forma predeterminada, vea el artículo de Microsoft Knowledge Base 961177, [cómo personalizar los mensajes de voz o archivos de música para conferencias de audio de acceso telefónico](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177).

También puede usar la utilidad de administración de [Microsoft Lync Server conferencia operador personalizado mensajes de voz](https://go.microsoft.com/fwlink/p/?LinkId=396880) , que permite a los administradores reemplazar los mensajes de voz predeterminado utilizados cuando un autor de llamada de teléfono se une a una Skype para la reunión de negocios con los mensajes personalizados para proporcionar una reunión diferente experiencia de entrada. Los mensajes de voz personalizados pueden instalarse en un servidor Enterprise o Standard Edition.

Aplicación operador de conferencia y aplicación de anuncio de conferencia tienen los siguientes requisitos para la música en espera, nombre grabado y archivos de audio de símbolo del sistema:

- Formato de archivo de audio de Windows Media (WMA)

- Mono de 16 bits

- 48 kbps CBR 2 pasos (velocidad de bits constante)

- Nivel de voz a -24DB

### <a name="user-requirements-for-dial-in-conferencing"></a>Requisitos de usuario para conferencias de acceso telefónico local

Los usuarios de conferencias de acceso telefónico local necesitan tener un número de teléfono único o una extensión asignada a su cuenta. Este requisito admite la autenticación durante las conferencias de acceso telefónico local. Los usuarios de empresa (es decir, los usuarios que tienen credenciales de servicios de dominio de Active Directory y Skype para las cuentas de Business Server dentro de la organización) escriben su número de teléfono (o la extensión) y un número de identificación personal (PIN) para conectarse a conferencias como un usuario autenticado.

## <a name="port-requirements-for-conferencing"></a>Requisitos de puerto para conferencias

Para poder usar las características de conferencia, Skype para Business Server requiere que estén abiertos determinados puertos. La siguiente tabla enumera los requisitos de los puertos para conferencias. Para obtener información detallada acerca de todos los requisitos de puerto, vea [requisitos de protocolo y puerto para los servidores](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Puertos de servidor necesarios**


|**Rol de servidor**|**Nombre de servicio**|**Puerto**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores front-end  <br/> |Skype para el servicio de conferencia de mensajería instantánea de servidor empresarial  <br/> |5062  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencia Web de Business Server  <br/> |8057  <br/> |TCP (TLS)  <br/> |Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de compatibilidad de conferencia Web Business Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Se usa para escuchar las conexiones del modelo de objetos de compartidos persistente (PSOM) desde el cliente de Live Meeting y versiones anteriores de Skype para Business Server.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencia de Audio y vídeo de servidor empresarial  <br/> |5063  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencia de Audio y vídeo de servidor empresarial  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervalo de puertos de medios que se usa para conferencias de vídeo.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de operador de conferencia del servidor empresarial (telefónico)  <br/> |5064  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de acceso telefónico local.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de operador de conferencia del servidor empresarial (telefónico)  <br/> |5072  <br/> |TCP  <br/> |Se utiliza para las solicitudes SIP entrantes operador (conferencia de acceso telefónico).  <br/> |
|Servidores front-end  <br/> |Skype para uso compartido de Business Server aplicaciones de servicio  <br/> |5065  <br/> |TCP  <br/> |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  <br/> |
|Servidores front-end  <br/> |Skype para uso compartido de Business Server aplicaciones de servicio  <br/> |49152-65535  <br/> |TCP  <br/> |Intervalo de puertos de medios que se usa para compartir aplicaciones.  <br/> |
|Servidores front-end  <br/> |Skype para servicio de anuncio de conferencia del servidor empresarial  <br/> |5073  <br/> |TCP  <br/> |Se utiliza para las solicitudes SIP entrantes de la Skype para servicio de anuncio de conferencia del servidor empresarial (es decir, para conferencias de acceso telefónico).  <br/> |
|Todos los usuarios internos  <br/> |Varios  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |El intervalo de puertos de medios se usa para audioconferencias en todos los servidores internos. Utilizado por todos los servidores que terminar audio: servidores Front-End (para Skype para el servicio de operador de conferencia del servidor empresarial, Skype para servicio de anuncio de conferencia del servidor empresarial y Skype para el servicio de conferencia de Audio y vídeo de servidor empresarial), y Servidor de mediación.  <br/> |
|Servidores de Office Web Apps  <br/> ||443  <br/> ||Usa Skype para Business Server para conectarse a Office Web Apps Server.  <br/> |

**Puertos de cliente requerida**


|**Puerto**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Se usa para el acceso de usuarios externos a las sesiones de conferencia web.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP).  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Se usa para el acceso de usuarios externos a los medios y las sesiones de A/V (UDP)  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de puertos de audio (se requieren 20 puertos como mínimo).  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo).  <br/> |
|1024-65535\*  <br/> |TCP  <br/> |Uso compartido de aplicaciones.  <br/> |


