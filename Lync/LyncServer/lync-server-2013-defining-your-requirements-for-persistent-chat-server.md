---
title: 'Lync Server 2013: definición de los requisitos para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63e7af0dca758f6ac543bb0373d2cbb0d953ba0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504307"
---
# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Definición de los requisitos de la organización para el servidor de chat persistente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-15_

Antes de implementar el servidor de chat persistente en su organización, es fundamental tener en cuenta las siguientes preguntas clave para optimizar la implementación:

  - ¿Quién (Perfil de usuario) debe estar habilitado para el servidor de chat persistente? El servidor de chat persistente está habilitado por una directiva que se puede establecer en un nivel global, de sitio, de grupo o de usuario.

  - ¿Cuántos usuarios deben estar habilitados para el servidor de chat persistente? El servidor de chat persistente admite usuarios aprovisionados de 150.000 (habilitados por directiva) y un máximo de 80.000 usuarios simultáneos que usan el servidor de chat persistente. Un único servidor de chat persistente puede admitir 20.000 usuarios conectados y un solo grupo de servidores de chat persistente puede tener hasta 4 servidores activos para un total de 80.000 usuarios conectados simultáneamente.

  - ¿Va a migrar desde una versión anterior del servidor de chat en grupo o va a implementar el servidor de chat persistente por primera vez?

  - ¿Hay requisitos de cumplimiento? El servidor de chat persistente admite el cumplimiento. El servicio de cumplimiento se ejecuta en el servidor front-end del servidor de chat persistente, en lugar del requisito para un equipo independiente en las implementaciones anteriores del servidor de chat en grupo. El cumplimiento es opcional y si se elige, requiere una base de datos de cumplimiento que debe configurarse para almacenar eventos y datos de cumplimiento. Es posible que también desee configurar un adaptador para que tome los datos de la base de datos de cumplimiento y los convierta a otro formato (como archivos XML o archivos hospedados por Exchange).

  - ¿Cómo desea controlar los ámbitos, los límites éticos y el acceso? Puede definir **Categorías** para segregar estos límites y elegir quién puede estar en salones que se crean en cada una de estas categorías.

  - ¿Qué desea para controlar quién puede crear salones? Puede configurar **Creadores**, correspondientes a las categorías, que pueden crear salones. Los creadores pueden asignar otros miembros como **Administradores de salones de chat** para la administración continua de los salones (agregar o quitar miembros adicionales), según el ámbito de **AllowedMembers/DeniedMembers** configurado por la categoría.

  - ¿Cómo desea crear los salones? El servidor de chat persistente proporciona una característica basada en web para la creación y administración de salas. Puede iniciarse desde el cliente de Lync 2013. Puede definir una solución personalizada (usando el kit de desarrollo de software (SDK) del servidor de chat persistente) que implementa los requisitos de negocio y flujos de trabajo, y configura el servidor de chat persistente para dirigir a los usuarios a la solución personalizada.

  - ¿Qué tipo de complemento desea suministrar? Los **Complementos** mejoran la experiencia en el salón aprovechando el panel de extensibilidad en el cliente de Lync 2013 para proporcionar contexto que sea relevante para el salón. Puede elegir qué complementos generales podrían ser más útiles (por ejemplo, el sitio web de la empresa, los documentos de colaboración interna, etc.). Los administradores del salón de chat pueden elegir uno de los complementos registrados y asociarlo a sus salones, si lo desean.

  - ¿Qué tipo de requisitos de alta disponibilidad y recuperación ante desastres tiene? El servidor de chat persistente admite la creación de reflejos de SQL Server y la agrupación en clústeres de SQL Server para alta disponibilidad y admite hasta 8 servidores (4 activos y 4 en espera) en un grupo extendido con el trasvase de registros de SQL Server para la recuperación ante desastres.

  - ¿Existen requerimientos legales? Si su empresa se encuentra en un país o región en el que los datos deben conservarse dentro del país, es posible que deba implementar varios grupos de servidores de chat persistente, cada uno de ellos local en una ubicación geográfica específica. Un salón, una categoría o un complemento no abarcan grupos; solo pertenece a un grupo de servidores de chat persistente. Puede administrar el conjunto de categorías, complementos y salas para cada grupo de servidores de chat persistente. Los usuarios se pueden configurar para que tengan acceso a los salones de uno o más grupos de servidores mediante el ámbito de categoría miembros permitidos o el ámbito de pertenencia de la sala, en función de cómo diseñe las categorías.
    
    <div>
    

    > [!IMPORTANT]  
    > Tener varios grupos de servidores de chat persistente no le da más escala (todavía puede tener sólo 80.000 usuarios conectados simultáneamente en todos los grupos de servidores de chat persistente). La razón principal para admitir varios grupos de servidores de chat persistente es apoyar las cuestiones regulatorias.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

