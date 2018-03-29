---
title: Definir propiedades y opciones para grupo de servidores de chat persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Configurar opciones para el servidor de charla persistente o el grupo de servidores de charla persistente mediante la definición de las propiedades siguientes:'
ms.openlocfilehash: 445e84b4be0567b63b9a56a7bc130e584a826430
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="2d47f-103">Definir propiedades y opciones para grupo de servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2d47f-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="2d47f-104">Configurar opciones para el servidor de charla persistente o el grupo de servidores de charla persistente mediante la definición de las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="2d47f-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="2d47f-105">**Nombre para mostrar del grupo de servidores de charla persistente**: una propiedad necesaria que define un nombre de usuario descriptivo que se mostrará para este servidor de Chat persistentes o el grupo de servidores de charla persistente.</span><span class="sxs-lookup"><span data-stu-id="2d47f-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="2d47f-106">**Puerto de Chat persistentes**: una propiedad requiere que se defina el puerto número que este servidor de Chat persistentes o grupo persistente Chat Server escuchará en.</span><span class="sxs-lookup"><span data-stu-id="2d47f-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="2d47f-107">**Permitir el cumplimiento**: Active la casilla de verificación si piensa implementar y la función opcional de conformidad Chat persistente y la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2d47f-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="2d47f-108">**Utilice copia de seguridad de SQL Server almacena para permitir una recuperación ante desastres**: seleccione esta casilla si va a implementar y la recuperación de desastres de la persistente de SQL Server de Chat se almacena en un conjunto de copia de seguridad configurado de almacenes en otro SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2d47f-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="2d47f-109">Para obtener información detallada, vea [configurar alta disponibilidad y recuperación ante desastres para el servidor de charla persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="2d47f-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d47f-110">Esta opción solamente está disponible para grupos de servidores con varios servidores.</span><span class="sxs-lookup"><span data-stu-id="2d47f-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="2d47f-111">**Utilizar este grupo como predeterminado para el sitio \<sitio está configurado en este servidor o grupo de\>**: Active esta casilla si va a ser el predeterminado del servidor de charla persistente o grupo de servidor de charla persistente para el sitio.</span><span class="sxs-lookup"><span data-stu-id="2d47f-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="2d47f-112">Debe tener un servidor de Chat persistentes predeterminado o pol por sitio.</span><span class="sxs-lookup"><span data-stu-id="2d47f-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d47f-113">Si la topología incluye varios sitios, también aparecerá una casilla **Usar este grupo como predeterminado para todos los sitios**.</span><span class="sxs-lookup"><span data-stu-id="2d47f-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="2d47f-114">Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="2d47f-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="2d47f-115">Haga clic en **siguiente** cuando haya terminado de especificar las opciones para este grupo continuar con la definición de grupo del servidor de Chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="2d47f-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="2d47f-116">Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir el nuevo grupo de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="2d47f-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="2d47f-117">Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.</span><span class="sxs-lookup"><span data-stu-id="2d47f-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2d47f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d47f-118">See also</span></span>

#### 

[<span data-ttu-id="2d47f-119">Plan para el servidor de charla persistente en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2d47f-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="2d47f-120">Agregar servidor de Chat persistentes a su Skype para la topología de servidor de negocios 2015</span><span class="sxs-lookup"><span data-stu-id="2d47f-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

