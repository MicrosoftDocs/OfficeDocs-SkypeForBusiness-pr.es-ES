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
# <a name="teams-update-process"></a><span data-ttu-id="507e9-103">Teams de actualización</span><span class="sxs-lookup"><span data-stu-id="507e9-103">Teams update process</span></span>

<span data-ttu-id="507e9-104">La Teams web se actualiza semanalmente.</span><span class="sxs-lookup"><span data-stu-id="507e9-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="507e9-105">Teams actualizaciones de cliente de escritorio se lanzan cada dos semanas después de rigurosas pruebas internas y validación a través de Programa de adopción de tecnología (TAP).</span><span class="sxs-lookup"><span data-stu-id="507e9-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="507e9-106">La actualización suele tener lugar un martes.</span><span class="sxs-lookup"><span data-stu-id="507e9-106">The update usually takes place on a Tuesday.</span></span> <span data-ttu-id="507e9-107">Si se requiere una actualización crítica, Teams omitirá esta programación y la lanzará tan pronto como esté disponible.</span><span class="sxs-lookup"><span data-stu-id="507e9-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="507e9-108">El cliente de escritorio se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="507e9-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="507e9-109">Teams busca actualizaciones cada pocas horas en segundo plano, la descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar la actualización en silencio.</span><span class="sxs-lookup"><span data-stu-id="507e9-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="507e9-110">Los usuarios también pueden descargar  actualizaciones manualmente seleccionando Buscar actualizaciones en el menú desplegable Perfil en la parte superior derecha de la aplicación. </span><span class="sxs-lookup"><span data-stu-id="507e9-110">Users can also manually download updates by selecting **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="507e9-111">Si hay una actualización disponible, se descargará y se instalará de forma silenciosa cuando el equipo esté inactivo.</span><span class="sxs-lookup"><span data-stu-id="507e9-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="507e9-112">Los usuarios deben haber iniciado sesión para que se descarguen las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="507e9-112">Users need to be signed in for updates to be downloaded.</span></span>

<span data-ttu-id="507e9-113">A partir del 31 de julio de 2019, Teams actualizaciones de cliente usan un ancho de banda de red inferior durante la actualización.</span><span class="sxs-lookup"><span data-stu-id="507e9-113">Starting July 31, 2019, Teams client updates use lower network bandwidth during the update.</span></span> <span data-ttu-id="507e9-114">Esta actualización está activada de forma predeterminada y no requiere ninguna acción de administradores o usuarios.</span><span class="sxs-lookup"><span data-stu-id="507e9-114">This update is turned on by default and requires no action from admins or users.</span></span>

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="507e9-115">¿Qué sucede con las actualizaciones Aplicaciones Microsoft 365 para empresas?</span><span class="sxs-lookup"><span data-stu-id="507e9-115">What about updates to Microsoft 365 Apps for enterprise?</span></span>

<span data-ttu-id="507e9-116">Teams está instalado de forma predeterminada con nuevas instalaciones de Aplicaciones Microsoft 365 para empresas como se describe en Implementar [Microsoft Teams con Aplicaciones Microsoft 365 para empresas](/DeployOffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="507e9-116">Teams is installed by default with new installations of Microsoft 365 Apps for enterprise as described in [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](/DeployOffice/teams-install).</span></span>

<span data-ttu-id="507e9-117">Teams sigue su propio proceso de actualización como se describe anteriormente.</span><span class="sxs-lookup"><span data-stu-id="507e9-117">Teams follows its own update process as outlined above.</span></span> <span data-ttu-id="507e9-118">Teams no sigue el proceso de actualización de las otras aplicaciones de Office, como Word y Excel.</span><span class="sxs-lookup"><span data-stu-id="507e9-118">Teams doesn't follow the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="507e9-119">Para obtener más información, lea [Información general sobre los canales de actualización para Aplicaciones Microsoft 365 para empresas](/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span><span class="sxs-lookup"><span data-stu-id="507e9-119">To learn more, read [Overview of update channels for Microsoft 365 Apps for enterprise](/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="507e9-120">¿Qué sucede con las actualizaciones Teams en VDI?</span><span class="sxs-lookup"><span data-stu-id="507e9-120">What about updates to Teams on VDI?</span></span>


<span data-ttu-id="507e9-121">Teams los clientes Infraestructura de escritorio virtual (VDI) no se actualizan automáticamente de la forma en que los clientes que no son Teams VDI.</span><span class="sxs-lookup"><span data-stu-id="507e9-121">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="507e9-122">Tiene que actualizar la imagen de la máquina virtual instalando un nuevo MSI como se describe en las instrucciones de Instalar [Teams en VDI.](teams-for-vdi.md)</span><span class="sxs-lookup"><span data-stu-id="507e9-122">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](teams-for-vdi.md).</span></span> <span data-ttu-id="507e9-123">Debe desinstalar la versión actual para actualizar a una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="507e9-123">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="507e9-124">¿Pueden los administradores implementar actualizaciones en lugar Teams la actualización automática?</span><span class="sxs-lookup"><span data-stu-id="507e9-124">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="507e9-125">Teams no permite a los administradores implementar actualizaciones a través de ningún mecanismo de entrega.</span><span class="sxs-lookup"><span data-stu-id="507e9-125">Teams doesn't give admins the ability to deploy updates through any delivery mechanism.</span></span>

## <a name="servicing-agreement"></a><span data-ttu-id="507e9-126">Contrato de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="507e9-126">Servicing agreement</span></span>

<span data-ttu-id="507e9-127">Como servicio en línea moderno, el Teams cliente se actualiza automáticamente cada dos semanas.</span><span class="sxs-lookup"><span data-stu-id="507e9-127">As a modern online service, the Teams client auto-updates every two weeks.</span></span> <span data-ttu-id="507e9-128">Como Teams se rige por la directiva de ciclo de vida moderna, se espera que los usuarios permanezcan en la versión más actualizada del cliente de escritorio.</span><span class="sxs-lookup"><span data-stu-id="507e9-128">Because Teams is governed by the Modern Lifecycle Policy, it's expected that users remain on the most up-to-date version of the desktop client.</span></span> <span data-ttu-id="507e9-129">Las actualizaciones automáticas garantizan que los usuarios tengan las últimas capacidades, mejoras de rendimiento, seguridad y confiabilidad del servicio.</span><span class="sxs-lookup"><span data-stu-id="507e9-129">Auto-updates ensure that users have the latest capabilities, performance enhancements, security, and service reliability.</span></span>

<span data-ttu-id="507e9-130">Para identificar cuándo los clientes de escritorio no están actualizados, se mostrará una alerta desde la aplicación si la versión actual del usuario tiene entre uno y tres meses de antigüedad y si hay una nueva versión disponible.</span><span class="sxs-lookup"><span data-stu-id="507e9-130">To identify when desktop clients fall out of date, an in-app alert will be displayed if the user’s current version is between one and three months old, and if there's a new version available.</span></span> <span data-ttu-id="507e9-131">Esta mensajería desde la aplicación anima a los usuarios a actualizar a la última versión de Teams o, si es necesario, a comunicarse con su administrador de TI para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="507e9-131">This in-app messaging encourages users to update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="507e9-132">Los usuarios de Teams de escritorio que tienen más de tres meses de antigüedad verán una página de bloqueo que ofrece las opciones para actualizar ahora, comunicarse con su administrador de TI o continuar Teams en la Web.</span><span class="sxs-lookup"><span data-stu-id="507e9-132">Users on Teams desktop clients that are more than three months old will see a blocking page that gives the options to update now, reach out to their IT admin, or continue to Teams on the web.</span></span>

<span data-ttu-id="507e9-133">Teams de escritorio en las nubes gubernamentales actualmente tienen una excepción a este contrato de mantenimiento hasta nuevo aviso.</span><span class="sxs-lookup"><span data-stu-id="507e9-133">Teams desktop clients on Government Clouds currently have an exception to this servicing agreement until further notice.</span></span>

<span data-ttu-id="507e9-134">Para obtener información sobre las versiones nuevas, consulte Centro [de mensajes](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) o vaya **a** Ayuda  >  **novedades** del cliente.</span><span class="sxs-lookup"><span data-stu-id="507e9-134">For information on new version releases, check [Message Center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) or go to **Help** > **What’s new** in the client.</span></span>
