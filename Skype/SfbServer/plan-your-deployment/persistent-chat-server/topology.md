---
title: Planificar una topología de servidores de chat persistente
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Resumen: Leer este tema para obtener información acerca de los componentes del servidor de Chat persistentes y topologías de Skype para Business Server 2015.'
ms.openlocfilehash: 11d12283c3ee302c8133b0a56bbea53315508aec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-persistent-chat-server-topology"></a>Planificar una topología de servidores de chat persistente
 
**Resumen:** Leer este tema para obtener información acerca de los componentes del servidor de Chat persistentes y topologías de Skype para Business Server 2015.
  
Servidor de Chat persistente admite configuraciones de servidor único y de varios servidores. Puede instalar al servidor de charla persistente en ambos un Skype para servidor Standard Edition o Business Server 2015 Enterprise Edition. 
  
## <a name="persistent-chat-server-components"></a>Componentes de servidor de charla persistentes

El servidor de chat persistente incluye los componentes siguientes:
  
- Uno o más equipos ejecutando el servidor de charla persistente y proporciona los siguientes servicios:
    
  - Servicio de Chat persistente
    
  - Servicio de cumplimiento, que se activa si el cumplimiento está habilitado
    
- Uno o más servidores (más de uno si se utiliza el reflejo) ejecuta la base de datos de back-end de SQL Server para alojar la base de datos de contenido de Chat persistentes se almacenan contenido del salón de chat, salas y categorías.
    
    > [!NOTE]
    > La base de datos back-end almacena datos de historial de charla, incluida la información sobre categorías y salas de Chat persistentes que se crean. 
  
- Si está habilitado el cumplimiento de normas, ejecuta la base de datos de back-end de SQL Server para alojar la base de datos persistente cumplimiento de charla donde eventos de conformidad y chat de contenido con el fin de cumplimiento de normas se almacenan uno o más servidores (más de uno si se utiliza el reflejo).
    
Para obtener más información acerca de los requisitos de hardware y software para el servidor de charla persistente, consulte [requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) y [requisitos de Hardware y software para el servidor de charla persistente en Skype para Business Server 2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Topologías de servidor de charla persistentes

Puede implementar servidor de Chat persistente en grupos de servidor único o de varios servidores y con topología único grupo o varios grupos. Servidor de charla persistente admite las siguientes topologías:
  
-  Servidor Standard Edition con el servidor de chat persistente combinados en el servidor front-end
    
-  Servidor Standard Edition con el servidor de charla persistente en un servidor independiente
    
-  Servidor Enterprise Edition con un único servidor de Chat persistentes en un servidor independiente
    
-  Servidor Enterprise Edition con más de un servidor de charla persistente en servidores independientes
    
Aunque puede implementar servidor de Chat persistente en un servidor Standard Edition, tenga en cuenta que se verán afectados de performance y escalabilidad y alta disponibilidad no es una opción. Por lo tanto, se recomienda que implemente persistente de charla en un servidor Standard Edition principalmente para la prueba de concepto y evaluación. 
  
Skype para el año 2015 de Business Server admite una variedad de escenarios de colocación, proporcionando la flexibilidad para ahorrar costos de hardware mediante la ejecución de varios componentes en un servidor (si tiene una organización pequeña) o para ejecutar componentes individuales en distintos servidores ( Si tienes una organización mayor que las necesidades de rendimiento y escalabilidad). Necesita considerar los factores de escalabilidad antes de decidir si los componentes se van a combinar. Colocación difieren de Skype para servidores Business Server 2015 Enterprise Edition y Standard Edition. 
  
Los siguientes escenarios describen las topologías en más detalle, incluso los escenarios de combinación y las opciones para los servidores de base de datos back-end. Para obtener más información acerca de la colocación de todos los roles de servidor y las bases de datos, consulte [Aspectos básicos de la topología para Skype para Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Servidor Standard Edition con el servidor de chat persistente combinados en el servidor front-end

Con Standard Edition, puede combinar el chat persistente en el servidor front-end. Esta es la configuración más básica y más sencilla. Asegúrese de que el servidor existente de Front-End tiene suficiente capacidad en términos de recursos físicos: CPU, memoria, espacio en disco y así sucesivamente.
  
Además, se pueden colocar el servidor de back-end del servidor de Chat persistente y la base de datos de conformidad de Chat persistentes (si está activada) en el servidor back-end de SQL Server Express local. También, puede optar por usar un SQL Server independiente con una instancia dedicada. 
  
> [!IMPORTANT]
> No puede agregar servidores adicionales a un grupo de servidores de charla persistente si el primer servidor de Chat persistente está ubicado en un servidor de extremo frontal de Standard Edition. Se recomienda que instale al primer servidor como una instancia independiente para que pueda agregar más servidores más adelante, si es necesario. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Servidor Standard Edition con el servidor de chat persistente instalados en un servidor independiente

Con Standard Edition, puedes instalar el servidor de chat persistente como una instancia independiente y agregar más servidores luego, si es necesario.   
  
Puede colocar el servidor de back-end del servidor de Chat persistente y la base de datos de conformidad de Chat persistentes (si está activada) en el servidor back-end de SQL Server Express local. También, puede optar por usar un SQL Server independiente con una instancia dedicada. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Servidor Enterprise Edition con un único servidor de chat persistente

Con Enterprise Edition, debe instalar al servidor de charla persistente en un equipo independiente. Es decir, no puede colocar el servidor de charla persistente en el servidor de extremo frontal de Enterprise Edition. Esta implementación requiere un servidor independiente que ejecuta servidor de Chat persistente y el servicio de cumplimiento de normas (si está activada).
  
Sin embargo, puede colocar la base de datos de SQL Server para el servidor de charla persistente en la base de datos back-end de un grupo de servidores Enterprise Edition Front-End.
  
> [!NOTE]
> Si planea utilizar Grupos de disponibilidad AlwaysOn de SQL para HA DR, tenga en cuenta que no es compatible con las bases de datos del servidor de chat persistente. 
  
Si coloca la base de datos persistente de charla con la base de datos back-end, puede utilizar una única instancia de SQL Server para cualquiera o todas las bases de datos o puede utilizar una instancia independiente de SQL Server para cada base de datos.
  
> [!IMPORTANT]
> El servidor que aloja la base de datos persistente de charla puede alojar otras bases de datos. Sin embargo, al considerar la colocación de la base de datos persistente chatear con otras bases de datos, tenga en cuenta que si almacena los mensajes de más de unos pocos usuarios, el espacio en disco necesaria por la base de datos persistente de charla puede crecer considerablemente. Por este motivo, se recomienda la colocación de la base de datos persistente de charla con la base de datos back-end. 
  
La figura siguiente muestra todos los componentes de una topología de un único servidor de Chat persistentes con cumplimiento habilitado (opcional).
  
**Topología de servidor único**

![Servidor de chat persistente: topología de un servidor](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Servidor Enterprise Edition con varios servidores de chat persistente

Con Enterprise Edition, puede implementar una topología de varios servidores para una mayor capacidad y fiabilidad. Una topología de varios servidores es la misma que la topología de servidor único, excepto que varios servidores host servidor de Chat persistente y pueden escalar más. La topología de varios servidores puede incluir como máximo cuatro equipos activos ejecutando el servidor de charla persistente (hasta ocho permite configuraciones de recuperación ante desastres y disponibilidad alta, pero sólo cuatro puede ser activo y los restantes cuatro en modo de espera). Cada servidor puede admitir hasta 20.000 usuarios simultáneos, con un total de 80.000 usuarios simultáneos conectados a un grupo de servidores de charla persistente con 4 servidores. Varios equipos que ejecutan el servidor de charla persistente deben residir en el mismo dominio de servicios de dominio de Active Directory como Skype para Business Server y el servicio de cumplimiento de normas.
  
La figura siguiente muestra todos los componentes de una topología de varios servidores con varios equipos que ejecutan el servidor de charla persistente, el servicio opcional de cumplimiento de normas y una base de datos de conformidad por separado.
  
**Topología de varios servidores**

![Servidor de chat persistente: topología de varios servidores](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Las topologías de varios servidores permiten agrupar las funciones de servidor. En un grupo de servidores, los servicios de Chat persistentes comunican y compartan datos. Por ejemplo, historial de charla se registró originalmente en un servicio de charla persistente está disponible desde cualquier servicio de Chat persistentes en el sistema. Puede tener acceso a un archivo que se carga a través de un servicio de Chat persistentes cualquier servicio de Chat persistentes. Los usuarios pueden conectarse a diferentes persistente Chat Server servidores frontales y pueden comunicarse entre sí. El puerto predeterminado de TCP 8011 se conecta a un servidor a un grupo de servidores y es utilizada por los servicios de Chat persistentes para comunicarse entre sí, o bien para fines administrativos.
  
Por ejemplo, en un servidor de charla persistente de cuatro servidores implementación, donde pueden ser 80.000 usuarios simultáneamente sesión en y mediante Chat persistente, la carga se distribuye uniformemente a 20.000 usuarios por servidor. Si un servidor deja de estar disponible, los usuarios que están conectados a ese servidor perderá su acceso al servidor de Chat persistentes. Los usuarios desconectados se transferirán automáticamente a los servidores restantes hasta que se restaure el servidor que no se encuentra disponible. 
  

