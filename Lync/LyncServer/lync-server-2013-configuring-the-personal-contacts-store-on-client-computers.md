---
title: 'Lync Server 2013: configuración del almacén de contactos personales en equipos cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5672619302e169db5e89281323eec4b5d8312c06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Configuración del almacén de contactos personales en equipos cliente para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Si está integrando Microsoft Lync Server 2013 y Microsoft Exchange Server 2013, se recomienda que configure el almacén de contactos personales en todos los equipos cliente que ejecuten Microsoft Lync 2010. En concreto, debe configurar Lync para usar Exchange como almacén de contactos personales y, al mismo tiempo, asegurarse de que los usuarios no pueden invalidar dicha decisión. Esto puede hacerse creando y configurando un valor del registro en cada equipo cliente.

Tenga en cuenta que esto no es necesario en los equipos que ejecutan Lync 2013.

Para configurar este valor en un solo equipo, siga este procedimiento:

1.  En el equipo cliente, haga clic en **Inicio** y, a continuación, en **Ejecutar**.

2.  En el cuadro de diálogo **Ejecutar**, escriba regedit y, a continuación, presione ENTRAR.

3.  En el editor del registro, expanda el **equipo local\_\_HKEY**, expanda **software**, expanda **directivas**, expanda **Microsoft**y, a continuación, expanda **Communicator**.

4.  Haga clic con el botón secundario en **Communicator**, seleccione **nuevo**y, a continuación, haga clic en **valor DWORD (32-bit)**.

5.  Una vez creado el nuevo valor, escriba **PersonalContactStoreOverride** y, a continuación, presione Entrar para cambiar el nombre del valor.

6.  Compruebe que el valor de PersonalContactStoreOverride es 0 y, a continuación, cierre el Editor del Registro.

Si necesita realizar este procedimiento en más de un equipo, cree un objeto Directiva de grupo personalizado. Para obtener más información, consulte la documentación de [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)la Directiva de grupo en.

</div>

<span> </span>

</div>

</div>

</div>

