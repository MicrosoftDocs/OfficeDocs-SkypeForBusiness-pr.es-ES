---
title: Descargar una topología desde una implementación existente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26c47e6d78d3bd9522b8f0369924f05f8f939037
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>Descargar una topología desde una implementación existente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-29_

Al crear un grupo de servidores de Lync Server 2013, usará el almacén de administración central asociado a Lync Server 2010. Al iniciar el generador de topología en el primer uso y en sesiones de edición posteriores, se le pedirá la ubicación en la que desea que el generador de topología cargue el documento de configuración actual. Puesto que ya tiene una topología de Lync Server 2010 definida y ha establecido el almacén de administración central, debe elegir descargar una topología de una implementación existente. El generador de topología leerá la base de datos y recuperará la definición actual.

**Para descargar una topología de una implementación existente**

1.  Abra el **Asistente para la implementación de Lync Server**.

2.  En la página de **Lync Server 2013: Asistente para la implementación** , haga clic en **instalar herramientas administrativas**.

3.  Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013** y, a continuación, haga clic en **generador de topología de Lync Server**.

4.  Seleccione **Descargar topología de la implementación existente**.
    
    ![Configuración del generador de topología del Asistente para la implementación] (images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Configuración del generador de topología del Asistente para la implementación")

5.  Elija un nombre de archivo y guarde la topología con el tipo de archivo default. tbxml.

6.  Expanda el nodo de Lync Server, como se muestra a continuación, para mostrar los distintos roles de servidor en la implementación.
    
    ![Propiedades generales de roles del servidor del generador] de topologías (images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Propiedades generales de roles del servidor del generador") de topologías

</div>

<span> </span>

</div>

</div>

</div>

