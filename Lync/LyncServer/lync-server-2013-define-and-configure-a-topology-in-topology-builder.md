---
title: 'Lync Server 2013: definir y configurar una topología en el generador de topologías'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aa4a2c12771adf41972fc0c69222935d6935570
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504607"
---
# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>Definir y configurar una topología en el generador de topologías para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Ejecutar el generador de topologías para definir una nueva topología o modificar una topología existente no requiere la pertenencia a un grupo de dominio con privilegios o de administrador local. El generador de topología le guía por los pasos necesarios para definir la topología de un grupo de servidores front-end Enterprise Edition o Standard Edition, según los requisitos de configuración.

Debe usar el generador de topologías para completar y publicar la topología antes de poder instalar Lync Server 2013 en los servidores. En el siguiente procedimiento se indican los pasos necesarios para definir una nueva topología.

<div>

## <a name="to-define-a-topology"></a>Para definir una topología

1.  Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.

2.  En generador de topologías, seleccione **nueva topología**. Se le pedirá que elija una ubicación y un nombre de archivo para guardar la topología. Asigne un nombre descriptivo al archivo de topología y acepte la extensión predeterminada de .tbxml. Haga clic en **Aceptar**.

3.  Vaya a la ubicación donde desea guardar el nuevo archivo XML de topología, especifique un nombre para el archivo y haga clic en **Guardar**.

4.  En la página **Definir el dominio principal**, escriba el nombre del dominio SIP principal de la organización y, a continuación, haga clic en **Siguiente**.

5.  En la página **Especificar dominios admitidos adicionales**, especifique el nombre de los dominios adicionales, si los hay, y haga clic en **Siguiente**.

6.  En la página **Definir el primer sitio**, escriba un nombre y una descripción para el primer sitio y haga clic en **Siguiente**.

7.  En la página **Especificar detalles del sitio**, escriba la información de ubicación del sitio y, a continuación, haga clic en **Siguiente**.

8.  En la página **nueva topología definida correctamente** , asegúrese de que esté activada la casilla **abrir el Asistente para nuevo front-end cuando se cierre este asistente** y, a continuación, haga clic en **Finalizar**.

Una vez que haya definido y guardado la topología, use el Asistente para nuevo servidor front-end con el fin de definir un grupo de servidores front-end o un servidor Standard Edition para el sitio. Para obtener más información, consulte [definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

