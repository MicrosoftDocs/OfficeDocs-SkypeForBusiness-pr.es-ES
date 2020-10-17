---
title: Importación de directivas y parámetros
description: Importar directivas y configuración.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e014b7e8f0498742104118eec9eb313394ae6a94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569036"
---
# <a name="import-policies-and-settings"></a>Importación de directivas y parámetros

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Tras combinar la información de topología de Office Communications Server 2007 R2 con el grupo piloto de Lync Server 2013, debe ejecutar un cmdlet del shell de administración de Lync Server 2013 para migrar las directivas y las opciones de configuración de Office Communications Server 2007 R2 al grupo piloto de Lync Server 2013.

El cmdlet **Import-CsLegacyConfiguration** importa directivas, rutas de voz, planes de marcado, direcciones URL de Communicator Web Access y números de acceso telefónico a Lync Server 2013.

<div>

## <a name="to-migrate-policies-and-settings"></a>Para migrar directivas y configuración

1.  En el servidor front-end de Lync Server 2013, inicie el shell de administración de Lync Server.

2.  Escriba lo siguiente en la línea de comandos:
    
        Import-CsLegacyConfiguration
    
    Una vez importadas las directivas, siga el procedimiento que se indica a continuación para ver las directivas importadas en el panel de control de Lync Server.

</div>

<div>

## <a name="to-view-imported-policies"></a>Par ver directivas importadas

1.  Abra el panel de control de Lync Server 2013.

2.  Haga clic en **Enrutamiento de voz** y vea las directivas importadas.

3.  Haga clic en **Conferencia** y vea las directivas importadas.

4.  Haga clic en **Federación y acceso externo** y vea las directivas importadas.

5.  Haga clic en **Supervisión y archivado** y vea las directivas importadas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

