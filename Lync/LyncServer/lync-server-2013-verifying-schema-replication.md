---
title: 'Lync Server 2013: Comprobar la replicación de esquemas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d115738a4f22cb7795c2eb5a00ac642fbe43fc77
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Comprobar la replicación de esquemas de Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Antes de ejecutar la preparación del bosque, compruebe manualmente que la partición de esquema se ha replicado.

<div>

## <a name="to-manually-verify-schema-replication"></a>Para comprobar manualmente la replicación del esquema

1.  Inicie sesión en un controlador de dominio como miembro del grupo administradores de la empresa.

2.  Abra ADSI Edit haciendo clic en **Inicio**, en **herramientas administrativas**y, a continuación, en **ADSI Edit**.
    
    <div>
    

    > [!TIP]  
    > Como alternativa, puede ejecutar <STRONG>ADSIEdit. msc</STRONG> desde la línea de comandos.

    
    </div>

3.  En el árbol de Microsoft Management Console (MMC), si aún no está seleccionado, haga clic en **ADSI Edit**.

4.  En el menú **Acción**, haga clic en **Conectar con**.

5.  En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, luego, haga clic en **Aceptar**.

6.  En el contenedor de esquema, busque CN=ms-RTC-SIP-SchemaVersion. Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema se ha actualizado y replicado correctamente. Si este objeto no existe o los valores de los atributos **rangeUpper** y **rangeLower** no se especifican, el esquema no se modificó o no se ha replicado.

</div>

<div>

## <a name="see-also"></a>Vea también


[Ejecutar la preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-running-schema-preparation.md)  


[Preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

