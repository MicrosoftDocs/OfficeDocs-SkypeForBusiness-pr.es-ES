---
title: Requisitos de hardware y software para conferencias en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Resumen: Lea este tema para obtener información sobre los requisitos de hardware y software para las conferencias en Skype empresarial Server.'
ms.openlocfilehash: c4efb85c7ae1674cab7ee123833df779a835e14c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277345"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Requisitos de hardware y software para conferencias en Skype empresarial Server

**Resumen:** Lea este tema para obtener información sobre los requisitos de hardware y software para las conferencias en Skype empresarial Server.

En esta sección se describen los requisitos de hardware y software para las conferencias web, las conferencias de audio y vídeo (A/V), las conferencias de acceso telefónico local y las conferencias de mensajería instantánea (mi). Todas las capacidades de conferencia se ejecutan en servidores frontales; Existen requisitos adicionales para diferentes tipos de conferencias, como se muestra en el siguiente diagrama.

Por ejemplo, si desea permitir las conferencias de acceso telefónico local, tendrá que implementar un servidor de mediación y una puerta de enlace para conectarse a la red de telefonía pública conmutada (RTC). Si desea permitir las conferencias web, tendrá que asegurarse de que Skype empresarial Server pueda conectarse a un servidor de Office Web Apps. Si desea permitir que los usuarios externos participen en las conferencias, necesitará implementar un servidor perimetral.

**Características y requisitos de conferencia**

![Componentes de conferencia](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Para obtener más información acerca de las consideraciones de topología, consulte [planear la topología de conferencias de Skype empresarial Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Requisitos de hardware y software de los servidores front-end

Debido a que las conferencias web, A/V, las conferencias de acceso telefónico local y las conferencias de mensajería instantánea se colocan en el servidor front-end, los requisitos de software y hardware del servidor son los mismos que los servidores front-end. Para obtener más información sobre estos requisitos, consulte [requisitos del servidor para Skype empresarial server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) y [requisitos ambientales para skype empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisitos de servidor para Skype empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Requisitos para las conferencias web

Si ha elegido habilitar la conferencia web, tiene que planear lo siguiente:

- Obtenga acceso al almacén de archivos, que se usa para almacenar contenido de conferencia web.

- Integración con Office Web Apps Server, que es necesaria para compartir archivos de PowerPoint durante una conferencia.

### <a name="file-store"></a>Almacén de archivos

El servicio de conferencias por Internet de Skype empresarial Server almacena contenido compartido durante las reuniones en el almacén de archivos. Como parte de la implementación, debe especificar un recurso compartido de archivos para que se use como almacén de archivos del servidor Standard Edition o del grupo front-end de Enterprise Edition. Para ello, use un recurso compartido de archivos ya creado o especificar uno nuevo indicando el nombre de dominio completo del servidor de archivos donde necesita ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso. Para obtener más información, vea [crear un recurso compartido de archivos en Skype empresarial Server](../../deploy/install/create-a-file-share.md). El servicio de conferencia web cifra el contenido antes de almacenarlo en el almacén de archivos.

Skype empresarial Server admite el uso de archivos compartidos en almacenamiento de conexión directa (DAS) o en una red de área de almacenamiento (SAN), incluido el sistema de archivos distribuido (DFS) y en una matriz redundante de discos independientes (RAID) para los almacenes de archivos. Una vez que el Asistente para la implementación de Skype empresarial Server haya definido la ubicación del recurso compartido de archivos, Skype empresarial Server creará una estructura de carpetas dentro del recurso compartido de archivos similar a:

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

El servicio de conferencia web almacena entonces el contenido como diapositivas de PowerPoint, pizarras, sondeos y datos adjuntos en las carpetas CollabContent y CollabMetadata, que se encuentran en la carpeta WebServices.

### <a name="office-web-apps-server"></a>Servidor Office Web Apps

Para poder usar las capacidades de conferencias web, debe instalar Office Web Apps Server y configurar Skype empresarial Server para comunicarse con Office Web Apps Server.

Office Web Apps Server debe instalarse en un equipo independiente que no esté ejecutando Skype empresarial Server, SQL Server o cualquier otra aplicación de servidor. (No debe tener ninguna versión de Office instalada en ese equipo). Cualquier equipo usado para ejecutar Office Web Apps Server también debe tener instalado un conjunto específico de software (incluidos .NET Framework 4,5 y Windows PowerShell 3,0). Estos requisitos, junto con información sobre cómo configurar certificados y servicios de información de Internet (IIS), se tratan en detalle en el [sitio web de implementación de Microsoft Office Web Apps](https://go.microsoft.com/fwlink/p/?linkid=257525).

Para obtener más información sobre cómo configurar Skype empresarial Server para que funcione con Office Web Apps Server, consulte [configurar la integración con Office Web Apps Server en Skype empresarial Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Requisitos para conferencias de audio y vídeo

Para planear una conferencia A/V, necesita conocer el ancho de banda necesario para el tipo de medio de conferencia que requiere su organización. Esto podría incluir audio, vídeo y vídeo panorámico. Si el ancho de banda de red no es suficiente, la experiencia del usuario puede verse afectada en gran medida.

Para más información sobre la planificación de capacidad de audio y vídeo para conferencias, vea [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md).

Puede usar el servicio de control de admisión de llamadas (CAC) para administrar el ancho de banda de red que se usa en las conferencias A/V. Esto es importante para redes restringidas, como vínculos de ancho de banda limitados entre los sitios centrales y de sucursal. Para obtener más información, consulte [plan para el control de admisión de llamadas en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Si implementa las audioconferencias en su red, los usuarios necesitarán dispositivos de audio, como pueden ser auriculares, para participar en las audioconferencias. Si implementa las videoconferencias, necesita implementar dispositivos de vídeo, como cámaras web para los usuarios. Tanto para los dispositivos de audio como para los de vídeo, la implementación de los dispositivos y el aprendizaje de los usuarios son pasos importantes que hay que tener en cuenta. Para obtener más información, vea [planear clientes y dispositivos](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft recomienda que use los dispositivos de comunicaciones unificadas (UC) certificados por Microsoft para todos los tipos de dispositivos, con el fin de garantizar una experiencia óptima para el usuario. Para obtener más información sobre los dispositivos certificados con UC, consulte [teléfonos y dispositivos para Skype empresarial](https://go.microsoft.com/fwlink/?LinkId=619916).

## <a name="requirements-for-dial-in-conferencing"></a>Requisitos para conferencias de acceso telefónico local

Las conferencias de acceso telefónico local son una característica opcional de la carga de trabajo de conferencia de Skype empresarial Server que incluye una variedad de componentes. Algunos de los componentes son específicos de las conferencias de acceso telefónico local y otros son componentes de telefonía empresarial. En esta sección se describen los requisitos de los componentes necesarios para las conferencias de acceso telefónico local. Para obtener más información sobre los requisitos de la puerta de enlace de la red de telefonía pública conmutada (RTC), consulte [componente servidor de mediación en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) e [implementar un servidor de mediación en el generador de topologías de Skype empresarial Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Componentes requeridos

Tendrá que instalar los siguientes componentes de Skype empresarial Server para poder configurar las conferencias de acceso telefónico local:

- Servicio de aplicaciones de comunicaciones unificadas (UCAS) (denominado el servicio de aplicación)

- Aplicación Operador de conferencia

- Aplicación de anuncio de conferencia

- Página web de configuración de la conferencia de acceso telefónico local

- Al menos un servidor de mediación y al menos una puerta de enlace RTC

Para las conferencias de acceso telefónico local, servicio de aplicaciones, operador de conferencias y aplicación de anuncio de Conferencia tienen los mismos requisitos del sistema operativo que los servidores de aplicaciones para el usuario. Para más información, vea [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

El Asistente de conferencia y la aplicación de anuncio de conferencia requieren que Windows Media Format Runtime esté instalado en los servidores frontales. El tiempo de ejecución de Windows Media Format es necesario para reproducir archivos de Windows Media Audio (WMA) que se usan para la música en espera, nombres registrados y avisos. Si está instalando en Windows Server 2012 o Windows Server 2012 R2 (lo que recomendamos), tendrá que instalar Microsoft Media Foundation para obtener el tiempo de ejecución de Windows Media Format. Si va a instalar en cualquier versión de Windows Server anterior a Windows 2012, necesitará asegurarse de que la experiencia de escritorio de Windows esté instalada para obtener el tiempo de ejecución de Windows Media Format.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisitos de archivo de audio para conferencias de acceso telefónico local

Skype empresarial Server no admite la personalización de mensajes de voz y de música para conferencias de acceso telefónico local. Sin embargo, si tiene una gran necesidad comercial que le exija cambiar los archivos de audio predeterminados, consulte el artículo 961177 de Microsoft Knowledge base, [Cómo personalizar las solicitudes de voz o los archivos de música para conferencias de audio de acceso telefónico local](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177).

También puede usar la herramienta de administración de [solicitudes de voz personalizadas del operador de conferencias de Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=396880) , que permite a los administradores reemplazar los mensajes de voz predeterminados que se usan cuando una llamada de teléfono se une a una reunión de Skype empresarial con avisos personalizados para proporcionar una experiencia de entrada de reunión diferente. Los mensajes de voz personalizados pueden instalarse en un servidor Enterprise o Standard Edition.

El operador de conferencia y la aplicación de anuncio de Conferencia tienen los siguientes requisitos de música en espera, nombre grabado y archivos de solicitud de audio:

- Formato de archivo de audio de Windows Media (WMA)

- Mono de 16 bits

- 48 kbps CBR 2 pasos (velocidad de bits constante)

- Nivel de voz a -24DB

### <a name="user-requirements-for-dial-in-conferencing"></a>Requisitos de usuario para conferencias de acceso telefónico local

Los usuarios de conferencias de acceso telefónico local necesitan tener un número de teléfono único o una extensión asignada a su cuenta. Este requisito admite la autenticación durante las conferencias de acceso telefónico local. Los usuarios empresariales (es decir, los usuarios que tienen credenciales de servicios de dominio de Active Directory y cuentas de Skype empresarial Server dentro de su organización) escriben su número de teléfono (o extensión) y un número de identificación personal (PIN) para llamar a conferencias como un usuario autenticado.

## <a name="port-requirements-for-conferencing"></a>Requisitos de puerto para conferencias

Para poder usar las características de conferencia, Skype empresarial Server requiere que determinados puertos estén abiertos. La siguiente tabla enumera los requisitos de los puertos para conferencias. Para obtener más información sobre los requisitos de puertos, consulte [requisitos de puertos y protocolos para servidores](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Puertos de servidor necesarios**


|**Rol de servidor**|**Nombre de servicio**|**Puerto**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores front-end  <br/> |Servicio de conferencia de mensajería instantánea de Skype empresarial Server  <br/> |5062  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.  <br/> |
|Servidores front-end  <br/> |Servicio de conferencias por Internet de Skype empresarial Server  <br/> |8057  <br/> |TCP (TLS)  <br/> |Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.  <br/> |
|Servidores front-end  <br/> |Servicio de compatibilidad con conferencias web de Skype empresarial Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Se usa para escuchar conexiones persistentes del modelo de objetos compartidos (PSOM) del cliente de Live Meeting y de las versiones anteriores de Skype empresarial Server.  <br/> |
|Servidores front-end  <br/> |Servicio de videoconferencias de audio y videollamadas de Skype empresarial Server  <br/> |5063  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).  <br/> |
|Servidores front-end  <br/> |Servicio de videoconferencias de audio y videollamadas de Skype empresarial Server  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervalo de puertos de medios que se usa para conferencias de vídeo.  <br/> |
|Servidores front-end  <br/> |Servicio del operador de conferencias de Skype empresarial Server (Conferencia de acceso telefónico local)  <br/> |5064  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de acceso telefónico local.  <br/> |
|Servidores front-end  <br/> |Servicio del operador de conferencias de Skype empresarial Server (Conferencia de acceso telefónico local)  <br/> |5072  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes para operadores (llamar en conferencia).  <br/> |
|Servidores front-end  <br/> |Servicio de uso compartido de aplicaciones de Skype empresarial Server  <br/> |5065  <br/> |TCP  <br/> |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  <br/> |
|Servidores front-end  <br/> |Servicio de uso compartido de aplicaciones de Skype empresarial Server  <br/> |49152-65535  <br/> |TCP  <br/> |Intervalo de puertos de medios que se usa para compartir aplicaciones.  <br/> |
|Servidores front-end  <br/> |Servicio de anuncios de conferencias de Skype empresarial Server  <br/> |5073  <br/> |TCP  <br/> |Se usa para solicitudes SIP entrantes para el servicio de anuncios de conferencias de Skype empresarial Server (es decir, para conferencias de acceso telefónico local).  <br/> |
|Todos los usuarios internos  <br/> |Varios  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |El intervalo de puertos de medios se usa para audioconferencias en todos los servidores internos. Usado por todos los servidores que terminan audio: servidores front-end (para el servicio del operador de conferencias de Skype empresarial Server, servicio de anuncios de conferencias de Skype empresarial Server y servicio de videoconferencia de audio y videollamada de Skype empresarial), y Servidor de mediación.  <br/> |
|Servidores de Office Web Apps  <br/> ||443  <br/> ||Usado por Skype empresarial Server para conectarse a Office Web Apps Server.  <br/> |

**Puertos de cliente necesarios**


|**Puerto**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Se usa para el acceso de usuarios externos a las sesiones de conferencia web.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP).  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Se usa para el acceso de usuarios externos a los medios y las sesiones de A/V (UDP)  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de puertos de audio (se requieren 20 puertos como mínimo).  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo).  <br/> |
|1024-65535\*  <br/> |TCP  <br/> |Uso compartido de aplicaciones.  <br/> |


