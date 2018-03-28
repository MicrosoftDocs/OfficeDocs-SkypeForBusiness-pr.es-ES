---
title: Administrar equipos durante la transición al nuevo Teams de Microsoft y Skype para el centro de administración de negocios
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Entender cómo administrar todo el inquilino y configuración de usuario de los equipos durante la transición de los equipos de experiencia en el centro de administración de Office 365 para el nuevo Microsoft Teams & Skype para el centro de administración de negocios.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 0f660130ce9fe2973178385e87433cac29fa8733
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-and-skype-for-business-admin-center"></a>Administrar equipos durante la transición al nuevo Teams de Microsoft y Skype para el centro de administración de negocios
======================================================

El nuevo Centro de administración de Microsoft Teams y Skype Empresarial estará disponible muy pronto. 

A partir de marzo de 2018, gradualmente nos estamos migrar la configuración a la Teams de Microsoft & Skype para el centro de administración de negocios de ambos el Skype actual para el centro de administración de negocios y experiencia de los Teams de Microsoft en el centro de administración de Office 365. Cuando se migra una configuración, recibe una notificación y, a continuación, se le dirige a la ubicación de la configuración en el nuevo Centro de administración de Microsoft Teams y Skype Empresarial.

Seguimos migrar otras funciones desde el Skype para el centro de administración de negocio en los próximos meses. Puede mantenerse al día a través de nuestro público [roadmap](https://aka.ms/Office365Roadmap).

> [!NOTE]
> Nos estamos distribuir el nuevo Microsoft Teams & Skype para el centro de administración de negocios en etapas. Como resultado, todos los clientes no verán el nuevo centro de Admin al mismo tiempo. Te informaremos cuando puede empezar a utilizar el nuevo centro de Admin.

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>¿Cuál es el nuevo Microsoft Teams & Skype para el centro de administración de negocios?  

La nueva experiencia de Admin Center le proporcionará una experiencia unificada para administrar equipos y Skype para el negocio. Ofrecemos una funcionalidad adicional, información end-to-end y la capacidad para administrar la configuración de los equipos a nivel de usuario.

![Captura de pantalla de equipos de Microsoft & Skype para el centro de administración de negocios.](media/manage-teams-skype-for-business-admin-center-portal.png)


A partir de mediados de marzo 2018, las funciones siguientes estarán disponibles en el nuevo Microsoft Teams & Skype para el centro de administración de negocios: 

- **Directiva de mensajería de equipos de Microsoft**: crear directivas de administración de nivel de usuario de la experiencia del cliente de Microsoft Teams para escenarios de mensajería.
- **Directiva de interoperabilidad de equipos de Microsoft**: configuración de la experiencia de interoperabilidad entre Skype para empresas y Teams de Microsoft.
- **Configuraciones de mensajería de invitado de equipos de Microsoft**: controlar las capacidades de mensajería para las cuentas de invitado en Microsoft Teams. 
- **Configuración de federación**: administrar la federación entre los inquilinos para Teams de Microsoft y Skype para el negocio. 
- **Administración de usuarios**: asignar directivas y configurar cuentas de usuario. 
- **Conferencia de audio**: configurar números de acceso telefónico y de Skype para empresas y Teams de Microsoft. 

 

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>La configuración se migra al nuevo Microsoft Teams & Skype para el centro de administración de negocios

La configuración General, integración correo electrónico, almacenamiento de nube personalizados, llamadas y reuniones y mensajería en Teams de Microsoft existente (consulte la imagen siguiente) se migrarán a la nueva Microsoft Teams & Skype para Business Admin Center (también conocido como el nuevo portal de administración) en los próximos meses. 



> [!NOTE]
>Podrá continuar utilizar el panel de grupos en el centro de administración de Office 365 para la configuración de **los equipos y los canales**. Configuración para **aplicaciones** permanecerá en el área de equipos del centro de administración de Office 365 y se migrarán posteriormente. 

![Página de captura de pantalla de equipos en el centro de administración de Office 365.](media/manage-teams-skypeforbusiness-admin-center-teams-in-O365.png)

Con respecto a los valores disponibles en **configuración de tipo de usuario o licencia**, básicamente proporciona una manera de configurar grupos de usuarios de forma diferente. Ahora, con el nuevo portal de administración, puede hacer en cada usuario. 


Se migrará la configuración del tipo de licencia. Si actualmente está utilizando la opción de **Activar equipos Microsoft o desactivar para todos los usuarios de este tipo** para controlar el acceso a los equipos de los usuarios a través de SKU, mantenemos la configuración actual. Sin embargo, no podrá modificar esta configuración en el nuevo portal de administración. En su lugar, asignará las licencias correspondientes a los usuarios en su inquilino a través del centro de administración de Office 365. Para obtener más información, vea [administrar el acceso de usuario a equipos de Microsoft](user-access.md). 

La siguiente tabla identifica las secciones de la experiencia actual de los equipos que se van a migrar y muestra la relación entre la configuración actual y las directivas en el nuevo portal de administración.


|Sección de equipos en el centro de administración de Office 365  |Nombre de la configuración (nivel de inquilinos)  |Teams Microsoft & Skype para la política del negocio Admin Center   |Nivel: Inquilino o usuario   |
|---------|---------|---------|---------|
|General     |Mostrar Chat organizativa en perfil Personal        |  TeamsClientConfiguration       |  Inquilinos       |
|General     |Usar Skype para empresas para los destinatarios que no dispongan de equipos         |TeamsClientConfiguration         |Inquilinos         |
|General     |Permitir que los mensajes de ayuda proactiva T-Bot         |TeamsClientConfiguration         |Inquilinos         |
|Integración del correo electrónico     |Permitir a los usuarios enviar correos electrónicos a canales         |TeamsClientConfiguration         |Inquilinos         |
|Integración del correo electrónico     |Permitir que los remitentes lista         |TeamsClientConfiguration        |Inquilinos         |
|Almacenamiento en nube personalizado     |Cuadro de         |TeamsClientConfiguration         |Inquilinos         |
|Almacenamiento en nube personalizado     |Lista desplegable        |TeamsClientConfiguration         |Inquilinos         |
|Almacenamiento en nube personalizado     |Unidad de Google        |TeamsClientConfiguration         |Inquilinos         |
|Almacenamiento en nube personalizado     |ShareFile        |TeamsClientConfiguration         |Inquilinos         |
|Ajustes por tipo de usuario o licencia     |Activar Microsoft Teams o desactivar para todos los usuarios          |En desuso. Use el centro de administración de Office 365 para asignar licencias.        |         |
|Equipos y canales     |         |Redirige a Azure grupo de administración de Active Directory (igual que la experiencia actual).              |Usuario         |
|Equipos y canales     |         |Redirige a la administración de grupo DAA (igual que la experiencia actual).             |Usuario          |
|Llamadas y reuniones     |Permitir la programación de reuniones privadas         |TeamsMeetingPolicy         |Usuario          |
|Llamadas y reuniones     |Permitir la meetup de canal Ad hoc         |TeamsMeetingPolicy         |Usuario          |
|Llamadas y reuniones     |Permitir la programación de reuniones de canal         |TeamsMeetingPolicy         |Usuario          |
|Llamadas y reuniones     |Permitir vídeos en reuniones         |TeamsMeetingPolicy         |Usuario          |
|Llamadas y reuniones     |Permitir compartir en las reuniones de pantalla         |TeamsMeetingPolicy         |Usuario          |
|Llamadas y reuniones     |Permitir llamada privada         |TeamsCallingPolicy         |Usuario          |
|Mensajes     |Habilitar Giphy, por lo que los usuarios pueden agregar archivos GIF a conversaciones         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Clasificación de contenido         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Habilitar memes que los usuarios puedan editar y agregar a las conversaciones         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Habilitar a etiquetas que los usuarios puedan editar y agregar a las conversaciones         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Permitir a los propietarios eliminar todos los mensajes         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Permitir a los usuarios modificar sus propios mensajes.         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Permitir a los usuarios eliminar sus propios mensajes         |TeamsMessagingPolicy         |Usuario         |
|Mensajes     |Permite a los usuarios de charla privada         |TeamsMessagingPolicy         |Usuario         |



## <a name="manage-settings-during-the-migration"></a>Administrar la configuración durante la migración

Se planea migrar la configuración de los equipos en secciones en el orden siguiente: mensajería, reuniones, llamadas y, por último, las secciones de la directiva de configuración de TeamsClient (General, integración de correo electrónico y almacenamiento en nube personalizado).   

Puede continuar modificar la configuración en el centro de administración de Office 365 y el Skype para el centro de administración de negocios hasta que se complete para el arrendatario la migración de una sección. 

La tabla siguiente muestra dónde puede administrar características durante la migración.

|Característica  |Skype para el centro de administración de negocios y equipos de Microsoft                       |Skype para el centro de administración de negocios (heredado)  |Centro de administración de Office 365  |
|---------|:---------:|:---------:|:---------:|
|Directiva de mensajería     |     X    |         |         |
|Directiva de interoperabilidad de los equipos     |    X     |         |         |
|Configuración de mensajería del invitado     |   X      |         |         |
|Opciones de acceso externo    |    X     |         |         |
|Administración de usuarios    |         |         |    X     |    
|Conferencia de audio     |    X     |    X     |         |
|Planes de llamada     |         |    X     |         |
|Sistema telefónico    |         |     X    |         |
|Administración de números de teléfono     |         |   X      |         |
|Licencias para funciones de voz de la nube     |         |         |    X     |
|Operadores automáticos     |         |    X     |         |
|Colas de llamadas     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Administrar la configuración después de la migración

Te informaremos tras la migración completa de una sección específica dentro de los equipos. En ese momento, podrá ver los valores existentes de esa sección en el centro de administración de Office 365, pero no podrá realizar modificaciones allí. En su lugar, utilizará el Teams de Microsoft & Skype para el centro de administración de negocios para administrar la configuración recién migrada.

Una vez completada la migración de estas configuraciones, los podrá deshabilitar en el centro de administración de Office 365 y el Skype para el centro de administración de negocios.


