---
title: Usar categorías para administrar el servidor de chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52e56f776969ece55f71355ed7f184dd6dd46a91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>Usar categorías para administrar el servidor de chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-10-01_

La implementación del servidor de chat persistente puede alojar muchos salones de chat persistentes simultáneos. Los salones de chat pueden estar organizados jerárquicamente en un conjunto de categorías en el servidor. Cada salón de chat pertenece a una categoría y hereda parte de la configuración de dicha categoría. Esta organización crea una estructura útil para identificar conversaciones según el fin del negocio y, asimismo, facilita la delegación y simplificación de la administración.

<div>


> [!NOTE]  
> Aunque muchas de las características de administración de los salones de chat están disponibles en equipos que ejecutan una conversación persistente (cliente de Lync) para el usuario, los administradores de chats persistentes (en el rol <STRONG>cspersistentchatadministrator</STRONG> ) deben usar el panel de control de Lync Server o los cmdlets de Windows PowerShell para crear o administrar categorías.



</div>

Los administradores de chat persistentes usan el panel de control de Lync Server o los cmdlets de Windows PowerShell para crear y administrar categorías, así como para diseñar el acceso a los salones de chat para los usuarios de su organización.

Los administradores de salones de chat persistentes, que tienen la capacidad de administrar una o más salas de chat, pueden usar el cliente de Lync para iniciar una aplicación Web de administración de salas para crear y administrar salas (o para que los clientes puedan crear soluciones personalizadas y flujos de trabajo que se invocarán). Los administradores de chat persistentes también pueden usar el panel de control de Lync Server o los cmdlets de Windows PowerShell para crear y administrar salas.

<div>


> [!NOTE]  
> Un salón de chat persistente no puede tener el mismo nombre que una categoría de chat persistente.



</div>

Los administradores de los salones de chat pueden realizar cambios en todas las propiedades del salón de chat, salvo para cambiar la categoría del salón. No se les puede impedir ejecutar las acciones siguientes:

  - Deshabilitar un salón de chat

  - Cambiar el nombre de un salón de chat

  - Cambiar la descripción de un salón de chat

  - Cambiar el tipo de salón de chat (Auditorio o Normal)

  - Cambiar la privacidad de un salón (abierto, cerrado o secreto)

  - Agregar o quitar miembros

  - Agregar o quitar administradores de salones de chat

  - Agregar o quitar un complemento

  - Cambiar configuraciones como invitaciones (de acuerdo con lo permitido por la categoría)

<div>

## <a name="delegated-administration"></a>Administración delegada

Crear y administrar salones de chat persistentes es mucho más fácil con el uso correcto de categorías. Un administrador de chat persistente puede definir **AllowedMembers** y **creadores** de cada categoría, y también puede definir la configuración y los comportamientos predeterminados del salón de chat que se aplicarán a todos los salones de chat creados en la categoría. Los administradores de chats persistentes crean y administran categorías mediante el panel de control de Lync Server o los cmdlets de Windows PowerShell.

Los usuarios, las unidades organizativas (UO) y los grupos de usuarios que se identifican como creadores de la categoría son los únicos individuos y grupos que pueden crear salones en la categoría. Después de crear la categoría, pueden elegir usuarios, UO y grupos de usuarios en la lista de **miembros permitidos** de la categoría como administradores y miembros del salón de chat para administrar el salón y participar en él.

Los salones de chat creados en una categoría respetan las directivas y la configuración exigidas por la categoría (como quién puede estar en la pertenencia de la sala, quién puede administrar el salón, si se permiten las cargas de archivos, si se han enviado invitaciones, etc.).

</div>

</div>

<span> </span>

</div>

</div>

</div>

