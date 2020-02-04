---
title: Introducción a la pertenencia al chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b4eb5fbe4342c1bd6bcb3bbb842e076e5863ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>Introducción a la pertenencia al chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

El acceso de usuarios a salas de chat persistentes lo administran los miembros. los usuarios deben ser miembros de un salón de chat para poder publicar y leer mensajes. Solo los **moderadores** que tienen una afiliación designada con salones de chat pueden usar la **publicación en salas de Auditorio**. Un auditorio es un tipo de salón de chat (el otro es **normal**), en el que solo los moderadores pueden publicar y cualquier persona puede leer.

Además, los salones de chat persistente funcionan conforme a las normas de una categoría. Para obtener más información acerca de las categorías, vea [administrar categorías, salas y complementos en Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), así como las secciones "Cómo funciona el ámbito de la categoría" y "estrategias de categorías de sala" más adelante en este tema.

Un administrador de chat persistente puede crear y administrar categorías de salones de chat. Como parte de la creación y administración de categorías de salones de chat, el administrador de chat persistente puede configurar principales (grupos de servicios de dominio de Active Directory, contenedores y usuarios) que tienen acceso a miembros o creadores de salones de chat de una determinada categoría.

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Servicios de dominio de Active Directory y chat persistente

El servidor de chat persistente depende de Active Directory para el grupo de usuarios internos de la conversación persistente. Después de instalar chat persistente (cliente), puede agregar dominios de usuarios y grupos de usuarios a la categoría sala. Después, puede agregar estos usuarios y grupos a la pertenencia de las categorías de su sala.

<div>


> [!IMPORTANT]  
> Debes asegurarte de que no haya nombres duplicados para los usuarios que deseen realizar cambios en sus salones de chat persistentes. Si existen nombres de usuario duplicados, cámbielos por otros nombres para desbloquear a los usuarios para que no realicen esos cambios. Si un usuario tiene nombres duplicados en Active Directory e intenta realizar cambios en sus salas, aparece un mensaje de error que solicita al usuario que se ponga en contacto con el administrador para que lo resuelva.



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>Cómo funciona el ámbito de la categoría

Una categoría especifica todos los usuarios y grupos que pueden ser miembros de una lista de miembros de un salón de chat persistente en esa categoría, en función de su propiedad **AllowedMembers** . Por ejemplo, si establece la **AllowedMembers** de la categoría en contoso.com, puede agregar cualquier grupo o usuario de *contoso* como miembro a los salones de chat de esa categoría. Si establece las **AllowedMembers** en una categoría para las *ventas*, solo se pueden agregar grupos y usuarios de esta lista de distribución como miembros de los salones de chat de esa categoría. De forma similar, la propiedad **Creators** te permite controlar quién puede crear salones de chat en esa categoría. Una vez que se crea el salón de chat, cualquier persona del grupo **AllowedMembers** se puede designar como **Administrador** para las operaciones de administración continuas en las salas (por ejemplo, cambios de miembros y aprobaciones).

La definición de **AllowedMembers** y **creadores** de una categoría tiene las siguientes ventajas:

  - Todos los salones de chat de esta categoría están vinculados por las restricciones establecidas en el nivel de categoría. Puedes usarlo para separar los salones de chat según las necesidades empresariales y las políticas de acceso.

  - Un usuario que se encuentra en la lista de **creadores** puede crear nuevos salones de chat en esa categoría. Si desea implementar un sistema en el que un número restringido de personal de la organización puede crear salones de chat, este control se puede usar para cumplir con ese requisito.

</div>

<div>

## <a name="room-category-strategies"></a>Estrategias de categoría de sala

El **AllowedMembers** de una categoría debe incluir todos los usuarios que usarán cualquier salón de chat persistente en esta categoría. En función de sus requisitos para proteger los datos empresariales y garantizar el nivel adecuado de acceso, es posible que desee definir una o más categorías para especificar quién puede buscar y participar en salas. Si desea permitir que solo un conjunto de usuarios determinado (un helpdesk central o solo empleados de tiempo completo) creen salas, puede definir el ámbito de los **creadores** de una categoría para satisfacer ese requisito.

Las categorías también se pueden usar para crear paredes éticas. Las paredes éticas evitan conflictos de intereses en una organización. Por ejemplo, un administrador puede crear salones de chat en una categoría solo para operadores, mientras que los salones de chat de otra categoría solo pueden ser usados por analistas.

<div>


> [!NOTE]  
> En Lync Server 2013, el servidor de chat persistente no es compatible con el acceso a usuarios federados. Si hay chats de usuarios federados en versiones anteriores de un servidor de chat persistente, se migrarán. Los usuarios federados se agregan como principales deshabilitados.



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>Restringir los miembros a grupos de usuarios

Cuando agregue un dominio a una categoría, los grupos de usuarios cuyos objetos de grupo están disponibles en ese dominio estarán disponibles para que pueda especificarlos como miembros de las salas de esa categoría.

Como regla general, le recomendamos que use contenedores de Active Directory, como dominios y unidades organizativas, para definir el **AllowedMembers** y los **creadores**de una categoría. Puede agregar objetos desde cualquier dominio a una lista de **AllowedMembers** o **creadores** . Solo se pueden agregar a las habitaciones de esa categoría los objetos de la lista **AllowedMembers** o **creadores** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

