---
title: Planificar el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Resumen: Lea este tema para obtener información sobre cómo planear para servidores de Chat persistente en Skype Business Server 2015.'
ms.openlocfilehash: 9e78935393eb01b5bb79bb71a167df9cd6a60aa9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213756"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planificar el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo planear para servidores de Chat persistente en Skype Business Server 2015.
  
Persistent Chat Server es un rol opcional que permite a varios usuarios de la organización participar en conversaciones de salón de chat que persisten a lo largo del tiempo. A pesar de que los usuarios se pueden comunicar en tiempo real durante una sesión de chat, el contenido de cada sesión (incluso el texto, los vínculos y los archivos) es persistente, por lo que los usuarios pueden ver y buscar todo el contenido de la sesión en cualquier momento.
  
Servidor de Chat persistente puede ayudar a mejorar la comunicación dentro de la organización mediante:
  
- Ampliar el conocimiento de la información y la participación en toda la organización
    
- Habilitar el uso compartido eficiente de la información 
    
- Mejorar la comunicación entre equipos, incluso geográficamente dispersos y con funciones cruzadas
    
- Reducir la sobrecarga de información
    
- Respetar las normas de cumplimiento con la implementación opcional del servicio de cumplimiento del chat persistente

> [!NOTE] 
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Arquitectura de alto nivel del servidor de chat persistente

En el siguiente diagrama se muestra una visión general de la arquitectura de servidor de Chat persistente. 
  
![Arquitectura de alto nivel del servidor de chat persistente](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
El chat persistente consiste de un rol de servidor front-end que brinda los servicios de chat persistente, así como también de un componente de base de datos de SQL back-end. Los componentes tanto front-end como back-end se incluyen en un grupo de chat persistente dedicado. Cada equipo que hospeda el servidor de Chat persistente debe tener acceso a un Skype existente para la topología empresarial Server 2015. En este diagrama, hay un grupo de servidores de Chat persistente (A), que es dependiente de Skype para un grupo de servidores de negocio para enrutar mensajes a ella.
  
Puede implementar uno o más grupos de servidores de Chat persistente, cada uno con hasta cuatro active servidores de Chat persistente compatibilidad con copia de seguridad a los usuarios simultáneos de 80 KB.
  
Skype para Business Server 2015 se comunica con el servicio de Chat en grupo mediante el protocolo de inicio de sesión (SIP) para el registro y el Protocolo Extensible Chat comunicación a través de SIP (GRPCHAT) de chat. 
  
## <a name="persistent-chat-services"></a>Servicios de chat persistente

El siguiente diagrama muestra los servicios front-end del servidor de Chat persistente, y cómo estos servicios se comunican con los componentes de base de datos back-end. Los componentes front-end incluyen los servicios de chat persistente y el servicio de cumplimiento. Los componentes back-end incluyen el almacén de chat persistente y el almacén de cumplimiento del chat persistente.
  
![Servicios de alto nivel del servidor de chat persistente](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Servicio de chat

El servicio de chat, también denominado servicio de canal, es el servicio principal que se encarga del servidor de chat persistente. El servicio de chat brinda las siguientes funciones:
  
- Acepta mensajes entrantes
    
- Registra y enumera los participantes en línea dentro de un salón de chat persistente
    
- Retransmite mensajes a los suscriptores de otros canales
    
- Implementa la lógica para la administración del canal, las invitaciones a un salón de chat, las búsquedas y las notificaciones de nuevo contenido
    
El servicio de chat persistente almacena el contenido del salón de chat y otros metadatos del sistema (como las reglas de autorización, etc.) y obtiene acceso a ellos por medio del almacén de chat persistente. Este servicio almacena archivos que se cargan en los salones de chat en el almacén de archivos del chat persistente.
  
### <a name="compliance-service"></a>Servicio de cumplimiento

Si la organización cuenta con normas que precisan que se archive la actividad del chat persistente, puede implementar el servicio de cumplimiento opcional del chat persistente. El servicio de cumplimiento se encarga del archivado del contenido del chat y de los eventos (como entrar y salir de los salones) en el almacén de archivos de cumplimiento del chat persistente. El servicio de cumplimiento se instala en cada servidor de Chat persistente de un grupo de Chat persistente. 
  
### <a name="web-services"></a>Servicios web

Los servicios web de Chat persistente que se ejecutan en el Skype para servidores Front-End de negocio. Los servicios web dependen de Internet Information Services (IIS) y se implementan como componentes web:
  
- Los servicios web del chat persistente para cargar y descargar archivos se encargan de publicar archivos y de recuperarlos de los salones de chat.
    
- Los servicios web del chat persistente para la administración de los salones de chat se encargan de brindar a los usuarios la capacidad de administrar los salones de chat y de crearlos.
    
## <a name="defining-requirements-for-your-organization"></a>Definir los requisitos para la organización

Si decide implementar servidor de Chat persistente, debe determinar los requisitos empresariales de su organización y, después, definir la topología, infraestructura y requisitos técnicos para admitir las necesidades de negocio. Para optimizar la implementación, debe responder a las siguientes preguntas:
  
- ¿Está migrando desde una versión anterior del servidor de conversaciones en grupo, o una versión anterior del servidor de Chat persistente o a implementar servidor de Chat persistente por primera vez?
    
- ¿Quién puede usar el servidor de chat persistente? Puede especificar las directivas de chat persistente a fin de determinar el acceso de usuario en el ámbito global, en el sitio o por usuario.
    
- ¿Cuántos usuarios necesitarán disponer de acceso al servidor de chat persistente? El servidor de chat persistente es compatible con 150 000 usuarios aprovisionados (habilitados por directiva) y un máximo de 80 000 usuarios simultáneos. Un único servidor de chat persistente puede admitir 20 000 usuarios conectados y un único grupo de servidores de chat persistente puede tener hasta 4 servidores activos para un total de 80 000 usuarios conectados de forma simultánea.
    
- ¿Cómo desea controlar los ámbitos, los límites éticos y el acceso? Puede definir categorías para segregar estos límites y elegir quién puede estar en los salones que se crean en cada una de estas categorías.
    
- ¿Cómo desea controlar quién puede crear salones? Es posible definir creadores para la creación de salones. Dichos creadores pueden asignar a otros miembros como directores de los salones de chat para la administración en curso de los salones.
    
- ¿Cómo desea crear salones de? Servidor de Chat persistente proporciona una característica basada en web para la creación y administración de salas. Esto se puede iniciar desde el Skype para clientes empresariales. Puede elegir definir una solución de cliente que implementa los requisitos del negocio y flujos de trabajo y se configura el servidor de Chat persistente para dirigir a los usuarios a su solución personalizada.
    
- ¿Qué tipo de complementos desea suministrar? Los complementos mejoran la experiencia en el salón al aprovechar el panel de extensibilidad del cliente de Skype Empresarial para proporcionar un contexto relevante al salón. Puede elegir qué complementos generales podrían ser más útiles (por ejemplo, el sitio web de la compañía, los documentos de colaboración interna, etc.). Los directores del salón de chat pueden elegir uno de los complementos registrados y asociarlo a los salones, si así lo desean. 
    
- ¿Qué tipo de requisitos de alta disponibilidad y recuperación ante desastres tiene? Servidor de Chat persistente admite la creación de reflejos de SQL Server y agrupación en clústeres de SQL Server para una alta disponibilidad. Para la recuperación ante desastres, Persistent Chat Server admite hasta 8 servidores (4 activo y 4 suspensión) en un grupo de servidores expandida con SQL Server el trasvase de registros. 
    
- ¿Dispone de requisitos de regulación? Si la compañía se encuentra en un país o región donde datos deben mantenerse dentro del país, necesita implementar varios grupos de servidores de Chat persistente, cada local en una zona geográfica específica. Una sala, categoría o complemento no abarcan grupos de servidores--al que pertenece el grupo de servidores de un solo servidor de Chat persistente. 
    
    > [!NOTE]
    > Tener varios grupos de servidores de Chat persistente no da más escala (todavía puede tener solo 80.000 usuarios simultáneos a través de todos los grupos de servidores de Chat persistente). La razón principal para la compatibilidad con varios grupos de servidores de Chat persistente que se va a admitir problemas regulatorios. 
  
## <a name="for-more-information"></a>Para más información

Para más información sobre la instalación y la configuración del servidor de chat persistente, consulte los siguientes temas:
  
- Para obtener información detallada acerca de cómo implementar servidores de Chat persistente, vea [Implementar servidor de Chat persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Para obtener información detallada acerca de cómo configurar las opciones en la implementación de servidor de Chat persistente, vea [Administrar servidor de Chat persistente en Skype para Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
    

