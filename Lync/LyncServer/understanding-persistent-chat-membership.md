---
title: Descripción de la pertenencia al chat persistente
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
ms.openlocfilehash: 3cc357eff6cdc68c5285eeb915f5534b6f38b871
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>Descripción de la pertenencia al chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

El acceso de los usuarios a los salones de chat persistente se administra por suscripción; los usuarios deben ser miembros de un salón de chat para poder publicar y leer mensajes. Solo los **moderadores** que tengan una afiliación designada a los salones de chat pueden **publicar en salones de Auditorio**. Un Auditorio es un tipo de salón de chat (el otro es **Normal**), en el que solo los moderadores pueden publicar y todos pueden leer.

Además, los salones de chat persistente funcionan según las reglas de una categoría. Para obtener más información sobre las categorías, vea [administrar categorías, salones y complementos en Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), así como las secciones "Cómo funciona el ámbito de la categoría" y "estrategias de categoría de sala" más adelante en este tema.

Un administrador de chat persistente puede crear y administrar categorías de salones de chat. Como parte de la creación y la administración de categorías de salones de chat, el administrador de chat persistente puede configurar entidades de identidad (grupos de servicios de dominio de Active Directory, contenedores y usuarios) que tienen acceso a miembros o creadores de salones de chat de una categoría determinada.

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Servicios de dominio de Active Directory y chat persistente

El servidor de chat persistente depende de Active Directory para el grupo de usuarios de chat persistente internos. Después de instalar chat persistente (cliente), puede agregar dominios de usuarios y grupos de usuarios a la categoría de salón. Puede agregar estos usuarios y grupos a la pertenencia de las categorías de salón.

<div>


> [!IMPORTANT]  
> Debe asegurarse de que no haya nombres duplicados para los usuarios que deseen realizar cambios en sus salones de chat persistente. Si hubiera nombres de usuario duplicados, cámbielos por nombres diferentes para permitir a dichos usuarios realizar cambios. Si un usuario tiene nombres duplicados en Active Directory e intenta realizar cambios en sus salas, aparece un mensaje de error que solicita al usuario que se ponga en contacto con el administrador para que lo resuelva.



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>Funcionamiento del ámbito de categoría

Una categoría especifica todos los usuarios y grupos que pueden ser miembros de una lista de pertenencia de un salón de chat persistente en esa categoría, en función de su propiedad **miembros permitidos** . Por ejemplo, si establece el **miembros permitidos** de la categoría en contoso.com, puede agregar cualquier grupo o usuario de *contoso* como miembro a los salones de chat de esa categoría. Si establece el valor de **AllowedMembers** de una categoría en *Sales*, solo los grupos y usuarios de esta lista de distribución se pueden agregar como miembros a los salones de chat de esa categoría. De forma similar, la propiedad **Creators** permite controlar quién puede crear salones de chat en esa categoría. Una vez creado el salón de chat, todos los miembros del grupo **AllowedMembers** pueden designarse como **Administrator** para las operaciones de administración continuadas en los salones (por ejemplo, cambios y aprobaciones de pertenencia como miembro).

Definir **AllowedMembers** y **Creators** para una categoría tiene las siguientes ventajas:

  - Todos los salones de chat de esta categoría se rigen por las restricciones establecidas en el nivel de la categoría. Puede usarlo para segregar salones de chat en función de las necesidades empresariales y las directivas de acceso.

  - Un usuario de la lista **Creators** puede crear nuevos salones de chat en esa categoría. Si quiere implementar un sistema en el que un número restringido de personal de la organización pueda crear salones de chat, se puede usar este control para cumplir ese requisito.

</div>

<div>

## <a name="room-category-strategies"></a>Estrategias de categoría de salón

El **miembros permitidos** de una categoría debe incluir todos los usuarios que usarán cualquier salón de chat persistente en esta categoría. En función de sus requisitos para proteger los datos empresariales y garantizar un nivel de acceso adecuado, quizás quiera definir una o varias categorías para especificar quién puede buscar salones y participar en ellos. Si quiere permitir que solo un conjunto determinado de usuarios (departamento de soporte técnico central o solo empleados a tiempo completo) pueda crear salones, puede definir el ámbito de la lista **Creators** de una categoría para satisfacer ese requisito.

Las categorías también se pueden usar para crear zonas de protección. Las zonas de protección evitan conflictos de intereses en una organización. Por ejemplo, un administrador puede crear salones de chat en una categoría solo para comerciales, mientras que los salones de chat de otra categoría son solo para analistas.

<div>


> [!NOTE]  
> En Lync Server 2013, el servidor de chat persistente no es compatible con el acceso a usuarios federados. Si hay chats de usuarios federados en versiones anteriores del servidor de chat persistente, se migrarán. Los usuarios federados se agregan como entidades deshabilitadas.



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>Restringir los miembros a grupos de usuarios

Cuando se agrega un dominio a una categoría, los grupos de usuarios cuyos objetos de grupo estén incluidos en dicho dominio estarán disponibles para que pueda especificarlos como miembros de los salones de esa categoría.

Como regla general, se recomienda usar contenedores de Active Directory, como dominios y unidades organizativas, para definir **miembros permitidos** y **creadores**de una categoría. Puede agregar objetos de cualquier dominio a una lista **AllowedMembers** o **Creators**. Solo los objetos de la lista **AllowedMembers** o **Creators** se pueden agregar a los salones de esa categoría.

</div>

</div>

<span> </span>

</div>

</div>

</div>

