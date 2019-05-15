---
title: Proceso de actualización de los equipos
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
description: Obtenga información sobre cómo se actualiza el cliente de escritorio de los equipos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08381341903d21deb42ca83b3769c49f67d18b14
ms.sourcegitcommit: 2449c6dbda4a63aefe5291558cfa41ad7ccf9e39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "33970279"
---
# <a name="teams-update-process"></a>Proceso de actualización de los equipos

La aplicación web de los equipos se actualiza semanalmente.

Los equipos cliente de escritorio se lanzan las actualizaciones cada dos semanas después de realizar rigurosas pruebas interno y validación a través de nuestro programa de adopción de tecnología (TAP). Normalmente, esto lleva a cabo un martes. Si se requiere una actualización crítica, los equipos omitir esta programación y la actualización de la versión tan pronto como está disponible.

El cliente de escritorio se actualiza automáticamente. Comprobaciones de los equipos para actualiza cada pocas horas en segundo plano, lo descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar la actualización de modo silencioso.

Los usuarios pueden descargar manualmente las actualizaciones, haga clic en **Buscar actualizaciones** en el menú desplegable de **perfil** en la parte superior derecha de la aplicación. Si hay disponible una actualización, se descargará y se instala en modo silencioso cuando el equipo está inactivo.

Los usuarios deben haber iniciado sesión en para que las actualizaciones se descarguen.

## <a name="what-about-updates-to-office-365-proplus"></a>¿Qué información acerca de las actualizaciones para Office 365 ProPlus?

Los equipos se instala de forma predeterminada con las nuevas instalaciones de Office 365 ProPlus tal como se describe en [Implementar Microsoft equipos con Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install). 

Los equipos sigue su propio proceso de actualización descritas anteriormente y no el proceso de actualización de las otras aplicaciones de oficinas, como Word y Excel.

## <a name="what-about-updates-to-teams-on-vdi"></a>¿Qué ocurre con las actualizaciones de los equipos de la VDI?

Los clientes de los equipos en la infraestructura de Escritorio Virtual (VDI) no se actualizan automáticamente el modo en que los clientes de equipos que no sean de VDI. Se debe actualizar la imagen de la máquina virtual mediante la instalación de un nuevo MSI tal como se describe en las instrucciones para [Instalar los equipos de la VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi). Debe desinstalar la versión actual para actualizar a una versión más reciente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>¿Pueden administradores implementar las actualizaciones en lugar de los equipos de actualización automática?

Los equipos no dar a los administradores de la capacidad para implementar las actualizaciones a través de ningún mecanismo de entrega.
