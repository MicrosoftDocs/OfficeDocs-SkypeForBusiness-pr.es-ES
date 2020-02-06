---
title: Definir propiedades y opciones para grupo de servidores de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Para configurar las opciones del servidor de chat persistente o del grupo de servidores de chat persistente, defina las siguientes propiedades:'
ms.openlocfilehash: 39816bcc4c76a5be07e90c63dfa9064c4a0670d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820192"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="ec24a-103">Definir propiedades y opciones para grupo de servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="ec24a-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="ec24a-104">Para configurar las opciones del servidor de chat persistente o del grupo de servidores de chat persistente, defina las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="ec24a-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="ec24a-105">**Nombre para mostrar del grupo de chats persistentes**: una propiedad obligatoria que define un nombre descriptivo de usuario que se mostrará para este servidor de chat persistente o grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ec24a-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="ec24a-106">**Puerto de chat persistente**: propiedad necesaria que definirá el número de puerto en el que escuchará este servidor de chat persistente o el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ec24a-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="ec24a-107">**Habilitar cumplimiento**: Active la casilla si tiene previsto implementar e implementar la característica de cumplimiento de la conversación persistente y la base de datos opcional.</span><span class="sxs-lookup"><span data-stu-id="ec24a-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="ec24a-108">**Use la copia de seguridad de almacenes de SQL Server para habilitar la recuperación de desastres**: Seleccione esta casilla si desea implementar e implementar la recuperación de desastres de los almacenes de SQL Server de la conversación persistente desde un conjunto de almacenes de copia de seguridad configurado en otro servidor SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ec24a-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="ec24a-109">Para obtener más información, consulte [configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="ec24a-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec24a-110">Esta opción solamente está disponible para grupos de servidores con varios servidores.</span><span class="sxs-lookup"><span data-stu-id="ec24a-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="ec24a-111">**Use este grupo como predeterminado para el sitio \<del sitio en el que se está configurando\>este servidor o grupo de**servidores: Active esta casilla si este es el servidor de chat persistente predeterminado o el grupo de servidores de chat persistente para el sitio.</span><span class="sxs-lookup"><span data-stu-id="ec24a-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="ec24a-112">Debe tener un servidor de chat persistente predeterminado o Pol por sitio.</span><span class="sxs-lookup"><span data-stu-id="ec24a-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec24a-113">Si la topología incluye varios sitios, también aparecerá una casilla **Usar este grupo como predeterminado para todos los sitios**.</span><span class="sxs-lookup"><span data-stu-id="ec24a-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="ec24a-114">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ec24a-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="ec24a-115">Haga clic en **siguiente** cuando haya terminado de escribir las opciones de este grupo para continuar con la definición del grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ec24a-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="ec24a-116">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="ec24a-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="ec24a-117">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="ec24a-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ec24a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec24a-118">See also</span></span>

[<span data-ttu-id="ec24a-119">Planificar el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="ec24a-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="ec24a-120">Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ec24a-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
