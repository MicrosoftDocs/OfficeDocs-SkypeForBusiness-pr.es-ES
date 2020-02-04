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
ms.openlocfilehash: 6b3eaf347693d079ef713716c5ebd0d8c470feef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Crear o modificar una colección de opciones de configuración de Lync Phone Edition en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Al instalar Lync Server, obtiene una colección global de la configuración de Lync Phone Edition. Esta configuración se aplica a todos los dispositivos que ejecutan Lync Phone Edition en su implementación. Puedes cambiar esta configuración en cualquier momento. También puede configurar una nueva colección de opciones de configuración que se apliquen a los dispositivos de un sitio específico. La configuración del sitio tiene prioridad sobre la configuración global.

Las opciones de configuración consisten en el nombre de la colección, el ámbito (global o sitio), la configuración de seguridad SIP, el nivel de registro, la calidad de servicio (QoS) de voz, la configuración de bloqueo de teléfono y el bloqueo de teléfono, es decir, cuánto tiempo se desbloquea el número de identificación personal ( PIN) debe ser y b el teléfono permanecerá inactivo antes de bloquearse.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Para crear una colección de opciones de configuración de Lync Phone Edition o editar la configuración de una colección existente

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación **configuración de dispositivo** .

4.  En la página **configuración de dispositivo** , siga uno de estos procedimientos:
    
      - Para crear una nueva colección de opciones de configuración de Lync Phone Edition, haga clic en **nuevo**, seleccione un sitio, haga clic en **Aceptar**, revise la configuración predeterminada y, si lo desea, realice los cambios.
    
      - Para modificar la configuración de una colección existente, haga clic en la colección, haga clic en el menú **Editar** , haga clic en **Mostrar detalles**y, a continuación, realice los cambios.
        
        <div>
        

        > [!TIP]
        > Para volver a usar la configuración predeterminada de la colección global, haga clic en la colección global, haga clic en el menú <STRONG>Editar</STRONG> , haga clic en <STRONG>eliminar</STRONG>y, a continuación, haga clic en <STRONG>Aceptar</STRONG>. Esto no eliminará la colección global; simplemente restablece la configuración a los valores predeterminados.

        
        </div>

5.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Crear nuevas opciones de configuración de Lync Phone Edition con cmdlets de Windows PowerShell

Puede crear opciones de configuración de Lync Phone Edition (solo en el ámbito del sitio) mediante Windows PowerShell y el cmdlet **New-CsUCPhoneConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>Para crear una nueva configuración de Lync Phone Edition que use los valores predeterminados

  - Este comando crea un nuevo conjunto de parámetros de configuración del teléfono UC para el sitio de Redmond:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>Para cambiar un único valor de propiedad al crear nuevas opciones de configuración de Lync Phone Edition

  - Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados. Por ejemplo, para crear una colección de opciones de configuración de teléfono UC que, de forma predeterminada, requieren bloqueo de teléfono, use un comando como este:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>Para cambiar varios valores de propiedad al crear nuevas opciones de configuración de Lync Phone Edition

  - Puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando aplica bloqueo de teléfono y establece también la longitud mínima del PIN en 8 dígitos:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

Para obtener más información, vea [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar una colección existente de opciones de configuración de Lync Phone Edition en Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Establecer la configuración de seguridad de Lync Phone Edition en Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Exigir el bloqueo de teléfono en Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

