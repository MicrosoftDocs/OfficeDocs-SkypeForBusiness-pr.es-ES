---
title: 'Lync Server 2013: eliminar la calidad de la configuración de la experiencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bef2a59243d065f74c09dd4bc5c3aeb6a4451bbd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Eliminar la configuración de la calidad de la experiencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Las métricas de calidad de la experiencia (QoE) realizan un seguimiento de la calidad de las llamadas de audio y vídeo que se han efectuado en la organización, incluido la cantidad de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otras estadísticas, como los registros de detalles de llamadas, lo que permite activar y desactivar las métricas QoE de manera independiente de otros datos registrados.

Al instalar Microsoft Lync Server 2013, se crea una única colección global de parámetros de configuración de QoE. Los administradores tienen la opción de crear conjuntos personalizados de configuraciones que se podrán aplicar a sitios individuales. De forma predeterminada, las opciones configuradas en el ámbito de sitio tienen prioridad sobre las opciones de ámbito global. Si se elimina la configuración de sitio, la QoE se gestionará en ese sitio por medio de la configuración global.

Tenga en cuenta que también puede "eliminar" la configuración global. Pero, las configuraciones globales no se quitan realmente, sino que todas las propiedades de ese conjunto se restablecen a los valores predeterminados. Por ejemplo, de manera predeterminada, la depuración está habilitada en un conjunto de configuraciones de QoE. Supongamos que modifica el conjunto global y que deshabilita la depuración. Si después elimina la configuración global, todas las propiedades se restablecerán a los valores predeterminados y, en este caso, eso significa habilitar de nuevo la depuración.

Puede quitar la configuración de la calidad de la aplicación mediante el panel de control de Lync Server o mediante el cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) .

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Para eliminar la configuración de la calidad de la aplicación mediante el panel de control de Lync Server

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.

4.  En la página **Datos de calidad de la experiencia**, haga clic en la directiva que desee, haga clic en **Editar** y, luego, en **Eliminar**.

5.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar las opciones de configuración de QoE mediante cmdlets de Windows PowerShell

Puede eliminar la configuración de la configuración de la calidad de usuario mediante Windows PowerShell y el cmdlet **Remove-CsQoEConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Para quitar un conjunto concreto de configuraciones de QoE

  - Este comando quita la configuración de QoE aplicada al sitio Redmond:
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Para quitar todas las opciones de configuración de QoE aplicadas al ámbito de sitio

  - Este comando quita todas las opciones de configuración de QoE aplicadas al ámbito de sitio:
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para quitar todas las opciones de configuración de QoE en las que se ha deshabilitado la supervisión de QoE

  - Este comando quita todas las opciones de configuración de QoE donde se ha deshabilitado la supervisión de QoE:
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

Para obtener más información, consulte [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

