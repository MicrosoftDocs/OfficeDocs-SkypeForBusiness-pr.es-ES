---
title: Planear la topología de conferencias para Skype Empresarial Server
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
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Resumen: lea este tema para obtener información sobre cómo planear la topología de conferencias en Skype Empresarial Server.'
ms.openlocfilehash: dc7c62d45a2ebd84f38cc67ce996ba0ac72aa794
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814100"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planear la topología de conferencias para Skype Empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo planear la topología de conferencias en Skype Empresarial Server.
  
En este tema se describen los conceptos básicos de topología para conferencias en Skype Empresarial Server:
  
- Topologías admitidas
    
- Consideraciones sobre conferencias de acceso telefónico local
    
- Consideraciones sobre conferencias web
    
- Requisitos para reuniones grandes
    
Para obtener más información acerca de los requisitos de hardware y software, consulte Requisitos de hardware y software para [conferencias en Skype Empresarial Server.](hardware-and-software-requirements.md)
  
## <a name="supported-topologies"></a>Topologías admitidas

En Skype Empresarial Server, el servidor que ejecuta servicios de conferencia siempre se coloca con los servidores front-end o los servidores Standard Edition. Al implementar Skype Empresarial Server, las funcionalidades de conferencia de mensajería instantánea se implementan automáticamente. Puede especificar si desea implementar web, audio y vídeo (A/V) y conferencias de acceso telefónico local mediante el Generador de topologías. También puede utilizar el Generador de topologías para agregar conferencia a una implementación existente. Para obtener más información sobre los conceptos básicos de la topología y los escenarios de colocación, consulte [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Puede implementar conferencias en las siguientes topologías y configuraciones:
  
- Skype Empresarial Server Standard Edition
    
- Skype Empresarial Server Enterprise Edition
    
- Con o sin Telefonía IP empresarial
    
## <a name="dial-in-conferencing-considerations"></a>Consideraciones sobre conferencias de acceso telefónico local

Si va a implementar conferencias de acceso telefónico local, debe tener en cuenta lo siguiente:
  
- Las conferencias de acceso telefónico local requieren un servidor de mediación para traducir la señalización (y los medios en algunas configuraciones) entre Skype Empresarial Server y la puerta de enlace RTC, y una puerta de enlace RTC para traducir la señalización y los medios entre el servidor de mediación y la puerta de enlace RTC.
    
   Antes de configurar las conferencias de acceso telefónico local, debe implementar Telefonía IP empresarial o un servidor de mediación y al menos uno de los siguientes:
    
  - Una puerta de enlace RTC
    
  - IP-PBX
    
  - Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta mediante la configuración de un tronco SIP
    
- Puede implementar el servicio de aplicación, la aplicación Operador de conferencia y la aplicación Anuncio de conferencia en un sitio central, pero no en un sitio de sucursal.
    
- Debe implementar las conferencias de acceso telefónico local en cada grupo donde implemente las conferencias de Skype Empresarial Server. No es necesario asignar números de acceso en cada grupo de servidores, pero debe implementar la característica de conferencia de acceso telefónico local en cada grupo de servidores. Este requisito admite la característica de nombre grabado cuando un usuario llama a un número de acceso de un grupo de servidores para unirse a una conferencia de Skype Empresarial Server en un grupo diferente. 
    
Para obtener más información, consulte [Plan for dial-in conferencing in Skype for Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Consideraciones sobre conferencias web

Las conferencias web requieren lo siguiente: 
  
- Acceso al almacén de archivos, que se usa para almacenar contenido de conferencia web.
    
- Integración con Office Web Apps Server/Office Online Server, que es necesaria para compartir archivos de PowerPoint durante una conferencia.
    
> [!NOTE]
> La iteración más reciente de Office Web Apps Server se denomina Office Online Server, que es compatible con Skype Empresarial Server. Para obtener más información, consulte la [documentación de Office Online Server.](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx) 
  
Skype Empresarial Server proporciona las siguientes formas de configurar Office Web Apps Server/Office Online Server. Dependiendo de sus necesidades, puede:
  
- **Instale Skype Empresarial Server y Office Web Apps Server/Office Online Server localmente detrás del firewall de su organización y en la misma zona de red.** Con esta topología, se proporciona acceso externo a Office Web Apps Server/Office Online Server a través del servidor proxy inverso. Lo ideal es instalar Office Web Apps Server/Office Online Server en la misma zona de red que Skype Empresarial Server.
    
    Los clientes externos de Skype Empresarial pueden conectarse a Skype Empresarial Server y a Office Web Apps Server/Office Online Server mediante un servidor proxy inverso, que es un servidor que toma solicitudes de Internet y las reenvía a la red interna. (Los clientes internos no necesitan usar el servidor proxy inverso porque pueden conectarse directamente a Office Web Apps Server/Office Online Server). Esta topología funciona mejor si desea usar una granja de servidores dedicada de Office Web Apps Server/Office Online Server que solo usa Skype Empresarial Server.
    
- **Use un servidor de Office Web Apps o Office Online Server implementado externamente.** En esta topología, Skype Empresarial Server se implementa localmente y usa un Servidor de Office Web Apps/Office Online Server que se implementa fuera de la zona de red de Skype Empresarial Server. Esto puede ocurrir cuando Office Web Apps Server/Office Online Server se comparte entre varias aplicaciones de la corporación y se implementa en una red que requiere que Skype Empresarial Server use la interfaz externa de Office Web Apps Server/Office Online Server y viceversa.
    
    No es necesario instalar un servidor proxy inverso; en su lugar, todas las solicitudes de Office Web Apps Server/Office Online Server a Skype Empresarial Server se enrutar a través de su servidor perimetral. Los clientes internos y externos de Skype Empresarial se conectan a Office Web Apps Server/Office Online Server mediante la dirección URL externa.
    
    Si Office Web Apps Server/Office Online Server se implementa fuera del firewall interno, seleccione la opción **Office Web Apps Server** se implementa en una red externa (es decir, perimetral/Internet) en el Generador de topologías.
    
Para obtener más información, vea [Configurar la integración con Office Web Apps Server en Skype Empresarial Server.](../../deploy/deploy-conferencing/office-web-app-server.md) 
  
Sea cual sea la topología seleccionada, es fundamental que estén abiertos los puertos de firewall correctos. Debe asegurarse de que los firewalls no bloqueen los nombres DNS, las direcciones IP y los puertos en Office Web Apps Server/Office Online Server, el equilibrador de carga o Skype Empresarial Server.
  
> [!NOTE]
> Otra opción para proporcionar acceso externo a Office Web Apps Server/Office Online Server es implementar el servidor en la red perimetral. Si opta por hacerlo, tenga en cuenta que la configuración de Office Web Apps Server/Office Online Server requiere que el equipo servidor sea miembro del dominio de Active Directory. A menos que la directiva de red permita que los equipos de la red perimetral sean miembros del dominio de Active Directory, se recomienda no instalar Office Web Apps Server/Office Online Server en la red perimetral. En su lugar, debe instalar Office Web Apps Server/Office Online Server en la red interna y proporcionar acceso de usuarios externos a través del servidor proxy inverso. 
  
## <a name="topology-requirements-for-large-meetings"></a>Requisitos de topología para reuniones grandes

Una única reunión grande requiere al menos un servidor front-end y un servidor back-end. Sin embargo, para proporcionar alta disponibilidad, se recomienda un grupo de servidores front-end con servidores back-end reflejados como se muestra en el siguiente diagrama:
  
**Topología de reuniones grandes**

![Topología de reuniones grandes](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
El usuario que hospeda las reuniones grandes debe tener su cuenta de usuario hospedada en el grupo de servidores front-end. Sin embargo, no se recomienda hospedar otras cuentas de usuario en este grupo. Úselo solo para reuniones grandes. El procedimiento recomendado es crear una cuenta de usuario especial en este grupo y usarla solo para hospedar reuniones grandes. Dado que la configuración de reunión grande está optimizada para el rendimiento, usarlo como un usuario normal podría tener problemas como la incapacidad de promover una sesión P2P a una reunión cuando se involucra un extremo de RTC.
  
Administrar un grupo con exactamente dos servidores front-end requiere algunas consideraciones especiales. Para obtener más información, consulte [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) and [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Además, si desea proporcionar opcionalmente copias de seguridad y conmutación por error de recuperación ante desastres para el grupo de servidores usado para reuniones grandes, puede emparejar con un grupo dedicado configurado de forma similar en un centro de datos diferente. Para obtener más información, consulte [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Las siguientes son notas adicionales sobre la topología:
  
- Se requiere un recurso compartido de archivos para almacenar el contenido de las reuniones y, si el servidor de archivado está implementado y habilitado, para almacenar los archivos de archivado. El recurso compartido de archivos puede estar dedicado al grupo o puede ser el mismo recurso compartido de archivos que usa otro grupo del sitio en el que el grupo está implementado. Para obtener más información sobre cómo configurar el recurso compartido de archivos, consulte Crear un recurso compartido de [archivos en Skype Empresarial Server 2015.](../../deploy/install/create-a-file-share.md)
    
- Se necesita un servidor de Office Web Apps/Office Online Server para habilitar la funcionalidad de presentación de PowerPoint en reuniones grandes. Office Web Apps Server/Office Online Server puede estar dedicado al grupo de reuniones grande o puede ser el mismo servidor de Office Web Apps Server/Office Online Server que usan otros grupos de servidores en el sitio en el que se implementa el grupo dedicado. Para obtener más información, vea [Configurar la integración con Office Web Apps Server en Skype Empresarial Server.](../../deploy/deploy-conferencing/office-web-app-server.md) 
    
- El equilibrio de carga de los servidores front-end requiere equilibrio de carga de hardware para el tráfico HTTP (como la descarga de contenido de reuniones). El equilibrio de carga de DNS se recomienda para el tráfico SIP. Para obtener más [información, vea los requisitos de equilibrio de carga para Skype Empresarial.](../../plan-your-deployment/network-requirements/load-balancing.md) 
    
- Si desea usar el servidor de supervisión para el grupo de reuniones grandes dedicado, se recomienda usar el servidor de supervisión y su base de datos que se comparten en todos los grupos de servidores front-end de la implementación de Skype Empresarial Server. Para obtener más información, consulte [Plan for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).
    

