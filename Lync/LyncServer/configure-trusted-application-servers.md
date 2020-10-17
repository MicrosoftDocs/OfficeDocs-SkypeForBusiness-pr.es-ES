---
title: Configuración de servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 664adfc18709a5976465548d326d2d7f4e79c468
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503297"
---
# <a name="configure-trusted-application-servers"></a>Configuración de servidores de aplicaciones de confianza

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-11_

En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe establecer el grupo de servidores del próximo salto como un grupo de servidores de Lync Server 2013. En un entorno mixto, tanto el grupo de servidores de Lync Server 2010 y el grupo de servidores de Lync Server 2013 aparecen en la lista desplegable. No se admite la selección del grupo heredado.

**Seleccione Lync Server 2013 como próximo salto al crear un servidor de aplicaciones de confianza**

1.  Abra el Generador de topologías.

2.  En el panel izquierdo, haga clic con el botón secundario en **Servidores de aplicaciones de confianza** y, a continuación, en **Nuevo grupo de aplicaciones de confianza**.

3.  Escriba el **FQDN del grupo de servidores** correspondiente al grupo de aplicaciones de confianza y seleccione si se tratará de un servidor único o de varios servidores.

4.  Haga clic en **Siguiente**.

5.  En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end 2013 de Lync Server.

6.  Haga clic en **Finalizar **.

7.  Seleccione el nodo superior **Lync Server** y, a continuación, en el menú **Acción**, seleccione **Publicar**.
    
    Compruebe que se ha creado el **Grupo de aplicaciones de confianza** y que está asociado correctamente con el grupo de servidores front-end correcto.

</div>

<span> </span>

</div>

</div>

</div>

