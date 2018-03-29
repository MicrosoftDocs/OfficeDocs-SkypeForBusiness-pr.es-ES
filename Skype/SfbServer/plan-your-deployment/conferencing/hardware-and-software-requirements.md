---
title: Requisitos de hardware y software para conferencias en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 'Resumen: Leer este tema para obtener información acerca de los requisitos de hardware y software para conferencias en Skype para Business Server 2015.'
ms.openlocfilehash: dcabd3b0216eebfa3873b44b0d19d32522d6564f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server-2015"></a>Requisitos de hardware y software para conferencias en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información acerca de los requisitos de hardware y software para conferencias en Skype para Business Server 2015.
  
Esta sección describe los requisitos de hardware y software para conferencias web, audio y vídeo (A / V) conferencia, marcado en la conferencia y conferencia de mensajería instantánea (IM). Todas las capacidades de conferencia se ejecutan en servidores frontales; Existen requisitos adicionales para diferentes tipos de conferencias, como se muestra en el siguiente diagrama.
  
Por ejemplo, si desea permitir el marcado de conferencia, debe implementar un servidor de mediación y una puerta de enlace para conectarse a la red telefónica pública conmutada (PSTN). Si desea permitir conferencias web, debe asegurarse de que Skype para Business Server puede conectarse a un servidor de Office Web Apps. Si desea permitir que los usuarios externos participen en las conferencias, necesitará implementar un servidor perimetral. 
  
**Requisitos y capacidades de conferencias**

![Componentes de conferencia](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)
  
 Para obtener más información acerca de las consideraciones de topología, vea [Planear la topología de las conferencias de Skype para Business Server 2015](conferencing-topology.md).
  
## <a name="hardware-and-software-requirements-for-front-end-servers"></a>Requisitos de hardware y software de los servidores front-end

Dado conferencias por Internet, A / conferencias de mensajería instantánea, conferencias de acceso telefónico y conferencias audiovisuales están ubicados con el servidor Front-End, los requisitos de hardware y software de servidor son los mismos que los servidores frontales. Para obtener más información acerca de estos requisitos, vea [requisitos de servidor de Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) y [medioambientales para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). 
  
## <a name="requirements-for-web-conferencing"></a>Requisitos para las conferencias web

Si ha elegido habilitar la conferencia web, tiene que planear lo siguiente:
  
- Obtenga acceso al almacén de archivos, que se usa para almacenar contenido de conferencia web.
    
- Integración con Office Web Apps Server, que es necesaria para compartir archivos de PowerPoint durante una conferencia.
    
### <a name="file-store"></a>Almacén de archivos

El Skype para el servicio de conferencias web Business Server almacena contenido compartido durante las reuniones en el almacén de archivos. Como parte de la implementación, debe especificar un recurso compartido de archivo que se utilizará como el almacén de archivos para el servidor Standard Edition o un grupo de servidores Enterprise Edition Front-End. Para ello, use un recurso compartido de archivos ya creado o especificar uno nuevo indicando el nombre de dominio completo del servidor de archivos donde necesita ubicarse el recurso compartido de archivos y un nombre de carpeta para dicho recurso. Para obtener más información, vea [crear un recurso compartido de archivo en Skype para Business Server 2015](../../deploy/install/create-a-file-share.md). El servicio de conferencia web cifra el contenido antes de almacenarlo en el almacén de archivos.
  
Skype para Business Server admite el uso de recursos compartidos de archivos en el almacenamiento de conexión directa (DAS) o una red de área de almacenamiento (SAN), incluido el sistema de archivos distribuido (DFS) y en una matriz redundante de discos independientes (RAID) para almacenes de archivos. Una vez el Skype para el Asistente para implementación de Business Server ha definido la ubicación del recurso compartido de archivos, Skype para Business Server crea una estructura de carpetas del recurso compartido de archivo similar a: 
  
- 1-ApplicationServer-1
    
- 1-CentralMgmt-1
    
- 1-WebServices-1
    
  - CollabContent
    
  - CollabMetadata
    
  - DataConf
    
El servicio de conferencia web almacena entonces el contenido como diapositivas de PowerPoint, pizarras, sondeos y datos adjuntos en las carpetas CollabContent y CollabMetadata, que se encuentran en la carpeta WebServices.
  
### <a name="office-web-apps-server"></a>Servidor Office Web Apps

Para poder utilizar capacidades de conferencias web, debe instalar el servidor de Office Web Apps y configurar Skype para Business Server para comunicarse con el servidor de Office Web Apps. 
  
Office Web Apps Server debe instalarse en un equipo independiente que no se está ejecutando Skype para Business Server, SQL Server o cualquier otra aplicación de servidor. (No debe tener ninguna versión de Office instalada en el equipo.) Cualquier equipo que se utiliza para ejecutar el servidor de Office Web Apps también tiene un conjunto específico de software instalado (incluyendo.NET Framework 4.5 y 3.0 de Windows PowerShell). Estos requisitos, junto con información sobre la configuración de certificados y servicios de Internet Information Server (IIS), se describen detalladamente en la [página Web de implementación de Microsoft Office Web Apps](https://go.microsoft.com/fwlink/p/?linkid=257525). 
  
Para obtener información sobre cómo configurar Skype para Business Server para que funcione con el servidor de Office Web Apps, vea [Configurar la integración con Office Web Apps Server en Skype para Business Server 2015](../../deploy/deploy-conferencing/office-web-app-server.md).
  
## <a name="requirements-for-audio-and-video-conferencing"></a>Requisitos para conferencias de audio y vídeo

Para planear una conferencia A/V, necesita conocer el ancho de banda necesario para el tipo de medio de conferencia que requiere su organización. Esto podría incluir audio, vídeo y vídeo panorámico. Si el ancho de banda de red no es suficiente, la experiencia del usuario puede verse afectada en gran medida. 
  
Para obtener información sobre el diseño de conferencias de capacidad de audio y vídeo, consulte [Plan de requisitos de red para Skype para negocios 2015](../../plan-your-deployment/network-requirements/network-requirements.md).
  
Puede usar el servicio de control de admisión de llamadas (CAC) para administrar el ancho de banda de red que se usa en las conferencias A/V. Esto es importante para redes restringidas, como vínculos de ancho de banda limitados entre los sitios centrales y de sucursal. Para obtener información detallada, consulte [Plan de control de admisión de llamada en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
Si implementa las audioconferencias en su red, los usuarios necesitarán dispositivos de audio, como pueden ser auriculares, para participar en las audioconferencias. Si implementa las videoconferencias, necesita implementar dispositivos de vídeo, como cámaras web para los usuarios. Tanto para los dispositivos de audio como para los de vídeo, la implementación de los dispositivos y el aprendizaje de los usuarios son pasos importantes que hay que tener en cuenta. Para obtener más información, consulte [Plan de clientes y dispositivos](../../plan-your-deployment/clients-and-devices/clients-and-devices.md). Microsoft recomienda que use los dispositivos de comunicaciones unificadas (UC) certificados por Microsoft para todos los tipos de dispositivos, con el fin de garantizar una experiencia óptima para el usuario. Para obtener más información acerca de los dispositivos certificados de comunicaciones unificadas, consulte [los teléfonos y dispositivos de Skype para el negocio](https://go.microsoft.com/fwlink/?LinkId=619916).
  
## <a name="requirements-for-dial-in-conferencing"></a>Requisitos para conferencias de acceso telefónico local

Conferencia de marcado es una característica opcional de la Skype para carga de conferencias Business Server que incluye una variedad de componentes. Algunos de los componentes son específicas a las conferencias de acceso telefónico y algunos son componentes de Telefonía IP empresarial. Esta sección describe los requisitos para los componentes que son necesarios para las conferencias de acceso telefónico. Para obtener más información acerca de servidor de mediación y requisitos de telefónica pública conmutada (PSTN) de red puerta de enlace, vea [componentes de servidor de mediación en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) y [de implementar un servidor de mediación en el generador de topología en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md).
  
### <a name="required-components"></a>Componentes requeridos

Debe instalar el siguiente Skype para los componentes de servidor empresarial para poder configurar el acceso telefónico de la conferencia: 
  
- Servicio de aplicaciones de comunicaciones unificadas (UCAS) (denominado el servicio de aplicación)
    
- Aplicación Operador de conferencia
    
- Aplicación de anuncio de conferencia
    
- Página web de configuración de la conferencia de acceso telefónico local
    
- Al menos un servidor de mediación y al menos una puerta de enlace RTC
    
Para conferencias de acceso telefónico, servicio de aplicación, aplicación de conferencia operador y aplicación de anuncio de conferencia tienen los mismos requisitos de sistema operativo como los servidores frontales. Para obtener más información, consulte [requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
Aplicación operador de conferencia y conferencia anuncio requieren que esté instalado Windows Media Format Runtime en servidores frontales. El tiempo de ejecución de Windows Media Format es necesario para reproducir archivos de Windows Media Audio (WMA) que se usan para la música en espera, nombres registrados y avisos. Si va a instalar en Windows Server 2012 o Windows Server 2012 R2 (que recomendamos), debe instalar Microsoft Media Foundation para obtener Windows Media Format Runtime. Si va a instalar en cualquier versión de Windows Server anterior a Windows 2012, necesitará asegurarse de que la experiencia de escritorio de Windows esté instalada para obtener el tiempo de ejecución de Windows Media Format.
  
### <a name="audio-file-requirements-for-dial-in-conferencing"></a>Requisitos de archivo de audio para conferencias de acceso telefónico local

Skype para Business Server no admite la personalización de los mensajes de voz y música para conferencias de acceso telefónico. Sin embargo, si tiene una necesidad de negocios sólidos que requiere que cambie los archivos de audio de forma predeterminada, consulte el artículo de Microsoft Knowledge Base 961177, [cómo personalizar los mensajes de voz o archivos de música para conferencias de audio de acceso telefónico](http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177).
  
También puede utilizar la utilidad de administración de [Microsoft Lync Server conferencia operador personalizado mensajes de voz](https://go.microsoft.com/fwlink/p/?LinkId=396880) , que permite a los administradores reemplazar los mensajes de voz predeterminado utilizados cuando une a un llamador de teléfono un Skype para reuniones de negocios con mensajes personalizados entrada de experiencia para ofrecer una sesión diferente. Los mensajes de voz personalizados pueden instalarse en un servidor Enterprise o Standard Edition.
  
Aplicación de conferencia operador y anuncio de conferencia tienen los siguientes requisitos para la música en espera, nombre grabado y archivos de audio de símbolo del sistema:
  
- Formato de archivo de audio de Windows Media (WMA)
    
- Mono de 16 bits
    
- 48 kbps CBR 2 pasos (velocidad de bits constante)
    
- Nivel de voz a -24DB
    
### <a name="user-requirements-for-dial-in-conferencing"></a>Requisitos de usuario para conferencias de acceso telefónico local

Los usuarios de conferencias de acceso telefónico local necesitan tener un número de teléfono único o una extensión asignada a su cuenta. Este requisito admite la autenticación durante las conferencias de acceso telefónico local. Los usuarios de la empresa (es decir, los usuarios que tienen credenciales de servicios de dominio de Active Directory y Skype para cuentas Business Server dentro de su organización) escriben su número de teléfono (o extensión) y un número de identificación personal (PIN) para llamar a conferencias como un usuario autenticado.
  
## <a name="port-requirements-for-conferencing"></a>Requisitos de puerto para conferencias

Para poder utilizar las características de conferencia, Skype para Business Server requiere que estén abiertos determinados puertos. La siguiente tabla enumera los requisitos de los puertos para conferencias. Para obtener más información acerca de todos los requisitos de puerto, consulte [requisitos de protocolo y puerto para los servidores](../../plan-your-deployment/network-requirements/ports-and-protocols.md).
  
**Puertos de servidor requerido**


|**Función de servidor**|**Nombre de servicio**|**Puerto**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Servidores front-end  <br/> |Skype para el servicio de conferencia de negocios servidor IM  <br/> |5062  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencias Web de Business Server  <br/> |8057  <br/> |TCP (TLS)  <br/> |Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de compatibilidad con conferencias Web Business Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Se utiliza para escuchar las conexiones del modelo de objeto de compartidos persistente (PSOM) desde el cliente de Live Meeting y versiones anteriores de Skype para Business Server.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencia de Audio y vídeo servidor Business  <br/> |5063  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencia de Audio y vídeo servidor Business  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervalo de puertos de medios que se usa para conferencias de vídeo.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de operador de Conferencing Server Business (conferencia de marcado)  <br/> |5064  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de acceso telefónico local.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de operador de Conferencing Server Business (conferencia de marcado)  <br/> |5072  <br/> |TCP  <br/> |Se utiliza para las solicitudes SIP entrantes para operador (marcado en conferencias).  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de uso compartido de Business Server  <br/> |5065  <br/> |TCP  <br/> |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de uso compartido de Business Server  <br/> |49152-65535  <br/> |TCP  <br/> |Intervalo de puertos de medios que se usa para compartir aplicaciones.  <br/> |
|Servidores front-end  <br/> |Skype para servicio de anuncio de Conferencing Server Business  <br/> |5073  <br/> |TCP  <br/> |Utilizado para las solicitudes SIP entrantes para el Skype para servicio de anuncio de Conferencing Server Business (es decir, para las conferencias de acceso telefónico).  <br/> |
|Todos los usuarios internos  <br/> |Varios  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |El intervalo de puertos de medios se usa para audioconferencias en todos los servidores internos. Utilizado por todos los servidores que terminar audio: servidores frontales (por Skype para el servicio de operador de Conferencing Server Business, Skype para servicio de anuncio de Conferencing Server Business y Skype para servicio Business Server Audio y videoconferencia), y Servidor de mediación.  <br/> |
|Servidores de Office Web Apps  <br/> ||443  <br/> ||Utiliza Skype para Business Server 2015 para conectarse al servidor de Office Web Apps.  <br/> |
   
**Puertos de cliente requerido**


|**Puerto**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |Se usa para el acceso de usuarios externos a las sesiones de conferencia web.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP).  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |Se usa para el acceso de usuarios externos a los medios y las sesiones de A/V (UDP)  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de puertos de audio (se requieren 20 puertos como mínimo).  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo).  <br/> |
|1024-65535\*  <br/> |TCP  <br/> |Uso compartido de aplicaciones.  <br/> |
   

