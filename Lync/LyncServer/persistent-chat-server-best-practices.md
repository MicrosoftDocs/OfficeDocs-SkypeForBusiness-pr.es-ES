---
title: Procedimientos recomendados para el servidor de chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 119bc67622928ec2e60f082e72322e7b0b923c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>Procedimientos recomendados para el servidor de chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

A medida que crea las categorías y los salones de chat persistentes, y diseña su alcance y pertenencia, las siguientes sugerencias pueden ayudar a su planeamiento:

  - Si su empresa no requiere una pared ética, no limite el ámbito del árbol de categorías. Coloca a todos los usuarios en el ámbito de una categoría y crea todos los salones de chat en esa categoría. Posteriormente, use solo listas de pertenencia para conceder o restringir el acceso a cada salón de chat.

  - En la mayoría de los casos, debe permitir que los usuarios creen nuevos salones de chat para que las discusiones sobre los nuevos temas se puedan iniciar en cualquier momento. Para ello, la lista de **creadores** es la misma que la lista de **AllowedMembers** . Sin embargo, si desea permitir que solo un equipo de soporte técnico central o usuarios designados creen salas, convierta la lista de **creadores** en el subconjunto correspondiente.

  - Asigne a cada salón de chat un nombre completo y un resumen de descripción que describa Dónde encaja en la organización. Como los usuarios no pueden ver el nombre de la categoría cuando usan el salón de chat, no puede confiar en el nombre de la categoría para ayudar a los usuarios a determinar el foro de discusión previsto para el salón de chat.

  - Es posible que desee tener un flujo de trabajo de creación de salas personalizada si tiene determinadas convenciones de nomenclatura u otros controles de acceso o validaciones para implementar. La configuración de chat persistente le permite personalizar el **RoomManagementUrl** a algo que hospede. Por ejemplo, cuando los usuarios hacen clic en **crear una sala** en su cliente de Lync, pueden redirigirse a la solución personalizada.

  - Cree una variedad de complementos que le ayuden a mejorar la experiencia de los salones de chat aportando otros datos empresariales a salones de chat. Los administradores deben registrar los complementos que desean permitir en el sistema. Los administradores de salones de chat y los creadores pueden elegir en la lista de complementos permitidos para los más importantes para sus respectivos salones.

<div>

## <a name="see-also"></a>Vea también


[Administrar categorías, salones de chat y complementos en Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

