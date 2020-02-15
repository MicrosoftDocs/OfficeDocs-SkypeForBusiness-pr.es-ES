---
title: Migrar los números de acceso telefónico
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15ee86d78b75fe1928cb92459f8689aea2f6b1b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Migrar los números de acceso telefónico

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-26_

La migración de los números de acceso telefónico local requiere dos pasos: ejecutar el cmdlet **Import-CsLegacyConfiguration** (completado anteriormente en [importar directivas y configuración](import-policies-and-settings.md)) para migrar los planes de marcado y otras opciones de números de acceso telefónico y ejecutar el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto.

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>Para migrar los números de acceso telefónico

1.  Abra la herramienta administrativa de Office Communications Server 2007 R2.

2.  En el árbol de consola, haga clic con el botón secundario en el nodo del bosque, haga clic en **Propiedades** y, a continuación, haga clic en **Propiedades de operador de conferencia**.

3.  En la ficha **Números de teléfono de acceso**, haga clic en **Servido por grupo de servidores** para ordenar los números de teléfono de acceso por su grupo asociado e identificar todos los números de acceso para el grupo del que está migrando.

4.  Para identificar el URI del SIP para cada número de acceso, haga doble clic en el número de acceso para abrir el cuadro de diálogo **Editar número de operador de conferencia** y busque en **URI del SIP**.

5.  Abra el Shell de administración de Lync Server.

6.  Para mover cada número de acceso telefónico a un grupo hospedado en Lync Server 2013, ejecute:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  En la herramienta administrativa de Office Communications Server 2007 R2, en la pestaña **números de teléfono de acceso** , compruebe que no quedan números de acceso telefónico para el grupo de Office Communications Server 2007 R2 desde el que va a migrar.

</div>

</div>

<span> </span>

</div>

</div>

</div>

