---
title: Planificar el servidor de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Resumen: Leer este tema para aprender a planear persistente Server Chat de Skype para Business Server 2015.'
ms.openlocfilehash: 0380b5ebb43e198160faa3e7f10b1563b4def80f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planificar el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a planear persistente Server Chat de Skype para Business Server 2015.
  
Servidor de charla persistente es una función opcional que permite a varios usuarios de la organización participar en las conversaciones de salón de chat que persisten en el tiempo. A pesar de que los usuarios se pueden comunicar en tiempo real durante una sesión de chat, el contenido de cada sesión (incluso el texto, los vínculos y los archivos) es persistente, por lo que los usuarios pueden ver y buscar todo el contenido de la sesión en cualquier momento.
  
Servidor de charla persistente puede ayudar a mejorar la comunicación dentro de su organización por:
  
- Ampliar el conocimiento de la información y la participación en toda la organización
    
- Habilitar el uso compartido eficiente de la información 
    
- Mejora de la comunicación entre equipos, incluidos los equipos geográficamente dispersos y de funciones cruzadas
    
- Reducir la sobrecarga de información
    
- Respetar las normas de cumplimiento con la implementación opcional del servicio de cumplimiento del chat persistente
    
## <a name="persistent-chat-server-high-level-architecture"></a>Arquitectura de alto nivel del servidor de chat persistente

El diagrama siguiente muestra una visión general de la arquitectura de servidor de charla persistente. 
  
![Arquitectura de alto nivel del servidor de chat persistente](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
El chat persistente consiste de un rol de servidor front-end que brinda los servicios de chat persistente, así como también de un componente de base de datos de SQL back-end. Los componentes tanto front-end como back-end se incluyen en un grupo de chat persistente dedicado. Cada equipo que aloja el servidor de charla persistente debe tener acceso a un Skype existente para la topología de servidor de negocios 2015. En este diagrama, hay un grupo de servidor de charla persistente (A), que depende de Skype para un grupo de servidores empresariales para enrutar mensajes a él.
  
Puede implementar uno o más grupos de servidor de charla persistente, cada uno con hasta cuatro active servidores de charla persistente soporta hasta 80K de usuarios simultáneos.
  
Skype para Business Server 2015 se comunica con el servicio de charla persistente mediante el protocolo de inicio de sesión (SIP) para el registro y el Protocolo Extensible charla comunicación sobre SIP (XCCOS) para la charla. 
  
## <a name="persistent-chat-services"></a>Servicios de chat persistente

El diagrama siguiente muestra los servicios front-end Server Chat persistente y cómo estos servicios se comunican con los componentes de base de datos back-end. Los componentes front-end incluyen los servicios de chat persistente y el servicio de cumplimiento. Los componentes back-end incluyen el almacén de chat persistente y el almacén de cumplimiento del chat persistente.
  
![Servicios de alto nivel del servidor de chat persistente](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Servicio de chat

El servicio de chat, también denominado servicio de canal, es el servicio principal que se encarga del servidor de chat persistente. El servicio de chat brinda las siguientes funciones:
  
- Acepta mensajes entrantes
    
- Registra y muestra a los participantes en línea dentro de una sala de Chat persistentes
    
- Retransmite mensajes a otros suscriptores de canal
    
- Implementa la lógica para la administración del canal, las invitaciones a un salón de chat, las búsquedas y las notificaciones de nuevo contenido
    
El servicio de chat persistente almacena el contenido del salón de chat y otros metadatos del sistema (como las reglas de autorización, etc.) y obtiene acceso a ellos por medio del almacén de chat persistente. Este servicio almacena archivos que se cargan en los salones de chat en el almacén de archivos del chat persistente.
  
### <a name="compliance-service"></a>Servicio de cumplimiento

Si la organización cuenta con normas que precisan que se archive la actividad del chat persistente, puede implementar el servicio de cumplimiento opcional del chat persistente. El servicio de cumplimiento se encarga del archivado del contenido del chat y de los eventos (como entrar y salir de los salones) en el almacén de archivos de cumplimiento del chat persistente. El servicio de cumplimiento de normas se instala en cada servidor de charla persistente en un grupo de Chat persistentes. 
  
### <a name="web-services"></a>Servicios web

Los servicios de web Chat persistente que se ejecutan en el Skype para servidores empresariales frontales. Los servicios web dependen de Internet Information Services (IIS) y se implementan como componentes web:
  
- Los servicios web del chat persistente para cargar y descargar archivos se encargan de publicar archivos y de recuperarlos de los salones de chat.
    
- Los servicios web del chat persistente para la administración de los salones de chat se encargan de brindar a los usuarios la capacidad de administrar los salones de chat y de crearlos.
    
## <a name="defining-requirements-for-your-organization"></a>Definir los requisitos para la organización

Si decide implementar el servidor de charla persistente, necesitará determinar los requisitos empresariales de su organización, a continuación, definir la topología, la infraestructura y los requisitos técnicos para apoyar las necesidades de su negocio. Para optimizar la implementación, debe responder las siguientes preguntas:
  
- ¿Está migrando desde una versión anterior del servidor de charla de grupo o una versión anterior del servidor de charla persistente o está implementando el servidor de charla persistente por primera vez?
    
- ¿Quién puede usar el servidor de chat persistente? Puede especificar las directivas de chat persistente a fin de determinar el acceso de usuario en el ámbito global, en el sitio o por usuario.
    
- ¿Cuántos usuarios necesitarán disponer de acceso al servidor de chat persistente? El servidor de chat persistente es compatible con 150 000 usuarios aprovisionados (habilitados por directiva) y un máximo de 80 000 usuarios simultáneos. Un único servidor de chat persistente puede admitir 20 000 usuarios conectados y un único grupo de servidores de chat persistente puede tener hasta 4 servidores activos para un total de 80 000 usuarios conectados de forma simultánea.
    
- ¿Cómo desea controlar los ámbitos, los límites éticos y el acceso? Puede definir categorías para segregar estos límites y elegir quién puede estar en los salones que se crean en cada una de estas categorías.
    
- ¿Cómo desea controlar quién puede crear salones? Es posible definir creadores para la creación de salones. Dichos creadores pueden asignar a otros miembros como directores de los salones de chat para la administración en curso de los salones.
    
- ¿Cómo desea crear salas? Servidor de charla persistente proporciona una función basada en web para la creación y administración de salas. Esto se puede iniciar desde el Skype para cliente de empresa. Puede definir una solución de cliente que implementa sus requisitos de negocio y flujos de trabajo y se configura el servidor de charla persistente para dirigir a los usuarios a su solución personalizada.
    
- ¿Qué tipo de complementos desea suministrar? Los complementos mejoran la experiencia en el salón al aprovechar el panel de extensibilidad del cliente de Skype Empresarial para proporcionar un contexto relevante al salón. Puede elegir qué complementos generales podrían ser más útiles (por ejemplo, el sitio web de la compañía, los documentos de colaboración interna, etc.). Los directores del salón de chat pueden elegir uno de los complementos registrados y asociarlo a los salones, si así lo desean. 
    
- ¿Qué tipo de requisitos de alta disponibilidad y recuperación ante desastres tiene? Servidor de charla persistente admite la creación de reflejos de SQL Server y SQL Server clustering de alta disponibilidad. Recuperación ante desastres, persistente Chat Server admite hasta 8 servidores (4 activos y 4 suspensión) en un grupo estirado con SQL Server trasvase de registros. 
    
- ¿Dispone de requisitos de regulación? Si su empresa está en un país o región donde los datos deben mantenerse dentro del país, debe implementar varios grupos de servidor de charla persistente, cada local en una zona geográfica específica. Una sala, categoría o complemento no abarcan grupos--pertenece a sólo un grupo de servidores de charla persistente. 
    
    > [!NOTE]
    > Tener varios grupos de servidor de charla persistente no le otorga más escala (sólo 80.000 usuarios simultáneos puede tener todavía a través de todos los grupos de servidor de charla persistente). La razón principal para la compatibilidad con varios grupos de servidor de charla persistente es apoyar problemas regulatorios. 
  
## <a name="for-more-information"></a>Para más información

Para más información sobre la instalación y la configuración del servidor de chat persistente, consulte los siguientes temas:
  
- Para obtener más información acerca de cómo implementar el servidor de charla persistente, vea [Implementar servidor de charla persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Para obtener más información acerca de cómo configurar la implementación del servidor de charla persistente, vea [Administrar servidor de charla persistente en Skype para Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
    

