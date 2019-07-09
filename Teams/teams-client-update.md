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
ms.openlocfilehash: 436a2a3175cd057082c0e658ea5ab6d3db0364cc
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588186"
---
# <a name="teams-update-process"></a><span data-ttu-id="bcb6b-103">Proceso de actualización de Teams</span><span class="sxs-lookup"><span data-stu-id="bcb6b-103">Teams update process</span></span>

<span data-ttu-id="bcb6b-104">Teams Web App se actualiza semanalmente.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="bcb6b-105">Las actualizaciones de clientes de escritorio de Teams se publican cada dos semanas después de rigurosas pruebas internas y validación por medio de nuestro programa de adopción de tecnología (TAP).</span><span class="sxs-lookup"><span data-stu-id="bcb6b-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="bcb6b-106">Normalmente, esto tiene lugar un martes.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="bcb6b-107">Si se requiere una actualización crítica, Teams evitará esta programación y liberará la actualización tan pronto como esté disponible.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="bcb6b-108">El cliente de escritorio se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="bcb6b-109">Teams busca actualizaciones cada pocas horas, las descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar silenciosamente la actualización.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="bcb6b-110">Los usuarios también pueden descargar actualizaciones manualmente haciendo clic en **Buscar actualizaciones** en el menú desplegable **perfil** en la parte superior derecha de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="bcb6b-111">Si hay una actualización disponible, se descargará y se instalará en modo silencioso cuando el equipo esté inactivo.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="bcb6b-112">Los usuarios deben iniciar sesión para que se descarguen las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-112">Users need to be signed in for updates to be downloaded.</span></span> <span data-ttu-id="bcb6b-113">A partir del 9 de julio de 2019, las actualizaciones de los clientes de Teams usan mucho menos ancho de banda de red durante la actualización.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-113">Starting July 9, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="bcb6b-114">Esta opción está activada de forma predeterminada y no requiere ninguna acción de administradores o usuarios.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-114">This is turned on by default and requires no action from admins or users.</span></span>


## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="bcb6b-115">¿Qué hay de las actualizaciones de Office 365 ProPlus?</span><span class="sxs-lookup"><span data-stu-id="bcb6b-115">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="bcb6b-116">Teams se instala de forma predeterminada con nuevas instalaciones de Office 365 ProPlus, como se describe en [implementar Microsoft Teams con office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="bcb6b-116">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="bcb6b-117">Teams sigue su propio proceso de actualización, como se indica anteriormente, y no el proceso de actualización para las otras aplicaciones de Office, como Word y Excel.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="bcb6b-118">Para obtener más información, vea [información general sobre los canales de actualización de Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) .</span><span class="sxs-lookup"><span data-stu-id="bcb6b-118">To learn more, read [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="bcb6b-119">¿Qué hay de las actualizaciones de Teams en VDI?</span><span class="sxs-lookup"><span data-stu-id="bcb6b-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="bcb6b-120">Los clientes de Teams en la infraestructura de escritorio virtual (VDI) no se actualizan automáticamente de la manera en que los clientes de equipos ajenos a VDI son.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="bcb6b-121">Tiene que actualizar la imagen de VM instalando un nuevo MSI, tal y como se describe en las instrucciones para [instalar Teams en VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span><span class="sxs-lookup"><span data-stu-id="bcb6b-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="bcb6b-122">Debe desinstalar la versión actual para actualizar a una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="bcb6b-123">¿Los administradores pueden implementar actualizaciones en lugar de la actualización automática de Teams?</span><span class="sxs-lookup"><span data-stu-id="bcb6b-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="bcb6b-124">Teams no proporciona a los administradores la capacidad de implementar actualizaciones a través de cualquier mecanismo de envío.</span><span class="sxs-lookup"><span data-stu-id="bcb6b-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
