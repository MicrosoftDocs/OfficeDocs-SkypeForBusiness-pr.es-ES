---
title: Administrar los equipos durante la transición a la nueva Microsoft Teams & Skype para el centro de administración de negocio
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Entender cómo administrar todo el inquilino y configuración del usuario para los equipos durante la transición de los equipos de la experiencia en el centro de administración de Office 365 para el nuevo Microsoft Teams & Skype para el centro de administración de negocio.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: dddb73e5b616fead421d1b610eff6229b4191d06
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965702"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Administrar los equipos durante la transición a la nueva Microsoft Teams & Skype para el centro de administración de negocio
======================================================

El nuevo Centro de administración de Microsoft Teams y Skype Empresarial estará disponible muy pronto. 

A partir de marzo de 2018, gradualmente nos estamos migrar la configuración de Microsoft Teams & Skype para el centro de administración de negocio desde ambos Skype el actual para el centro de administración de negocio y la Teams Microsoft experiencia en el centro de administración de Office 365. Cuando se migra una configuración, recibe una notificación y, a continuación, se le dirige a la ubicación de la configuración en el nuevo Centro de administración de Microsoft Teams y Skype Empresarial.

Vamos a continuar migrar otras funciones de la Skype para el centro de administración de negocio en los próximos meses. Puede permanecer al día a través de nuestro pública [Guía básica](https://aka.ms/Office365Roadmap).

> [!NOTE]
> Nos estamos implantar el nuevo Microsoft Teams & Skype para el centro de administración de negocio en etapas. Como resultado, todos los clientes no verán el centro de administración de nuevo al mismo tiempo. Se le notificará cuando puede empezar a usar el nuevo centro de administración.

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>¿Qué es el nuevo Microsoft Teams & Skype para el centro de administración de negocio?  

La nueva experiencia del centro de administración le proporcionará una experiencia unificada para administrar los equipos y Skype para la empresa. Ofrecemos una funcionalidad adicional, entendimiento de extremo a otro y la capacidad para administrar la configuración de los equipos en un nivel de usuario.

![Captura de pantalla de los equipos de Microsoft & Skype para el centro de administración de negocio.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>La configuración de migrar a la nueva Microsoft Teams & Skype para el centro de administración de negocio

A partir de mediados de marzo 2018, las siguientes capacidades estaban disponibles en el nuevo Microsoft Teams & Skype para el centro de administración de negocio: 

- **Directiva de mensajería de equipos de Microsoft**: Crear directiva para la administración de nivel de usuario de la experiencia del cliente Microsoft Teams para escenarios de mensajería.
- **Directiva de actualización de los equipos de Microsoft**: configuración de la experiencia de actualización e interoperabilidad entre Skype para la empresa y Microsoft Teams. Vea, https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype. 
- **Configuración de mensajería de invitado de los equipos de Microsoft**: controlar las capacidades de mensajería para las cuentas de invitado en Microsoft Teams. 
- **Configuración de federación**: administrar la federación entre los inquilinos para Microsoft Teams y Skype para la empresa. 
- **Administración de usuarios**: asignar directivas y configuración de cuentas de usuario. 
- **Conferencias de audio**: configurar números de acceso telefónico y de Skype para empresas y Microsoft Teams.  

Además, la configuración existente para General, integración correo electrónico, almacenamiento en la nube personalizados, las llamadas y las reuniones y mensajería en Microsoft Teams ahora se han migrado a la nueva Microsoft Teams & Skype para el centro de administración empresarial (también conocido como el nuevo administrador Portal). 

> [!NOTE]
>Podrá continuar usar el panel de grupos en el centro de administración de Office 365 para la configuración relacionada con **los equipos y los canales**. Configuración de **aplicaciones** permanecerá en el área de los equipos del centro de administración de Office 365 y se van a migrar más adelante. 

![Página de captura de pantalla de los equipos en el centro de administración de Office 365.](media/manage-teams-skypeforbusiness-admin-center-teams-in-O365.png)

Con respecto a los valores disponibles en **configuración de tipo de licencia de usuario /**, básicamente proporciona una forma de configurar grupos de usuarios de forma diferente. Ahora, con el nuevo portal de administración, es posible en cada usuario. 

La configuración del tipo de licencia se van a migrar. Si actualmente usa la opción de **Activar equipos de Microsoft activado o desactivado para todos los usuarios de este tipo** para controlar el acceso a los equipos de los usuarios a través de SKU, se mantendrá la configuración actual. Sin embargo, no podrá modificar esta configuración en el nuevo portal de administración. En su lugar, podrá asignar las licencias adecuadas a los usuarios en el inquilino a través del centro de administración de Office 365. Para obtener más información, vea [administrar el acceso de usuarios a los equipos de Microsoft](user-access.md). 

En la siguiente tabla identifica las secciones de la experiencia actual de los equipos que se han migrado y se muestran la relación entre la configuración actual y las directivas en el nuevo portal de administración.

|Sección de los equipos en el centro de administración de Office 365  |Nombre de la configuración (nivel de inquilino)  |Microsoft Teams & Skype para directiva de centro de administración de negocio   |Nivel: Usuario o inquilino   |
|---------|---------|---------|---------|
|General     |Mostrar Chat organizativa en perfil Personal        |  TeamsClientConfiguration       |  Inquilino       |
|General     |Usar Skype para la empresa para los destinatarios que no tienen los equipos         |TeamsClientConfiguration         |Inquilino         |
|General     |Permitir que los mensajes de ayuda proactiva T-Bot         |TeamsClientConfiguration         |Inquilino         |
|Integración del correo electrónico     |Permitir a los usuarios enviar correos electrónicos a canales         |TeamsClientConfiguration         |Inquilino         |
|Integración del correo electrónico     |Permitir que los remitentes lista         |TeamsClientConfiguration        |Inquilino         |
|Almacenamiento en nube personalizado     |Cuadro de         |TeamsClientConfiguration         |Inquilino         |
|Almacenamiento en nube personalizado     |Lista desplegable        |TeamsClientConfiguration         |Inquilino         |
|Almacenamiento en nube personalizado     |Unidad de Google        |TeamsClientConfiguration         |Inquilino         |
|Almacenamiento en nube personalizado     |ShareFile        |TeamsClientConfiguration         |Inquilino         |
|Configuración por tipo de licencia de usuario o     |Activar Microsoft Teams activado o desactivado para todos los usuarios          |En desuso. Use el centro de administración de Office 365 para asignar licencias.        |         |
|Equipos y canales     |         |Redirecciones a Azure grupo Administración de Active Directory (igual que la experiencia actual).              |Usuario         |
|Equipos y canales     |         |Redirige a la administración de grupo de AAD (igual que la experiencia actual).             |Usuario          |
|Las llamadas y las reuniones     |Permitir la programación de reuniones privadas         |TeamsMeetingPolicy         |Usuario          |
|Las llamadas y las reuniones     |Permitir meetup de canal Ad hoc         |TeamsMeetingPolicy         |Usuario          |
|Las llamadas y las reuniones     |Permitir la programación de reuniones de canal         |TeamsMeetingPolicy         |Usuario          |
|Las llamadas y las reuniones     |Permitir vídeos en las reuniones         |TeamsMeetingPolicy         |Usuario          |
|Las llamadas y las reuniones     |Permitir el uso compartido en reuniones de pantalla         |TeamsMeetingPolicy         |Usuario          |
|Las llamadas y las reuniones     |Permitir llamadas privada         |TeamsCallingPolicy         |Usuario          |
|Mensajes     |Habilitar Giphy, por lo que los usuarios pueden agregar archivos GIF a las conversaciones         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Clasificación de contenido         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Habilitar memes que los usuarios pueden editar y agregar a las conversaciones         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Habilitar a pegatinas que los usuarios pueden editar y agregar a las conversaciones         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Permitir que los propietarios de eliminar todos los mensajes         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Permitir a los usuarios editar sus propios mensajes de         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Permitir a los usuarios eliminar sus propios mensajes de         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Permite a los usuarios a conversaciones en privado         |TeamsMessagingPolicy         |Usuario         |


## <a name="manage-settings-during-the-migration"></a>Administración de la configuración durante la migración

Puede continuar modificar la configuración en el centro de administración de Office 365 y el Skype para el centro de administración de negocio hasta que se complete para el inquilino de migración para una sección. 

La siguiente tabla se muestra donde puede administrar las características durante la migración.

|Característica  |Los equipos de Microsoft y Skype para el centro de administración de negocio                       |Skype para el centro de administración empresarial (heredada)  |Centro de administración de Office 365  |
|---------|:---------:|:---------:|:---------:|
|Directiva de mensajería     |     X    |         |         |
|Directiva de interoperabilidad de los equipos     |    X     |         |         |
|Configuración de la mensajería invitado     |   X      |         |         |
|Configuración del acceso externo    |    X     |         |         |
|Administración de usuarios    |         |         |    X     |    
|Conferencias de audio     |    X     |    X     |         |
|Planes de llamada     |         |    X     |         |
|Sistema telefónico    |         |     X    |         |
|Administración de números de teléfono     |         |   X      |         |
|Concesión de licencias para las características de voz en la nube     |         |         |    X     |
|Operadores automáticos     |         |    X     |         |
|Colas de llamadas     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Administrar la configuración después de la migración

Se le notificará una vez finalizada la migración de una sección específica dentro de los equipos. En ese momento, podrá ver la configuración existente de esa sección en el centro de administración de Office 365, pero no podrá realizar modificaciones no existe. En su lugar, usará el Microsoft Teams & Skype para el centro de administración de negocio para administrar la configuración recién migrada.

Una vez finalizada la migración de estas configuraciones, los podrá deshabilitar en el centro de administración de Office 365 y el Skype para el centro de administración de negocio.


