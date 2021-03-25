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
description: En este artículo, aprenderá sobre el proceso de actualización del cliente de escritorio de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e26325f4efcc5ffd7731b73e397f1f96579dd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119249"
---
# <a name="teams-update-process"></a>Proceso de actualización de Teams

La aplicación web de Teams se actualiza semanalmente.

Las actualizaciones del cliente de escritorio de Teams se lanzan cada dos semanas después de las rigurosas pruebas internas y la validación a través de Programa de adopción de tecnología (TAP) (TAP). La actualización suele tener lugar un martes. Si se requiere una actualización crítica, Teams omitirá esta programación y la lanzará tan pronto como esté disponible.

El cliente de escritorio se actualiza automáticamente. Teams comprueba si hay actualizaciones cada pocas horas en segundo plano, la descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar la actualización en silencio.

Los usuarios también pueden descargar  actualizaciones manualmente seleccionando Buscar actualizaciones en el menú desplegable Perfil en la parte superior derecha de la aplicación.  Si hay una actualización disponible, se descargará y se instalará de forma silenciosa cuando el equipo esté inactivo.

Los usuarios deben haber iniciado sesión para que se descarguen las actualizaciones.

A partir del 31 de julio de 2019, las actualizaciones de cliente de Teams usan menor ancho de banda de red durante la actualización. Esta actualización está activada de forma predeterminada y no requiere ninguna acción de administradores o usuarios.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>¿Qué sucede con las actualizaciones de las aplicaciones de Microsoft 365 para empresas?

Teams está instalado de forma predeterminada con nuevas instalaciones de aplicaciones de Microsoft 365 para empresas, como se describe en Implementar Microsoft Teams con aplicaciones de [Microsoft 365 para empresas.](/DeployOffice/teams-install)

Teams sigue su propio proceso de actualización como se describe anteriormente. Teams no sigue el proceso de actualización de las otras aplicaciones de Office, como Word y Excel. Para obtener más información, lea Información general sobre los canales de [actualización para aplicaciones de Microsoft 365 para empresas](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>¿Qué sucede con las actualizaciones de Teams en VDI?


Los clientes de Teams en infraestructura de escritorio virtual (VDI) no se actualizan automáticamente de la forma en que los clientes de Teams que no son VDI. Tiene que actualizar la imagen de la máquina virtual instalando un nuevo MSI como se describe en las instrucciones [para Instalar Teams en VDI.](teams-for-vdi.md) Debe desinstalar la versión actual para actualizar a una versión más reciente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>¿Pueden los administradores implementar actualizaciones en lugar de la actualización automática de Teams?

Teams no ofrece a los administradores la capacidad de implementar actualizaciones a través de ningún mecanismo de entrega.

## <a name="servicing-agreement"></a>Contrato de mantenimiento

Como servicio en línea moderno, el cliente de Teams se actualiza automáticamente cada dos semanas. Dado que Teams se rige por la directiva de ciclo de vida moderna, se espera que los usuarios permanezcan en la versión más actualizada del cliente de escritorio. Las actualizaciones automáticas garantizan que los usuarios tengan las últimas capacidades, mejoras de rendimiento, seguridad y confiabilidad del servicio.

Para identificar cuándo los clientes de escritorio no están actualizados, se mostrará una alerta desde la aplicación si la versión actual del usuario tiene entre uno y tres meses de antigüedad y si hay una nueva versión disponible. Esta mensajería desde la aplicación anima a los usuarios a actualizar a la versión más reciente de Teams o, si es necesario, a comunicarse con su administrador de TI para hacerlo. Los usuarios de los clientes de escritorio de Teams que tienen más de tres meses de antigüedad verán una página de bloqueo que ofrece las opciones para actualizar ahora, comunicarse con su administrador de TI o continuar con Teams en la web.

Las versiones de cliente de escritorio con más de tres meses de antigüedad al instalar y/o ejecutar por primera vez Teams tienen un período de gracia de 28 días antes de encontrar la información de mantenimiento mencionada anteriormente. Durante este período, el proceso de actualización automática actualizará el cliente de Teams. Si no se actualiza, los usuarios verán una alerta desde la aplicación animándoles a actualizar manualmente a la última versión de Teams. Es posible que se pida a los usuarios que se pondrán en contacto con su administrador de TI para realizar la actualización. Esto incluye los usuarios que usan el cliente de escritorio de Teams como parte del paquete Aplicaciones de Microsoft 365 para empresas.

Actualmente, los clientes de escritorio de Teams en las nubes gubernamentales tienen una excepción a este contrato de mantenimiento hasta nuevo aviso.

Para obtener información sobre las versiones nuevas, consulte Centro [de mensajes](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) o vaya **a** Ayuda  >  **novedades** del cliente.
