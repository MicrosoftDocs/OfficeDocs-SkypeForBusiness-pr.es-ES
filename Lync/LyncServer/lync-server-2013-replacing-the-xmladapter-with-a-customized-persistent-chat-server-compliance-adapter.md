---
title: 'Lync Server 2013: reemplazar XmlAdapter por un adaptador de cumplimiento del servidor de chat persistente personalizado'
description: 'Lync Server 2013: reemplazar XmlAdapter por un adaptador de cumplimiento del servidor de chat persistente personalizado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a90b4df7df42ffdc6c55e9b551b0eb53d07ab1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576146"
---
# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="5e25e-103">Reemplazar el XmlAdapter por un adaptador de cumplimiento del servidor de chat persistente personalizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e25e-103">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e25e-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5e25e-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5e25e-105">Puede escribir un adaptador personalizado en lugar de usar XmlAdapter que se instala con el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5e25e-105">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="5e25e-106">Para ello, debe proporcionar un ensamblado de .NET Framework que contenga una clase pública que implemente la interfaz **IComplianceAdapter** .</span><span class="sxs-lookup"><span data-stu-id="5e25e-106">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="5e25e-107">Debe situar este ensamblado en la carpeta de instalación del servidor de chat persistente de cada servidor del grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5e25e-107">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="5e25e-108">Cualquiera de los servidores de cumplimiento puede proporcionar datos de cumplimiento a su adaptador, pero los servidores de cumplimiento no proporcionarán datos de cumplimiento duplicados a varias instancias del adaptador.</span><span class="sxs-lookup"><span data-stu-id="5e25e-108">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="5e25e-109">Implementación de la interfaz IComplianceAdapter</span><span class="sxs-lookup"><span data-stu-id="5e25e-109">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="5e25e-110">La interfaz se define en el ensamblado Compliance.dll del espacio de nombres `Microsoft.Rtc.Internal.Chat.Server.Compliance` .</span><span class="sxs-lookup"><span data-stu-id="5e25e-110">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="5e25e-111">La interfaz define dos métodos que debe implementar su adaptador personalizado.</span><span class="sxs-lookup"><span data-stu-id="5e25e-111">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="5e25e-112">El servidor de cumplimiento de chat persistente llamará a este método cuando se cargue el adaptador por primera vez.</span><span class="sxs-lookup"><span data-stu-id="5e25e-112">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="5e25e-113">El `AdapterConfig` contiene la configuración de cumplimiento de chat persistente que es relevante para el adaptador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="5e25e-113">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="5e25e-114">El servidor de cumplimiento de chat persistente llama a este método a intervalos periódicos siempre que haya datos nuevos para traducir.</span><span class="sxs-lookup"><span data-stu-id="5e25e-114">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="5e25e-115">Este intervalo de tiempo es igual al `RunInterval` establecido en la configuración de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5e25e-115">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="5e25e-116">El `ConversationCollection` contiene la información de la conversación que se recopiló desde la última vez que se llamó a este método.</span><span class="sxs-lookup"><span data-stu-id="5e25e-116">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

