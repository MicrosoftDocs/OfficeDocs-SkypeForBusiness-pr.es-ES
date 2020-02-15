---
title: 'Lync Server 2013: comprobación de la replicación del esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41cb48da1711cfa6eb29a90f19a9b6e42b110c52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Comprobar la replicación de esquemas de Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Antes de ejecutar la preparación del bosque, compruebe manualmente que la partición del esquema se ha replicado.

<div>

## <a name="to-manually-verify-schema-replication"></a>Para comprobar manualmente la replicación del esquema

1.  Inicie sesión en un controlador de dominio como miembro del grupo Administradores de organización.

2.  Abra el Editor ADSI. Para ello, haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, haga clic en **Editor ADSI**.
    
    <div>
    

    > [!TIP]  
    > También puede ejecutar <STRONG>adsiedit.msc</STRONG> en la línea de comandos.

    
    </div>

3.  En el árbol de Microsoft Management Console (MMC), haga clic en **Editor ADSI** si aún no está seleccionado.

4.  En el menú **Acción**, haga clic en **Conectar con**.

5.  En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, a continuación, haga clic en **Aceptar**.

6.  En el contenedor de esquema, busque CN=ms-RTC-SIP-SchemaVersion. Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema se ha actualizado y replicado correctamente. Si este objeto no existe o los valores de los atributos **rangeUpper** y **rangeLower** son distintos de lo que se ha especificado, el esquema no se ha modificado o no se ha replicado.

</div>

<div>

## <a name="see-also"></a>Vea también


[Ejecución de la preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-running-schema-preparation.md)  


[Preparar el esquema de Active Directory en Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

