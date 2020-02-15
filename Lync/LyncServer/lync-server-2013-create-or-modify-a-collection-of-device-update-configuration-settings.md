---
title: Crear o modificar una colección de opciones de configuración de actualización de dispositivos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3f58e67a0d1fc8f6b01fecfbab7c7ff7dd8f31d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Crear o modificar una colección de opciones de configuración de actualización de dispositivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Se pueden crear opciones de configuración de actualización de dispositivos (solo en el ámbito del sitio) mediante Windows PowerShell y el cmdlet **New-CsDeviceUpdateConfiguration** y modificados mediante el cmdlet **set-CsDeviceUpdateConfiguration** . Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


> [!NOTE]
> Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>Para crear valores de configuración de actualización de dispositivos que usen los valores predeterminados

  - Este comando crea un nuevo conjunto de opciones de configuración de actualización de dispositivos para el sitio de Redmond:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    Como no se especificó ningún parámetro que no sea el parámetro de identidad obligatorio en el comando anterior, la nueva colección de opciones de configuración usará los valores predeterminados para todas sus propiedades.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>Para cambiar un valor de propiedad único al crear opciones de configuración de actualización de dispositivo

  - Para crear configuraciones que usen valores de propiedad diferentes, solo tiene que incluir el parámetro y el valor de parámetro adecuado. Por ejemplo, para crear una colección de opciones de configuración de actualización de dispositivos que, de forma predeterminada, elimina los archivos de registro antiguos cada 21 días, use un comando como el siguiente:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>Para cambiar varios valores de propiedad al crear opciones de configuración de actualización de dispositivos

  - Puede cambiar varios valores de propiedad incluyendo varios parámetros. Por ejemplo, este comando establece el intervalo de limpieza del registro en 21 días y el intervalo de vaciado del registro en 30 minutos:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

Para obtener información detallada sobre cómo modificar las opciones de configuración existentes de los dispositivos, consulte el tema de ayuda del cmdlet [set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) . Para obtener más información sobre cómo crear colecciones de opciones de configuración, consulte el tema de ayuda del cmdlet [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

