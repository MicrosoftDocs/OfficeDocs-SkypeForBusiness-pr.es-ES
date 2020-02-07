---
title: Actualizaciones de Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo se actualiza el cliente de escritorio de Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8058fa1e79b7d415d03c08500213206579029042
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832620"
---
# <a name="teams-update-process"></a>Proceso de actualización de Teams

Teams Web App se actualiza semanalmente.

Las actualizaciones de clientes de escritorio de Teams se publican cada dos semanas después de rigurosas pruebas internas y validación por medio de nuestro programa de adopción de tecnología (TAP). Normalmente, esto tiene lugar un martes. Si se requiere una actualización crítica, Teams evitará esta programación y liberará la actualización tan pronto como esté disponible.

El cliente de escritorio se actualiza automáticamente. Teams busca actualizaciones cada pocas horas, las descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar silenciosamente la actualización.

Los usuarios también pueden descargar actualizaciones manualmente haciendo clic en **Buscar actualizaciones** en el menú desplegable **perfil** en la parte superior derecha de la aplicación. Si hay una actualización disponible, se descargará y se instalará en modo silencioso cuando el equipo esté inactivo.

Los usuarios deben iniciar sesión para que se descarguen las actualizaciones. 

A partir del 31 de julio de 2019, las actualizaciones de los clientes de Teams usan mucho menos ancho de banda de red durante la actualización. Esta opción está activada de forma predeterminada y no requiere ninguna acción de administradores o usuarios.

## <a name="what-about-updates-to-office-365-proplus"></a>¿Qué hay de las actualizaciones de Office 365 ProPlus?

Teams se instala de forma predeterminada con nuevas instalaciones de Office 365 ProPlus, como se describe en [implementar Microsoft Teams con office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install). 

Teams sigue su propio proceso de actualización, como se indica anteriormente, y no el proceso de actualización para las otras aplicaciones de Office, como Word y Excel. Para obtener más información, vea [información general sobre los canales de actualización de Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) .

## <a name="what-about-updates-to-teams-on-vdi"></a>¿Qué hay de las actualizaciones de Teams en VDI?

Los clientes de Teams en la infraestructura de escritorio virtual (VDI) no se actualizan automáticamente de la manera en que los clientes de equipos ajenos a VDI son. Tiene que actualizar la imagen de VM instalando un nuevo MSI, tal y como se describe en las instrucciones para [instalar Teams en VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi). Debe desinstalar la versión actual para actualizar a una versión más reciente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>¿Los administradores pueden implementar actualizaciones en lugar de la actualización automática de Teams?

Teams no proporciona a los administradores la capacidad de implementar actualizaciones a través de cualquier mecanismo de envío.

## <a name="servicing-agreement"></a>Contrato de mantenimiento

Como servicio en línea moderno, el cliente de Teams se actualiza automáticamente cada dos semanas. Debido a que Teams está regido por la Directiva moderna del ciclo de vida, se espera que los usuarios permanezcan en la versión más actualizada del cliente de escritorio. Esto garantiza que los usuarios tengan las últimas funciones, mejoras de rendimiento, seguridad y confiabilidad de los servicios.

Para empezar a identificar cuándo los clientes de escritorio no están actualizados, se mostrará una alerta en la aplicación si la versión actual del usuario se encuentra entre uno y tres meses de antigüedad y si hay una nueva versión disponible. Esta mensajería desde la aplicación anima a los usuarios a actualizar a la última versión de Teams o, si es necesario, a comunicarse con su administrador de TI para hacerlo. Los usuarios de equipos con clientes de escritorio de más de tres meses de edad verán una página de bloqueo que ofrece las opciones para actualizar ahora, comunicarse con su administrador de ti o continuar con Teams en la Web.

Las versiones de clientes de escritorio con más de tres meses de antigüedad en la primera instalación o primera ejecución de Teams tienen un período de gracia de 28 días antes de que se produzca la información de servicio mencionada anteriormente. Durante este período, el proceso de actualización automática actualizará el cliente de Teams. Si no se actualiza, los usuarios verán una alerta desde la aplicación que les anima a actualizar de forma manual a la última versión de Teams o, si es necesario, a su administrador de TI para hacerlo. Esto incluye a los usuarios que usan el cliente de escritorio de Teams como parte del paquete de Office 365 ProPlus.

Los clientes de escritorio de Teams de las nubes gubernamentales actualmente tienen una excepción a este contrato de mantenimiento hasta un aviso más importante.

Para obtener información sobre las nuevas versiones, [consulte Centro de mensajes](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) o ir para **obtener** > información sobre**las novedades del** cliente.
