---
title: 'Lync Server 2013: ver la información de configuración de Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64d6bca76586f6a4b9636a92f2026658b77a9382
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>Ver información de opciones de configuración de Lync Phone Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede ver la información de configuración de los dispositivos que ejecutan Lync Phone Edition. La información se organiza en colecciones. Al instalar Lync Server, obtiene una colección de opciones de configuración de Lync Phone Edition que se aplican a todos los dispositivos que ejecutan Lync Phone Edition en su implementación. También puede crear nuevas colecciones de opciones de configuración para un sitio específico. La configuración del sitio tiene prioridad sobre la configuración global. Cada colección de opciones de configuración consta de un nombre, el ámbito (global o sitio), la configuración de seguridad SIP, el nivel de registro, el nivel de calidad de servicio (QoS), la configuración de bloqueo de teléfono y los detalles de bloqueo de teléfono, es decir, la longitud mínima del bloque de identificación personal número (PIN) y tiempo antes de que el teléfono se bloquee a sí mismo.

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>Para ver la información de configuración de los dispositivos que ejecutan Lync Phone Edition

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, después, en el botón de navegación **Configuración de dispositivo**.

4.  En la página **configuración de dispositivo** , haga clic en la colección de configuraciones de la que desea ver información. El nombre, el ámbito, la configuración de seguridad SIP, el nivel de calidad de voz y la configuración de bloqueo de teléfono se enumeran en la Página principal. Para ver los detalles de nivel de registro y bloqueo telefónico, haga clic en el menú **Editar** y, a continuación, haga clic en **Mostrar detalles**.

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>Ver la información de configuración de Lync Phone Edition mediante cmdlets de Windows PowerShell

Puede ver las opciones de configuración de Lync Phone Edition mediante el shell de administración de Lync Server y el cmdlet **Get-CsUCPhoneConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>Para ver la información de configuración de Lync Phone Edition

  - Para ver información sobre todas las opciones de configuración de Lync Phone Edition, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsUCPhoneConfiguration
    
    El comando devuelve información similar a la siguiente:
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

Para obtener más información, consulte [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar una colección de opciones de configuración de Lync Phone Edition en Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Eliminar una colección existente de opciones de configuración de Lync Phone Edition en Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Configurar las opciones de seguridad de Lync Phone Edition en Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Aplicar el bloqueo de teléfono en Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

