---
title: Requisitos de hardware y software para conferencias en Skype Empresarial Server
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
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Resumen: lea este tema para obtener información sobre los requisitos de hardware y software para conferencias en Skype Empresarial Server.'
ms.openlocfilehash: 6ffa86266d8782e9e49c708998714bef4dbbed51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118519"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>Requisitos de hardware y software para conferencias en Skype Empresarial Server

**Resumen:** Lea este tema para obtener información sobre los requisitos de hardware y software para conferencias en Skype Empresarial Server.

En esta sección se describen los requisitos de hardware y software para conferencias web, conferencias de audio y vídeo (A/V), conferencias de acceso telefónico local y conferencias de mensajería instantánea (MI). Todas las funciones de conferencia se ejecutan en servidores front-end; existen requisitos adicionales para distintos tipos de conferencia, como se muestra en el siguiente diagrama.

Por ejemplo, si desea permitir conferencias de acceso telefónico local, deberá implementar un servidor de mediación y una puerta de enlace para conectarse a la red telefónica conmutada (RTC). Si desea permitir conferencias web, deberá asegurarse de que Skype Empresarial Server pueda conectarse a un servidor de Office Web Apps. Si desea permitir que los usuarios externos participen en conferencias, deberá implementar un servidor perimetral.

**Requisitos y capacidades de conferencia**

![Componentes de conferencia](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 Para obtener más información acerca de las consideraciones de topología, vea [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Requisitos de hardware y software para servidores front-end

Dado que las conferencias web, las conferencias A/V, las conferencias de acceso telefónico local y las conferencias de mensajería instantánea se asocian con el servidor front-end, los requisitos de hardware y software del servidor son los mismos que para los servidores front-end. Para obtener más información sobre estos requisitos, vea Requisitos del servidor para Skype Empresarial [Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) y Requisitos del entorno [para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o Requisitos de servidor para Skype Empresarial [Server 2019](../../../SfBServer2019/plan/system-requirements.md).

## <a name="requirements-for-web-conferencing"></a>Requisitos para conferencias web

Si ha elegido habilitar la conferencia web, debe planear lo siguiente:

- Acceso al almacén de archivos, que se usa para almacenar contenido de conferencia web.

- Integración con Office Web Apps Server, que es necesaria para compartir archivos de PowerPoint durante una conferencia.

### <a name="file-store"></a>Almacén de archivos

El servicio de conferencia web de Skype Empresarial Server almacena el contenido compartido durante las reuniones en el almacén de archivos. Como parte de la implementación, debe especificar un recurso compartido de archivos que se usará como almacén de archivos para el servidor Standard Edition o el grupo de servidores front-end Enterprise Edition. Puede utilizar un recurso compartido de archivos existente como almacén o elegir uno nuevo especificando el nombre de dominio completo (FQDN) del servidor de archivos en el que se deba ubicar el recurso compartido de archivos y un nombre de carpeta para el nuevo recurso compartido de archivos. Para obtener más información, vea [Create a file share in Skype for Business Server](../../deploy/install/create-a-file-share.md). El servicio de conferencia web cifra el contenido antes de almacenarlo en el almacén de archivos.

Skype Empresarial Server admite el uso de recursos compartidos de archivos en almacenamiento conectado directo (DAS) o en una red de área de almacenamiento (SAN), incluido el sistema de archivos distribuido (DFS), y en una matriz redundante de discos independientes (RAID) para almacenes de archivos. Después de que el Asistente para la implementación de Skype Empresarial Server haya definido la ubicación del recurso compartido de archivos, Skype Empresarial Server crea una estructura de carpetas dentro del recurso compartido de archivos similar a:

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

A continuación, el servicio de conferencia web almacena contenido como diapositivas, pizarras, sondeos y datos adjuntos de PowerPoint en las carpetas CollabContent y CollabMetadata, ubicadas en la carpeta WebServices.

### <a name="office-web-apps-server"></a>Servidor Office Web Apps

Para usar las funcionalidades de conferencia web, debe instalar Office Web Apps Server y configurar Skype Empresarial Server para comunicarse con Office Web Apps Server.

Office Web Apps Server debe instalarse en un equipo independiente que no ejecute Skype Empresarial Server, SQL Server o cualquier otra aplicación de servidor. (No debe tener ninguna versión de Office instalada en ese equipo). Cualquier equipo usado para ejecutar Office Web Apps Server también debe tener instalado un conjunto específico de software (incluidos .NET Framework 4.5 y Windows PowerShell 3.0). Estos requisitos, junto con la información sobre la configuración de certificados e Internet Information Services (IIS), se analizan en detalle en el sitio web de Microsoft Office web de implementación [de aplicaciones web](/webappsserver/deploy-the-infrastructure-office-web-apps-server).

Para obtener información sobre cómo configurar Skype Empresarial Server para que funcione con Office Web Apps Server, vea [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).

## <a name="requirements-for-audio-and-video-conferencing"></a>Requisitos para conferencias de audio y vídeo

Para planear una conferencia A/V, necesita conocer el ancho de banda necesario para el tipo de medio de conferencia que requiere su organización. Esto podría incluir audio, vídeo y vídeo panorámico. Si el ancho de banda de red no es suficiente, la experiencia del usuario puede verse afectada en gran medida.

Para obtener información sobre la planeación de capacidad de audio y vídeo para conferencias, vea [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md).

Puede usar el control de admisión de llamadas (CAC) para administrar el ancho de banda de red usado por las conferencias A/V. Esto es importante para redes restringidas, como vínculos de ancho de banda limitado entre los sitios central y de sucursal. Para obtener más información, vea [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).

Si implementa una conferencia de audio en la red, los usuarios necesitarán dispositivos de audio, como pueden ser auriculares, para participar en ella. Si implemente una conferencia de vídeo, necesitará implementar dispositivos de vídeo, como cámaras web para los usuarios. Tanto para dispositivos de audio como de vídeo, la implementación de dispositivos y la formación del usuario son pasos importantes que debes tener en cuenta. Para obtener más información, vea [Plan for clients and devices](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft recomienda usar dispositivos de comunicaciones unificadas (UC) certificados por Microsoft para todos los tipos de dispositivos, para garantizar una experiencia de usuario óptima. Para obtener más información acerca de los dispositivos certificados por la UC, vea [Teléfonos y dispositivos para Skype Empresarial.](../../../SfbPartnerCertification/certification/devices-ip-phones.md)

## <a name="requirements-for-dial-in-conferencing"></a>Requisitos para conferencias de acceso telefónico local

La conferencia de acceso telefónico local es una característica opcional de la carga de trabajo de conferencias de Skype Empresarial Server que incluye una variedad de componentes. Algunos componentes son específicos de las conferencias de acceso telefónico local y otros lo son de Enterprise Voice. En esta sección se describen los requisitos para los componentes necesarios para las conferencias de acceso telefónico local. Para obtener más información sobre los requisitos de puerta de enlace de red telefónica conmutada (RTC) y servidor de mediación, vea Mediation [Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) e Deploy a Mediation Server in [Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).

### <a name="required-components"></a>Componentes necesarios

Deberá instalar los siguientes componentes de Skype Empresarial Server antes de configurar las conferencias de acceso telefónico local:

- Servicio de aplicaciones de comunicaciones unificadas (UCAS) (denominado servicio de aplicaciones)

- Aplicación Operador de conferencia

- Aplicación de anuncio de conferencia

- Página web configuración de conferencia de acceso telefónico local

- Al menos un servidor de mediación y al menos una puerta de enlace RTC

Para conferencias de acceso telefónico local, el servicio de aplicaciones, la aplicación operador de conferencia y la aplicación anuncio de conferencia tienen los mismos requisitos del sistema operativo que los servidores front-end. Para obtener más información, vea [Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

La aplicación operador de conferencia y la aplicación de anuncio de conferencia requieren que Windows Media Format Runtime esté instalado en servidores front-end. Windows Media Format Runtime es necesario para reproducir archivos de audio de Windows Media (WMA) que se usan para la música en espera, nombres grabados y mensajes. Si vas a instalar en Windows Server 2012 o Windows Server 2012 R2 (lo que te recomendamos), tendrás que instalar Microsoft Media Foundation para obtener Windows Media Format Runtime. Si vas a instalar en cualquier versión de Windows Server anterior a Windows 2012, debes asegurarte de que la experiencia de escritorio de Windows está instalada para obtener Windows Media Format Runtime.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisitos de archivos de audio para conferencias de acceso telefónico local

Skype Empresarial Server no admite la personalización de mensajes de voz y música para conferencias de acceso telefónico local. Sin embargo, si tiene una necesidad empresarial sólida que requiere cambiar los archivos de audio predeterminados, consulte el artículo 961177 de Microsoft Knowledge Base, Cómo personalizar mensajes de voz o archivos de música para audioconferencias de acceso [telefónico](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)local.

También puede usar la utilidad de administración de mensajes de voz personalizados del operador de conferencia de [Microsoft Lync Server,](https://go.microsoft.com/fwlink/p/?LinkId=396880) que permite a los administradores reemplazar los mensajes de voz predeterminados usados cuando un llamador de teléfono se une a una reunión de Skype Empresarial con mensajes personalizados para proporcionar una experiencia de entrada de reunión diferente. Los mensajes de voz personalizados se pueden instalar en un servidor Enterprise o Standard Edition.

La aplicación operador de conferencia y la aplicación de anuncio de conferencia tienen los siguientes requisitos para la música en espera, el nombre grabado y los archivos de símbolo del sistema de audio:

- Formato de archivo de audio de Windows Media (WMA)

- Mono de 16 bits

- 48 kbps CBR 2 pasos (velocidad de bits constante)

- Nivel de voz a -24DB

### <a name="user-requirements-for-dial-in-conferencing"></a>Requisitos de usuario para conferencias de acceso telefónico local

Los usuarios de conferencias de acceso telefónico local deben tener un número de teléfono único o una extensión asignada a su cuenta. Este requisito admite la autenticación durante las conferencias de acceso telefónico local. Los usuarios de empresa (es decir, los usuarios que tienen credenciales de Servicios de dominio de Active Directory y cuentas de Skype Empresarial Server dentro de su organización) escriben su número de teléfono (o extensión) y un número de identificación personal (PIN) para llamar a las conferencias como usuario autenticado.

## <a name="port-requirements-for-conferencing"></a>Requisitos de puerto para conferencias

Para usar las características de conferencia, Skype Empresarial Server requiere que determinados puertos estén abiertos. En la tabla siguiente se enumeran los requisitos de puerto para conferencias. Para obtener más información acerca de todos los requisitos de puerto, vea [Port and protocol requirements for servers](../../plan-your-deployment/network-requirements/ports-and-protocols.md).

**Puertos de servidor necesarios**


|**Rol del servidor**|**Nombre del servicio**|**Port**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores front-end  <br/> |Servicio de conferencia de mensajería instantánea de Skype Empresarial Server  <br/> |5062  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.  <br/> |
|Servidores front-end  <br/> |Servicio de conferencia web de Skype Empresarial Server  <br/> |8057  <br/> |TCP (TLS)  <br/> |Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.  <br/> |
|Servidores front-end  <br/> |Servicio de compatibilidad de conferencia web de Skype Empresarial Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Se usa para escuchar las conexiones del modelo de objetos compartidos persistentes (PSOM) desde el cliente de Live Meeting y versiones anteriores de Skype Empresarial Server.  <br/> |
|Servidores front-end  <br/> |Servicio de conferencia de audio y vídeo de Skype Empresarial Server  <br/> |5063  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).  <br/> |
|Servidores front-end  <br/> |Servicio de conferencia de audio y vídeo de Skype Empresarial Server  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervalo de puerto de medios usado para conferencias de vídeo.  <br/> |
|Servidores front-end  <br/> |Servicio de operador de conferencia de Skype Empresarial Server (conferencia de acceso telefónico local)  <br/> |5064  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias telefónicas.  <br/> |
|Servidores front-end  <br/> |Servicio de operador de conferencia de Skype Empresarial Server (conferencia de acceso telefónico local)  <br/> |5072  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes para Attendant (dial in conferencing).  <br/> |
|Servidores front-end  <br/> |Servicio de uso compartido de aplicaciones de Skype Empresarial Server  <br/> |5065  <br/> |TCP  <br/> |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  <br/> |
|Servidores front-end  <br/> |Servicio de uso compartido de aplicaciones de Skype Empresarial Server  <br/> |49152-65535  <br/> |TCP  <br/> |Intervalo de puerto de medios usado para compartir aplicaciones.  <br/> |
|Servidores front-end  <br/> |Servicio de anuncio de conferencia de Skype Empresarial Server  <br/> |5073  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes para el servicio de anuncio de conferencia de Skype Empresarial Server (es decir, para conferencias de acceso telefónico local).  <br/> |
|Todos los usuarios internos  <br/> |Varios  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |El intervalo de puerto de medios se usa para audioconferencias en todos los servidores internos. Usado por todos los servidores que terminan el audio: servidores front-end (para el servicio de operador de conferencia de Skype Empresarial Server, el servicio de anuncios de conferencia de Skype Empresarial Server y el servicio de conferencia de audio y vídeo de Skype Empresarial Server) y el servidor de mediación.  <br/> |
|Servidores de Office Web Apps  <br/> ||443  <br/> ||Usado por Skype Empresarial Server para conectarse a Office Web Apps Server.  <br/> |

**Puertos de cliente necesarios**


|**Port**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Se usa para el acceso de usuarios externos a las sesiones de conferencia web.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP)  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Se usa para el acceso de usuarios externos a sesiones A/V y medios (UDP)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Intervalo de puertos de audio (se requieren 20 puertos como mínimo)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo)  <br/> |
|1024-65535 \*  <br/> |TCP  <br/> |Uso compartido de aplicaciones.  <br/> |