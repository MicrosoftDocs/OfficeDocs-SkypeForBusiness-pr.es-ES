---
title: Planear la topología de conferencias de Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Resumen: Lea este tema para obtener información sobre la planificación de la topología de conferencias en Skype empresarial Server.'
ms.openlocfilehash: 1b9d9024d90b4bd847c763747dad7a5f96616aa3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816019"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planear la topología de conferencias de Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre la planificación de la topología de conferencias en Skype empresarial Server.
  
En este tema se describen los conceptos básicos de la topología para conferencias en Skype empresarial Server:
  
- Topologías compatibles
    
- Consideraciones de las conferencias de acceso telefónico local
    
- Consideraciones de las conferencias web
    
- Requisitos para reuniones grandes
    
Para obtener más información sobre los requisitos de hardware y software, consulte [requisitos de hardware y software para conferencias en Skype empresarial Server](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Topologías compatibles

En Skype empresarial Server, el servidor que ejecuta servicios de conferencia siempre se encuentra en los servidores front-end o servidores Standard Edition. Al implementar Skype empresarial Server, las capacidades de conferencia de mensajería instantánea se implementan automáticamente. Puede especificar si se va a implementar web, audio y vídeo (A/V) y las conferencias de acceso telefónico local con el generador de topologías. También puede utilizar el generador de topologías para agregar conferencias a una implementación existente. Para obtener más información sobre los aspectos básicos de la topología y escenarios de collocation, consulte [aspectos básicos de la topología de Skype empresarial Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Puede implementar la característica de conferencia en las configuraciones y topologías siguientes:
  
- Skype empresarial Server Standard Edition
    
- Skype empresarial Server Enterprise Edition
    
- Con o sin telefonía IP empresarial
    
## <a name="dial-in-conferencing-considerations"></a>Consideraciones de las conferencias de acceso telefónico local

Si implementa las conferencias de acceso telefónico local, necesita tener en cuenta los siguientes puntos:
  
- Las conferencias de acceso telefónico local requieren un servidor de mediación para traducir la señalización (y los medios de algunas configuraciones) entre Skype empresarial Server y la puerta de enlace PSTN, y una puerta de enlace RTC para traducir la señalización y los medios entre el servidor de mediación y la puerta de enlace PSTN .
    
   Para poder configurar la conferencia de acceso telefónico local, también necesita implementar la telefonía IP empresarial o un servidor de mediación y al menos uno de los siguientes elementos:
    
  - Puerta de enlace RTC
    
  - Un sistema IP-PBX
    
  - Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta por medio de la configuración de un tronco SIP
    
- Puede implementar el servicio de aplicación, la aplicación Operador de conferencia y la aplicación Anuncio de conferencia en un sitio central, pero no en un sitio de sucursal.
    
- Debe implementar conferencias de acceso telefónico local en todos los grupos donde implementará las conferencias de Skype empresarial Server. No es necesario asignar números de acceso en cada grupo de servidores, pero tiene que implementar la característica de conferencia de acceso telefónico local en cada grupo de servidores. Este requisito admite la característica de nombre grabado cuando un usuario llama a un número de acceso desde un grupo para unirse a una conferencia de Skype empresarial Server en un grupo diferente. 
    
Para obtener más información, vea [planear las conferencias de acceso telefónico local en Skype empresarial Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Consideraciones de las conferencias web

Las conferencias web requieren los siguientes puntos: 
  
- Obtenga acceso al almacén de archivos, que se usa para almacenar contenido de conferencia web.
    
- Integración con Office Web Apps Server/Office Online Server, que es necesaria para compartir archivos de PowerPoint durante una conferencia.
    
> [!NOTE]
> La última iteración de Office Web Apps Server se denomina Office Online Server, que es compatible con Skype empresarial Server. Para obtener más información, consulte la [documentación del servidor de Office Online](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
Skype empresarial Server proporciona las siguientes formas de configurar Office Web Apps Server/Office Online Server. Dependiendo de sus necesidades, puede:
  
- **Instale Skype empresarial Server y Office Web Apps Server/Office Online Server local detrás del firewall de su organización y en la misma zona de red.** With this topology, external access to Office Web Apps Server/Office Online Server will be provided through your reverse proxy server. Idealmente, debe instalar Office Web Apps Server/Office Online Server en la misma zona de red que Skype empresarial Server.
    
    Los clientes externos de Skype empresarial se pueden conectar a Skype empresarial Server y a Office Web Apps Server/Office Online Server con un servidor proxy inverso, que es un servidor que recibe solicitudes de Internet y las reenvía a la red interna. (Los clientes internos no necesitan usar el servidor proxy inverso porque pueden conectarse directamente a Office Web Apps Server/Office Online Server). Esta topología funciona mejor si desea usar una granja de Office Web Apps Server/Office Online Server dedicada que solo se usa en Skype empresarial Server.
    
- **Use un servidor de Office Web Apps o un servidor de Office Online implementado externamente.** En esta topología, Skype empresarial Server se ha implementado de forma local y usa un servidor de Office Web Apps o de Office online que se ha implementado fuera de la zona de red de Skype empresarial Server. Esto puede ocurrir cuando Office Web Apps Server/Office Online Server se comparte entre varias aplicaciones de la Corporación y se implementa en una red que requiere que Skype empresarial Server use la interfaz externa de Office Web Apps Server/Office Online Server y viceversa.
    
    No es necesario instalar un servidor proxy inverso; en su lugar, todas las solicitudes de Office Web Apps Server/Office Online Server a Skype empresarial Server se enrutan a través del servidor perimetral. Los clientes internos y externos de Skype empresarial se conectan a Office Web Apps Server/Office Online Server mediante la dirección URL externa.
    
    Si Office Web Apps Server/Office Online Server está implementado fuera del firewall interno, seleccione la opción **El servidor de Office Web Apps se implementa en una red externa** (o sea, perímetro/Internet) en el generador de topologías.
    
Para obtener más información, vea [configurar la integración con Office Web Apps Server en Skype empresarial Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Sea cual sea la topología seleccionada, es fundamental que estén abiertos los puertos de firewall correctos. Debe asegurarse de que los firewalls, las direcciones IP y los puertos no estén bloqueados por los firewalls en el Office Web Apps Server/Office Online Server, el equilibrador de carga o Skype empresarial Server.
  
> [!NOTE]
> Otra opción para ofrecer acceso externo a Office Web Apps Server/Office Online Server es implementar el servidor en la red perimetral. Si se decide a hacerlo, recuerde que para configurar Office Web Apps Server/Office Online Server necesita que el equipo servidor sea miembro de su dominio de Active Directory. A menos que su directiva de red permita a los equipos de la red perimetral ser miembros del dominio de Active Directory, no se recomienda instalar Office Web Apps Server/Office Online Server en la red perimetral, sino instalar Office Web Apps Server/Office Online Server en la red interna y ofrecer acceso a usuarios externos a través de su servidor proxy inverso.  
  
## <a name="topology-requirements-for-large-meetings"></a>Requisitos de topología para reuniones grandes

Una única reunión grande requiere al menos un servidor front-end y un servidor back-end. Pero, para proporcionar alta disponibilidad, recomendamos un grupo de dos servidores front-end con servidores back-end reflejados tal y como se muestra en el siguiente diagrama:
  
**Topología de reunión grande**

![Topología de reunión grande](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
El usuario que hospeda las reuniones grandes necesita tener su cuenta de usuario alojada en el grupo de servidores front-end. Pero, no se recomienda hospedar otras cuentas de usuario en este grupo. Úselo solo para reuniones grandes. El procedimiento recomendado es crear una cuenta de usuario especial en este grupo y usarla solo para hospedar reuniones grandes. Como la configuración de las reuniones grandes se optimiza para el rendimiento, al utilizarla como un usuario normal podría tener problemas como la imposibilidad de promover una sesión P2P a una reunión cuando hay un extremo RTC involucrado.
  
Administrar un grupo con exactamente dos servidores front-end requiere algunas consideraciones especiales. Para más información, vea [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) y [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Además, si desea proporcionar la opción de recuperación ante desastres y conmutación por error para el grupo que se usa para las reuniones grandes, puede asociarlo a un grupo dedicado con una configuración similar y datos diferentes. Para obtener más información, consulte [planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Las siguientes son notas adicionales sobre la topología:
  
- Se necesita un recurso compartido de archivos para almacenar el contenido de la reunión y, si el servidor de archivado está implementado y habilitado, para el archivado de los archivos. El recurso compartido de archivos puede estar dedicado al grupo o puede ser el mismo recurso compartido de archivos que usa otro grupo del sitio en el que el grupo está implementado. Para obtener más información sobre cómo configurar el recurso compartido de archivos, vea [crear un recurso compartido de archivos en Skype empresarial Server 2015](../../deploy/install/create-a-file-share.md).
    
- Se requiere un Office Web Apps Server/Office Online Server para habilitar la función de presentación de PowerPoint en reuniones grandes. El Office Web Apps Server/Office Online Server puede ser exclusivo del grupo de reuniones grandes o puede ser el mismo Office Web Apps Server/Office Online Server que otros grupos utilizan en el sitio donde el grupo dedicado está implementado. Para obtener más información, vea [configurar la integración con Office Web Apps Server en Skype empresarial Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- El equilibrio de carga de los servidores front-end requiere equilibrio de carga de hardware para el tráfico HTTP (como la descarga de contenido de la reunión). El equilibrio de carga de DNS se recomienda para el tráfico SIP. Para más información, vea [Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Si desea usar el servidor de supervisión para el grupo de reuniones de gran tamaño dedicado, le recomendamos que use el servidor de supervisión y su base de datos que se comparten en todos los grupos de servidores front-end de su implementación de Skype empresarial Server. Para obtener más información, vea [planear la supervisión en Skype empresarial Server](../../plan-your-deployment/monitoring.md).
    

