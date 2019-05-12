---
title: Planeación de la topología de las conferencias de Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Resumen: Lea este tema para obtener más información acerca de cómo planear la topología de las conferencias en Skype Business Server.'
ms.openlocfilehash: bf54bca61631734a29ddd95ea8b16912f9bb5514
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897957"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planeación de la topología de las conferencias de Skype para Business Server
 
**Resumen:** Lea este tema para obtener más información acerca de cómo planear la topología de las conferencias en Skype Business Server.
  
Este tema describen los conceptos básicos de topología para las conferencias en Skype para Business Server:
  
- Topologías compatibles
    
- Consideraciones de las conferencias de acceso telefónico local
    
- Consideraciones de las conferencias web
    
- Requisitos para reuniones grandes
    
Para obtener más información acerca de los requisitos de hardware y software, vea [requisitos de Hardware y software para conferencias en Skype para Business Server](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Topologías compatibles

En Skype para Business Server, el servidor que ejecuta Servicios de conferencia siempre se combina con los servidores de servidores Front-End o Standard Edition. Al implementar Skype para Business Server, automáticamente se implementan las funciones de conferencia de mensajería instantánea. Puede especificar si se va a implementar web, audio y vídeo (A/V) y las conferencias de acceso telefónico local con el generador de topologías. También puede utilizar el generador de topologías para agregar conferencias a una implementación existente. Para obtener información detallada sobre los conceptos básicos de la topología y la combinación de escenarios, vea [Conceptos básicos de la topología de Skype para Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Puede implementar la característica de conferencia en las configuraciones y topologías siguientes:
  
- Skype para Business Server Standard Edition
    
- Skype para Business Server Enterprise Edition
    
- Con o sin telefonía IP empresarial
    
## <a name="dial-in-conferencing-considerations"></a>Consideraciones de las conferencias de acceso telefónico local

Si implementa las conferencias de acceso telefónico local, necesita tener en cuenta los siguientes puntos:
  
- Conferencia de acceso telefónico requiere un servidor de mediación para traducir señalización (y medios en algunas configuraciones) entre Skype para Business Server y la puerta de enlace RTC y una puerta de enlace de RTC para traducir la señalización y los medios entre el servidor de mediación y la puerta de enlace de RTC .
    
   Para poder configurar la conferencia de acceso telefónico local, también necesita implementar la telefonía IP empresarial o un servidor de mediación y al menos uno de los siguientes elementos:
    
  - Puerta de enlace RTC
    
  - Un sistema IP-PBX
    
  - Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta por medio de la configuración de un tronco SIP
    
- Puede implementar el servicio de aplicación, la aplicación Operador de conferencia y la aplicación Anuncio de conferencia en un sitio central, pero no en un sitio de sucursal.
    
- Debe implementar conferencias en cada grupo de servidores donde implementar Skype para conferencias de Business Server. No es necesario asignar números de acceso en cada grupo de servidores, pero tiene que implementar la característica de conferencia de acceso telefónico local en cada grupo de servidores. Este requisito es compatible con la característica de nombre grabado cuando un usuario llama a un número de acceso de un grupo de servidores para unirse a una Skype para conferencia de Business Server en un grupo de servidores diferente. 
    
Para obtener más información, consulte [Plan para conferencias de acceso telefónico en Skype para Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Consideraciones de las conferencias web

Las conferencias web requieren los siguientes puntos: 
  
- Obtenga acceso al almacén de archivos, que se usa para almacenar contenido de conferencia web.
    
- Integración con Office Web Apps Server/Office Online Server, que es necesaria para compartir archivos de PowerPoint durante una conferencia.
    
> [!NOTE]
> La iteración más reciente de Office Web Apps Server se denomina servidor en línea de Office, que es compatible con Skype para Business Server. Para obtener más detalles, consulte la [documentación de Office Server en línea](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
Skype para Business Server proporciona las siguientes opciones para configurar Office Web Apps Server/Office Online Server. Dependiendo de sus necesidades, puede:
  
- **Instalar ambos Skype para Business Server y Office Web Apps Server/Office Online Server local detrás de firewall de la organización y en la misma zona de red.** With this topology, external access to Office Web Apps Server/Office Online Server will be provided through your reverse proxy server. Idealmente, debe instalar a Office Web Apps Server/Office Online Server en la misma zona de red como Skype para Business Server.
    
    Skype externo para los clientes empresariales puede conectarse a Skype para Business Server y Office Web Apps Server/Office Online Server mediante el uso de un servidor proxy inverso, que es un servidor que toma las solicitudes desde Internet y los reenvía a la red interna. (Los clientes internos no es necesario usar el servidor proxy inverso, porque se pueden conectar directamente a Office Web Apps Server/Office Online Server). Esta topología funciona mejor si desea usar una granja de servidores de Office Web Apps Server/Office Online Server dedicado que usa Skype para Business Server.
    
- **Use un implementado en el exterior Office Web Apps Server/Office Online Server.** En esta topología, Skype para Business Server es instalados en servidores locales y usa un Office Web Apps Server/Office Online Server que se implementa fuera de la Skype para zona de red de servidor empresarial. Esto puede ocurrir cuando Office Web Apps Server/Office Online Server se comparte entre varias aplicaciones de la corporación y se implementa en una red que requiere Skype para Business Server usar la interfaz externa de Office Web Apps Server/Office Online Server y viceversa.
    
    No es necesario instalar a un servidor proxy inverso; en su lugar, todas las solicitudes de Office Web Apps Server/Office Online Server a Skype para Business Server se enrutan a través de su servidor perimetral. Interno y su Skype externo para los clientes empresariales conectan a Office Web Apps Server/Office Server en línea con la dirección URL externa.
    
    Si Office Web Apps Server/Office Online Server está implementado fuera del firewall interno, seleccione la opción **El servidor de Office Web Apps se implementa en una red externa** (o sea, perímetro/Internet) en el generador de topologías.
    
Para obtener más información, vea [Configurar la integración con Office Web Apps Server en Skype para Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Sea cual sea la topología seleccionada, es fundamental que estén abiertos los puertos de firewall correctos. Debe asegurarse de que los nombres DNS, direcciones IP y puertos no están bloqueados por firewalls en Office Web Apps Server/Office Online Server, el equilibrador de carga o Skype para Business Server.
  
> [!NOTE]
> Otra opción para ofrecer acceso externo a Office Web Apps Server/Office Online Server es implementar el servidor en la red perimetral. Si se decide a hacerlo, recuerde que para configurar Office Web Apps Server/Office Online Server necesita que el equipo servidor sea miembro de su dominio de Active Directory. A menos que su directiva de red permita a los equipos de la red perimetral ser miembros del dominio de Active Directory, no se recomienda instalar Office Web Apps Server/Office Online Server en la red perimetral, sino instalar Office Web Apps Server/Office Online Server en la red interna y ofrecer acceso a usuarios externos a través de su servidor proxy inverso.  
  
## <a name="topology-requirements-for-large-meetings"></a>Requisitos de topología para reuniones grandes

Una única reunión grande requiere al menos un servidor front-end y un servidor back-end. Pero, para proporcionar alta disponibilidad, recomendamos un grupo de dos servidores front-end con servidores back-end reflejados tal y como se muestra en el siguiente diagrama:
  
**Topología de reunión grande**

![Topología de reunión grande](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
El usuario que hospeda las reuniones grandes necesita tener su cuenta de usuario alojada en el grupo de servidores front-end. Pero, no se recomienda hospedar otras cuentas de usuario en este grupo. Úselo solo para reuniones grandes. El procedimiento recomendado es crear una cuenta de usuario especial en este grupo y usarla solo para hospedar reuniones grandes. Como la configuración de las reuniones grandes se optimiza para el rendimiento, al utilizarla como un usuario normal podría tener problemas como la imposibilidad de promover una sesión P2P a una reunión cuando hay un extremo RTC involucrado.
  
Administrar un grupo con exactamente dos servidores front-end requiere algunas consideraciones especiales. Para más información, vea [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) y [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Además, si desea proporcionar la opción de recuperación ante desastres y conmutación por error para el grupo que se usa para las reuniones grandes, puede asociarlo a un grupo dedicado con una configuración similar y datos diferentes. Para obtener información detallada, consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Las siguientes son notas adicionales sobre la topología:
  
- Se necesita un recurso compartido de archivos para almacenar el contenido de la reunión y, si el servidor de archivado está implementado y habilitado, para el archivado de los archivos. El recurso compartido de archivos puede estar dedicado al grupo o puede ser el mismo recurso compartido de archivos que usa otro grupo del sitio en el que el grupo está implementado. Para obtener información detallada acerca de cómo configurar el recurso compartido de archivos, vea [crear un recurso compartido de archivos en Skype para Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- Se requiere un Office Web Apps Server/Office Online Server para habilitar la función de presentación de PowerPoint en reuniones grandes. El Office Web Apps Server/Office Online Server puede ser exclusivo del grupo de reuniones grandes o puede ser el mismo Office Web Apps Server/Office Online Server que otros grupos utilizan en el sitio donde el grupo dedicado está implementado. Para obtener más información, vea [Configurar la integración con Office Web Apps Server en Skype para Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- El equilibrio de carga de los servidores front-end requiere equilibrio de carga de hardware para el tráfico HTTP (como la descarga de contenido de la reunión). El equilibrio de carga de DNS se recomienda para el tráfico SIP. Para más información, vea [Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Si desea usar el servidor de supervisión para el grupo de reuniones grandes dedicado, se recomienda usar el servidor de supervisión y su base de datos que se comparten a través de todos los grupos de servidor Front-End en su Skype para la implementación de Business Server. Para obtener más información, vea [Planear la supervisión en Skype para Business Server](../../plan-your-deployment/monitoring.md).
    

