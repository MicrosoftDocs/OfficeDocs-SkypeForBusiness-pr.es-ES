---
title: Planeación de la topología del servidor de chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Resumen: lea este tema para obtener información sobre las topologías y componentes del servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 548fc5ebecb0f123172ee4733346c03cf44aba7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825510"
---
# <a name="plan-persistent-chat-server-topology"></a>Planeación de la topología del servidor de chat persistente
 
**Resumen:** Lea este tema para obtener información sobre las topologías y componentes del servidor de chat persistente en Skype Empresarial Server 2015.
  
El servidor de chat persistente admite configuraciones de servidor único y de varios servidores. Puede instalar el servidor de chat persistente en un servidor De Skype Empresarial Server 2015 Enterprise Edition o Standard Edition. 

> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 
  
## <a name="persistent-chat-server-components"></a>Componentes del servidor de chat persistente

El servidor de chat persistente consta de los siguientes componentes:
  
- Uno o más equipos que ejecutan el servidor de chat persistente y proporcionan los siguientes servicios:
    
  - Servicio de chat persistente
    
  - Servicio de cumplimiento, que se activa si el cumplimiento está habilitado
    
- Uno o más servidores (más de uno si se usa la creación de reflejos) que ejecutan la base de datos back-end de SQL Server para hospedar la base de datos de contenido de chat persistente donde se almacenan el contenido del salón de chat, los salas y las categorías.
    
    > [!NOTE]
    > La base de datos back-end almacena los datos del historial de chat, incluida la información sobre las categorías y los salón de chat persistente que se crean. 
  
- Si el cumplimiento está habilitado, uno o más servidores (más de uno si se usa la creación de reflejo) que ejecutan la base de datos back-end de SQL Server para hospedar la base de datos de cumplimiento de chat persistente, donde se almacenan los eventos de cumplimiento y el contenido de chat con fines de cumplimiento.
    
Para obtener más información sobre los requisitos de hardware y software para el servidor de chat persistente, consulte Requisitos de servidor para [Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) y Requisitos de hardware y software para el servidor de chat persistente en [Skype Empresarial Server 2015.](hardware-and-software-requirements.md) 
  
## <a name="persistent-chat-server-topologies"></a>Topologías de servidor de chat persistente

Puede implementar el servidor de chat persistente en grupos de un solo servidor o de varios servidores, y con una topología de grupo único o de varios grupos de servidores. El servidor de chat persistente admite las siguientes topologías:
  
-  Servidor Standard Edition con servidor de chat persistente junto con el servidor front-end
    
-  Servidor Standard Edition con servidor de chat persistente en un servidor independiente
    
-  Servidor Enterprise Edition con un único servidor de chat persistente en un servidor independiente
    
-  Servidor Enterprise Edition con más de un servidor de chat persistente en servidores independientes
    
Aunque puede implementar un servidor de chat persistente en un servidor Standard Edition, tenga en cuenta que el rendimiento y la escala se verán afectados y la alta disponibilidad no es una opción. Por lo tanto, se recomienda implementar el chat persistente en un servidor Standard Edition principalmente con fines de prueba de concepto y evaluación. 
  
Skype Empresarial Server 2015 admite una variedad de escenarios de colocación, lo que proporciona flexibilidad para ahorrar costos de hardware mediante la ejecución de varios componentes en un servidor (si tiene una organización pequeña) o para ejecutar componentes individuales en diferentes servidores (si tiene una organización más grande que necesita escalabilidad y rendimiento). Debe tener en cuenta los factores de escalabilidad antes de decidir si se deben colocar componentes. Los escenarios de colocación difieren para los servidores De Skype Empresarial Server 2015 Enterprise Edition y Standard Edition. 
  
En las secciones siguientes se describen las topologías con más detalle, incluidos escenarios de colocación y opciones para los servidores de bases de datos back-end. Para obtener más información sobre la colocación de todas las bases de datos y roles de servidor, consulte [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Servidor Standard Edition con servidor de chat persistente junto con el servidor front-end

Con Standard Edition, puede colocar el chat persistente en el servidor front-end. Esta es la configuración más sencilla y básica. Debe asegurarse de que el servidor front-end existente tiene suficiente capacidad en términos de recursos físicos: CPU, memoria, espacio en disco, entre otros.
  
Además, puede colocar el servidor back-end del servidor de chat persistente y la base de datos de cumplimiento de chat persistente (si está habilitada) en el servidor back-end local de SQL Server Express. También puede elegir usar una instancia independiente SQL Server una instancia dedicada. 
  
> [!IMPORTANT]
> No puede agregar servidores adicionales a un grupo de servidores de chat persistente si el primer servidor de chat persistente se coloca con un servidor front-end Standard Edition. Se recomienda instalar el primer servidor como una instancia independiente para poder agregar más servidores más adelante, si es necesario. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Servidor Standard Edition con servidor de chat persistente instalado en un servidor independiente

Con Standard Edition, puede instalar el servidor de chat persistente como una instancia independiente y agregar más servidores más adelante si es necesario. 
  
Puede colocar el servidor back-end del servidor de chat persistente y la base de datos de cumplimiento de chat persistente (si está habilitado) en el servidor back-end local de SQL Server Express. También puede elegir usar una instancia independiente SQL Server una instancia dedicada. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Servidor Enterprise Edition con un único servidor de chat persistente

Con Enterprise Edition, debe instalar el servidor de chat persistente en un equipo independiente. Es decir, no puede colocar el servidor de chat persistente en el servidor front-end Enterprise Edition. Esta implementación requiere un servidor independiente que ejecute el servidor de chat persistente y el servicio de cumplimiento (si está habilitado).
  
Sin embargo, puede colocar la base de datos SQL Server para el servidor de chat persistente en la base de datos back-end de un grupo de servidores front-end de Enterprise Edition.
  
> [!NOTE]
> Si tiene previsto usar SQL grupos de disponibilidad AlwaysOn para HA DR, tenga en cuenta que no es compatible con las bases de datos del servidor de chat persistente. 
  
Si coloca la base de datos de chat persistente con la base de datos back-end, puede usar una sola instancia de SQL Server para una o todas las bases de datos, o puede usar una instancia independiente de SQL Server para cada base de datos.
  
> [!IMPORTANT]
> El servidor que hospeda la base de datos de chat persistente puede hospedar otras bases de datos. Sin embargo, cuando considere la posibilidad de colocar la base de datos de chat persistente con otras bases de datos, tenga en cuenta que si almacena los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de chat persistente puede crecer mucho. Por este motivo, no se recomienda instalar la base de datos de chat persistente con la base de datos back-end. 
  
En la figura siguiente se muestran todos los componentes de una topología para un único servidor de chat persistente con cumplimiento habilitado (opcional).
  
**Topología de un servidor**

![Servidor de chat persistente: topología de servidor único](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Servidor Enterprise Edition con varios servidores de chat persistente

Con Enterprise Edition, puede implementar una topología de varios servidores para una mayor capacidad y confiabilidad. Una topología de varios servidores es la misma que la topología de servidor único, excepto que varios servidores hospedan el servidor de chat persistente y pueden escalar más alto. La topología de varios servidores puede incluir hasta cuatro equipos activos que ejecuten el servidor de chat persistente (las configuraciones de alta disponibilidad y recuperación ante desastres permitirán hasta ocho, pero solo cuatro pueden estar activos y los cuatro restantes en modo de espera). Cada servidor puede admitir hasta 20 000 usuarios simultáneos, para un total de 80 000 usuarios simultáneos conectados a un grupo de servidores de chat persistente con 4 servidores. Varios equipos que ejecuten el servidor de chat persistente deben residir en el mismo dominio de Servicios de dominio de Active Directory que Skype Empresarial Server y el servicio de cumplimiento.
  
En la figura siguiente se muestran todos los componentes de una topología de varios servidores con varios equipos que ejecutan el servidor de chat persistente, el servicio de cumplimiento opcional y una base de datos de cumplimiento independiente.
  
**Topología de varios servidores**

![Servidor de chat persistente: topología de varios servidores](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Las topologías de varios servidores permiten agrupar las funciones de servidor. En un grupo de servidores, los servicios de chat persistente comunican y comparten datos. Por ejemplo, el historial de chat que se publicó originalmente en un servicio de chat persistente está disponible en cualquier servicio de chat persistente del sistema. Cualquier servicio de chat persistente puede tener acceso a un archivo que se carga a través de un servicio de chat persistente. Los usuarios pueden conectarse a diferentes servidores front-end del servidor de chat persistente y pueden comunicarse entre sí. El puerto predeterminado de TCP 8011 conecta un servidor a un grupo de servidores y lo usan los servicios de chat persistente para comunicarse entre sí o con fines administrativos.
  
Por ejemplo, en una implementación de servidor de chat persistente de cuatro servidores, donde 80.000 usuarios pueden haber iniciado sesión simultáneamente en el chat persistente, la carga se distribuye uniformemente a 20.000 usuarios por servidor. Si un servidor deja de estar disponible, los usuarios conectados a ese servidor perderán su acceso al servidor de chat persistente. Los usuarios desconectados se transferirán automáticamente a los servidores restantes hasta que se restaure el servidor no disponible. 
  

