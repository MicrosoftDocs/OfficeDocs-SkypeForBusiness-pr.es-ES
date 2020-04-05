---
title: Información del administrador de TI sobre el cliente de RealWear para Microsoft Teams (versión preliminar)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: A, Tutorial del administrador de TI del cliente de RealWear para Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: e95440652111dbcd39b756ef942e7a974ef31de0
ms.sourcegitcommit: dc6108917392754d950cea47b92f871211bf4212
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131208"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="2bd19-103">Microsoft Teams para RealWear</span><span class="sxs-lookup"><span data-stu-id="2bd19-103">Microsoft Teams for RealWear</span></span>

> [!NOTE]
> <span data-ttu-id="2bd19-104">Esta es una característica en versión preliminar o anticipada.</span><span class="sxs-lookup"><span data-stu-id="2bd19-104">This is a preview or early release feature.</span></span>

<span data-ttu-id="2bd19-105">Este artículo trata sobre el cliente de Microsoft Teams para los dispositivos portátiles RealWear.</span><span class="sxs-lookup"><span data-stu-id="2bd19-105">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="2bd19-106">Los Firstline Workers que usan el RealWear HMT-1 y el HMT-1Z1 ahora pueden colaborar con un experto remoto mediante las llamadas de vídeo en Teams.</span><span class="sxs-lookup"><span data-stu-id="2bd19-106">FirstLine Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="2bd19-107">Mediante una interfaz de usuario controlada por voz, Teams para RealWear permite que los trabajadores de campo estén 100% de manos libres mientras mantienen su concentración en las situaciones que puedan ocurrir en entornos ruidosos y peligrosos.</span><span class="sxs-lookup"><span data-stu-id="2bd19-107">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="2bd19-108">Al mostrar lo que ven en tiempo real, los trabajadores de campo pueden resolver problemas de forma más rápida y reducir el riesgo de un tiempo de inactividad costoso.</span><span class="sxs-lookup"><span data-stu-id="2bd19-108">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="2bd19-109">Cómo implementar Microsoft Teams para RealWear</span><span class="sxs-lookup"><span data-stu-id="2bd19-109">How to deploy Microsoft Teams for RealWear</span></span>

<span data-ttu-id="2bd19-110">El cliente de Microsoft Teams para RealWear está actualmente en versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="2bd19-110">Microsoft Teams client for RealWear is currently in Public Preview.</span></span> <span data-ttu-id="2bd19-111">Para participar en esta versión preliminar, necesita lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2bd19-111">To participate in this preview, you will need the following:</span></span>

<span data-ttu-id="2bd19-112">Dispositivos RealWear actualizados a la versión 10.5.0 o superior.</span><span class="sxs-lookup"><span data-stu-id="2bd19-112">RealWear devices updated to release 10.5.0 or above.</span></span> <span data-ttu-id="2bd19-113">Obtenga más información [aquí](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span><span class="sxs-lookup"><span data-stu-id="2bd19-113">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bd19-114">Regístrese [aquí](https://www.realwear.com/solutions/microsoft-teams/#C1) para tener acceso al cliente de RealWear para Teams en [RealWear Foresight](https://cloud.realwear.com/).</span><span class="sxs-lookup"><span data-stu-id="2bd19-114">Register [here](https://www.realwear.com/solutions/microsoft-teams/#C1) for access to Teams for RealWear client in [RealWear Foresight](https://cloud.realwear.com/).</span></span>

## <a name="required-licenses"></a><span data-ttu-id="2bd19-115">Licencias necesarias</span><span class="sxs-lookup"><span data-stu-id="2bd19-115">Required Licenses</span></span>

<span data-ttu-id="2bd19-116">Las licencias de Microsoft Teams forman parte de las suscripciones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2bd19-116">Microsoft Teams licenses are part of Office 365 subscriptions.</span></span> <span data-ttu-id="2bd19-117">No se requiere ninguna licencia adicional para usar Teams para RealWear.</span><span class="sxs-lookup"><span data-stu-id="2bd19-117">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="2bd19-118">Para más información sobre cómo obtener Teams, consulte [Cómo obtengo acceso a Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span><span class="sxs-lookup"><span data-stu-id="2bd19-118">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="2bd19-119">Administración de dispositivos RealWear</span><span class="sxs-lookup"><span data-stu-id="2bd19-119">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="2bd19-120">Administrador de puntos de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2bd19-120">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="2bd19-121">Los dispositivos RealWear se pueden administrar mediante el modo de Administrador de dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="2bd19-121">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="2bd19-122">El soporte técnico para la administración mediante Android Enterprise es limitado, ya que en este momento los dispositivos no tienen disponibles los servicios móviles de Google (GMS).</span><span class="sxs-lookup"><span data-stu-id="2bd19-122">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="2bd19-123">Para obtener más información sobre la administración de dispositivos de RealWear en Microsoft Endpoint Manager, consulte [Inscripción del administrador de dispositivos Android en Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span><span class="sxs-lookup"><span data-stu-id="2bd19-123">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span></span>
- <span data-ttu-id="2bd19-124">Para obtener más información sobre las directivas, consulte [Cómo usar Intune en entornos sin Google Mobile Services](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span><span class="sxs-lookup"><span data-stu-id="2bd19-124">For more details on policies, see [How to use Intune in environments without Google Mobile Services](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="2bd19-125">Administradores externos de gestión de la movilidad empresarial (EMMs)</span><span class="sxs-lookup"><span data-stu-id="2bd19-125">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="2bd19-126">Para obtener instrucciones sobre EMMs externos, consulte [Proveedores de gestión de la movilidad empresarial compatibles](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span><span class="sxs-lookup"><span data-stu-id="2bd19-126">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="2bd19-127">Contenido de usuario final</span><span class="sxs-lookup"><span data-stu-id="2bd19-127">End-user content</span></span>

<span data-ttu-id="2bd19-128">Para obtener más información sobre esto desde el punto de vista del usuario final, consulte [Usar Microsoft Teams para RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span><span class="sxs-lookup"><span data-stu-id="2bd19-128">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>
