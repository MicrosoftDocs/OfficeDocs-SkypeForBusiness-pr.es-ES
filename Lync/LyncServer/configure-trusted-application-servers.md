---
title: Configurar servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cab126429fc5ec77a2308fdc1e1f8965fdfccb5b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Configurar servidores de aplicaciones de confianza

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-11_

En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe configurar el grupo de próximos saltos para que sea un grupo de servidores de Lync 2013. En un entorno mixto, tanto el grupo heredado de Lync Server 2010 y el grupo de servidores Lync Server 2013 aparecen en la lista desplegable. No se puede seleccionar el grupo heredado.

**Seleccione Lync Server 2013 como próximo salto al crear un servidor de aplicaciones de confianza**

1.  Abra el generador de topologías.

2.  En el panel izquierdo, haga clic con el botón secundario en **servidores de aplicaciones de confianza** y haga clic en **nuevo grupo de aplicaciones de confianza**.

3.  Escriba el **FQDN del grupo** del grupo de aplicaciones de confianza y seleccione si será un servidor único o de varios servidores.

4.  Haga clic en **Siguiente**.

5.  En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end de Lync Server 2013.

6.  Haga clic en **Finalizar**.

7.  Seleccione el nodo superior de **Lync Server** y, en el menú **acción** , seleccione **publicar**.
    
    Compruebe que el **grupo de aplicaciones de confianza** se haya creado correctamente y que esté asociado al grupo de servidores front-end correcto.

</div>

<span> </span>

</div>

</div>

</div>

