---
title: 'Lync Server 2013: requisitos de Lync para Android'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync for Android requirements
ms:assetid: 4ff53e03-0c1f-4a2b-9cec-1131c2a48563
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690980(v=OCS.15)
ms:contentKeyID: 53312965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c584a20df5dc2516115b4b137c0543576d5fa4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-for-android-requirements-in-lync-server-2013"></a><span data-ttu-id="843c5-102">Requisitos de Lync para Android en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="843c5-102">Lync for Android requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="843c5-103">_**Última modificación del tema:** 2014-04-24_</span><span class="sxs-lookup"><span data-stu-id="843c5-103">_**Topic Last Modified:** 2014-04-24_</span></span>

<span data-ttu-id="843c5-104">Microsoft Lync 2013 Microsoft Lync 2013 para Android proporciona funciones de mensajería instantánea (mi), presencia mejorada y Unión de reuniones de Lync a los usuarios de su organización que se conecten desde un dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="843c5-104">Microsoft Lync 2013 Microsoft Lync 2013 for Android provides instant messaging (IM), enhanced presence, and Lync meeting join capabilities for users in your organization who are connecting from an Android device.</span></span> <span data-ttu-id="843c5-105">En este tema se describen las consideraciones para Lync 2013 para Android, incluidos los requisitos previos, los requisitos técnicos y los componentes necesarios.</span><span class="sxs-lookup"><span data-stu-id="843c5-105">This topic describes considerations for Lync 2013 for Android, including prerequisites, technical requirements, and required components.</span></span>

<div>

## <a name="lync-for-android-prerequisite"></a><span data-ttu-id="843c5-106">Requisito previo de Lync para Android</span><span class="sxs-lookup"><span data-stu-id="843c5-106">Lync for Android Prerequisite</span></span>

<span data-ttu-id="843c5-107">Para admitir Lync 2013 para Android, el dispositivo Android debe cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="843c5-107">To support Lync 2013 for Android, the Android device must meet the following requirements:</span></span>

  - <span data-ttu-id="843c5-108">El dispositivo Android debe estar ejecutando Android 4,0 o un sistema operativo orientado a teléfonos o tableta, incluidas las tabletas, excepto las que tienen el chip Tegra2.</span><span class="sxs-lookup"><span data-stu-id="843c5-108">The Android device must be running Android 4.0 or a later phone- or tablet-oriented operating system, including tablets, except those with the Tegra2 chip.</span></span>

  - <span data-ttu-id="843c5-109">El dispositivo debe tener una CPU de 1,2 GHz de doble núcleo o superior.</span><span class="sxs-lookup"><span data-stu-id="843c5-109">The device must have a 1.2 GHz dual core or higher CPU.</span></span>

  - <span data-ttu-id="843c5-110">La resolución de cámara de dispositivo (frontal y trasera) debe ser VGA o superior.</span><span class="sxs-lookup"><span data-stu-id="843c5-110">The device camera (front/rear) resolution should be VGA or higher.</span></span>

  - <span data-ttu-id="843c5-111">Otros requisitos de hardware se deben alinear con el documento definición de compatibilidad de Android 4,0.</span><span class="sxs-lookup"><span data-stu-id="843c5-111">Other hardware requirements should be aligned with Android 4.0 Compatibility Definition Document.</span></span>

</div>

<div>

## <a name="other-technical-considerations"></a><span data-ttu-id="843c5-112">Otras consideraciones técnicas</span><span class="sxs-lookup"><span data-stu-id="843c5-112">Other Technical Considerations</span></span>

<span data-ttu-id="843c5-113">En la plataforma de dispositivos Android, la aplicación Lync puede ejecutarse en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="843c5-113">On the Android device platform, the Lync application can run in the background.</span></span> <span data-ttu-id="843c5-114">Por lo tanto, a diferencia de otras plataformas de dispositivos móviles, las notificaciones push no son necesarias para dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="843c5-114">Therefore, unlike other mobile device platforms, push notifications are not required for Android devices.</span></span> <span data-ttu-id="843c5-115">La única forma de salir de la aplicación de Lync en un dispositivo Android es cerrar la sesión de forma explícita de Lync.</span><span class="sxs-lookup"><span data-stu-id="843c5-115">The only way to exit the Lync application on an Android device is to explicitly sign out of Lync.</span></span> <span data-ttu-id="843c5-116">Esta versión de la aplicación Lync no se admite en dispositivos con chipsets Tegra 2.</span><span class="sxs-lookup"><span data-stu-id="843c5-116">This version of the Lync application is not supported on devices with Tegra 2 chipsets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

