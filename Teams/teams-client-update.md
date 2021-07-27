---
title: Actualizaciones del cliente de Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: En este artículo, obtendrá información sobre el proceso de actualización del cliente de escritorio de Microsoft Teams.
localization_priority: Priority
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 136cca899b0c79b549ee9ae890e90f1e84c04eaa
ms.sourcegitcommit: d34dbdc2f71f3d024cb7f1856fc0f8bbc701f66d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2021
ms.locfileid: "53506389"
---
# <a name="teams-update-process"></a>El proceso de actualización de Teams

La aplicación web de Teams se actualiza semanalmente.

Las actualizaciones del cliente de escritorio de Teams se publican cada dos semanas tras un riguroso proceso interno de prueba y validación mediante nuestro Programa de adopción de tecnología (TAP). La actualización suele tener lugar en un martes. Si se requiere una actualización crítica, Teams omite esta programación y publica la actualización en cuanto está disponible.

El cliente de escritorio se actualiza automáticamente. Teams busca actualizaciones cada pocas horas en segundo plano, las descarga y, a continuación, espera a que el equipo esté inactivo para instalar la actualización de forma silenciosa.

Los usuarios también pueden descargar manualmente las actualizaciones en **Buscar actualizaciones** en el menú desplegable de **Perfil** que se encuentra en la parte superior derecha de la aplicación. Si hay una actualización disponible, se descargará y se instalará de forma silenciosa cuando el equipo esté inactivo.

Los usuarios deben iniciar sesión para que se descarguen las actualizaciones.

A partir del 31 de julio de 2019, las actualizaciones de cliente de Teams usan menos ancho de banda durante la actualización. Esta actualización está activada de forma predeterminada y no requiere ninguna acción por parte de administradores ni usuarios.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>¿Que ocurre con las actualizaciones de Aplicaciones de Microsoft 365 para empresas?

Teams se instala de forma predeterminada con las nuevas instalaciones de Aplicaciones de Microsoft 365 para empresas, como se describe en [Implementar Microsoft Teams con Aplicaciones de Microsoft 365 para empresas](/DeployOffice/teams-install).

Teams sigue su propio proceso de actualización como se ha descrito anteriormente. Teams no sigue el proceso de actualización de otras aplicaciones de Office, como Word y Excel. Para recibir más información, consulte [Información general sobre los canales de actualización de Aplicaciones de Microsoft 365 para empresas](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>¿Qué ocurre con las actualizaciones de Teams en VDI?


Los clientes de Teams en la infraestructura de escritorio virtual (VDI) no se actualizan automáticamente del mismo modo que los clientes de Teams que no son VDI. Tiene que actualizar la imagen de máquina virtual mediante la instalación de una nueva MSI como se describe en las instrucciones para [Instalar Teams en VDI](teams-for-vdi.md). Debe desinstalar la versión actual para actualizar a una versión más reciente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>¿Los administradores pueden implementar actualizaciones en lugar de la actualización automática de Teams?

Teams no ofrece a los administradores la capacidad de implementar actualizaciones con ningún mecanismo de entrega.

## <a name="servicing-agreement"></a>Acuerdo de mantenimiento

El cliente de Teams es un servicio en línea moderno que se actualiza automáticamente cada dos semanas. Dado que Teams se rige por la directiva moderna de ciclo de vida, se espera que los usuarios permanezcan en la versión más actualizada del cliente de escritorio. Las actualizaciones automáticas garantizan que los usuarios tengan las funcionalidades, las mejoras de rendimiento, la seguridad y la confiabilidad del servicio más recientes.

Para identificar cuándo los clientes de escritorio no están actualizados, se mostrará una alerta desde la aplicación si la versión actual del usuario tiene entre uno y tres meses de antigüedad y si hay una nueva versión disponible. Esta mensajería desde la aplicación anima a los usuarios a actualizar a la versión más reciente de Teams o, si es necesario, a ponerse en contacto con su administrador de TI para que este se encargue de ello. Los usuarios de clientes de escritorio de Teams con más de tres meses de antigüedad verán una página de bloqueo que ofrece las opciones para actualizar ahora, ponerse en contacto con su administrador de TI o continuar con Teams en la Web.

Los clientes de escritorio de Teams en las nubes gubernamentales tienen actualmente, y hasta nuevo aviso, una excepción a este contrato de servicio.

Para obtener información sobre las nuevas versiones, compruebe el [Centro de mensajes](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) o vaya a **Ayuda** > **Novedades** en el cliente.
