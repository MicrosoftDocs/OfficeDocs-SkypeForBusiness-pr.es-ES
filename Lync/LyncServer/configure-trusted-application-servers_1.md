---
title: Configurar servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b28002e8bb060e9ac966121a419d8475b4828258
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Configurar servidores de aplicaciones de confianza

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza después de combinar la topología heredada de Office Communications Server con Lync Server 2013 y define un nuevo servidor de aplicaciones de confianza con el generador de topología, debe configurar el grupo de próximos saltos para que sea un Grupo 2013 de Lync Server. En un entorno combinado, tanto el grupo heredado de Office Communications Server como el grupo de servidores Lync Server 2013 aparecen en la lista desplegable. *No* se puede seleccionar el grupo heredado.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>Para seleccionar Lync Server 2013 como próximo salto al crear un servidor de aplicaciones de confianza

1.  Abra una topología existente en el generador de topología.

2.  En el panel izquierdo, haga clic con el botón secundario en **servidores de aplicaciones de confianza** y haga clic en **nuevo grupo de aplicaciones de confianza**.

3.  Escriba el **FQDN del grupo** del grupo de aplicaciones de confianza y seleccione si será una implementación de servidor único o de varios servidores.

4.  Haga clic en **Siguiente**.

5.  En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end de Lync Server 2013.
    
    ![Cuadro de diálogo definir nuevo grupo de aplicaciones de confianza] (images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo de aplicaciones de confianza")  

6.  Haga clic en **Finalizar**.

7.  Seleccione el nodo superior de **Lync Server** y, en el panel **acciones** , seleccione **publicar**.

8.  Compruebe que el **grupo de aplicaciones de confianza** se creó correctamente y que está asociado con el grupo de servidores front-end correcto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

