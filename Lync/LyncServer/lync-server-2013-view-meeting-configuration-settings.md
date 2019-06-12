---
title: 'Lync Server 2013: ver la configuración de la reunión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b3107045d62b244c7ee89dbb47228bc5dd72583
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a>Ver la configuración de la configuración de la reunión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

En el panel de control de Lync Server 2013, use la opción Configuración de la reunión para controlar cómo se implementan las reuniones en la implementación. Esto incluye las siguientes configuraciones de reunión:

  - Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Configuraciones opcionales de nivel de sitio y de usuario que puede crear y usar para especificar cómo se implementan las reuniones para usuarios o sitios específicos.

<div>

## <a name="to-view-meeting-configuration-settings"></a>Para ver la configuración de la reunión

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **configuración de reunión**.

4.  En la página **Configuración de reunión**, haga clic en la configuración de reunión que desee ver.

5.  En **Editar filtro de archivo**, seleccione **Mostrar detalles...** casilla de verificación.
    
    **Editar la configuración de \<la\> reunión:** se abre la Directiva que muestra la configuración de la Directiva seleccionada. Para obtener más información sobre cómo configurar las opciones, vea [crear o modificar una colección de opciones de configuración de reuniones en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualización de la información de configuración de reuniones con cmdlets de Windows PowerShell

La configuración de la reunión se puede ver con Windows PowerShell y el cmdlet Get-CsMeetingConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-view-meeting-configuration-information"></a>Para ver la información de configuración de reunión

  - Para ver información sobre todas las opciones de configuración de la reunión, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsMeetingConfiguration
    
    Devolverá información similar a la siguiente:
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

