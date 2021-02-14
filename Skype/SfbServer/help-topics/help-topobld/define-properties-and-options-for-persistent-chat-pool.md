---
title: Definir propiedades y opciones para grupo de servidores de chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Las opciones para el servidor de chat persistente o el grupo de servidores de chat persistente se configuran definiendo las siguientes propiedades:'
ms.openlocfilehash: acc80c76e79364be730ec56a2b64e5dcd001f661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818430"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="0c221-103">Definir propiedades y opciones para grupo de servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="0c221-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="0c221-104">Las opciones para el servidor de chat persistente o el grupo de servidores de chat persistente se configuran definiendo las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="0c221-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="0c221-105">**Nombre para mostrar del** grupo de chat persistente: una propiedad necesaria que define un nombre descriptivo que se mostrará para este servidor de chat persistente o grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0c221-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="0c221-106">**Puerto de chat persistente:** una propiedad necesaria que definirá el número de puerto en el que escuchará este servidor de chat persistente o grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0c221-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="0c221-107">**Habilitar cumplimiento:** active la casilla si tiene previsto implementar la base de datos y la característica opcional de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0c221-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="0c221-108">**Use** almacenes de SQL Server de copia de seguridad para habilitar la recuperación ante desastres: active esta casilla si tiene previsto implementar e implementar la recuperación ante desastres de los almacenes de SQL Server de chat persistente de un conjunto de almacenes de copia de seguridad configurado en otro SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c221-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="0c221-109">Para obtener más información, consulte Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de [chat persistente en Skype Empresarial Server 2015.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)</span><span class="sxs-lookup"><span data-stu-id="0c221-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c221-110">Esta opción solamente está disponible para grupos de servidores con varios servidores.</span><span class="sxs-lookup"><span data-stu-id="0c221-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="0c221-111">**Use este grupo de \<site that this server or pool is being configured in\> servidores como** predeterminado para el sitio: active esta casilla si será el servidor de chat persistente predeterminado o el grupo de servidores de chat persistente para el sitio.</span><span class="sxs-lookup"><span data-stu-id="0c221-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="0c221-112">Debe tener un servidor de chat persistente o pol predeterminado por sitio.</span><span class="sxs-lookup"><span data-stu-id="0c221-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0c221-113">Si la topología incluye varios sitios también aparecerá una casilla de verificación para **Usar este grupo de servidores como predeterminado para todos los sitios**.</span><span class="sxs-lookup"><span data-stu-id="0c221-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="0c221-114">Haga clic en **Atrás** para retroceder al diálogo de definición de grupo de servidores anterior.</span><span class="sxs-lookup"><span data-stu-id="0c221-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="0c221-115">Haga **clic en** Siguiente una vez que haya terminado de especificar las opciones para que este grupo continúe con la definición del grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0c221-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="0c221-116">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="0c221-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="0c221-117">Haga clic en **Ayuda** para acceder a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="0c221-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0c221-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c221-118">See also</span></span>

[<span data-ttu-id="0c221-119">Planear el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0c221-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="0c221-120">Agregar un servidor de chat persistente a la topología de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0c221-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
