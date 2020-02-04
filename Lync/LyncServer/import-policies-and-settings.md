---
title: Importar directivas y configuración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f8023f917e3da6757ce27ede44a63cf0ab1a08d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>Importar directivas y configuración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Después de combinar la información de topología de Office Communications Server 2007 R2 con el grupo piloto de Lync Server 2013, tendrá que ejecutar un cmdlet del shell de administración de Lync Server 2013 para migrar las directivas de Office Communications Server 2007 R2 y la configuración de configuración al grupo de pruebas piloto de Lync Server 2013.

El cmdlet **Import-CsLegacyConfiguration** importa directivas, rutas de voz, planes de marcado, direcciones URL de Communicator Web Access y números de acceso telefónico local a Lync Server 2013.

<div>

## <a name="to-migrate-policies-and-settings"></a>Para migrar directivas y configuraciones

1.  En el servidor front-end de Lync Server 2013, inicie el shell de administración de Lync Server.

2.  En la línea de comandos, escriba:
    
        Import-CsLegacyConfiguration
    
    Una vez importadas las directivas, siga el procedimiento que se indica a continuación para ver las directivas importadas en el panel de control de Lync Server.

</div>

<div>

## <a name="to-view-imported-policies"></a>Para ver las directivas importadas

1.  Abra el panel de control de Lync Server 2013.

2.  Haga clic en **enrutamiento de voz** y vea las directivas importadas.

3.  Haga clic en **Conferencia** y vea las directivas importadas.

4.  Haga clic en **Federación y acceso externo** , y vea las directivas importadas.

5.  Haga clic en **supervisión y archivado** y vea las directivas importadas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

