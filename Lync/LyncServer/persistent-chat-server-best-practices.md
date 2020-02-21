---
title: Procedimientos recomendados del servidor de chat persistente
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
ms.openlocfilehash: b613e3ce5c70b9bad7de2ef821d1e0f41e27b956
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>Procedimientos recomendados del servidor de chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

A medida que crea categorías y salones de chat persistente, y diseña el ámbito y la pertenencia, las siguientes sugerencias pueden ayudarle a planear:

  - Si la compañía no necesita la imposición de zonas de protección de datos confidenciales y no está concediendo acceso a usuarios federados, no limite el ámbito en el árbol de categorías. Ponga a todos los usuarios en el ámbito de la categoría raíz y cree todos los salones de chat en dicha categoría. Después, utilice únicamente las listas de pertenencia para conceder o restringir el acceso a cada salón de chat.

  - En la mayoría de casos, deberá habilitar a los usuarios para crear nuevos salones de chat, para que se puedan iniciar debates sobre temas nuevos en cualquier momento. Para ello, haga que la lista **Creators** sea la misma que la lista de **AllowedMembers**. Ahora bien, si desea que un solo equipo de soporte técnico central o usuarios designados puedan crear salones, convierta la lista **Creators** en el subconjunto apropiado.

  - Proporcione a cada salón de chat un nombre completo y un resumen de temas que lo ubique totalmente dentro de la organización. Como los usuarios no verán el nombre de categoría cuando usen el salón de chat, no puede basarse en el nombre de categoría para ayudar a los usuarios a ver lo que está previsto debatirse en el salón de chat.

  - Probablemente quiera tener un flujo de trabajo de creación de salones personalizado si desea implementar determinadas convenciones de nomenclatura o validaciones. La configuración de chat persistente permite personalizar el **RoomManagementUrl** en algo que hospede. Por ejemplo, cuando los usuarios hacen clic en **crear una sala** en su cliente de Lync, pueden redirigirse a su solución personalizada.

  - Cree varios complementos para que le sea más fácil mejorar la experiencia de los salones de chat incorporando datos de negocio a los salones de chat. Los administradores deben registrar los complementos que desean permitir en el sistema. Los creadores y los administradores de salones de chat pueden elegir en una lista de complementos permitidos aquellos complementos que sean más adecuados para sus respectivos salones.

<div>

## <a name="see-also"></a>Consulta también


[Administrar categorías, salones y complementos en Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

