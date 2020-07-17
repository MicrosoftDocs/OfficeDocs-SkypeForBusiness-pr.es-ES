---
title: Procedimientos recomendados del servidor de chat persistente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebe9742b76ec6abfd7b7407f38edda937bdf6ecc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="9f86a-102">Procedimientos recomendados del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="9f86a-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f86a-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="9f86a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9f86a-104">A medida que crea categorías y salones de chat persistente, y diseña el ámbito y la pertenencia, las siguientes sugerencias pueden ayudarle a planear:</span><span class="sxs-lookup"><span data-stu-id="9f86a-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="9f86a-p101">Si la compañía no necesita la imposición de zonas de protección de datos confidenciales y no está concediendo acceso a usuarios federados, no limite el ámbito en el árbol de categorías. Ponga a todos los usuarios en el ámbito de la categoría raíz y cree todos los salones de chat en dicha categoría. Después, utilice únicamente las listas de pertenencia para conceder o restringir el acceso a cada salón de chat.</span><span class="sxs-lookup"><span data-stu-id="9f86a-p101">If your company does not require an ethical wall, do not narrow the scope in your category tree. Put all your users in the scope of one category, and create all chat rooms in that category. Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="9f86a-p102">En la mayoría de casos, deberá habilitar a los usuarios para crear nuevos salones de chat, para que se puedan iniciar debates sobre temas nuevos en cualquier momento. Para ello, haga que la lista **Creators** sea la misma que la lista de **AllowedMembers**. Ahora bien, si desea que un solo equipo de soporte técnico central o usuarios designados puedan crear salones, convierta la lista **Creators** en el subconjunto apropiado.</span><span class="sxs-lookup"><span data-stu-id="9f86a-p102">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time. Do this by making the **Creators** list the same as the **AllowedMembers** list. However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="9f86a-p103">Proporcione a cada salón de chat un nombre completo y un resumen de temas que lo ubique totalmente dentro de la organización. Como los usuarios no verán el nombre de categoría cuando usen el salón de chat, no puede basarse en el nombre de categoría para ayudar a los usuarios a ver lo que está previsto debatirse en el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="9f86a-p103">Give each chat room a complete name and description summary that describes where it fits in with your organization. Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="9f86a-113">Probablemente quiera tener un flujo de trabajo de creación de salones personalizado si desea implementar determinadas convenciones de nomenclatura o validaciones.</span><span class="sxs-lookup"><span data-stu-id="9f86a-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="9f86a-114">La configuración de chat persistente permite personalizar el **RoomManagementUrl** en algo que hospede.</span><span class="sxs-lookup"><span data-stu-id="9f86a-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="9f86a-115">Por ejemplo, cuando los usuarios hacen clic en **crear una sala** en su cliente de Lync, pueden redirigirse a su solución personalizada.</span><span class="sxs-lookup"><span data-stu-id="9f86a-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="9f86a-p105">Cree varios complementos para que le sea más fácil mejorar la experiencia de los salones de chat incorporando datos de negocio a los salones de chat. Los administradores deben registrar los complementos que desean permitir en el sistema. Los creadores y los administradores de salones de chat pueden elegir en una lista de complementos permitidos aquellos complementos que sean más adecuados para sus respectivos salones.</span><span class="sxs-lookup"><span data-stu-id="9f86a-p105">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms. Administrators must register the add-ins that they want to allow in the system. Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9f86a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f86a-119">See Also</span></span>


[<span data-ttu-id="9f86a-120">Administrar categorías, salones y complementos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f86a-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

