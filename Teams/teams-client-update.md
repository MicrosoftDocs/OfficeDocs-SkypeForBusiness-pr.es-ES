---
title: Actualizaciones de Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Obtenga información sobre cómo se actualiza el cliente de escritorio de Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba5280e03e316dfcde3bda9b62520fa513f3157a
ms.sourcegitcommit: 5faa89ea686448d5b339178f1330edc63e21a52f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35602274"
---
# <a name="teams-update-process"></a>Proceso de actualización de Teams

Teams Web App se actualiza semanalmente.

Las actualizaciones de clientes de escritorio de Teams se publican cada dos semanas después de rigurosas pruebas internas y validación por medio de nuestro programa de adopción de tecnología (TAP). Normalmente, esto tiene lugar un martes. Si se requiere una actualización crítica, Teams evitará esta programación y liberará la actualización tan pronto como esté disponible.

El cliente de escritorio se actualiza automáticamente. Teams busca actualizaciones cada pocas horas, las descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar silenciosamente la actualización.

Los usuarios también pueden descargar actualizaciones manualmente haciendo clic en **Buscar actualizaciones** en el menú desplegable **perfil** en la parte superior derecha de la aplicación. Si hay una actualización disponible, se descargará y se instalará en modo silencioso cuando el equipo esté inactivo.

Los usuarios deben iniciar sesión para que se descarguen las actualizaciones. 

A partir del 9 de julio de 2019, las actualizaciones de los clientes de Teams usan mucho menos ancho de banda de red durante la actualización. Esta opción está activada de forma predeterminada y no requiere ninguna acción de administradores o usuarios.


## <a name="what-about-updates-to-office-365-proplus"></a>¿Qué hay de las actualizaciones de Office 365 ProPlus?

Teams se instala de forma predeterminada con nuevas instalaciones de Office 365 ProPlus, como se describe en [implementar Microsoft Teams con office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install). 

Teams sigue su propio proceso de actualización, como se indica anteriormente, y no el proceso de actualización para las otras aplicaciones de Office, como Word y Excel. Para obtener más información, vea [información general sobre los canales de actualización de Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) .

## <a name="what-about-updates-to-teams-on-vdi"></a>¿Qué hay de las actualizaciones de Teams en VDI?

Los clientes de Teams en la infraestructura de escritorio virtual (VDI) no se actualizan automáticamente de la manera en que los clientes de equipos ajenos a VDI son. Tiene que actualizar la imagen de VM instalando un nuevo MSI, tal y como se describe en las instrucciones para [instalar Teams en VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi). Debe desinstalar la versión actual para actualizar a una versión más reciente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>¿Los administradores pueden implementar actualizaciones en lugar de la actualización automática de Teams?

Teams no proporciona a los administradores la capacidad de implementar actualizaciones a través de cualquier mecanismo de envío.
