---
title: Teams actualizaciones
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
description: En este artículo, aprenderá sobre el proceso de actualización del Microsoft Teams de escritorio.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 004c615d2b624f4e5942562e6abfed6e1aebf7cd
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717901"
---
# <a name="teams-update-process"></a>Teams de actualización

La Teams web se actualiza semanalmente.

Teams actualizaciones de cliente de escritorio se lanzan cada dos semanas después de rigurosas pruebas internas y validación a través de Programa de adopción de tecnología (TAP). La actualización suele tener lugar un martes. Si se requiere una actualización crítica, Teams omitirá esta programación y la lanzará tan pronto como esté disponible.

El cliente de escritorio se actualiza automáticamente. Teams busca actualizaciones cada pocas horas en segundo plano, la descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar la actualización en silencio.

Los usuarios también pueden descargar  actualizaciones manualmente seleccionando Buscar actualizaciones en el menú desplegable Perfil en la parte superior derecha de la aplicación.  Si hay una actualización disponible, se descargará y se instalará de forma silenciosa cuando el equipo esté inactivo.

Los usuarios deben haber iniciado sesión para que se descarguen las actualizaciones.

A partir del 31 de julio de 2019, Teams actualizaciones de cliente usan un ancho de banda de red inferior durante la actualización. Esta actualización está activada de forma predeterminada y no requiere ninguna acción de administradores o usuarios.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>¿Qué sucede con las actualizaciones Aplicaciones Microsoft 365 para empresas?

Teams está instalado de forma predeterminada con nuevas instalaciones de Aplicaciones Microsoft 365 para empresas como se describe en Implementar [Microsoft Teams con Aplicaciones Microsoft 365 para empresas](/DeployOffice/teams-install).

Teams sigue su propio proceso de actualización como se describe anteriormente. Teams no sigue el proceso de actualización de las otras aplicaciones de Office, como Word y Excel. Para obtener más información, lea [Información general sobre los canales de actualización para Aplicaciones Microsoft 365 para empresas](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>¿Qué sucede con las actualizaciones Teams en VDI?


Teams los clientes Infraestructura de escritorio virtual (VDI) no se actualizan automáticamente de la forma en que los clientes que no son Teams VDI. Tiene que actualizar la imagen de la máquina virtual instalando un nuevo MSI como se describe en las instrucciones de Instalar [Teams en VDI.](teams-for-vdi.md) Debe desinstalar la versión actual para actualizar a una versión más reciente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>¿Pueden los administradores implementar actualizaciones en lugar Teams la actualización automática?

Teams no permite a los administradores implementar actualizaciones a través de ningún mecanismo de entrega.

## <a name="servicing-agreement"></a>Contrato de mantenimiento

Como servicio en línea moderno, el Teams cliente se actualiza automáticamente cada dos semanas. Como Teams se rige por la directiva de ciclo de vida moderna, se espera que los usuarios permanezcan en la versión más actualizada del cliente de escritorio. Las actualizaciones automáticas garantizan que los usuarios tengan las últimas capacidades, mejoras de rendimiento, seguridad y confiabilidad del servicio.

Para identificar cuándo los clientes de escritorio no están actualizados, se mostrará una alerta desde la aplicación si la versión actual del usuario tiene entre uno y tres meses de antigüedad y si hay una nueva versión disponible. Esta mensajería desde la aplicación anima a los usuarios a actualizar a la última versión de Teams o, si es necesario, a comunicarse con su administrador de TI para hacerlo. Los usuarios de Teams de escritorio que tienen más de tres meses de antigüedad verán una página de bloqueo que ofrece las opciones para actualizar ahora, comunicarse con su administrador de TI o continuar Teams en la Web.

Teams de escritorio en las nubes gubernamentales actualmente tienen una excepción a este contrato de mantenimiento hasta nuevo aviso.

Para obtener información sobre las versiones nuevas, consulte Centro [de mensajes](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) o vaya **a** Ayuda  >  **novedades** del cliente.
