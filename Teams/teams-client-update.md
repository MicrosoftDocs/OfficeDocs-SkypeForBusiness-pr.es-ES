---
title: Proceso de actualización de los equipos
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
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
ms.openlocfilehash: 04b7d1e66905e7859139605b90b3093a48e8afbd
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2019
ms.locfileid: "33829099"
---
# <a name="teams-update-process"></a><span data-ttu-id="3c31a-103">Proceso de actualización de los equipos</span><span class="sxs-lookup"><span data-stu-id="3c31a-103">Teams update process</span></span>

<span data-ttu-id="3c31a-104">La aplicación Web de los equipos se actualiza semanalmente.</span><span class="sxs-lookup"><span data-stu-id="3c31a-104">The Teams Web App is updated weekly.</span></span>

<span data-ttu-id="3c31a-105">Los equipos cliente de escritorio se lanzan las actualizaciones cada dos semanas después de realizar rigurosas pruebas interno y validación a través de nuestro programa de adopción de tecnología (TAP).</span><span class="sxs-lookup"><span data-stu-id="3c31a-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="3c31a-106">Normalmente, esto lleva a cabo un martes.</span><span class="sxs-lookup"><span data-stu-id="3c31a-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="3c31a-107">Si se requiere una actualización crítica, los equipos omitir esta programación y la actualización de la versión tan pronto como está disponible.</span><span class="sxs-lookup"><span data-stu-id="3c31a-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="3c31a-108">El cliente de escritorio se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3c31a-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="3c31a-109">Comprobaciones de los equipos para actualiza cada pocas horas en segundo plano, lo descarga y, a continuación, espera a que el equipo esté inactivo antes de instalar la actualización de modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="3c31a-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="3c31a-110">Los usuarios pueden descargar manualmente las actualizaciones, haga clic en **Buscar actualizaciones** en el menú desplegable de **perfil** en la parte superior derecha de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c31a-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="3c31a-111">Si hay disponible una actualización, se descargará y se instala en modo silencioso cuando el equipo está inactivo.</span><span class="sxs-lookup"><span data-stu-id="3c31a-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="3c31a-112">Los usuarios deben haber iniciado sesión en para que las actualizaciones se descarguen.</span><span class="sxs-lookup"><span data-stu-id="3c31a-112">Users need to be signed in for updates to be downloaded.</span></span>

## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="3c31a-113">¿Qué información acerca de las actualizaciones para Office 365 ProPlus?</span><span class="sxs-lookup"><span data-stu-id="3c31a-113">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="3c31a-114">Los equipos se instala de forma predeterminada con las nuevas instalaciones de Office 365 ProPlus tal como se describe en [Implementar Microsoft equipos con Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="3c31a-114">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="3c31a-115">Los equipos sigue su propio proceso de actualización descritas anteriormente y no el proceso de actualización de las otras aplicaciones de oficinas, como Word y Excel.</span><span class="sxs-lookup"><span data-stu-id="3c31a-115">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="3c31a-116">¿Qué ocurre con las actualizaciones de los equipos de la VDI?</span><span class="sxs-lookup"><span data-stu-id="3c31a-116">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="3c31a-117">Los clientes de los equipos en la infraestructura de Escritorio Virtual (VDI) no se actualizan automáticamente el modo en que los clientes de equipos que no sean de VDI.</span><span class="sxs-lookup"><span data-stu-id="3c31a-117">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="3c31a-118">Se debe actualizar la imagen de la máquina virtual mediante la instalación de un nuevo MSI tal como se describe en las instrucciones para [Instalar los equipos de la VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span><span class="sxs-lookup"><span data-stu-id="3c31a-118">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="3c31a-119">Debe desinstalar la versión actual para actualizar a una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="3c31a-119">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="3c31a-120">¿Pueden administradores implementar las actualizaciones en lugar de los equipos de actualización automática?</span><span class="sxs-lookup"><span data-stu-id="3c31a-120">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="3c31a-121">Los equipos no dar a los administradores de la capacidad para implementar las actualizaciones a través de ningún mecanismo de entrega.</span><span class="sxs-lookup"><span data-stu-id="3c31a-121">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
