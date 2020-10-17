---
title: Cambiar las rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34c4ea975225eb685acaa1843e324ffa720a93e9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499667"
---
# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>Cambiar las rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Con este procedimiento se cambian las rutas de voz para usar el servidor de mediación de Lync Server 2013, en lugar del servidor de mediación de Office Communications Server 2007 R2 heredado.

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>Para cambiar las rutas de voz para usar el nuevo servidor de mediación

1.  Panel de control de Lync Server 2013

2.  En el panel izquierdo, seleccione **Enrutamiento de voz** y luego **Ruta**.

3.  Haga clic en **Nueva** para crear una nueva ruta de voz.

4.  Rellene los siguientes campos:
    
      - **Nombre**: escriba un nombre descriptivo de la ruta de voz. En este documento usaremos **W14PSTNRoute**.
    
      - **Descripción**: escriba una breve descripción de la ruta de voz.

5.  Omita todas las secciones restantes hasta llegar a **Puertas de enlace asociadas**. Haga clic en **Agregar **. Seleccione la nueva puerta de enlace predeterminada y haga clic en **Aceptar**.

6.  En **Usos de la RTC asociados**, haga clic en **Seleccionar**.

7.  En la página **Seleccionar registro de uso de RTC**, seleccione un nombre de registro y haga clic en **Aceptar**.

8.  En la página **Nueva ruta de voz**, haga clic en **Aceptar** para crear la ruta**** de voz.

9.  En la página **Enrutamiento de voz**, seleccione **Ruta**.

10. Mueva la ruta que acaba de crear al principio de la lista y seleccione **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

