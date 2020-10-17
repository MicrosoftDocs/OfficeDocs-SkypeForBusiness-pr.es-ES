---
title: 'Lync Server 2013: implementación del complemento Lync VDI'
description: 'Lync Server 2013: implementación del complemento VDI de Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync VDI plug-in
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48183449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3addecb07f269e4524f3da835f479439639935ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557806"
---
# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="a2e50-103">Implementación del complemento Lync VDI en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2e50-103">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2e50-104">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a2e50-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a2e50-105">El cliente de Lync 2013 admite audio y vídeo en un entorno de infraestructura de escritorio virtual (VDI).</span><span class="sxs-lookup"><span data-stu-id="a2e50-105">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="a2e50-106">Un usuario puede conectar un dispositivo de audio o vídeo (por ejemplo, un auricular o una cámara) al equipo local (por ejemplo, un cliente ligero o un equipo con un repropósito).</span><span class="sxs-lookup"><span data-stu-id="a2e50-106">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="a2e50-107">El usuario puede conectarse a la máquina virtual, iniciar sesión en el cliente de Lync 2013 que se está ejecutando en la máquina virtual y participar en comunicaciones de audio y vídeo en tiempo real como si el cliente se ejecuta de forma local.</span><span class="sxs-lookup"><span data-stu-id="a2e50-107">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="a2e50-108">El complemento de VDI de Lync es una aplicación independiente que se instala en el equipo local y permite el uso de dispositivos de audio y vídeo locales con el cliente de Lync 2013 que se ejecuta en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="a2e50-108">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="a2e50-109">El complemento no requiere que Lync esté instalado en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a2e50-109">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="a2e50-110">Después de que el usuario inicie sesión en el cliente de Lync 2013 que se ejecuta en la máquina virtual, Lync solicita al usuario que vuelva a escribir sus credenciales para establecer una conexión con el complemento VDI de Lync que se ejecuta en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a2e50-110">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="a2e50-111">Una vez establecida esta conexión, el usuario está listo para realizar y recibir llamadas de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="a2e50-111">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a2e50-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a2e50-112">In This Section</span></span>

  - [<span data-ttu-id="a2e50-113">Requisitos previos del complemento Lync VDI en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2e50-113">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="a2e50-114">Preparar el entorno de Lync Server 2013 para VDI</span><span class="sxs-lookup"><span data-stu-id="a2e50-114">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="a2e50-115">Inicio de sesión y uso de Lync 2013 en la máquina virtual</span><span class="sxs-lookup"><span data-stu-id="a2e50-115">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="a2e50-116">Solución de problemas del complemento Lync VDI en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2e50-116">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="a2e50-117">Tecnologías de virtualización admitidas y limitaciones conocidas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2e50-117">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

