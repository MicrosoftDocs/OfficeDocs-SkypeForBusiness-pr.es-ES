---
title: Crear o modificar una colección de opciones de configuración de Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23248517bc0bba55c600e732c0a7edb96f468713
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Crear o modificar una colección de opciones de configuración de Lync Phone Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Al instalar Lync Server, obtiene una colección global de opciones de configuración de Lync Phone Edition. Esta configuración se aplica a todos los dispositivos que ejecutan Lync Phone Edition en su implementación. Puede cambiar esta configuración en cualquier momento. También puede configurar una nueva colección de opciones de configuración que se aplican a los dispositivos de un sitio específico. La configuración del sitio tiene prioridad sobre la configuración global.

Las opciones de configuración están constituidas por: el nombre y el ámbito (de sitio o global) de la colección, la opción de seguridad SIP, el nivel de registro, el nivel de calidad del servicio (QoS) de voz, la opción del bloqueo del teléfono y, por último, los detalles del bloqueo del teléfono, que definen la longitud del número de identificación personal (PIN) de desbloqueo y el tiempo que el teléfono permanece inactivo hasta que se bloquea.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Para crear una colección de opciones de configuración de Lync Phone Edition o para editar la configuración de una colección existente

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, después, en el botón de navegación **Configuración de dispositivo**.

4.  En la página **Configuración de dispositivo**, realice alguna de las operaciones siguientes:
    
      - Para crear una nueva colección de opciones de configuración de Lync Phone Edition, haga clic en **nuevo**, seleccione un sitio, haga clic en **Aceptar**, revise la configuración predeterminada y, si quiere, realice los cambios que desee.
    
      - Para editar alguna configuración de una colección existente, haga clic en la colección, haga clic en el menú **Editar**, en **Mostrar detalles** y realice los cambios que desee.
        
        <div>
        

        > [!TIP]
        > Para volver a usar las opciones en configuración predeterminadas en la colección global, haga clic en ella, haga clic en el menú <STRONG>Editar</STRONG>, en <STRONG>Eliminar</STRONG> y, después, en <STRONG>Aceptar</STRONG>. Con esto no se eliminará la colección global, sino que solo se restablecerán las opciones predeterminadas.

        
        </div>

5.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Crear nuevas opciones de configuración de Lync Phone Edition con los cmdlets de Windows PowerShell

Puede crear opciones de configuración de Lync Phone Edition (solo en el ámbito del sitio) mediante Windows PowerShell y el cmdlet **New-CsUCPhoneConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>Para crear nuevas opciones de configuración de Lync Phone Edition que usen los valores predeterminados

  - Este comando crea un conjunto de opciones de configuración de teléfonos para UC para el sitio Redmond:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Como no se especificó ningún parámetro (aparte del parámetro obligatorio Identity) en el comando anterior, la colección nueva de opciones de configuración usará los valores predeterminados para todas sus propiedades.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>Para cambiar un valor de propiedad único al crear nuevas opciones de configuración de Lync Phone Edition

  - Para crear opciones de configuración que usen valores de propiedad distintos, simplemente tiene que incluir el valor del parámetro y el parámetro adecuados. Por ejemplo, para crear una colección de opciones de configuración de teléfonos para UC que utilicen el bloqueo del teléfono de forma predeterminada, use un comando como este:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>Para cambiar varios valores de propiedad al crear nuevas opciones de configuración de Lync Phone Edition

  - Se pueden modificar varios valores de propiedad incluyendo varios parámetros. Este comando, por ejemplo, sirve para aplicar el bloqueo del teléfono y para establecer una longitud mínima de 8 dígitos del PIN:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

Para obtener más información, consulte [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar una colección existente de opciones de configuración de Lync Phone Edition en Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Configurar las opciones de seguridad de Lync Phone Edition en Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Aplicar el bloqueo de teléfono en Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

