---
title: Migrar los números de acceso telefónico
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86db6e669fd5f52827591c25e5bb237bd9ee012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Migrar los números de acceso telefónico

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

La migración de números de acceso telefónico local requiere dos pasos: ejecutar el cmdlet **Import-CsLegacyConfiguration** (completado anteriormente en [importar directivas y configuración](import-policies-and-settings.md)) para migrar los planes de marcado y otras opciones de números de acceso telefónico local, y ejecutar el ** Cmdlet Move-CsApplicationEndpoint** para migrar los objetos de contacto.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>Para migrar los números de acceso telefónico local

1.  Abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  En el árbol de consola, haga clic con el botón secundario en el nodo bosque, haga clic en **propiedades**y, después, en **propiedades del operador de conferencia**.

3.  En la ficha **números de teléfono de Access** , haga clic en **servicio por grupo** de servidores para ordenar los números de teléfono de acceso por su grupo asociado e identifique todos los números de acceso para el grupo desde el que va a migrar.

4.  Para identificar el URI del SIP para cada número de acceso, haga doble clic en el número de acceso para abrir el cuadro de diálogo **Editar número del operador de conferencia** y busque en **URI del SIP**.

5.  Abra el shell de administración de Lync Server.

6.  Para mover cada número de acceso de acceso telefónico local a un grupo hospedado en Lync Server 2013, ejecute:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  En la herramienta administrativa de Office Communications Server 2007 R2, en la ficha **números de teléfono de Access** , compruebe que no quedan números de acceso telefónico local para el grupo de Office Communications Server 2007 R2 del que va a migrar.

</div>

</div>

<span> </span>

</div>

</div>

</div>

