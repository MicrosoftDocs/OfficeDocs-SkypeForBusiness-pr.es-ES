---
title: Planificar una topología de servidores de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Resumen: Lea este tema para obtener información sobre las topologías y los componentes del servidor de chat persistentes en Skype empresarial Server 2015.'
ms.openlocfilehash: afcdf7ed85cca6b54652dcf5170316258a6b5551
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815728"
---
# <a name="plan-persistent-chat-server-topology"></a>Planificar una topología de servidores de chat persistente
 
**Resumen:** Lea este tema para obtener información sobre los componentes y las topologías de servidores de chat persistentes en Skype empresarial Server 2015.
  
El servidor de chat persistente admite configuraciones de servidor único y de varios servidores. Puede instalar el servidor de chat persistente en un servidor de Skype empresarial Server 2015 Enterprise Edition o Standard Edition. 

> [!NOTE] 
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 
  
## <a name="persistent-chat-server-components"></a>Componentes del servidor de chat persistentes

El servidor de chat persistente incluye los componentes siguientes:
  
- Uno o más equipos que ejecutan el servidor de chat persistente y proporcionan los siguientes servicios:
    
  - Servicio de chat persistente
    
  - Servicio de cumplimiento, que se activa si el cumplimiento está habilitado
    
- Uno o más servidores (más de uno si se usa el reflejo) ejecutando la base de datos back-end de SQL Server para hospedar la base de datos de contenido de chat persistente en la que se almacenan el contenido, las salas y las categorías del salón de chat.
    
    > [!NOTE]
    > La base de datos back-end almacena los datos del historial de chats, incluida información sobre categorías y salones de chat persistentes que se crean. 
  
- Si el cumplimiento está habilitado, se pueden almacenar uno o varios servidores (más de uno si se usan reflejos) ejecutando la base de datos back-end de SQL Server para hospedar la base de datos de cumplimiento de chats persistentes, donde se almacenan los eventos de cumplimiento y el contenido de chat para el cumplimiento.
    
Para obtener más información sobre los requisitos de hardware y software para el servidor de chat persistente, consulte [requisitos del servidor de Skype empresarial server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) y [requisitos de hardware y software para el servidor de chat persistente en skype empresarial Server 2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Topologías de servidores de chat persistentes

Puede implementar un servidor de chat persistente en grupos de un solo servidor o de varios servidores, y con topología de un único grupo o de varios grupos. El servidor de chat persistente admite las siguientes topologías:
  
-  Servidor Standard Edition con el servidor de chat persistente combinados en el servidor front-end
    
-  Servidor Standard Edition con servidor de chat persistente en un servidor independiente
    
-  Servidor Enterprise Edition con un único servidor de chat persistente en un servidor independiente
    
-  Servidor Enterprise Edition con más de un servidor de chat persistente en servidores independientes
    
Aunque puede implementar un servidor de chat persistente en un servidor Standard Edition, tenga en cuenta que el rendimiento y la escala se verán afectados, y la alta disponibilidad no es una opción. Por lo tanto, se recomienda implementar una conversación persistente en un servidor Standard Edition principalmente con fines de prueba de concepto y evaluación. 
  
Skype empresarial Server 2015 admite una gran variedad de escenarios collocation, lo que le ofrece la flexibilidad de ahorrar costos de hardware ejecutando varios componentes en un servidor (si tiene una pequeña organización) o para ejecutar componentes individuales en diferentes servidores ( Si tiene una organización más grande que necesita escalabilidad y rendimiento). Necesita considerar los factores de escalabilidad antes de decidir si los componentes se van a combinar. Los escenarios de collocation difieren en los servidores de Skype empresarial Server 2015 Enterprise Edition y Standard Edition. 
  
Los siguientes escenarios describen las topologías en más detalle, incluso los escenarios de combinación y las opciones para los servidores de base de datos back-end. Para obtener más información sobre collocation de todos los roles de servidor y bases de datos, consulte [aspectos básicos de la topología para Skype empresarial server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Servidor Standard Edition con el servidor de chat persistente combinados en el servidor front-end

Con Standard Edition, puede combinar el chat persistente en el servidor front-end. Esta es la configuración más básica y más sencilla. Debe asegurarse de que el servidor front-end existente tiene la capacidad suficiente en cuanto a recursos físicos: CPU, memoria, espacio en disco, etc.
  
Además, puede Collocate el servidor back-end del servidor de chat persistente y la base de datos de cumplimiento persistente de chat (si está habilitada) en el servidor back-end local de SQL Server Express. También, puede optar por usar un SQL Server independiente con una instancia dedicada. 
  
> [!IMPORTANT]
> No puede agregar servidores adicionales a un grupo de servidores de chat persistente si el primer servidor de chat persistente se encuentra en un servidor de front-end Standard Edition. Se recomienda instalar el primer servidor como una instancia independiente para que pueda agregar más servidores más adelante, si es necesario. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Servidor Standard Edition con el servidor de chat persistente instalados en un servidor independiente

Con Standard Edition, puedes instalar el servidor de chat persistente como una instancia independiente y agregar más servidores luego, si es necesario.   
  
Puede Collocate el servidor back-end del servidor de chat persistente y la base de datos de cumplimiento persistente de chat (si está habilitada) en el servidor back-end local de SQL Server Express. También, puede optar por usar un SQL Server independiente con una instancia dedicada. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Servidor Enterprise Edition con un único servidor de chat persistente

Con Enterprise Edition, debe instalar el servidor de chat persistente en un equipo independiente. Es decir, no puede Collocate el servidor de chat persistente en el servidor front-end Enterprise Edition. Esta implementación requiere un servidor independiente que ejecute el servidor de chat persistente y el servicio de cumplimiento (si está habilitado).
  
Sin embargo, puede Collocate la base de datos de SQL Server para el servidor de chat persistente en la base de datos back-end de un grupo de servidores front end Enterprise Edition.
  
> [!NOTE]
> Si planea utilizar Grupos de disponibilidad AlwaysOn de SQL para HA DR, tenga en cuenta que no es compatible con las bases de datos del servidor de chat persistente. 
  
Si Collocate la base de datos de chat persistente con la base de datos back-end, puede usar una única instancia de SQL Server para cualquiera de las bases de datos o todas ellas, o bien puede usar una instancia independiente de SQL Server para cada una de ellas.
  
> [!IMPORTANT]
> El servidor que hospeda la base de datos de chat persistente puede hospedar otras bases de datos. Sin embargo, cuando considere collocating la base de datos de chat persistente con otras bases de datos, tenga en cuenta que si está almacenando los mensajes de más de unos pocos usuarios, el espacio en disco necesario para la base de datos de chat persistente puede crecer muy grande. Por esta razón, no recomendamos collocating la base de datos de chat persistente con la base de datos back-end. 
  
La siguiente ilustración muestra todos los componentes de una topología para un único servidor de chat persistente con el cumplimiento habilitado (opcional).
  
**Topología de un único servidor**

![Servidor de chat persistente: topología de un servidor](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Servidor Enterprise Edition con varios servidores de chat persistente

Con Enterprise Edition, puede implementar una topología de varios servidores para una mayor capacidad y confiabilidad. Una topología de varios servidores es la misma que la topología de servidor único, excepto en que varios servidores hospedan un servidor de chat persistente y pueden escalar más alto. La topología de varios servidores puede incluir hasta cuatro equipos activos que ejecutan el servidor de chat persistente (la alta disponibilidad y las configuraciones de recuperación ante desastres permiten hasta ocho, pero solo cuatro pueden estar activos y los cuatro restantes en espera). Cada servidor puede admitir hasta 20.000 usuarios simultáneos, para un total de 80.000 usuarios simultáneos conectados a un grupo de servidores de chat persistente con 4 servidores. Varios equipos que ejecutan el servidor de chat persistente deben residir en el mismo dominio de servicios de dominio de Active Directory que Skype empresarial Server y el servicio de cumplimiento.
  
La siguiente ilustración muestra todos los componentes de una topología de varios servidores con varios equipos que ejecutan un servidor de chat persistente, el servicio de cumplimiento opcional y una base de datos de cumplimiento independiente.
  
**Topología de varios servidores**

![Servidor de chat persistente: topología de varios servidores](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Las topologías de varios servidores permiten agrupar las funciones de servidor. En un grupo de servidores, los servicios de chat persistentes se comunican y comparten datos. Por ejemplo, el historial de conversaciones publicado originalmente en un servicio de chat persistente está disponible desde cualquier servicio de chat persistente en el sistema. Cualquier servicio de chat persistente puede acceder a un archivo que se carga a través de un servicio de chat persistente. Los usuarios se pueden conectar a diferentes servidores de aplicaciones para el servidor de mensajería instantánea y se pueden comunicar entre sí. El puerto predeterminado de TCP 8011 conecta un servidor a un grupo de servidores y es utilizado por los servicios de chat persistentes para comunicarse entre sí o con fines administrativos.
  
Por ejemplo, en una implementación de servidor de chat persistente de cuatro servidores, en la que los usuarios de 80.000 pueden iniciar sesión de forma simultánea en una conversación persistente, la carga se distribuye uniformemente en 20.000 usuarios por servidor. Si un servidor no está disponible, los usuarios que estén conectados a él perderán el acceso al servidor de chat persistente. Los usuarios desconectados se transferirán automáticamente a los servidores restantes hasta que se restaure el servidor que no se encuentra disponible. 
  

