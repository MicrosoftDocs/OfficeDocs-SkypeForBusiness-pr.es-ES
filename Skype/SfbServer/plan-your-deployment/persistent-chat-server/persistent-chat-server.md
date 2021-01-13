---
title: Planear el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Resumen: lea este tema para obtener información sobre cómo planear el servidor de chat persistente en Skype Empresarial Server 2015.'
ms.openlocfilehash: 9195c149744b9aab9927f0b2a6e490442cff6573
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813670"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planear el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo planear el servidor de chat persistente en Skype Empresarial Server 2015.
  
El servidor de chat persistente es un rol opcional que permite a varios usuarios de su organización participar en conversaciones de salón de chat que persisten con el tiempo. Aunque los usuarios pueden comunicarse en tiempo real durante una sesión de chat, el contenido de cada sesión (incluido el texto, los vínculos y los archivos) es persistente, lo que significa que los usuarios pueden ver y buscar todo el contenido de la sesión en cualquier momento.
  
El servidor de chat persistente puede ayudar a mejorar la comunicación dentro de la organización mediante:
  
- Ampliar el conocimiento y la participación de la información en toda la organización
    
- Habilitar el uso compartido eficaz de la información 
    
- Mejorar la comunicación entre equipos, incluidos los equipos dispersos geográficamente y entre funciones
    
- Reducción de la sobrecarga de información
    
- Seguir las normativas de cumplimiento mediante la implementación opcional del servicio de cumplimiento de chat persistente

> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Arquitectura de alto nivel del servidor de chat persistente

En el siguiente diagrama se muestra una vista general de la arquitectura del servidor de chat persistente. 
  
![Arquitectura de alto nivel del servidor de chat persistente](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
El chat persistente consta de un rol de servidor front-end que proporciona los servicios de chat persistente, así como un componente back-end SQL base de datos. Los componentes front-end y back-end se incluyen en un grupo de chat persistente dedicado. Cada equipo que hospeda el servidor de chat persistente debe tener acceso a una topología existente de Skype Empresarial Server 2015. En este diagrama, hay un grupo de servidores de chat persistente (A), que depende del grupo A de Skype Empresarial Server para enrutar mensajes a él.
  
Puede implementar uno o más grupos de servidores de chat persistente, cada uno con hasta cuatro servidores de chat persistente activos que admitan hasta 80.000 usuarios simultáneos.
  
Skype Empresarial Server 2015 se comunica con el servicio de chat persistente mediante el protocolo de inicio de sesión (SIP) para el registro y el protocolo XCCOS (Extensible Chat Communication Over SIP) para chat. 
  
## <a name="persistent-chat-services"></a>Servicios de chat persistente

En el siguiente diagrama se muestran los servicios front-end del servidor de chat persistente y cómo estos servicios se comunican con los componentes de la base de datos back-end. Los componentes front-end incluyen los servicios de chat persistente y el servicio de cumplimiento. Los componentes back-end incluyen el almacén de chat persistente y el almacén de cumplimiento de chat persistente.
  
![Servicios de alto nivel del servidor de chat persistente](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Servicio de chat

El servicio de chat, también denominado servicio canal, es el servicio principal responsable del servidor de chat persistente. El servicio de chat proporciona las siguientes funciones:
  
- Acepta mensajes entrantes
    
- Registra y enumera participantes en línea dentro de un salón de chat persistente
    
- Retransmite mensajes a los suscriptores de otros canales
    
- Implementa lógica para la administración de canales, invitaciones a salas de chat, búsquedas y nuevas notificaciones de contenido
    
El servicio de chat persistente almacena y tiene acceso al contenido del salón de chat y otros metadatos del sistema (reglas de autorización, entre otros) mediante el almacén de chat persistente. El servicio almacena los archivos que se cargan en los salas de chat en el almacén de archivos de chat persistente.
  
### <a name="compliance-service"></a>Servicio Cumplimiento

Si su organización tiene normativas que requieren que se archive la actividad de chat persistente, puede implementar el servicio opcional de cumplimiento de chat persistente. El servicio de cumplimiento es responsable de archivar el contenido y los eventos de chat, como unirse y salir de salas, al almacén de archivos de cumplimiento de chat persistente. El servicio de cumplimiento se instala en cada servidor de chat persistente de un grupo de chat persistente. 
  
### <a name="web-services"></a>Servicios web

Los servicios web de chat persistente se ejecutan en los servidores front-end de Skype Empresarial. Los servicios web dependen de Internet Information Services (IIS) y se implementan como componentes web:
  
- Los servicios web de chat persistente para la carga y descarga de archivos son responsables de publicar y recuperar archivos de los salón de chat.
    
- Los servicios web de chat persistente para la administración de salas de chat son responsables de proporcionar a los usuarios la capacidad de administrar sus salas de chat y crear nuevos salón de chat.
    
## <a name="defining-requirements-for-your-organization"></a>Definición de requisitos para la organización

Si decide implementar el servidor de chat persistente, deberá determinar los requisitos empresariales de su organización y, a continuación, definir la topología, la infraestructura y los requisitos técnicos para satisfacer sus necesidades empresariales. Para optimizar la implementación, tendrá que responder a las siguientes preguntas:
  
- ¿Está migrando desde una versión anterior del servidor de chat en grupo o una versión anterior del servidor de chat persistente, o está implementando el servidor de chat persistente por primera vez?
    
- ¿Quién puede usar el servidor de chat persistente? Las directivas de chat persistente se especifican para determinar el acceso de usuarios en el nivel global, de sitio o de usuario.
    
- ¿Cuántos usuarios requerirán acceso al servidor de chat persistente? El servidor de chat persistente admite 150 000 usuarios aprovisionados (habilitados por la directiva) y un máximo de 80 000 usuarios simultáneos. Un único servidor de chat persistente puede admitir 20.000 usuarios conectados y un único grupo de servidores de chat persistente puede tener hasta 4 servidores activos para un total de 80.000 usuarios conectados simultáneamente.
    
- ¿Cómo desea controlar los ámbitos, los límites éticos y el acceso? Puede definir categorías para segregar estos límites y elegir quién puede estar en salas creadas en cada una de estas categorías.
    
- ¿Qué desea para controlar quién puede crear salones? Puede definir creadores que pueden crear salas. Los creadores pueden asignar otros miembros como administradores de los salón de chat para la administración continua de las salas.
    
- ¿Cómo desea crear salas? El servidor de chat persistente proporciona una característica basada en web para crear y administrar salas. Esto se puede iniciar desde el cliente de Skype Empresarial. Puede definir una solución de cliente que implemente los flujos de trabajo y los requisitos empresariales, y configure el servidor de chat persistente para dirigir a los usuarios a la solución personalizada.
    
- ¿Qué tipo de complemento desea suministrar? Los complementos mejoran la experiencia en la sala aprovechando el panel de extensibilidad en el cliente de Skype Empresarial para proporcionar contexto que sea relevante para la sala. Puede elegir qué complementos generales podrían ser más útiles (por ejemplo, el sitio web de la empresa, los documentos de colaboración interna, etc.). Los administradores del salón de chat pueden elegir uno de los complementos registrados y asociarlo a sus salones, si lo desean. 
    
- ¿Qué tipo de requisitos de alta disponibilidad y recuperación ante desastres tiene? El servidor de chat persistente SQL Server creación de reflejos y SQL Server clústeres para alta disponibilidad. Para la recuperación ante desastres, el servidor de chat persistente admite hasta 8 servidores (4 activos y 4 en espera) en un grupo extendido con SQL Server de registros. 
    
- ¿Existen requerimientos legales? Si su empresa se encuentra en un país o región donde los datos deben mantenerse dentro del país, es posible que tenga que implementar varios grupos de servidores de chat persistente, cada uno local en una zona geográfica específica. Un salón, una categoría o un complemento no abarca grupos de servidores; pertenece a un solo grupo de servidores de chat persistente. 
    
    > [!NOTE]
    > Tener varios grupos de servidores de chat persistente no le da más escala (todavía puede tener solo 80 000 usuarios simultáneos en todos los grupos de servidores de chat persistente). La razón principal para admitir varios grupos de servidores de chat persistente es admitir problemas normativos. 
  
## <a name="for-more-information"></a>Más información

Para obtener más información acerca de la instalación y configuración del servidor de chat persistente, consulte los siguientes temas:
  
- Para obtener más información sobre cómo implementar el servidor de chat persistente, consulte [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Para obtener más información sobre cómo configurar las opciones en la implementación del servidor de chat persistente, consulte Administrar el servidor de chat persistente en [Skype Empresarial Server 2015.](../../manage/persistent-chat/persistent-chat.md)
    

