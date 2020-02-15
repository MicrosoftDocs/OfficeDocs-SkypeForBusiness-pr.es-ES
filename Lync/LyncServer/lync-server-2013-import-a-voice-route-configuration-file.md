---
title: 'Lync Server 2013: importar un archivo de configuración de enrutamiento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ce270b4321c484b40a20271ad21c2701c749d6a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a>Importar un archivo de configuración de enrutamiento de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Si desea guardar la configuración de enrutamiento de voz sin publicarla, siga estos pasos para usar los comandos exportar e importar de la configuración del panel de control de Lync Server para guardar y recuperar una instantánea de la configuración del enrutamiento de voz. Al importar un archivo de configuración de enrutamiento de voz (. vcfg), pero se han realizado cambios en la configuración del enrutamiento de voz en el servidor mientras tanto, las páginas del grupo de **enrutamiento de voz** del panel de control de Lync Server indicarán que hay cambios no confirmados en el enrutamiento de voz. Estos cambios sin confirmar son distintos entre dos configuraciones que requieren reconciliación.

Si ha realizado cambios no confirmados en la configuración de cualquier página del grupo, los cambios se guardan en el archivo de configuración de voz exportado (. vcfg). Esto le permite realizar cambios en la configuración del enrutamiento de voz durante varias sesiones antes de publicar los cambios.

<div>

## <a name="to-import-a-voice-routing-configuration"></a>Para importar una configuración de enrutamiento de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.

4.  En el menú **acciones** , haga clic en **importar configuración**.

5.  Busque el archivo de configuración que desee importar y, a continuación, haga clic en **abrir**.

6.  Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Cuando importe un archivo de configuración de voz, debe ejecutar el comando <STRONG>confirmar todo</STRONG> para publicar el cambio de configuración. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Exportar un archivo de configuración de enrutamiento de voz en Lync Server 2013](lync-server-2013-export-a-voice-route-configuration-file.md)  
[Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

