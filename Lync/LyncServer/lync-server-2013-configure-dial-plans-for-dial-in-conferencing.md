---
title: 'Lync Server 2013: Configurar planes de marcado para las conferencias de acceso telefónico local'
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
ms.openlocfilehash: 544c431257dea20db729e80dd1d9acc565da8201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-25_

Al implementar la conferencia de acceso telefónico local, tiene que crear o modificar uno o más planes de marcado para enrutar números de teléfono de acceso telefónico local. Asegúrese de que al menos una regla de normalización de cada plan de marcado convierte las extensiones telefónicas en números de teléfono completos en formato E. 164. Los usuarios de la conferencia de acceso telefónico local se unen a las conferencias como usuarios de empresa autenticados al escribir su número de identificación personal (PIN) y su número de teléfono. Necesita una regla de normalización para convertir las extensiones en números de teléfono completos, de modo que los usuarios puedan autenticarse cuando solo introduzcan una extensión telefónica.

Para configurar planes de marcado para conferencias de acceso telefónico local, haga lo siguiente:

  - Tanto si implementa la Telefonía IP empresarial como si no, modifique el plan de marcado global para agregar una región de conferencia de acceso telefónico local y para garantizar que una regla de normalización convierta de forma precisa los números de acceso telefónico. Para obtener instrucciones detalladas, vea [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Si no implementó la Telefonía IP empresarial, cree planes de marcado para los números de acceso a conferencias de acceso telefónico local. Recuerde incluir una región de conferencia de acceso telefónico local. Para obtener instrucciones detalladas, consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Si ha implementado la Telefonía IP empresarial, modifique los planes de marcado de la Telefonía IP empresarial según sea necesario para incluir regiones y usar las reglas de normalización pertinentes para los números de acceso telefónico. Para obtener instrucciones detalladas, vea [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md). También puede crear planes de marcado dedicados que solo se usarán para números de acceso telefónico. Para obtener instrucciones detalladas, consulte [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Para obtener más información acerca de las regiones de planeación, consulte [requisitos de conferencias de acceso telefónico local en Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) en la documentación de planeación.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Ver información de un plan de marcado en Lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Definir las reglas de normalización en Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

