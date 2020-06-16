---
title: Uso de categorías para administrar el servidor de chat persistente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73801c006f7ef5487960628d0f981809cdfd2d38
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>Uso de categorías para administrar el servidor de chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-01_

La implementación del servidor de chat persistente puede hospedar muchos salones de chat persistente simultáneos. Los salones de chat se pueden organizar en un conjunto de categorías en el servidor. Cada salón de chat pertenece a una categoría, y hereda alguna configuración de esa categoría. Esta configuración crea una estructura útil para identificar conversaciones, en función de su propósito empresarial, y facilita la delegación y simplificación de la administración.

<div>


> [!NOTE]  
> Aunque muchas de las características de administración de los salones de chat están disponibles en los equipos que ejecutan chat persistente (cliente de Lync) para el usuario, los administradores de chat persistente (en el rol <STRONG>cspersistentchatadministrator</STRONG> ) deben usar el panel de control de Lync Server o los cmdlets de Windows PowerShell para crear o administrar categorías.



</div>

Los administradores de chat persistente usan el panel de control de Lync Server o los cmdlets de Windows PowerShell para crear y administrar categorías, así como para diseñar el acceso para los salones de chat para los usuarios de su organización.

Los administradores de salones de chat persistente, que tienen la capacidad de administrar uno o más salones de chat, pueden usar el cliente de Lync para iniciar una aplicación Web de administración de salas para crear y administrar salones (o los clientes pueden crear soluciones personalizadas y flujos de trabajo que se invocarán). Los administradores de chat persistente también pueden usar el panel de control de Lync Server o los cmdlets de Windows PowerShell para crear y administrar salones.

<div>


> [!NOTE]  
> Un salón de chat persistente no puede tener el mismo nombre que una categoría de chat persistente.



</div>

Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:

  - Deshabilitar un salón de chat

  - Cambiar el nombre de un salón de chat

  - Cambiar la descripción de un salón de chat

  - Cambiar el tipo de salón de chat (Auditorio o Normal)

  - Cambiar la privacidad de un salón (abierto/cerrado/secreto)

  - Agregar o quitar miembros

  - Agregar o quitar administradores de salones de chat

  - Agregar o quitar un complemento

  - Cambiar configuración, como invitaciones (según lo que permite la categoría)

<div>

## <a name="delegated-administration"></a>Administración delegada

La creación y administración de salones de chat persistente es mucho más sencilla con el uso correcto de las categorías. Un administrador de chat persistente puede definir **miembros permitidos** y **creadores** para cada categoría y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salones de chat creados en la categoría. Los administradores de chat persistente crean y administran categorías mediante el panel de control de Lync Server o los cmdlets de Windows PowerShell.

Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category. After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.

Los salones de chat que se crean en una categoría respetan las directivas y la configuración que exige la categoría (por ejemplo, quién puede estar en la pertenencia de la sala, quién puede administrar el salón, si se permiten las cargas de archivos, si se envían invitaciones, etc.).

</div>

</div>

<span> </span>

</div>

</div>

</div>

