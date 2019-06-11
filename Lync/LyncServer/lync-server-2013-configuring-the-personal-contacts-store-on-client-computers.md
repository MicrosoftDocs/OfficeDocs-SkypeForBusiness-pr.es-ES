---
title: 'Lync Server 2013: configuración del almacén de contactos personales en equipos cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4f9b7bbb50b5e63e87904d29a01715fcdcac8c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Configurar el almacén de contactos personales en equipos cliente para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Si está integrando Microsoft Lync Server 2013 y Microsoft Exchange Server 2013, le recomendamos que configure el almacén de contactos personal en cualquier equipo cliente que ejecute Microsoft Lync 2010. En concreto, debe configurar Lync para usar Exchange como el almacén de contactos personal y, al mismo tiempo, asegurarse de que los usuarios no pueden reemplazar esta decisión. Puede hacerlo creando y configurando un valor del Registro en cada equipo cliente.

Tenga en cuenta que esto no es necesario en equipos que ejecutan Lync 2013.

Para configurar este valor en un solo equipo, siga este procedimiento:

1.  En el equipo cliente, haga clic en **Inicio** y en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar**, escriba "regedit" y después presione ENTRAR.

3.  En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **software**, expanda **directivas**, expanda **Microsoft**y, a continuación, expanda **Communicator**.

4.  Haga clic con el botón secundario en **Communicator**, seleccione **Nuevo** y, a continuación, haga clic en **Valor DWORD (32 bits)**.

5.  Tras crear el nuevo valor, escriba **PersonalContactStoreOverride** y presione ENTRAR para cambiar el nombre del valor.

6.  Compruebe que el valor de PersonalContactStoreOverride es 0 y, a continuación, cierre el Editor del Registro.

Si necesita realizar este procedimiento en más de un equipo, cree un objeto Directiva de grupo personalizado. Para obtener más información, consulte la documentación de [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)Directiva de grupo en.

</div>

<span> </span>

</div>

</div>

</div>

