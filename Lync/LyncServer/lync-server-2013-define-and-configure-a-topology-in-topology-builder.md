---
title: 'Lync Server 2013: Definir y configurar una topología en Topology Builder'
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
ms.openlocfilehash: 876651b0d0c5ed33d4e82429822585de4a2b8579
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>Definir y configurar una topología en Topology Builder para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Al ejecutar el generador de topologías para definir una topología nueva o modificar una topología existente, no es necesario ser miembro de un grupo de dominio de administrador local o privilegiado. El generador de topología le guía a través de los pasos necesarios para definir su topología para un grupo de servidores front-end Enterprise Edition o Standard Edition, en función de los requisitos de configuración.

Debe usar topología Builder para completar y publicar la topología antes de poder instalar Lync Server 2013 en servidores. El procedimiento siguiente incluye los pasos necesarios para definir una nueva topología.

<div>

## <a name="to-define-a-topology"></a>Para definir una topología

1.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.

2.  En el generador de topologías, seleccione **nueva topología**. Se le pedirá una ubicación y un nombre de archivo para guardar la topología. Asigne al archivo de topología un nombre significativo y acepte la extensión predeterminada de. tbxml. Haga clic en **Aceptar**.

3.  Vaya a la ubicación donde desea guardar el nuevo archivo XML de topología, escriba un nombre para el archivo y, a continuación, haga clic en **Guardar**.

4.  En la página **definir el dominio principal** , escriba el nombre del dominio SIP principal de la organización y, a continuación, haga clic en **siguiente**.

5.  En la página **especificar dominios admitidos adicionales** , escriba los nombres de los dominios adicionales, si los hay, y haga clic en **siguiente**.

6.  En la página **definir el primer sitio** , escriba un nombre y una descripción para el primer sitio y, a continuación, haga clic en **siguiente**.

7.  En la página **especificar detalles del sitio** , escriba la información de ubicación del sitio y, a continuación, haga clic en **siguiente**.

8.  En la **nueva topología se definió correctamente** como página, asegúrese de que la casilla **abrir el Asistente para el usuario nuevo al cerrar el asistente** está activada y, a continuación, haga clic en **Finalizar**.

Una vez que haya definido y guardado la topología, use el Asistente para nuevo front-end para definir un grupo de servidores front-end o un servidor Standard Edition para el sitio. Para obtener más información, vea [definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

