---
title: 'Lync Server 2013: configurar planes de marcado para conferencias de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a86bf3061c714089ee326a729d0dd43ef267b8e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

Al implementar la Conferencia de acceso telefónico local, debe crear o modificar uno o más planes de marcado para enrutar números de teléfono de acceso telefónico. Asegúrese de que al menos una regla de normalización en cada plan de marcado convierte las extensiones telefónicas en números de teléfono completos en formato E. 164. Los usuarios de conferencias de acceso telefónico local se unen a conferencias como usuarios empresariales autenticados introduciendo su número de identificación personal (PIN) y su número de teléfono. Necesita una regla de normalización para convertir las extensiones en números de teléfono completos para que los usuarios se puedan autenticar cuando entren solo una extensión telefónica.

Para configurar planes de marcado para las conferencias de acceso telefónico local, haga lo siguiente:

  - Independientemente de si implementa la telefonía IP empresarial, modifique el plan de marcado global para agregar una región de conferencia de acceso telefónico local y asegurarse de que una regla de normalización convierta con precisión los números de acceso telefónico. Para obtener instrucciones detalladas, consulte [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Si no implementó la telefonía IP empresarial, cree planes de marcado para los números de acceso de conferencia de acceso telefónico local. Asegúrese de incluir una región de conferencia de acceso telefónico local. Para obtener instrucciones detalladas, consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Si ha implementado Enterprise Voice, modifique los planes de marcado de Enterprise Voice según sea necesario para incluir regiones y usar las reglas de normalización adecuadas para los números de acceso telefónico. Para obtener instrucciones detalladas, consulte [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md). También puede crear planes de marcado dedicados que solo se usan para números de acceso telefónico local. Para obtener instrucciones detalladas, consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Para obtener más información sobre las regiones de planeación, consulte [requisitos de conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) en la documentación referente a la planeación.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Ver información de plan de marcado en Lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Definición de reglas de normalización en Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

