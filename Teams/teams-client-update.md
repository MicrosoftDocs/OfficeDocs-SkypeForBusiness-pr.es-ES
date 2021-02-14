---
title: Actualizaciones de Teams
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
description: En este artículo, aprenderá sobre el proceso tras actualizar el cliente de escritorio de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8681f3f4cc7c25e9499e25e3978848084086a2a
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031886"
---
# <a name="teams-update-process"></a>Proceso de actualización de Teams

La aplicación web de Teams se actualiza semanalmente.

Las actualizaciones del cliente de escritorio de Teams se lanzan cada dos semanas después de la validación y pruebas internas rigurosos a través de Programa de adopción de tecnología (TAP) (TAP). Esto suele tener lugar un martes. Si se requiere una actualización crítica, Teams omitirá esta programación y la actualizará en cuanto esté disponible.

El cliente de escritorio se actualiza automáticamente. Teams comprueba si hay actualizaciones cada pocas horas entre bastidores, la descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar la actualización de forma silenciosa.

Los usuarios también pueden descargar actualizaciones manualmente  haciendo clic en Buscar **actualizaciones** en el menú desplegable Perfil, en la parte superior derecha de la aplicación. Si hay una actualización disponible, se descargará e instalará de forma silenciosa cuando el equipo esté inactivo.

Los usuarios deben haber iniciado sesión para que se descarguen las actualizaciones. 

Desde el 31 de julio de 2019, las actualizaciones de los clientes de Teams usan un ancho de banda de red considerablemente inferior durante la actualización. Esta opción está activada de forma predeterminada y no requiere ninguna acción por parte de los administradores o usuarios.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>¿Qué hay de las actualizaciones de las aplicaciones de Microsoft 365 para empresas?

Teams se instala de forma predeterminada con nuevas instalaciones de aplicaciones de Microsoft 365 para empresas, como se describe en Implementar Microsoft Teams con aplicaciones de [Microsoft 365 para empresas.](https://docs.microsoft.com/DeployOffice/teams-install) 

Teams sigue su propio proceso de actualización, como se describe anteriormente, y no el proceso de actualización para las demás aplicaciones de Office, como Word y Excel. Para obtener más información, lea [Información general sobre los canales de actualización de las aplicaciones de Microsoft 365 para empresas](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>¿Qué hay de las actualizaciones de Teams en VDI?

Los clientes de Teams en infraestructura de escritorio virtual (VDI) no se actualizan automáticamente de la misma forma que los clientes de equipos que no son de VDI. Tiene que actualizar la imagen de máquina virtual mediante la instalación de un nuevo MSI como se describe en las instrucciones [para instalar Teams en VDI.](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi) Debe desinstalar la versión actual para actualizar a una versión más reciente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>¿Los administradores pueden implementar actualizaciones en lugar de la actualización automática de Teams?

Teams no ofrece a los administradores la capacidad de implementar actualizaciones a través de ningún mecanismo de entrega.

## <a name="servicing-agreement"></a>Contrato de mantenimiento

Como servicio en línea moderno, el cliente de Teams se actualiza automáticamente cada dos semanas. Como Teams se rige por la directiva moderna de ciclo de vida, se espera que los usuarios permanezcan en la versión más actualizada del cliente de escritorio. Esto garantiza que los usuarios tengan las capacidades, mejoras de rendimiento, seguridad y confiabilidad del servicio más recientes.

Para comenzar a ayudar a identificar cuándo los clientes de escritorio no están actualizados, se mostrará una alerta desde la aplicación si la versión actual del usuario tiene entre uno y tres meses de antigüedad, y si hay una nueva versión disponible. Esta mensajería desde la aplicación anima a los usuarios a actualizar a la versión más reciente de Teams o, si es necesario, a comunicarse con su administrador de TI para hacerlo. Los usuarios de clientes de escritorio de Teams que tienen más de tres meses de antigüedad verán una página de bloqueo que ofrece las opciones para actualizar ahora, tendrán que comunicarse con su administrador de TI o continuar con Teams en la web.

Las versiones de cliente de escritorio que tengan más de tres meses de antigüedad tras la primera instalación o primera ejecución de Teams tienen un período de gracia de 28 días antes de encontrar la información de mantenimiento mencionada anteriormente. Durante este período, el proceso de actualización automática actualizará el cliente de Teams. Si no se actualiza, los usuarios verán una alerta en la aplicación aníándoles que actualicen manualmente a la última versión de Teams o, si es necesario, que se pondrán en contacto con su administrador de TI para hacerlo. Esto incluye a los usuarios que usan el cliente de escritorio de Teams como parte del paquete Aplicaciones de Microsoft 365 para empresas.

Actualmente, los clientes de escritorio de Teams en Government Clouds tienen una excepción a este contrato de mantenimiento hasta nuevo aviso.

Para obtener información sobre las versiones nuevas, consulte el Centro [de mensajes](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) o vaya a Ayuda sobre novedades  >   del cliente.
