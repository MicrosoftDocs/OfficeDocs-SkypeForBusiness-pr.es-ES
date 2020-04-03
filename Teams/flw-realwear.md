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
ms.openlocfilehash: 95d3ead9c85fc58fdc55cd321e55b0ff9ca76853
ms.sourcegitcommit: 708270f1fecab6b7b44345d57a8e12bc36d19c8b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102398"
---
# <a name="realwear-for-microsoft-teams"></a><span data-ttu-id="2ac9b-103">RealWear para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ac9b-103">RealWear for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="2ac9b-104">Esta es una característica en versión preliminar o anticipada.</span><span class="sxs-lookup"><span data-stu-id="2ac9b-104">This is a preview or early release feature.</span></span>

<span data-ttu-id="2ac9b-105">Este artículo trata sobre el cliente de Microsoft Teams para los dispositivos portátiles RealWear.</span><span class="sxs-lookup"><span data-stu-id="2ac9b-105">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="2ac9b-106">Los Firstline Workers que usan el RealWear HMT-1 y el HMT-1Z1 ahora pueden colaborar con un experto remoto mediante las llamadas de vídeo en Teams.</span><span class="sxs-lookup"><span data-stu-id="2ac9b-106">FirstLine Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="2ac9b-107">Mediante una interfaz de usuario controlada por voz, Teams para RealWear permite que los trabajadores de campo estén 100% de manos libres mientras mantienen su concentración en las situaciones que puedan ocurrir en entornos ruidosos y peligrosos.</span><span class="sxs-lookup"><span data-stu-id="2ac9b-107">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="2ac9b-108">Al mostrar lo que ven en tiempo real, los trabajadores de campo pueden resolver problemas de forma más rápida y reducir el riesgo de un tiempo de inactividad costoso.</span><span class="sxs-lookup"><span data-stu-id="2ac9b-108">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="2ac9b-109">Cómo implementar Microsoft Teams para RealWear</span><span class="sxs-lookup"><span data-stu-id="2ac9b-109">How to deploy Microsoft Teams for RealWear</span></span>

<span data-ttu-id="2ac9b-110">El cliente de Microsoft Teams para RealWear está actualmente en versión preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="2ac9b-110">Microsoft Teams client for RealWear is currently in Public Preview.</span></span> <span data-ttu-id="2ac9b-111">Para participar en esta versión preliminar, necesita lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ac9b-111">To participate in this preview, you will need the following:</span></span>

<span data-ttu-id="2ac9b-112">Dispositivos RealWear actualizados a la versión 10.5.0 o superior.</span><span class="sxs-lookup"><span data-stu-id="2ac9b-112">RealWear devices updated to release 10.5.0 or above.</span></span> <span data-ttu-id="2ac9b-113">Obtenga más información [aquí](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span><span class="sxs-lookup"><span data-stu-id="2ac9b-113">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ac9b-114">Regístrese [aquí](https://www.realwear.com/solutions/microsoft-teams/#C1) para tener acceso al cliente de RealWear para Teams en [RealWear Foresight](https://cloud.realwear.com/).</span><span class="sxs-lookup"><span data-stu-id="2ac9b-114">Register [here](https://www.realwear.com/solutions/microsoft-teams/#C1) for access to Teams for RealWear client in [RealWear Foresight](https://cloud.realwear.com/).</span></span>

## <a name="required-licenses"></a><span data-ttu-id="2ac9b-115">Licencias necesarias</span><span class="sxs-lookup"><span data-stu-id="2ac9b-115">Required Licenses</span></span>

<span data-ttu-id="2ac9b-116">Las licencias de Microsoft Teams forman parte de las suscripciones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="2ac9b-116">Microsoft Teams licenses are part of Office 365 subscriptions.</span></span> <span data-ttu-id="2ac9b-117">No se requiere ninguna licencia adicional para usar Teams para RealWear.</span><span class="sxs-lookup"><span data-stu-id="2ac9b-117">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="2ac9b-118">Para más información sobre cómo obtener Teams, consulte [Cómo obtengo acceso a Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span><span class="sxs-lookup"><span data-stu-id="2ac9b-118">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="2ac9b-119">Administración de dispositivos RealWear</span><span class="sxs-lookup"><span data-stu-id="2ac9b-119">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="2ac9b-120">Administrador de puntos de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2ac9b-120">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="2ac9b-121">Los dispositivos RealWear se pueden administrar mediante el modo de Administrador de dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="2ac9b-121">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="2ac9b-122">El soporte técnico para la administración mediante Android Enterprise es limitado, ya que en este momento los dispositivos no tienen disponibles los servicios móviles de Google (GMS).</span><span class="sxs-lookup"><span data-stu-id="2ac9b-122">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="2ac9b-123">Para obtener más información sobre la administración de dispositivos de RealWear en Microsoft Endpoint Manager, consulte [Inscripción del administrador de dispositivos Android en Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span><span class="sxs-lookup"><span data-stu-id="2ac9b-123">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="2ac9b-124">Administradores externos de gestión de la movilidad empresarial (EMMs)</span><span class="sxs-lookup"><span data-stu-id="2ac9b-124">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="2ac9b-125">Para obtener instrucciones sobre EMMs externos, consulte [Proveedores de gestión de la movilidad empresarial compatibles](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span><span class="sxs-lookup"><span data-stu-id="2ac9b-125">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>
