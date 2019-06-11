---
title: 'Lync Server 2013: Definición de los requisitos para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68f9195a91a4f8334933d1fce7ffd3a5dceb564c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Definición de los requisitos de la organización para el servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-15_

Antes de implementar un servidor de chat persistente para su organización, es esencial que considere las siguientes preguntas clave para optimizar la implementación:

  - ¿Quién (Perfil de usuario) debe estar habilitado para el servidor de chat persistente? El servidor de chat persistente está habilitado por una directiva que se puede establecer en un nivel global, de sitio, de grupo o de usuario.

  - ¿Cuántos usuarios deben estar habilitados para el servidor de chat persistente? El servidor de chat persistente admite usuarios de 150.000 aprovisionados (habilitados por la Directiva) y un máximo de 80.000 usuarios simultáneos que usen el servidor de chat persistente. Un único servidor de chat persistente puede admitir 20 000 usuarios conectados y un único grupo de servidores de chat persistente puede tener hasta 4 servidores activos para un total de 80 000 usuarios conectados de forma simultánea.

  - ¿Va a migrar desde una versión anterior del servidor de chat de grupo o va a implementar un servidor de chat persistente por primera vez?

  - ¿Hay requisitos de cumplimiento? El servidor de chat persistente admite el cumplimiento. El servicio de cumplimiento se ejecuta en el servidor front-end del servidor de chat persistente, a diferencia del requisito de un equipo independiente en las implementaciones anteriores del servidor de chat de grupo. El cumplimiento es opcional y, si se elige, requiere una base de datos de cumplimiento que se debe configurar para almacenar los datos y eventos de cumplimiento. Es posible que también desee configurar un adaptador para que tome los datos de la base de datos de cumplimiento y los convierta a otro formato (como archivos XML o archivos hospedados por Exchange).

  - ¿Cómo desea controlar los ámbitos, los límites éticos y el acceso? Puede definir **categorías** para separar estos límites y elegir quién está permitido en las salas que se crean en cada una de estas categorías.

  - ¿Cómo desea controlar quién puede crear salones? Puede configurar **creadores**, según sus categorías, que puedan crear salas. Los creadores pueden asignar otros miembros como **administradores del salón de chat** para la administración continua de las salas (agregando o quitando miembros adicionales), según el ámbito de **AllowedMembers/DeniedMembers** configurado por la categoría.

  - ¿Cómo desea crear salas? El servidor de chat persistente proporciona una característica basada en la web para la creación y administración de salas. Esto se puede iniciar desde el cliente de Lync 2013. Puede definir una solución personalizada (mediante el kit de desarrollo de software (SDK) del servidor de chat persistente) que implementa los requisitos y los flujos de trabajo de su empresa, y configurar el servidor de chat persistente para dirigir a los usuarios a su solución personalizada.

  - ¿Qué tipo de complementos desea suministrar? **** Los complementos mejoran la experiencia en la sala aprovechando el panel de extensibilidad en el cliente de Lync 2013 para proporcionar contexto que sea relevante para el salón. Puede elegir qué complementos generales podrían ser más útiles (por ejemplo, el sitio web de la compañía, los documentos de colaboración interna, etc.). Los directores del salón de chat pueden elegir uno de los complementos registrados y asociarlo a los salones, si así lo desean.

  - ¿Qué tipo de requisitos de alta disponibilidad y recuperación ante desastres tiene? El servidor de chat persistente admite el reflejo de SQL Server y el clúster de SQL Server para ofrecer alta disponibilidad y admite hasta 8 servidores (4 activos y 4 en espera) en un grupo expandido con el trasvase de registros de SQL Server para la recuperación de desastres.

  - ¿Dispone de requisitos de regulación? Si su empresa se encuentra en un país o una región donde los datos deben conservarse dentro del país, es posible que tenga que implementar varios grupos de servidores de chat persistentes, cada uno local en una geografía específica. Un salón, una categoría o un complemento no abarcan agrupaciones: solo pertenece a un grupo de servidores de chat persistente. Puede administrar el conjunto de categorías, complementos y salas para cada grupo de servidores de chat persistente. Los usuarios se pueden configurar para que tengan acceso a salas en uno o más grupos de la categoría AllowedMembers ámbito o ámbito de suscripción de la sala, según el diseño de las categorías.
    
    <div>
    

    > [!IMPORTANT]  
    > Tener varios grupos de servidores de chat persistentes no le da más escala (todavía puede tener solo 80.000 usuarios conectados al mismo tiempo en todos los grupos de servidores de chat persistentes). El motivo principal por el que se admiten varios grupos de servidores de chat persistentes es apoyar problemas normativos.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

