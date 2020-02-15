---
title: Planeación de la topología de conferencia para Skype empresarial Server
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
description: 'Resumen: Lea este tema para obtener información sobre la planeación de la topología de conferencia en Skype empresarial Server.'
ms.openlocfilehash: 68ee859979deb7d977ee546e711474d0b6ba06e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030784"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planeación de la topología de conferencia para Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre la planeación de la topología de conferencia en Skype empresarial Server.
  
En este tema se describen los conceptos básicos de la topología para conferencias en Skype empresarial Server:
  
- Topologías admitidas
    
- Consideraciones sobre la Conferencia de acceso telefónico local
    
- Consideraciones de conferencia Web
    
- Requisitos para reuniones grandes
    
Para obtener más información acerca de los requisitos de hardware y software, vea [Hardware and software Requirements for Conferencing in Skype for Business Server](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Topologías admitidas

En Skype empresarial Server, el servidor que ejecuta los servicios de conferencia siempre se combina con los servidores front-end o los servidores Standard Edition. Al implementar Skype empresarial Server, las capacidades de conferencia de mensajería instantánea se implementan automáticamente. Puede especificar si desea implementar la web, audio y vídeo (A/V) y las conferencias de acceso telefónico local con el generador de topologías. También puede utilizar el Generador de topologías para agregar conferencia a una implementación existente. Para obtener más información sobre los aspectos básicos de la topología y los escenarios de combinación, consulte [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Puede implementar la Conferencia en las siguientes topologías y configuraciones:
  
- Skype empresarial Server Standard Edition
    
- Skype empresarial Server Enterprise Edition
    
- Con o sin telefonía IP empresarial
    
## <a name="dial-in-conferencing-considerations"></a>Consideraciones sobre la Conferencia de acceso telefónico local

Si va a implementar la Conferencia de acceso telefónico local, debe tener en cuenta lo siguiente:
  
- La Conferencia de acceso telefónico local requiere un servidor de mediación para convertir la señalización (y los medios en algunas configuraciones) entre Skype empresarial Server y la puerta de enlace RTC, y una puerta de enlace RTC para convertir la señalización y los medios entre el servidor de mediación y la puerta de enlace RTC. .
    
   Para poder configurar la Conferencia de acceso telefónico local, debe implementar la telefonía IP empresarial o un servidor de mediación y al menos una de las siguientes opciones:
    
  - Una puerta de enlace RTC
    
  - IP-PBX
    
  - Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta mediante la configuración de un tronco SIP
    
- Puede implementar el servicio de aplicación, la aplicación de operador de conferencia y la aplicación de anuncio de conferencia en un sitio central, pero no en un sitio de sucursal.
    
- Debe implementar la Conferencia de acceso telefónico local en cada grupo de servidores en el que implemente Skype empresarial Server Conferencing. No es necesario asignar números de acceso en cada grupo de servidores, pero debe implementar la característica de conferencia de acceso telefónico local en cada grupo de servidores. Este requisito admite la característica nombre grabado cuando un usuario llama a un número de acceso de un grupo de servidores para unirse a una conferencia de Skype empresarial Server en un grupo diferente. 
    
Para obtener más información, vea [Plan for Dial-in Conferencing in Skype for Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Consideraciones de conferencia Web

La conferencia web requiere lo siguiente: 
  
- Acceso al almacén de archivos, que se usa para almacenar contenido de conferencia Web.
    
- Integración con Office Web Apps Server/Office Online Server, que es necesaria para compartir archivos de PowerPoint durante una conferencia.
    
> [!NOTE]
> La última iteración de Office Web Apps Server se denomina Office Online Server, que es compatible con Skype empresarial Server. Para obtener más información, consulte la [documentación de Office Online Server](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx). 
  
Skype empresarial Server ofrece las siguientes formas de configurar Office Web Apps Server/Office Online Server. Dependiendo de sus necesidades, puede:
  
- **Instale Skype empresarial Server y Office Web Apps Server/Office Online Server de forma local detrás del firewall de su organización y en la misma zona de red.** Con esta topología, el acceso externo a Office Web Apps Server/Office Online Server se proporcionará a través del servidor proxy inverso. Lo ideal sería instalar Office Web Apps Server/Office Online Server en la misma zona de red que Skype empresarial Server.
    
    Los clientes externos de Skype empresarial pueden conectarse a Skype empresarial Server y a Office Web Apps Server/Office Online Server mediante un servidor de proxy inverso, que es un servidor que recibe solicitudes de Internet y las reenvía a la red interna. (Los clientes internos no necesitan usar el servidor de proxy inverso porque se pueden conectar directamente a Office Web Apps Server/Office Online Server). Esta topología funciona mejor si desea usar una granja dedicada de Office Web Apps Server/Office Online Server que solo se usa en Skype empresarial Server.
    
- **Use un Office Web Apps Server/Office Online Server implementado externamente.** En esta topología, Skype empresarial Server está implementado de forma local y usa un Office Web Apps Server/Office Online Server que está implementado fuera de la zona de red de Skype empresarial Server. Esto puede ocurrir cuando Office Web Apps Server/Office Online Server se comparte entre varias aplicaciones de la Corporación y se implementa en una red que requiere Skype empresarial Server para usar la interfaz externa de Office Web Apps Server/Office Online Server y viceversa.
    
    No es necesario instalar un servidor proxy inverso; en su lugar, todas las solicitudes de Office Web Apps Server/Office Online Server a Skype empresarial Server se enrutan a través del servidor perimetral. Los clientes internos y externos de Skype empresarial se conectan a Office Web Apps Server/Office Online Server con la dirección URL externa.
    
    Si Office Web Apps Server/Office Online Server está implementado fuera del firewall interno, seleccione la opción el **servidor de Office Web Apps se implementa en una red externa** (es decir, perimetral/Internet) en el generador de topologías.
    
Para obtener más información, vea [Configure Integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Sea cual sea la topología seleccionada, es fundamental que estén abiertos los puertos de firewall correctos. Debe asegurarse de que los firewalls, las direcciones IP y los puertos de los firewalls de Office Web Apps Server/Office Online Server, el equilibrador de carga o Skype empresarial Server no bloquean los nombres DNS.
  
> [!NOTE]
> Otra opción para ofrecer acceso externo a Office Web Apps Server/Office Online Server es implementar el servidor en la red perimetral. Si decide hacerlo, tenga en cuenta que el programa de instalación de Office Web Apps Server/Office Online Server requiere que el equipo servidor pertenezca a su dominio de Active Directory. A menos que la Directiva de red permita que los equipos de la red perimetral sean miembros de dominio de Active Directory, se recomienda no instalar Office Web Apps Server/Office Online Server en la red perimetral. En su lugar, debe instalar Office Web Apps Server/Office Online Server en la red interna y proporcionar a los usuarios externos el acceso a través del servidor proxy inverso. 
  
## <a name="topology-requirements-for-large-meetings"></a>Requisitos de la topología para reuniones grandes

Una única reunión grande requiere al menos un servidor front-end y un servidor back-end. Sin embargo, para proporcionar alta disponibilidad, recomendamos un grupo de servidores front-end con servidores back-end duplicados, como se muestra en el siguiente diagrama:
  
**Topología de reunión grande**

![Topología de reunión grande](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
El usuario que hospede las reuniones grandes debe tener su cuenta de usuario alojada en el grupo de servidores front-end. Sin embargo, no se recomienda hospedar otras cuentas de usuario en este grupo. Úselo solo para reuniones grandes. El procedimiento recomendado es crear una cuenta de usuario especial en este grupo y usarla solo para hospedar reuniones grandes. Dado que la configuración de reunión grande está optimizada para el rendimiento, su uso como un usuario normal podría tener problemas como la incapacidad de promover una sesión P2P a una reunión cuando se trata de un punto final de RTC.
  
Administrar un grupo con exactamente dos servidores front-end requiere algunas consideraciones especiales. Para obtener más información, consulte [Topology Basics for Skype for Business server 2015 y Reference topologys](../../plan-your-deployment/topology-basics/topology-basics.md) [for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Además, si desea proporcionar una copia de seguridad y conmutación por error de recuperación ante desastres para el grupo que se usa para reuniones grandes, puede emparejarlo con un grupo de servidores dedicado de configuración similar en un centro de datos diferente. Para obtener más información, consulte [Plan for High Availability and Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Las siguientes son notas adicionales sobre la topología:
  
- Se necesita un recurso compartido de archivos para almacenar el contenido de la reunión y, si el servidor de archivado está implementado y habilitado, para almacenar los archivos de archivado. El recurso compartido de archivos puede estar dedicado al grupo o puede ser el mismo recurso compartido de archivos que usa otro grupo del sitio en el que el grupo está implementado. Para obtener más información sobre cómo configurar el recurso compartido de archivos, consulte [crear un recurso compartido de archivos en Skype empresarial Server 2015](../../deploy/install/create-a-file-share.md).
    
- Se requiere un Office Web Apps Server/Office Online Server para habilitar la función de presentación de PowerPoint en reuniones grandes. Office Web Apps Server/Office Online Server puede dedicarse al grupo de reuniones de gran tamaño o puede ser el mismo Office Web Apps Server/Office Online Server que usan otros grupos de servidores en el sitio en el que se implementa el grupo dedicado. Para obtener más información, vea [Configure Integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- El equilibrio de carga de los servidores front-end requiere equilibrio de carga de hardware para el tráfico HTTP (como la descarga del contenido de la reunión). El equilibrio de carga de DNS se recomienda para el tráfico SIP. Para obtener información detallada, consulte [requisitos de equilibrio de carga para Skype empresarial](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Si desea usar el servidor de supervisión para el grupo de servidores de gran tamaño dedicado, se recomienda usar el servidor de supervisión y su base de datos que se comparten en todos los grupos de servidores front-end en su implementación de Skype empresarial Server. Para obtener más información, vea [Plan for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).
    

